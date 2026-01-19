# My Journey Towards Coding Agents

This blog post is about my journey towards coding agents. We have a very exciting release that represents state-of-the-art coding agents with the ability to rapidly specialize to any private data. This is the holy grail of coding agents. Many companies want to specialize coding agents to their own repositories, to their private codebases. That has been a very difficult problem, and we built a method that solves it.

But this blog post is not only about that result, but also the journey towards it. It contains all the information that is often hidden, all the paths taken and the ones that actually failed. Taken together, this gives you a more holistic perspective on what it was like to work on this project, make progress, and share the in-depth knowledge that goes beyond the papers—the knowledge that is between the lines and between the words in the paper.

## Switching Fields is Scary

I started in a very good position. I became an expert in quantization. Through my expertise, I could build methods like QLoRA and k-bit inference scaling laws. These have been hugely successful, particularly when I integrated them in the bitsandbytes library. Bitsandbytes reached millions of downloads per month, and QLoRA became a staple in the industry.

Research means extending knowledge. For me, it was clear that chatbot models will not yield the productivity improvements that we need. I started in August 2024 working on coding agents, and it was scary.

That is probably one of the hardest things if you switch a field. People were very excited that I was joining the Allen Institute for AI. I brought a lot of expertise with me. But then, after I joined, I more or less said I will not do anything that is related to my expertise. I will learn something new. That was pretty disappointing to many who were excited that I might be able to help them with their problems.

Since I am a proponent of open source, I naturally worked with open-weight models. When I looked at the SWEbench performance of the open-weight model that I could easily use, an 8 billion parameter model, I saw that it was basically 0%. SWEbench is a benchmark where you get a GitHub issue in a codebase, then you need to solve the bug that is presented in the GitHub issue. If you looked at closed source models at the time, they performed much better—around 30%, while the 8B model had 0%.

So my first challenge that I set myself was: can I improve the performance of this 8 billion model as much as possible and make open source competitive?

## Learning from Trajectories

Being resource limited forces you to run fewer experiments. Each experiment is more important. That means you look very carefully at each trajectory that you run. My first step was to download all the trajectories from some frontier models and look at them. I looked at two things: the workflow that models use to solve bugs, and the problems they encounter.

When analyzing the workflow, it was very quickly clear that each closed source coding model learns the same workflow. This workflow closely mirrors what humans do. They read the GitHub issue, try to understand where in the codebase the related functions and classes are. Once they find that, they go a little bit deeper. They see how these functions are related to other things and try to get an understanding of the problem. Then they home in on the problem, and once found, they work on a bug fix.

The next steps can be interchanged: either you write first a bug fix and then a replication script, or first a replication script and then a bug fix. Technically it is better to first write a replication script to see if the bug is really a bug, and then create the bug fix. But the closed source models would sometimes interchange these steps. Then comes an iteration stage where the editing is iterated until the replication no longer throws an error, and then you create a patch and submit it.

## The Copy Problem

I looked at the trajectories to see what was going wrong with small open-weight models and found the core problem. Small open-weight models are very bad at copying information. Copying information is extremely important for tool calling. If you want to explore a codebase, for example, you need to reference function names exactly. These small imprecisions in tool calls was exactly what stopped small open-weight models from getting any solutions—a solve rate of 0%.

One could easily solve this problem by doing a fuzzy search against existing functions, so their tool calls relating to a function are corrected. This immediately led to a 7% solve rate—a big improvement. From there it was easier to run trajectories and see what else was failing. I saw that the model would produce a closing tag that was required for the tool, and with that, no tool call was performed, which confused the model and led to errors. The simple fix was to make sure that tags are always closed for tool calls. This and similar fixes pushed the performance quickly to 14%.

The big lesson was that open-weight models were not good at copying information where closed source models were really good at it. Equipped with this knowledge, I then proceeded to make a couple of further changes that made these smaller models more robust when referring to symbolic information. That improved performance significantly.

I could push the 8 billion model performance up to 24%, which was very close to the performance of GPT-4o that sits at 25%. All of this was enabled by estimating the variance in overall results, which helped me to reliably measure if certain things improve results or not. This is something I learned from writing the QLoRA paper—running thousands of experiments that are small helped to verify the variables that were important at the larger scale.

