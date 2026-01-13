Use Agents or Be Left Behind? A Personal Guide to Automating Your Own Work

If you are reading this, you probably feel the FOMO. Maybe you have seen the Twitter threads about coding agents completing entire features in minutes. Maybe a colleague mentioned they are "10x more productive" now -- or “Influencers" saying AGI is here and you need to learn their particular thing now. Maybe you tried Claude Code and felt confused about why the magic everyone talks about is not working for you. This blog post is for those who want to cut through the hype and understand what actually works, what does not, and how to think about using agents to automate your own job further and further to be more productive.

I have been using agents — primarily Claude Code — for eight months to automate my own work. What you will read here is not speculation or theory. It is the product of hundreds of hours of experimentation, many failures, and some surprising successes. As a professor who does not write much code anymore, my perspective is different from the software engineering discourse that dominates Twitter. Most of my agent use is actually for writing — blog posts, grant proposals, meta reviews. This blog post offers that often-missing view of how to automate tasks beyond software engineering.

Just to give you a hint of how powerful agents have been for me: usually, the first year as a professor is very stressful and involves a lot of work. For me, it felt easy. I had some luck here and there, but I believe the use of agents is a significant reason why things have been manageable for me when they are hard for others.

This blog post is my attempt to share what I have learned so that it might help you grow in the long term. I will detail a number of different things I have built with agents — which succeeded and which failed. There are plenty of blog posts out there about software engineering with agents; this one tries to give a broader, more balanced view.

Before I worked in AI, I spent three years in the automation industry in Germany, developing SCADA systems. That experience taught me how to think about automation systematically — when it makes sense, when it does not, and how to build skills over time. I bring that perspective here, along with concepts like process optimization that are standard in manufacturing but rarely discussed in the context of AI agents.

One thing I want to address upfront is the Twitter hype around parallelization — running many agent sessions simultaneously. This is a real workflow pattern that works well for software engineering, where you have independent bugs, features, and reviews that do not interfere with each other. But parallelization is just one pattern, and it does not generalize to most tasks. Understanding this distinction is important for setting realistic expectations about what agents can do for your work.

What Is Hype and What Is Real

This blog post is mostly about my own experience with concrete examples of successes and failure cases. This is real. And I want to contrast this slightly with the Twitter discourse, which can create unnecessary FOMO.
Hype: Vast parallelization, large productivity increases, and autonomy

What you see on Twitter is mostly about software engineering. And while agents in software engineering are real and powerful, software engineering is very unlike most other problems.

Firstly, in software engineering, you often have many parallel problems that you work on independently: bugs, new features, quality control and refactoring, GitHub discussions, and reviews. All of these tasks are independent and can be parallelized. The larger the codebase, the more independent work can be done, and the more parallel sessions become useful.

But here is the thing: the concept of parallel sessions is an agentic workflow pattern that is useful for software engineering and some other tasks, but most tasks cannot benefit from parallelization.

Secondly, while productivity gains in software engineering are real, they do not automatically translate to all tasks. Coding is a very general capability. Theoretically, you can do anything digital – which spans a lot of tasks. But in practice, automation of many other non-software-engineering tasks is very difficult or has small payoffs. Later in this blog post, I will give you a framework for how to think about this more broadly.

Thirdly, while a fully autonomous system can be impressive, real work that is useful often creates design decisions. Iteratively designing a system with shorter bursts of autonomy with feedback loops where they shape the final solution that you want can be much more effective than just rolling out agents until a solution is achieved. It works, but it is not very helpful for most work because the quality is too low.



Real: Agents Should Be Used Everywhere

This blog post is about using coding agents for all kinds of tasks and how I learned from that experience. After 8 months of Claude Code use and trying to automate countless tasks, here is my honest assessment: more than 90% of code and text should be written by agents. You need to do so, or you will be left behind.

This statement might seem controversial and as FOMO-inducing as the software engineering story I just critiqued. But I believe it is reality, and understanding how to adjust to that reality will be a big part of everyone's jobs going forward. This blog post is an attempt to share my knowledge to help you on this path.

When I talk with people about this, a lot of people push back vehemently. Generate all your work with AI? They find it ridiculous. How can generic boilerplate generation replace the intricate style of a well-designed software system? It feels absurd for them to replace the immediately noticeable and distinct style of a writer with an AI-generated slop wall of text.
Why AI-Generated Content Is Personal, Not Generic

AI-generated content is personal content. When I explore a concept with Claude, the output is not generic. It is shaped entirely by my thinking, my style of conversation.

 I really like connections between fields, and the topics I explore are highly personal and unique traces of my thinking — and with that, my taste.

Let me give you a vivid example. I once started a conversation about jihad — the concept in Islamic theology that is often misunderstood, about the inner struggle to do the right thing when it is difficult, but it really matters. From there, I ended up connecting it to Krishna's advice to Arjuna about doing the right thing and to not worry about the outcome by surrendering the fruits of actions to him (karma yoga), to Lutheran grace that is purest when it emerges at the height of struggle, to Taoist Wu Wei where struggle disappears through letting go and letting your nature take over, to Beowulfian naked will against overwhelming odds — the struggle with Grendel as a symbol to surrender to your fate.

