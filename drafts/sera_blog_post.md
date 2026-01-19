# My Journey Towards Coding Agents: Building SERA

If you look at how people produce coding agents today, they have an industrial kitchen: large-scale reinforcement learning systems with many components for efficiency that span hundreds of GPUs, complex repository mixing, and large teams that work on all angles to optimize the data pipeline for training. We had the equivalent of a hot plate and a frying pan: 32 GPUs and three bright-eyed research who wanted to cook state-of-the-art coding agents.

This blog post is about how we cooked that coding agent.

Along the way, I will share the struggles and technical details that usually do not make it into papers: switching fields, disappointing people, feel irrelevant. And than the failures along the way when we actually tried to cook an agent with our frying pain to the eventual breakthrough.

Once we had our first breakthrough, we could upgrade our frying pan to a full set of pots and an induction oven (96 GPUs). The end result? A method with which you can cheaply, just with a couple of GPU days, finetune a 32B model on your own private codebase to create a coding agent that rivals or exceeds the teacher model's performance on this private data. And our software allows you to easily deploy it in the Claude Code environment for a smooth experience.

## What This Post Covers

This post has four parts:

1. **The Struggle**: Switching fields, the costs of starting over, and what it felt like to be in the middle of it.

2. **Getting a Foothold**: My early work on coding agents, taking an 8 billion parameter model from 0% to 24% on SWEbench.