This was a very exciting result. It made me feel that I was getting a foothold in coding agents. This was in November 2024, and after these results, people at AI2 were excited. Many people were interested in applying the methods I developed to their agent workflows. Nobody at AI2 was working on coding agents, but people worked on scientific agents. At this point I stopped working on coding agents and tried to build a general agent framework that works for scientific agents and works more broadly beyond that.

## Health Problems and a New Beginning

But at that time, misfortune struck. I developed some health problems that forced me to take a break. While that was a difficult decision, I basically stopped working from February 2025. I still committed to hiring an intern, Ethan Shen, who was very highly recommended and had an impressive background. While it did not work out for me, I wanted to not leave Ethan hanging when he arrived and wanted to mentor him.

Ethan started one day before Claude Code was released. He did not work on coding agents before, but together with my expertise, he made very rapid progress. Instead of improving the scaffolds for open source models, this was also a time when Qwen 3 was released. Together with the reasoning capabilities, the open source models now gained the precision to make tool calls that are mostly correct.

It was very clear that working with real training data with real issues is not scalable for two reasons. Ethan was working alone while I was just mentoring him and not working myself on this problem. Data work is very difficult to do with a single person who has not yet worked on coding agents. So the only scalable solution was to generate synthetic data to then train on it.

## Generating Synthetic Data

At that time, most people wanted to generate correct training data. For example, you look at GitHub issues with bugs that describe bugs in a codebase. That means you have the final solution (the patch), you have the faulty state (the bug), and the repository of the bug. Then you generate synthetic training data from a rollout from a larger model that you can then use to fine-tune a smaller model.

But if you want to work with synthetic data efficiently, you need to take a different approach. There is one simple approach where the core problem is how to generate labels. One approach that is very simple is to start with the label, then mutate your data to generate the example. You start with the correct codebase, then you generate a bug, and then you take the bug as the initial example and the correct codebase as the final state, the target state, the label. This makes it easy to generate synthetic data at scale.

Beyond this, we worked on multiple approaches that I will discuss in the next section.

## Improving Coding Agents with Data

### Subtask Splitting

Code search—searching for a bug—is one of the most important problems. If you cannot find the bug, you cannot solve it. If you found the bug, you have a good chance at solving it. That means if you have a trajectory, the most important thing to learn is searching the codebase for a bug. Why not first learn that, and then learn editing afterwards?

This has an advantage: if you divide a problem into subtasks, methods for subtasks might be shared across different problems. For example, searching a codebase might be useful in many different ways of working on coding problems or any kind of digital problem. Searching for information is a very general important task. Similarly, editing is another problem that is used across many other problems, for example adding a feature, fixing a bug, and so forth. By splitting into subtasks, we hoped to gain efficiency.

Because we are resource limited, first doing well on search trajectories gave us the hope that we would then be more efficient on learning editing, because we can already find bugs with higher precision.

If you want to do this, there is one problem: you do not have any labels for subtasks. But here we can use a mutation method. We go from a correct state, then mutate the correct state into a problem state, and then we use the initial state as a label and the mutated state as an input example. With this definition, there are countless tasks that you can generate to help the model learn searching information in the codebase.

### Finding Good Proxy Tasks

So how do you find which task is a good task to generate data from and to learn? There is a simple method that is very effective. What you do is take multiple models, then generate a subtask (a proxy task) through a mutation, then evaluate different models on the subtask and on your target task (SWEbench). Then you compute the correlation.

If a task is relevant, you will get a correlation close to one. That means the better you are on the subtask, the better you do on SWEbench. If your proxy task is bad, the correlation will be low.

For example, take a function in a codebase, then have a language model summarize a function as text, and you create a task where the model gets the summary of a function and a codebase, and then it needs to search the codebase and stop once it thinks it has found the function that is described in the summary. This task has almost a one-to-one correlation with SWEbench, which shows that search is very important for SWEbench and that you can quite easily create a task that mirrors this behavior.

If you fine-tune on just 500 samples generated from this task, small open source models, even 8 billion models, become almost as good as frontier models at searching information in codebases. This heavily boosts performance for open-weight models, particularly for small models. You very easily reach state-of-the-art results already with this method.

### Learning to Edit

But we wanted to push it further. In this split task design, you have search and editing. The second step was editing the function once you found it. We could find the function, but now we need to generate data that helps to learn this task.

Our method was simple. We take a correct codebase, insert a bug, and then our task will be: we describe the bug in a GitHub issue, just like in SWEbench, and give the altered codebase with the bug and also provide a search trace from the first subtask. Together, the model could then use the search context, which basically already points to the correct function, and then learn to edit the function to fix the bug.