None of this exists in any textbook or on the internet. It is a fingerprint. A very personal fingerprint. If you were to read the details of these conversations, you would know parts of me intimately — who I am and why I am that way. You would know me to a degree that is usually only reserved for close friends and your partner.

Someone thinking that AI-generated content is impersonal and generic is deeply mistaken. The concept of soulless AI generation is an artifact of less powerful AI, or the mistake of seeing your own generations as what AI can do, rather than recognizing it as a skill issue that has to be overcome.
Useful Background: How to Think About Automation
The Basic Calculus of Automation

Before I worked in AI, I worked in the automation industry in Germany. I was developing SCADA systems — integrating data from machines and databases to enable the control of workflows via data and monitoring. The knowledge gained in these three years in the automation industry applies directly to automating your own work with agents.

The first important question is: when should you automate versus when should you not? While people always think about automation in terms of full automation, this is almost never the case in practice. You always have a degree of automation.

Here is how to think about useful automation: if you take your current degree of automation and increase it by a new technology, then you improve by a certain percentage. If a task takes 10 hours and you improve the degree of automation by 10%, then it takes 9 hours.

With this view, there is a simple calculus: how often do you do the task, and how long do you need to automate this task to improve the degree of automation by 10%? If this calculus leads to a result where the cost of automating something is higher than the gain, then the problem is not fit for automation. The task should be done manually. There are many tasks that should not be automated because it is not effective. I will give a length example about email automation, where I tried hard, but it is a problem where automation fails.

Additionally, as your workflow changes, it adds overhead. For example, you might save 30 seconds, but if your agent needs 30 seconds to generate that automation, then the effectiveness is 0%. The degree of automation improves by 0%.

If you invest so much time into improving your work with agents, you want to make sure that it actually helps. This simple calculus – while not perfect – is a simple tool to help you decide where to start with automating your work.
The Method: Process Optimization

A very basic method in factory automation is process optimization. You are on the factory floor with a stopwatch. You look at and study what workers are doing. You time each step: how they hand off work to another person, when they wait for previous work to complete, how many resources they need, and if they wait for resources.

If you have all these components, you can construct a workflow — a process that reflects the current state of how work is done. Based on this, you can think about how to optimize. This thinking is extremely important for automating your own work. You have to think about how you work on a particular problem and how you can change your work with agents. Using this framework of process optimization can be extremely helpful to get a quick sense of how much productivity gains you can achieve with a particular solution. Sometimes you find that the process cannot be optimized much with agents – that saves you a lot of time.

Let me give you a concrete example. If I take one minute to read an email and 30 seconds to reply, then it takes 1 minute 30 seconds to complete an email. Now, if I use an agent to help me with my emails, then I need to guide it to process my emails. Then I need to read that content to decide how it should create drafts or answer emails so that I can then edit those drafts. But once you do this exercise, you realize that by using agents, you just shift the process and do some automatic generations — but you still need to read content, make sure it is aligned with your intent, and you need to edit the draft if it does not match exactly with what you wanted.

There are certain emails that are easy to automate. There are others that are not. It depends on your process and your underlying inputs to see if using agents and changing your process can actually lead to productivity.

Reading an email or reading AI-generated content has a cost. You need to include that cost in your process optimization thinking to understand if your process can benefit from automation. This insight — which seems obvious but is often ignored — is fundamental to achieving higher and higher degrees of automation.

The Long-Term Perspective: Building Automation Muscles

The process perspective I just gave is a short-term view. You look at the underlying processes and the degree of automation, then think about how long you will need to automate that work and how much you increase the degree of automation. It is a simple calculus. This is classic automation, how it is done in Germany and other countries. Very cost-effective and optimal in the short term.

However, it is very short-sighted because it does not consider long-term consequences.

The long-term view is a Shenzhen-style perspective. It is not about making any automation useful in the short term. It is about making automation useful in the long run by gathering knowledge that improves automation over time.

It is essentially short-term calculus with a meta-automation step added: even if the degree of automation is not worth it in the short term, will the skills I build and the tools I develop make future automation effective that was previously ineffective? Does the additional knowledge help me with future automation effectiveness?

This is exactly what led from Shenzhen-style scrappy factories to highly structured dark factories that are fully automated. Chinese automation is far superior to Western automation, not because of scale, but because the long-term view of automation led to a higher quality and degree of automation.

This is an important concept. You need to optimize both short-term and long-term perspectives to effectively automate your own job. Europe is struggling because of its short-term view of automation. The US is struggling in many segments because it did not build the long-term skillset that is required to build the automation muscles to tackle more challenging problems.

In other words, using agents and failing at automating a task effectively is important. You need to gain skills to improve future automation, and that means sometimes trying to automate things that you know you will not be able to automate.

A key part of making sure you learn over time is important. Often, you learn more from failure than successes and with agents, it is no different.
Why Automating Your Job Is Good for You

Software engineers are not replaceable. They just level up. The current hiring challenges are driven by COVID and financial dynamics much more than by AI. Software engineers are now much more effective at building software more rapidly, and the value of software has not decreased significantly. An engineer who uses agents like a hot knife slicing through butter is actually more valuable because they can produce more software that still has significant value.