3. **Data Generation Methods**: Three approaches we tried—subtask splitting, end-to-end training, and finally SERA. If you want to skip to what actually worked, jump straight to the [SERA section](#sera-soft-verified-efficient-repository-agents). If you want to understand why we ended up there, read on.

4. **What This Means For You**: How to deploy these models, the Claude Code integration, and what becomes possible when coding agent research is cheap.

---

## The Struggle

### Switching Fields is Scary

I started in a good position. I had become an expert in quantization, building methods like QLoRA and k-bit inference scaling laws. These were hugely successful, particularly when I integrated them into the bitsandbytes library, which reached millions of downloads per month. QLoRA became a staple in the industry. And all findings of k-bit inference scaling laws would eventually implement in Blackwell GPUs on the hardware level.

But research means extending knowledge, not just refining what you already have done. It was clear to me that chatbot models would not yield the productivity improvements we need. So in August 2024, I made the leap, abandoned all previous work, and started working on coding agents.

It was scary.

Switching fields is probably one of the hardest things you can do in research. People were excited that I was joining the Allen Institute for AI. I brought expertise with me. But after I joined, and people realized I was going to work on coding agents and not something related to my previous expertise, people were quickly disappointed. Efficient training and inference? Nope, I am going to learn about coding agents.

That was disappointing to many who hoped I might help with their problems. That was particularly painful because I disappointed many people that I liked and respected. And the costs accumulated. I had not published anything in about a year. Students in this PhD admission cycle who might have wanted to work with me did not know about my coding agent work because nothing had been released yet. And they saw nothing interesting that I produced. I watched as people paid less attention, as I became irrelevant. That is a particular kind of loneliness in research. Knowing you are working on something, but having nothing to show for it.

### Then Things Got Harder

At the point when I was starting to make progress, misfortune struck. I developed health problems that forced me to take a break. While that was a difficult decision, I stopped working from February 2025.

I had committed to hiring an intern, Ethan Shen, who was highly recommended with an impressive background. Even though I could not work, I wanted to mentor him. Ethan started one day before Claude Code was released. He had not worked on coding agents before.

But Ethan learned quickly. Remarkably quickly. Together with my mentoring, he made rapid progress. He would reach out to other researchers about coding agents, and it turned out he often had more insights into what determines good performance than they did. He became one of the most knowledgeable people in the coding agent space. I like to think I had a role in Ethan's growth, but really, Ethan is just exceptionally good.

By the time we got our first state-of-the-art results with the subtask splitting method, I had returned from medical leave. The results vindicated the struggle—all of it.

---

## Getting a Foothold

Before the data generation work with Ethan, I had spent months trying to understand coding agents from scratch.

As a proponent of open source, I naturally worked with open-weight models. When I looked at SWEbench performance for an 8 billion parameter model, it was basically 0%. SWEbench is a benchmark where you receive a GitHub issue describing a bug in a codebase, and you need to solve it. Closed source models at the time performed around 30%. The 8B model had 0%.

My first challenge: could I improve this 8 billion model as much as possible and make open source competitive?

### Learning from Trajectories

Being resource-limited forces you to run fewer experiments, making each one more important. My first step was downloading trajectories from frontier models and studying them. I examined two things: the workflow models use to solve bugs, and the problems they encounter.

Every closed source coding model learns the same workflow, one that closely mirrors what humans do. They read the GitHub issue and try to understand where the related functions and classes are in the codebase. Once found, they go deeper, seeing how these functions relate to other components, building an understanding of the problem. Then they home in on it and work on a bug fix.

The next steps can be interchanged: write a bug fix then a replication script, or vice versa. Technically, writing a replication script first to verify the bug is better, but closed source models sometimes interchange these steps. Then comes an iteration stage where editing continues until the replication no longer throws an error. Finally, you create a patch and submit it.

### The Copy Problem

Looking at what was going wrong with small open-weight models, I found the core problem: they are very bad at copying information. This is critical for tool calling—if you want to explore a codebase, you need to reference function names exactly. These small imprecisions stopped small open-weight models from getting any solutions at all.

The fix was straightforward: do a fuzzy search against existing functions so tool calls are corrected. This immediately led to a 7% solve rate. From there, I could run more trajectories and see other failures. The model would sometimes fail to produce a closing tag required for tools, meaning no tool call was performed, which confused the model and led to errors. Ensuring tags are always closed for tool calls pushed performance to 14%.

The big lesson: open-weight models were not good at copying information, while closed source models excelled at it. Armed with this knowledge, I made further changes to make smaller models more robust when referring to symbolic information.

I pushed the 8 billion model to 24%, very close to GPT-4o at 25%. This was enabled by estimating variance in results, helping me reliably measure improvements—something I learned from writing the QLoRA paper, where running thousands of small experiments verified which variables mattered at larger scale.

This was exciting. I felt I was getting a foothold in coding agents. By November 2024, people at AI2 were interested in applying these methods to their agent workflows. Nobody at AI2 was working on coding agents specifically, but people worked on scientific agents, so I shifted to building a general agent framework. Then came the health problems, and the pause.

---

## Data Generation Methods

When I returned and Ethan had made progress, the landscape had shifted. Qwen 3 had been released with improved reasoning capabilities. Open source models now had the precision for mostly correct tool calls. The bottleneck was no longer scaffolding—it was data.

Working with real training data from real GitHub issues was not scalable. Ethan was working largely alone while I mentored him. Data work is difficult for a single person new to coding agents. The only scalable solution was generating synthetic data.

At the time, most people wanted to generate correct training data: find GitHub issues with bugs, which gives you the final solution (the patch), the faulty state (the bug), and the repository. Then generate synthetic training data from a rollout by a larger model, which you use to fine-tune a smaller model.

For efficient synthetic data, you need a different approach. The core problem is generating labels. A simple approach: start with the label, then mutate your data to generate the example. Start with a correct codebase, generate a bug, then use the bug as the input and the correct codebase as the target. This makes scaling easy.

But here is where the resource constraint bit hard. Coding agents usually need massive compute to even figure out how to be efficient. It is a bootstrapping problem: you need resources to learn how to be resourceful, but you do not have the resources yet. Eventually it becomes a virtuous cycle, a flywheel. But first you need to get it spinning.

We tried three approaches. Each one taught us something that led to the next.

### Approach 1: Subtask Splitting

Code search is one of the most important problems in coding agents. If you cannot find the bug, you cannot solve it. If you find it, you have a good chance. So the most important thing to learn from a trajectory is searching the codebase. Why not learn that first, then learn editing afterwards?

This has an advantage: subtask methods might transfer across problems. Searching a codebase is useful for many digital problems. Editing is used for adding features, fixing bugs, and more. By splitting into subtasks, we hoped to gain efficiency. Doing well on search first would make learning editing more efficient since we could already find bugs with higher precision.

The problem: you have no labels for subtasks. But you can use a mutation method. Start with a correct codebase, mutate it into a problem state, then use the original state as the label and the mutated state as input. This generates countless tasks for learning to search.

#### Finding Good Proxy Tasks

How do you find which task is good for generating data? There is a simple, effective method. Take multiple models, generate a proxy task through mutation, evaluate models on both the proxy task and SWEbench, then compute the correlation.

A relevant task gives correlation close to one: better proxy task performance means better SWEbench performance. A bad proxy task shows low correlation.

For example: take a function, have a language model summarize it, then create a task where the model gets the summary and must search the codebase to find that function. This task has almost one-to-one correlation with SWEbench, showing search is critical and you can easily create tasks that mirror this.

Fine-tuning on just 500 samples from this task makes 8 billion models almost as good as frontier models at searching codebases. This heavily boosts open-weight model performance and easily reaches state-of-the-art results. This was our first state-of-the-art result—the one that came right as I returned from medical leave.

#### The Editing Step

But we wanted to push further. With search solved, the second step was editing once you found the function.

Our method: take a correct codebase, insert a bug, describe it in a GitHub issue like SWEbench, provide the altered codebase with the bug plus a search trace from the first subtask. The model uses the search context pointing to the correct function and learns to edit it.

Around this time, SWE-Smith was released by a friend of the lab, using the same method. The difference: they used unit tests to verify generated bugs actually break things. We did not have resources for that infrastructure.

Despite unverified bugs, we got good results. However, while search needs only 500 examples for near-frontier performance, editing is different. It requires precise updates, so we needed many samples with many different bugs.

The procedure was efficient since we could append the search trace and generate the bug. But we realized the editing model was as computationally expensive as an end-to-end approach combining both steps.

### Approach 2: End-to-End Training

For SWEbench performance alone, the end-to-end approach of just creating bugs is more efficient. This reduced our method to something like SWE-Smith's verified generation.

Generating lots of data is expensive, so we settled on not verifying and not running tests—reducing cost significantly since tests consume time and CPU cycles.

We also needed a cheap model for data generation. Qwen 4.5 and 4.6 give strong SWEbench results and are open-weight, but the full Qwen 4.5 is too big for 32 GPUs. The Qwen 4.5 Air model hit the sweet spot: strong performance at low cost on a few GPUs. This gave us low verification complexity and efficient generation.

Cost-effectiveness provides a double win: more efficient resource use and faster progress.

#### Soft Verification

Our method is cheap because we only compare the generated patch with the patch from mutation, looking for partial line-by-line overlap. If the model generates a patch overlapping 50% with the target patch, we accept it as training data.

This soft verification enables very fast, cheap data generation.

We improved efficiency further by getting closer to real GitHub issues. We generate a bug, solve it, create a GitHub issue from the trajectory, then solve it again. This is efficient because bug generation is complex—instead of compute for both bug generation and one rollout, we have two rollouts and one bug generation. The GitHub issue creation is trivial once you have the trajectory. This saves about 50%.

But doing this revealed something unexpected.

### Approach 3: SERA — Embracing Vagueness

The model often generates bugs vague enough that different solutions are acceptable. A bug from function reuse might lead to a solution looking more like refactoring than a bug fix. We have refactoring traces even when asking for bug fixes.

At first this seemed like a problem. But we embraced it, and that led to something unintuitive.

Generating real bugs is complex and expensive. You need to analyze the codebase, create a sensible bug, give the model an entry point without revealing the bug location. This requires careful prompting and increases cost.

Instead, we do something simpler. Take a correct codebase, select a random function, tell the model there is a bug downstream from that function.

The model explores from that function, looks at the code, and imagines a bug that does not actually exist. It might find a missing edge case or a missing assertion. While instructed to fix a bug, the model creates sensible improvements.

To keep generation cheap, we continue the pipeline: create a "bug" from a correct codebase starting with a random function, generate a GitHub issue from that trace, then do another rollout starting from the GitHub issue.

This generates lots of training data from just random functions in a codebase. We compare overlap between the two solutions for soft verification. Two trajectories in succession make everything compute-efficient and simple. All you need is a codebase with functions and a model that can generate trajectories through two calls.

---

## SERA: Soft Verified Efficient Repository Agents

This approach gives us a much higher data limit. Typical data generation pipelines are limited by how many sensible bugs you can create. Verifying that bugs actually make tests fail limits this further. You also need a starting point that does not reveal the bug location.

We have none of these limitations. A codebase with a thousand functions can generate a thousand trajectories. To amplify further, we examined papers analyzing common engineering bugs, getting a distribution of 51 bug types.

For each function, we can generate 51 different bugs. A codebase with 1,000 functions yields 51,000 trajectories easily and cheaply. We are almost not data-limited.

### Cost Comparison

Compared to SWE-Smith, we are about five times cheaper. Each trajectory costs about two cents and needs only 36 GPU seconds. Our data quality is slightly higher due to using a better model, and our method is six times more efficient per token.

A large cost in typical data generation is bug creation and validation. Since we do not verify and do not actually generate bugs—we assume something needs fixing in correct code—we skip this cost.

Compared to SWE-Smith, we are 60 times cheaper per trajectory. Compared to reinforcement learning approaches like SkyRL, we are 90 times more efficient.

With all of this, we can generate massive amounts of data for any codebase, helping us explore the limits of scaling. All of this leads to SERA: Soft Verified Efficient Repository Agents.

### Private Codebase Specialization

This lets us tackle the holy grail of coding agents: private codebase specialization.

Closed source models do well on popular programming languages and common patterns. But on less-represented languages or proprietary codebases, they struggle. The holy grail is specializing a model on private data without exposing that data to a provider.

We generate massive amounts of data for a particular repository. Generating 7,000 trajectories takes just one GPU hour on eight GPUs. Training on these trajectories gives us a 32 billion model as good as the teacher—Qwen 4.5 Air, the model we generated data from. This works for other teacher models too, meaning you can compress frontier-level performance specialized to private data into a small, easily deployable model.

With enough data, we exceed teacher model performance. This makes sense: we generate data from private repositories the teacher has never seen. The student can exceed the teacher through specialized data.

This is a massive result. It helps companies quickly specialize a small model to frontier-level performance—or exceed it—on their private data.

---

## What This Means For You

We trained models on AI2's private repositories and deployed them. The integration with Claude Code is seamless—you can deploy with a single line of code. We built a translator that converts SWE agent tool calls into Claude Code behavior, so everything works smoothly.

The experience is not just seamless, it is fun. You can take your own codebase, train an agent on it, deploy it, and use it in Claude Code.

A 32 billion model will not give you frontier performance right now. But it gives you a strong model specialized to your private code, and you do not need to send your data to any provider.

More importantly, by tinkering with this, you gain skills. Once more advanced methods become available, you will be ready to use them. The trajectory of this field suggests that matching or exceeding frontier-level performance on private data is within reach.

### Broader Impacts

Because our method is cheap, it opens coding agent research to everyone. You do not need large teams maintaining complicated reinforcement learning setups. You do not need thousands of dollars to replicate a baseline.

Our baseline costs $200 to create. Any lab with a few GPUs can do coding agent research.

I would not be surprised if academic labs reproduce frontier-level coding performance by the end of 2026. Open-weight models are already approaching that level. With our method and future methods, you can specialize to your private data without exposing it.

There is a real promise here: open source models exceeding frontier performance because you can keep your data private, train your own model, and deploy it yourself.

---

This is how we cooked our coding agent with a hot plate and a frying pan. The industrial kitchen is nice, but it is not required. Sometimes constraints force you to find simpler solutions—and sometimes those solutions turn out to be better.