Around this time SWE-Smith was released, a paper by a good friend of the lab, and it used the same method as we did. The only difference was that they used unit tests to verify that the generated bugs actually break things. We did not do that because we did not have the resources. We were thinking about doing this, but it was much easier to just generate from a model and not care so much about the infrastructure needed to verify tests and see if a bug was a real bug or not.

Despite our incorrect or unverified bugs, we got pretty good results. But what we also saw was that while we only need 500 examples to get close to frontier model performance for search, editing was quite different. Editing requires precise updates related to the bug. Because of this needed precision, we actually need quite a few samples to do well. So we needed to generate a lot of different bugs with a lot of different samples.

This procedure was still relatively efficient because once the search trace was generated, we could just append it and then generate the bug. But from this point, we realized that while creating search models is very efficient, the second step (editing model) is basically just as computationally expensive as combining both steps into an end-to-end approach.

### End-to-End Approach

If you just want to do well on SWEbench, the end-to-end approach where we just create a bug is much more efficient. That reduced our method to something similar to SWE-Smith: verified generation.

Because it was so expensive to generate a lot of data, we quickly settled that we can get pretty good data by not verifying it and not running tests. That reduced the cost significantly, since running tests can consume quite a bit of time and CPU cycles.

The other thing we wanted to do was find a cheap model to generate data from. There were very powerful models at that time—Qwen 4.5, and then soon Qwen 4.6—which give very strong results on SWEbench and are open-weight. But the full Qwen 4.5 model is just too big. You cannot deploy it efficiently if you have just 32 GPUs, and experimentation becomes infeasible.

When we used the Qwen 4.5 Air model, we quickly realized that this is kind of the sweet spot. After testing several models, we saw that it gives strong SWEbench performance at relatively low cost if you deploy it on a couple of GPUs. So with this we had low complexity in terms of verification and efficient generation by using the right model. This made things pretty cost-effective.

Once you are cost-effective, you have a double win. First, you can use your resources more efficiently. Second, you make faster progress on your problem.

### Soft Verification

With this approach, we rapidly made progress because our method is cheap. The only thing that we do is look at the final patch generated and compare it with the patch that we mutated it from when we created the bug. Then we just look for partial line-by-line overlap.

With this, we have soft verification. For example, if the model generates a patch that overlaps with 50% of the real patch that we created through the mutation of the correct codebase into the bug, then we would accept it as a training example once it reaches a certain threshold (say 50% of the lines are overlapping). The soft verification helped us with very fast data generation that is very cheap.

But that did not stop us from further improving efficiency. One idea was to get closer and closer to real GitHub issues. What we opted for was: we generate a bug, we solve the bug, then we create a new GitHub issue, and then we solve the bug again. This is much more efficient because generating the bug can be quite complex. Instead of using compute on both the bug generation and the rollout to solve the bug, we have two rollouts and one bug generation, because creation of the GitHub issue is trivial once you have the trajectory and the initial bug. This means about 50% savings.

### Embracing Vagueness

But once we did this, we realized a couple of things. First, the model often generates bugs that are vague enough that different solutions might be acceptable. For example, a bug might be created because of function reuse, and the model might guess and say it thinks this bug is related to some problems. The solution ends up looking more like refactoring than a bug fix. So we have refactoring traces even if we ask for a bug fix.

Once we realized that this is widespread, we embraced this vagueness. That led to a very unintuitive procedure.

Generating real bugs is complex and expensive. Complex in terms of analyzing the codebase to generate a bug that makes sense. For example, look at a function and its sub-functions and say that creates a bug in a sub-function, and then create an instruction that says there is a bug downstream of a particular function. You cannot reveal to the model the direct location of a bug, but a bug should somewhat be related to a search query. You need to give the model an initial point of entry to the codebase without giving away where the bug is. This is complex and expensive because it requires analysis and then very targeted bug generation with careful prompting, which increases cost.

So instead, by embracing vagueness, we use this following procedure that is very unintuitive. We take a correct codebase, then select a random function, and then tell the model there is a bug downstream from that function.

Because of this vagueness, the model goes down this function and then just looks at the code and thinks up a bug that actually does not exist. It might find that a certain edge case was missing that should not be passed. Or that an assertion was missing that captured a case which should not be passed into a function. So while the instruction is to fix a bug, the model created all kinds of things that actually make good sense.