A common view, particularly from the Bay Area,  is that this is the current state, but software engineering will be fully automated very soon. I have many friends at frontier labs who had this view about nine months ago, but it has broadly changed. They see that it is difficult to automate their own work and that, as they use these tools, new problems open up.

Even if an agent can do everything, it cannot do everything at the same time. If you have a limited amount of GPUs, you want to direct agents to tasks that are useful for you so they can generate value where you need it. While even that can be partially automated, once your existence is at stake, you probably want to direct what agents do yourself — at least specify the problem and solution you want.

I think it will be a long time until you use an agent to manage your retirement savings by analyzing the stock market and optimizing it fully autonomously. But what is more reasonable is that you build a system where you tell an agent what risk you are happy to accept and how to optimize this risk through hedging, so that you might manage your retirement fund with a trade-off between potential upside and risk over time. It would be unwise to fully trust an agent if you do not know the parameters that are important for you and how the agent chooses those parameters.

If resources are limited, you want to decide how those resources are used rather than fully trusting an agent. And if this is true, then directing agents will remain a problem, even if agents can do everything, because agents cannot do everything at once, because resources are finite.

Long story short, because of this resource problem, there will always be work where your personal preferences, decisions, and taste will be needed — even if 90% of the work happens through AI. From software engineering, we already see that these changes work, but they will not eliminate many jobs that we thought would be automated away quickly.

I think the other direction is actually more pressing: if you do not know how to use agents, you will not have a good job or be able to find a job. Agent use is now an essential skill that you need to develop and master.
My Personal Experience with Automating My Own Work
Personal tools and pipelines

What is most common on Twitter are examples of successful agent use, where people create a tool that is useful for them. Small extensions that help your everyday life — just vibe coding something that you always wanted and that is simple, but nobody provided.

While this is a simplistic way of using agents, it has its importance. This is a problem where agents work really well, and they require very little skill to be used correctly.

For example, I built tools that help me write this blog post. I built tools that help me work with agents. One of the most important tools is a voice tool, which helps me quickly interact with agents, particularly for parallel sessions. A voice tool also helps me because I have carpal tunnel in both my hands. Typing can be painful. I have a very custom keyboard layout and way of working with the keyboard that reduces pain to almost zero, but still, it is much more comfortable to just use my voice. And it is not only comfortable, it is also faster.

A main advantage is that with voice, you can inspect outputs and use your keyboard and mouse while narrating. This is extremely powerful. A key tool that everybody should develop is their own voice tool to use AI in this way, where they can do work while narrating.

Tools for Students
Finding related papers: Replication of Connected Paper

Another tool I built was to solve the problem of finding related work. The most useful tool I have ever used for this was Connected Papers. It was free at some time, but then it became commercial. I need something like this at the beginning of a project and when writing the related work section of a paper. I did not want to pay for the subscription, and I wanted my students to be able to access it. So I just replicated the entire software system.

This was probably not effective for automation in the short term — I could have just paid for Connected Papers subscription. But it gave me an overview of what I can do in the long term: what tools can I build, what is too ambitious, what is less ambitious, and how can I be more effective when creating complex tools.

My connected papers replication uses the Semantic Scholar API to retrieve data. Then it builds statistics on the citation graph of papers to find papers that are very similar to what Connected Papers finds. The key insight I had is how Connected Papers works: it finds papers that are in conversation. They are often indirectly related through a third paper that cites both of them. They create a chain, a loop of three papers, and this loop is distributed. If you have this loop across three-paper chains that create circles, you have a very good way of finding related papers.

The tool that I created was very useful, but here is where it failed: the user interface. The algorithm works well, making the software easy to use for others turned out to be the hard part. My students needed to execute a Python command and use a password to extract an API key – it is a mess to get started. Instead of local deployment, I should have built a deployment that is just a regular website that you can access anywhere with just your browser.

If you want to create a tool that improves the degree of automation of a task, a useful tool is often not enough. You need to figure out how you and other people can use these tools intuitively and effectively.

You see that even creating simple tools like this connected paper replication, can have its own complexity. But such failure cases give you perspective: While not highly successful in the short term, it will give you the skills needed to tackle problems more effectively in the long-term future.

I would encourage you to spend some time on projects that do not offer a high gain in terms of degree of automation, just for the sake of having more diverse points of failure that you encounter, which will inform your future automations.
Exploiting coding agents as an API

Other tools I build are mostly for my students. It was recently revealed that quite a bit of Claude Code use is actually by exploiting it as an API for regular LLM calls. This means you use a Claude Code endpoint just as an API to use it in other work. While I do not use Anthropic for this, there are other providers where you can get frontier capabilities at the cost of 1% of the usual API costs. So you get regular API calls, but at 1% of the price.

I built this pipeline for my students a couple of months ago, and when I asked my students if they needed any GPUs for their projects, they said no — they just generate evaluations and research directions with the API that I created. It has been a very useful tool. For a research group, having easy access to frontier model capabilities without the cost that is typical for APIs is liberating for research. And I built this tool in about 2 hours. This is where good tooling really paid off.
Other Tooling for Students

Other tooling that is much more straightforward includes infrastructure for Slurm and a common infrastructure to analyze experiments. I believe Weights and Biases actually harms research by biasing the interpretation of results and how experiments are run, and so the custom tools that I have in the pipeline will help my students to avoid this bias.

A tool I have not developed yet, but which my colleagues have mentioned is a review system where students can get feedback on ideas or papers by querying an agent or an agentic pipeline that mimics how they, their academic advisor, would give feedback to the students. Imagine a student being able to get a first-pass critique of their paper at any time they like without being embarrassed about it or worrying about perceptions. This would not replace advising, but it would make our collaborations more productive by handling the basic structural and clarity feedback automatically.

While not all of these tools might be useful, and some are more like distractions, it is clear that with the right pipelines, workflow, and tools, productivity for students can be increased dramatically — and this can be driven by an advisor who invests in building these systems.

Similarly, a technical manager can develop tools and guide a team in this way. Even if agents cannot do all the work, you need to figure out what work you actually want to do and how you want to build on each other's work as a team. Agents can work independently, but it might not be useful if your team is pulling on different ends of a problem. If coordination is missing, and everyone is using agents in their own way, it can lead to disaster. The tools an advisor or manager builds can provide that coordination layer.

All of these examples highlight where tools fail, where tools can be useful, and where tools might not be useful in the short term but give you the skills to improve tools in the future.



Writing Tasks
Blog Posts

You might have guessed it already: this blog post is AI-generated. My previous post about Why AGI Will Never Happen was AI-generate too. More than 95% of the text from both blog posts comes from an AI model. I did not even type prompts. Most of it was just me rambling into a microphone while doing other things, then transcribing that voice into text, shaping it into a blog post, then doing a style transfer to shape it into my voice, and then adding some small snippets that have character.

The last 5% is a cherry on top that is very important, but these edits make less than 5%, maybe even 2% of the overall blog post.

While I am still experimenting with blog posts, this pipeline allows me to write blog posts much more quickly — and blog posts that are much more current. A blog post like this would have taken me days in the past. Now it takes about 3 hours: one hour to speak content into a microphone, 10 minutes for my agentic workflow, and then ~2 hours of reviewing and editing. It is very fast, and when using the agents, you notice that the quality is pretty good.

Would you agree that this blog post has soul? Or is it AI slop now that you know it is AI-generated?
Writing Tasks: Grant Proposals

Grant proposals are a major time sink as an academic. A CMU student costs $150,000, and I need to find that money by writing grant proposals. A lot of proposals are rejected, so you have to write lots of them.

It is interesting because while you might think the blog post approach should work, it actually does not work that well. Grant proposals need to have a particular structure, and even small deviations read poorly. Good design is familiar design, and good proposals are familiar proposals.

This is just like a good abstract — for example, an abstract in Nature has almost always the same structure, sentence by sentence, the same for every paper. That makes it easy to read abstracts because you know where to find information.

I am dyslexic, and reading is very slow for me, but I learned to read papers at a relatively okay pace because I understand that they have a common structure that repeats again, and again, and again. I can skip sections, skip to particular phrases, and I know where an interesting part begins. If the introduction says "In this paper" or "Here," then I know now the list of contributions starts.

Grant proposals are highly structured. A free-flowing, talkative approach that I use for blog posts does not work out of the box, but it can be made to work by introducing an abstraction pattern.

This abstraction pattern works as follows: you create sentence-by-sentence extractions of what the grant proposal content should be. For example, for an abstract:
- The first sentence is about the general field and the subfield
- The second sentence mentions the problem, why it is important, and why it has not been solved
- The third sentence states your contributions and your main results
- The fourth sentence explains your main method
- Then, depending on taste, you expand on this method or keep it brief
- Finally, you state the impact and broad implications

If you have an AI model, you can apply this process very easily. Just take a couple of grant proposals of your own or others that you really liked. Then use an agent to do this, sentence by sentence, then merge multiple abstracted structures by commonality.

Then I use this structure together with an agent to create an interactive flow: The agent gives me particular questions, and I respond with a voice message about that content that I want – this is often casual “rambling” about my research that I want to do. After each response, the agent stores the content and analyzes the abstract template if key information is missing. The agent asks follow-up questions, and I answer them with my voice tool.

I then have the agent generate the draft and then smooth it over by doing style transfer using particular proposals that I have written and like.

With this, I can create a four-page grant proposal in about an hour and a half — even faster than a blog post.

Meta Reviews

Machine learning conferences are notorious for bad reviewing. The reviewing system is broken. There have been studies on ICLR and NeurIPS with clear results: reviewing does not work. Reviewing can identify the really worst papers and the best papers, but in-between it is a coin flip.

The finding from these studies is that reviewing quality is not related to knowledge but related to effort. Undergrad students have much higher quality reviews than PhD students or professors because they have more time and take it more seriously. For PhD students and professors, it is a chore.

Looking at that reality, using agents becomes very straightforward, and I would argue an imperative to improve review quality by reducing the time needed for reviewing.