To make generation cheap, we kept the rest of the pipeline. That means we create a bug from a correct codebase in a simple prompt that starts with a random function. Then from the trace that we generated, we create a GitHub issue. What we then do is another rollout where the beginning is not a random function, but the GitHub issue itself.

That helps us to generate lots of training data from just a random function in a codebase. We still look at soft verification where we compare the overlap of the first solution with the solution of the GitHub issue. Two trajectories are needed, and we create them in succession, which makes everything compute-efficient and very simple. All you need is a codebase with functions and a model that can generate trajectories through two calls.

## SERA: Soft Verified Efficient Repository Agents

This means we have a higher data limit. Usually data generation pipelines are limited by how many bugs you can create that make sense. If you verify bugs for correct bugs that actually make tests fail, this further limits the amount of data you can generate. And remember, you need to generate a bug but also a starting point that does not give away where the exact bug is.

In our case, we do not have these limitations. If a codebase has a thousand functions, we can generate a thousand trajectories. To further amplify how much data we can generate, we looked at papers that provide analyses of bugs commonly found in engineering. From that we get a distribution of bug types—overall 51 bug types.

So for each function, we can generate 51 different bugs. That means if a codebase has 1,000 functions, we can generate 51,000 trajectories very easily, very cheaply. This means we are almost not data-limited.

Furthermore, compared to SWE-Smith, we are about five times cheaper. The trajectory that we generate costs about two cents and just needs 36 GPU seconds to be generated. Our data quality is also slightly higher, mostly because we use a better model than SWE-Smith. Furthermore, our method is six times more efficient in terms of cost per token.

A large cost of SWEbench data generation is the bug generation and the validation of that bug. Since we do not verify and we actually do not generate a bug (we just assume that there is a bug in a correct codebase that needs to be fixed), we skip this cost. Overall, compared to other methods like SWE-Smith, we are 60 times cheaper per trajectory. Compared to reinforcement learning like SkyRL, we are 90 times more efficient and cheaper.

With all of this, it means we can generate massive amounts of data for any codebase. That helps us to explore where the limits of scaling are. All of this leads to SERA: Soft Verified Efficient Repository Agents.

## Private Codebase Specialization

Now combining all of this, we try to tackle the holy grail of coding agents. This holy grail is private codebase specialization.

The closed source models do well on popular programming languages and common patterns. But what many people noticed is that once you work on programming languages that have less representation, the models do not do as well. The holy grail is to take a model and actually specialize it on private data. This is exactly what we are doing, and it works really well.

With our method, we generate massive amounts of data for a particular repository. It is easy to generate 7,000 trajectories, which just takes one GPU hour if you run on eight GPUs. Then we train on those trajectories.

What we get is a 32 billion model that is as good as the teacher model—in this case, as good as Qwen 4.5 Air, the model that we generate the data from. It seems that this also works for other teacher models, which means you can compress frontier-level performance specialized to private data into a tiny model that you can easily deploy.

What we actually find is that with enough data, we exceed teacher model performance. This makes sense because we generate data from private repositories that the model has not seen, that the teacher has not seen. The student actually can exceed the teacher on this due to the specialized data.

It goes without saying that this is a massive result. It helps companies to quickly specialize a small model to frontier-level performance, or even exceed it, on their private data.

## Broader Impacts

We believe that with our methods, we step into a new era of coding agents.

First, private specialization: coding agent specialization on private data allows companies to take advantage of coding agents without exposing their proprietary code.

Second, because our method is so cheap, this opens up coding research for all kinds of researchers. You do not need large teams to maintain and create reinforcement learning setups that are highly complicated. You do not need thousands and thousands of dollars to just replicate a baseline, and more thousands to actually do research. Our baseline just costs $200 to create. This means any lab that has a couple of GPUs will be able to do coding agent research.

I would not be surprised if academic labs reproduce frontier-level coding performance within the end of 2026. We are already seeing that open-weight models approach frontier-level coding. Qwen 4.7 is very powerful. I believe if we take open-weight base models, we will quickly have procedures with which we can replicate frontier coding model performance.

But now, with our method and future methods, you will be able to specialize it to your private data. There is a real promise that open source models will exceed frontier-level performance because you do not need to expose your private data. You can keep it and just create your own model and deploy it.