In this case, we look at meta reviewing, reviewing the reviews, which is the task of an area chair. There are two philosophies about being an area chair. One is that you bring your own opinions and overrule decisions. The other is to follow what the reviewers said. I believe the second is more intellectually honest. While I have expertise and sometimes will overwrite reviewers, I have not had the depth to read every paper thoroughly, and certain concerns might be valid. A good paper is not a paper that I like, but a paper that is useful for the research community, and usefulness is difficult to judge if you do not read a paper in depth.

What I built to help with meta reviewing is a system to analyze the discussions, the points where reviewers disagree, give summaries of papers, summarize which papers are borderline, and identify which are clear rejects or accepts. The clear accepts or rejects have high score variability. These reviews can be processed quickly — you can understand why people have certain views.

The workflow is as follows: An agent uses my OpenReview login details to log in, navigate to the papers, get all the reviews and rebuttals, and store them to disk. Then the interactive part with the agent starts that helps me to understand where the issues are.

What is more subtle is tracking changes in the discussion. With the rebuttal, even if the score is not increased (which is very common because people do not have time), the rebuttal might contain information that could change the outcome.

From all this discussion about borderline cases, you can easily draft the first meta review. If it looks strange, you can ask the agent to explain, provide more detail, or provide evidence. It is a very interactive way of reviewing and actually mirrors what I would do without AI agents: separate straightforward and difficult cases; analyze difficult cases for disagreement; figure out which arguments have merit and if author rebuttals change the picture; draft a review; edit by looking at details; submit.

All these things can be done by an agent, and they can be done faster and probably more precisely. Understanding a subtle argument of a paper I have not seen before, between reviewers with different perspectives — this is hard if it is 5 PM and I have already had eight meetings, and I am just tired. But if I do it with my voice tool and my meta review agent system, this allows me to write high-quality meta reviews and make decisions that consider all information and arguments of reviewers and authors carefully.

The use of agents for meta reviews might be highly controversial, but again, AI-generated content is highly personal if you do it right. This also goes for reviews. I think we do a disservice to the research community if we do not use agents for reviewing, since they can improve quality dramatically.

Where Agents Fail: A Study of Email Automation

I alluded previously that I tried to automate emails for a long time. Over two months, I worked quite a bit on automating emails — for one, because I do not like emails, and also because it is now a major part of my work.

I wanted to build a system that helps me manage, prioritize, and draft emails. Probably for most people, the process of “doing your emails” is similar: Categorize emails into urgency, map out information that is needed to make a reply, and prioritize replies with the time that you have now until your next meeting or other event.

Doing this manually is very simple and fast. I can often look at the title and immediately sort it into a category. I can skim an email for 10 seconds and know if I need to reply now or if it has time. I can organize emails in bulk to review later.

My initial attempt at email automation was very focused on features. Can I do this categorization, prioritization, bulk sorting, and get the gist of an email with agents?

But here is the issue: even if you automate all of this, you still have a similar workflow. If you categorize an email automatically, you still need to look at the categorization to see if there are new emails. If you have an AI summary of an email, you still need to read it. If you create agent-generated drafts, you need to look at the drafts and see if it has the right details, the right tone, and actually say what you wanted to say more broadly.

Furthermore, Gmail is a familiar interface. You know where everything i,s and all these things of prioritization, categorization, etcetera, can be done easily and quickly. If an AI does that, many things are automated, but you still need to use a user interface. This interface may be unfamiliar, not optimized for all workflows, or might miss crucial information or features. And navigating and using an agent-driven email system costs time, just like how it costs time do it manually.

Here, the process optimization view kicks in. If I can categorize an email within five seconds, that is pretty fast. An AI agent needs to beat that in five seconds and be more precise than I am for it to actually be useful. While the reading and categorization can happen in the background, with an AI-generated draft, I still need to navigate to that draft and read it. That might take 10 to 30 seconds just for navigation and reading, but an additional 1 minute for editing the draft. In many cases, the manual approach is about equally fast. But if you add the development time for this system (it was more than 100 hours), it becomes clearly net negative in terms of productivity to use the agentic system.

Despite all these edge cases, I did not want to give up. For one, I really do not like emails. But the second part is that, for me, it was a challenge: can I automate this task? And if I cannot, it would serve as a hard-won lesson for future automation challenges.

So I made a second attempt. I knew about the process. I knew about the importance of interfaces and how to structure information. Since I am an avid Vim user, I wanted to build a vim-optimized interface. This was a long process — co-designing functionality, agents, and the user interface. My productivity using the agentic email system improved day by day, but at some point I saw the improvement plateauing, and I asked: Is Gmail, if I use it the right way, faster?

So I compared time spent on emails between the tool I created and just using Gmail – which is very much the process optimization view of having a stopwatch on the factory floor. What I found is that just using Gmail is faster. I could not get any degree of automation improvement by using agents for emails.

That was a very important lesson. Sometimes you fail, and that failure teaches you something valuable for the next challenge.

Conclusion

If you take away one thing from this blog post, let it be this: agent use is a skill, and like any skill, it requires deliberate practice, understanding of when it applies, and acceptance that you will fail often before you succeed.

The hype is real in some domains and misleading in others. Software engineering parallelization is real but not generalizable. The personal nature of AI-generated content is real and profound. The need for process thinking before automation is real and often ignored.

I hope these perspectives have been useful to help you think about how you can use agents, where agents work well, and what hype and what is not. The key is to think carefully, experiment often, and build skills for the long term. I hope this blog post will help you to make agents your own and see more and more benefits from agent-use.




Democratizing Foundation Model Research
While foundation models such as ChatGPT are now commonly used in everyday life, their steadily increasing scale requires massive amounts of resources. The main aim of my research is to democratize foundation models by making them cheaply accessible to all researchers. I approach this problem from three angles:
Science of deep learning: Basic research that aims to uncover fundamental relationships and properties of foundation models to create innovations that require less resources.
Democratizing foundation models: Innovations that reduce the cost of further training and analyzing the behavior of existing foundation models so that they can be studied with minimal resources.
Machine learning systems: Full stack design from algorithms to hardware to enable the efficient creation, adaptation and use of foundation models on existing infrastructure.

My work in these areas has had significant impact on the research community. The basic properties I uncovered on the compressibility of foundation models now form the bedrock of efficient inference and finetuning in large language models. My open-source software that democratizes access to foundation models, called bitsandbytes, is one of the most popular machine learning libraries and growing at a rate of 1.2 million installations per month. I was awarded a Google Open Source and PyTorch Foundation Contributor Awards for my library and my open source efforts. My machine learning system, Petals, allow the efficient training, and free adaptation and use of foundation models through a globally distributed system of computers. 
Democratizing Foundation models: Enabling access for all researchers
The increasing scale of AI models has led to the creation of powerful foundation models, such as ChatGPT and GPT-4. However, the computational resources required to do research has grown in lock-step with their increasing scale. I have developed quantization methods that compress foundation models without degrading their performance. This includes  reducing the computational and memory requirement by a factor of 17x and hardware cost by a factor of 75x, thereby unlock broad new classes of open research with these important models. I created the bitsandbytes library to share my research algorithms and enable access to even the largest foundation models with a $3,000 consumer-grade hardware system. My research library is one of the most popular machine learning libraries, currently at one million new installations per month.

Efficient fine-tuning of quantized large language models. Enabling foundation model research for all researchers: Once a foundation model is trained on trillions of words of general data, it can be adapted or fine-tuned to a specific domain or task, for example a chatbot that summarizes biomedical data. While supercomputers are needed to train a foundation model from scratch, the fine-tuning step is light in computation but heavy in memory requirements. For example, the most powerful open-source model Llama 2, with 70B parameters, requires only 48 hours to be finetuned, but uses 34 consumer-grade GPUs. We develop a solution, QLoRA, which uses quantization to compress the foundation model during fine-tuning in such a way that memory requirements by a factor of 17x, to enable training on only 2 consumer GPUs or 1 data center GPU, while the generative quality of the model remains the same.

Our work on QLoRA answers two intertwined research questions: (a) How can we compress neural networks during fine-tuning? (b) How can we maintain the quality of finetuned models under compression of the neural network? For (a) we show that the main memory bottleneck can be alleviated by compressing the neural network weights to 4-bit precision and backproping through these compressed representations to tune a very small set of full precision parameters. To prevent memory spikes, we develop a GPU-to-CPU paging system that works like RAM-to-disk paging but is adapted to neural network training. To prevent (b) loss of quality, we develop a hierarchical quantization scheme for further compression, and design a new 4-bit data type, 4-bit NormalFloat, which is information-theoretically optimal for normally distributed data types. We show that with the help of these innovations we can reduce the memory requirement to make the largest neural networks fine-tunable on consumer-grade hardware, while the 4-bit NormalFloat data type ensure high quality models. To demonstrate the effectiveness of our system, we develop the 4-bit Guanaco chatbot, which reaches 99.7% of the performance level as ChatGPT on the Vicuna chatbot benchmark. You can find a demo of our Guanaco model on the HF Spaces.  This work was selected for oral presentation at NeurIPS2023 (top 24 out of 12343 papers).

While QLoRA was a significant advance in making large foundation models accessible, further progress is needed to reach critical milestones. For example, to allow customizable foundation models on mobile phones that have a quality similar to ChatGPT, a average compression-level of close to 3.5 bits per neural network parameter is needed to fit it into a mobile phone. In previous work I have shown, that any compression below 4-bit significantly degrades the model quality making such models relatively useless. In our follow-up work, SpQR, we address this challenge by building on my previous work. We identify the particular source of quality degradation and isolate into a sparse matrix of outliers parameters. While we quantize the neural network weights to 3 bits, the sparse outlier matrix is kept at 8-bit. With this approach we can maintain very high quality foundation models at an average of 3.4 bits per parameters. With our solution, SpQR, it is possible to finetune a ChatGPT-quality model on modern mobile phones at 12M words per day. To continue this research, I have applied and have been awarded a grant from Apple valued at $100,000.

Another work in the direction of enabling researcher easier access to do research with foundation models is 8-bit optimizers. During training, optimizers represent the most significant source of memory. While effective techniques exists to reduce the optimizer memory requirement if one has multiple GPUs, the only way to reduce the memory with one GPU is to compress the optimizer buffers. We quantize the optimizer buffers from 32 to 8-bit without affecting the final training model quality. We achieve this by designing a new data type and analyzing the instabilities in optimization as we scale the model. This work has been awarded a spotlight award at ICLR 2022 (Top 176 of 3391 papers). 

Science of deep learning: uncovering properties of foundation models

Basic science is the main fuel for innovation. Without understanding, it is difficult to innovate. With understanding, innovation follows naturally. Foundation models were created with the basic insight of scaling laws which can accurately predict the performance of neural networks as a function of the amount of data and computation used in neural network training. In my work, I derived new understanding and theories that make predictions about foundation models. Basic questions I studied were "Is there a fundamental limit to compressing the information in neural networks?" and "Do foundation models learn to structure their information processing as we increase their size?". The insights from these questions now form the basis of foundation model compression research.

Uncovering fundamental structures that emerge in foundation models: Compressing already trained foundation models to fewer bits per parameter makes them more easily usable, but can degrade their predictive performance to the point of them being no longer useful. Can we understand which parts of the foundation model are more and less compressible to find a trade-off between usability and model quality? In our work, LLM.int8(), we study 8-bit compression of foundation models and find that even the best 8-bit compression techniques lead to a breakdown of information processing in Large Language Models (LLMs). We find that as we scale foundation models in size and compute, they increasingly learn to process context-dependent information in a particular sub-network that is highly structured. We find that these sub-networks have emergent behavior: they occur stochastically and are unpredictable for smaller foundation models, but at a certain scale these sub-networks cease to be stochastic and become highly predictable and structured. While only making up 0.1% of large foundation models, ablating these sub-networks degrades predictive performance by 600-1000%. With the help of this discovery, we isolate these sub-networks into 16-bit precision, while 99.9% of the foundation model was compressed into 8-bit precision with no loss in accuracy. Our discovery of emergent sub-networks now is the basis for research into foundation model compression.

Are there fundamental limits to neural network compression? After our initial work, we wanted to investigate how to maximize the predictive performance of foundation models for each bit in the model — or in other words, how to maximize the information density of foundation models. For example, a 1B parameter foundation model in 8-bit and a 2B parameter model in 4-bit have equal amounts of bits, but one of these has better performance. To investigate this question, we studied the scaling laws of compression by running a total of 35,000 experiments for 2 to 16-bit precision across 31 different foundation models to study any systematic relationships. We uncover three main findings: (a) information density for all models is maximal when parameters are encoded with 4-bit precision, (b) using our previous outlier network in 16-bit in conjunction with 3-bit improves performance, but not information density, making 4-bit optimal (c) data types improve information density, for example float data types provided better density than integer data types; the best data type from our experiments is a data type that is information-theoretically optimal for neural network weights. Our work now forms the starting point for most foundation model quantization research which is centered around the question “How to improve information density beyond 4-bit compression?”

In follow-up work, we combine these insights with our outlier network results from LLM.int8() to develop Sparse-quantized Representations (SpQR) a 3-bit quantization format with sparse outlier elements that are used in 16-bit precision. With this approach, we are able to improve the maximal information density by compressing the neural network parameters to an average of 3.35 bits per parameter. However, we also observe a sharp performance drop between below 3.3 bits per parameter thus setting a new lower bound on compression in terms of information density for foundation models.

Understanding instabilities in neural network training: A major problem in neural network training is loss spikes, where the loss functions of neural networks can be highly irregular leading to erratic changes in the loss function. The problem of loss spikes increases with the scale of the neural network making it the most significant challenge when training a large foundation model. In our work, we analyze the dynamics of gradients and optimization steps during the training of very large multi-modal image-text foundation models. We study loss spikes and extract a functional relationship between gradient magnitude and the magnitude of the second moment of the gradient. With this, we were able to build a causal model that predicts loss spikes with high accuracy before they happen. With insights from this analysis we were able to stabilize training thus making it possible to train in unstable 16-bit data types and 8-bit data types which previously did not work for neural network training. 

Machine learning systems: deep learning without a supercomputer 
The design of efficient machine learning systems requires the careful study of the interplay between neural networks, hardware, and software to achieve maximum system efficiency while maintaining the generative and predictive quality of neural networks. Existing large scale model training requires a supercomputer  with a high-performance network—usually 400 GBit/s speed and nanosecond latency. While efficient, supercomputers and their specialized buildings are very expensive. In a series of papers, we design and develop machine learning systems that aim to replace supercomputer with basic consumer-grade internet infrastructure while maintaining supercomputer efficiency levels. With our work, we enable the creation of and research on frontier models without the massive investments needed for supercomputers.

SWARM parallelism: efficient globally distributed training of foundation models: A key principle for efficient machine learning systems is to (a) overlap communication with computation, so that computer exchange essential information while the next layers in the neural network are processed. Beside a low network bandwidth, doing neural network training on standard internet infrastructure has the added problem of connectivity problems which can slow or halt processing. As such, an effective system needs to be (b) fault-tolerant and (c) actively explore alternatives routing of information in the case some computers in the system slow down. In our work SWARM parallelism we solve all these problems. Firstly, we build an analytic model of combinations of parallel algorithms. With this model, we find that the combination of 1-step-stale synchronous stochastic gradient decent in conjunction with stochastic pipeline parallelism scales well to large foundation models even if the network is 1000x slower than supercomputer networking. We also develop a stochastic round-robin algorithm to discover routing pathways that balances an exploration of alternatives routing pathways with exploitation of the fastest routing pathways.. Overall, our SWARM parallelism system reaches 89% of the runtime efficiency of a supercomputer while also working with heterogenous devices and being fault tolerant. 

In follow-up work, we build on SWARM parallelism to specialize it for the use-case of inference and parameter efficient fine-tuning. We focus on transformer-based large language models, where the difficulty is to manage the key-value caches that are required for fast inference of long-sequence between servers and clients while also minimizing latency. We base our routing protocol on the SWARM algorithms with the difference that after the generation of each token, the same routing path is maintained to make use of the key-value cache. Using this system, any client, even a slow CPU based client, can achieve fast LLM generation speed of even the largest open-source models at a speed of about 5 words per second.

Future research directions
Why do different neural networks have different compressibility limits? A key observation from my research and other initial work is that if we want to preserve the quality of a neural networks, different network types have different compressibility. For example, transformer-based large language models (LLMs) can be compressed to 4 bits per parameter, while computer vision models can be compressed to 2 bits, and mixture of expert models to 1 bit per parameter. My main hypothesis for these data is that compression is related to the degree a feature is distributed among the hidden units / neurons within a layer. To approach is problem, I would build a model that determines what feature is active for which label and how distributed that feature is. With such a model one can determine which parts of the model are needed to predict a certain example accurately from which we can then understand this fundamental relationship.

Cheap Google-scale information retrieval systems for academics: One frontier that is very promising to reduce hallucinations and make foundation model reliable is to verify their generation with internet search algorithms. Past research has focused on Wikipedia as a knowledge source because of its knowledge-density. While using much larger, internet-scale datasets would enable a broader scope of evidence retrieval to verify foundation model generations, systems that are sufficiently fast are very expensive (>$1.5M). I designed a custom system that is able to do information retrieval across 10 trillion words within 20ms while only costing $25,000. While new specialized software would need to be designed and written for this system, such a system would enable academics for the first time to study the interplay between foundation models and internet-scale information retrieval systems.

Developing stable 8-bit Float training: The current generation of GPUs, Hopper H100, is not much more cost-efficient in terms of compute per dollar, but the new generation of GPUs has strong 8-bit floating (FP8) point matrix multiplication capability that holds the promise to make both training and inference of foundation models three times cheaper. However, as shown in our previous work, while FP8 training is more stable than Int8 training, it leads to instabilities and failure of training for large foundation models. As such, its critical to develop method that stabilize FP8 training to enable the capability of cheaper training. From my experience with low-bit training, the key to developing stable FP8 training is to study the training dynamics and how they differ from regular 16-bit training. I would build simple predictive models of training instabilities which then can be used to test and build simple solutions to develop stable FP8 training.


Scaling-laws for synthetic data finetuning: Instruction finetuning is the paradigm where we take a pretrain language model, such as GPT-3, and we finetuning it to follow arbitrary instructions given by the user resulting in models such as ChatGPT. Currently, the best instruction finetuning datasets are synthetic, meaning they were not generation by humans but by foundation models themselves. This means that powerful foundation models like GPT-4 have the ability to improve themselves for certain tasks. However, currently it is not understood how the type and quality of synthetic data relates to the final instruction finetuned model performance. The main approach for this research direction would be to study which factors of synthetic data finetuning are critical for strong or weak performance for certain tasks and how does the size of the instruction generator and the instruction finetuned model affect performance. Deriving such relationships would lead to predictable finetuning such that models have approximate guarantees of weaknesses and strengths that can be determined by the user.

Real-time finetuning: Current AI systems like ChatGPT are designed with the general user in mind. When a user wants to interact with a model in a very specific way the model needs to be either extremely general (which is expensive), or it needs to be specialized for the users interaction. However, its difficult to anticipate the needs of each user. An effective solution to this problem would be to create a system that is adjusted to the user in real-time, just as the user uses the system. However, currently, such systems do not exists because the resource demand of fine-tuning is much higher than simply using the model. Based on my previous work of QLoRA, it is possible to develop systems that are efficient enough, but a major challenge is to adjust a system based on just a few samples. My approach for this problem would be to generate synthetic data that mimics the current user interaction which is then used to adjust the model. Other challenges might include that, unlike training where we can make small optimization steps over millions of examples, we need to aggressively optimize the foundation model to make its behavior change significantly. For this problem, I would use my knowledge gained when working on 8-bit optimizers to develop optimization algorithms that optimize with very high learning rates while remaining stable. The successful creation of real-time finetuning would make smaller, agile models much more capable than very large general models such as GPT-4 thus opening a rich research direction for academics.

AI Model Orchestration Systems:


Shared multi-adapter inference systems: 

