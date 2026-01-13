# Use Agents or Be Left Behind? A Personal Guide to Automating Your Own Work

If you are reading this, you probably feel the FOMO. Maybe you have seen the Twitter threads about coding agents completing entire features in minutes. Maybe a colleague mentioned they are "10x more productive" now -- or an "Influencers" saying AGI is here now. Maybe you tried Claude Code and felt confused about why the magic everyone talks about is not working for you. This blog post is for those who want to cut through the hype and understand what actually works, what does not, and how to think about automating your own job.

I have been using agents — primarily Claude Code — for eight months to automate my own work. What you will read here is not speculation or theory. It is the product of hundreds of hours of experimentation, many failures, and some surprising successes. As a professor who does not write much code anymore, my perspective is different from the software engineering discourse that dominates Twitter. Most of my agent use is actually for writing — blog posts, grant proposals, meta reviews. This blog post offers that often-missing view.

Just to give you a hint of how powerful agents have been for me: usually the first year as a professor is very stressful and involves a lot of work. For me, it felt easy. I had some luck here and there, but I believe the use of agents is a significant reason why things have been manageable for me when they are hard for others.

Before I go into the details, let me briefly introduce three perspectives that will help you think about agent use: the Reality Perspective, the Process Perspective, and the Long-Term Perspective.

The **Reality Perspective** separates what is genuine from what is hype. The software engineering story you see on Twitter is real, but it is also very particular. Most tasks are not like software engineering. Understanding this distinction is crucial.

The **Process Perspective** comes from my years working in the automation industry in Germany. Before you automate anything, you need to understand your process, measure it, and calculate if automation actually makes sense. Many tasks should not be automated because the cost exceeds the gain.

The **Long-Term Perspective** is the Shenzhen-style view: sometimes you automate things that do not pay off in the short term because the skills and knowledge you build will make future automation effective. This is exactly how China built superior automation capabilities — through the accumulation of long-term expertise, not short-term optimization.

Balancing all three perspectives probably leads to better automation decisions than looking at one angle alone. Let me go through each factor.

## The Reality Perspective: What Is Hype and What Is Real

### The Software Engineering Story

What you see on Twitter is mostly about software engineering. And while agents in software engineering are real and powerful, software engineering is very unlike most other problems.

In software engineering, you often have many parallel problems that you work on: bugs, new features, quality control and refactoring, GitHub discussions and reviews. All of these tasks are independent and can be parallelized. Usually a bug does not depend on a feature. Reviews are on top of fixed bugs or added features, so they do not interfere with other work. The larger the codebase, the more independent work can be done, and the more parallel sessions become useful.

But here is the thing: the concept of parallel sessions is not useful for most tasks. I cannot write three grant proposals in parallel by having three agents work simultaneously. I cannot review papers in parallel if each review requires my judgment. The parallelization story is real for software engineering but misleading as a general model of what agents can do.

That said, there is something useful in this thinking. You can restructure how you work so that most of your time is spent inputting information into agents rather than waiting for them to complete work. This is not easy. You need to context switch quite a bit, and context switching can reduce the quality of your work. But with practice, it can be effective.

### The Real Gains of Agents

Here is my honest assessment: more than 90% of code and text should be written by agents. You need to do so, or you will be left behind.

This statement might seem controversial and as FOMO-inducing as the software engineering story I just critiqued. But I believe it is reality. A lot of the work that we are doing can be prepared by coding agents.

When I talk with people about this — about almost everything being AI-generated — they find it ridiculous. How can generic boilerplate generation replace the intricate details of code and text that distinguish one person from another?

I think this is a delusion.

### Why AI-Generated Content Is Personal, Not Generic

AI-generated content is personal content. When I explore a concept with Claude, the output is not generic. It is shaped entirely by my thinking, my style of conversation. I really like connections between fields, and the topics I explore are highly personal and unique traces of my thinking — and with that, my taste.

Let me give you an example that will always stay with me. I once started a conversation about jihad — the concept in Islamic theology that is often misunderstood, about doing the right thing rather than the easy thing. From there, I ended up connecting it to Krishna's advice to Arjuna about surrendering the fruits of action (karma yoga), to Lutheran grace that emerges at the height of struggle, to Taoist Wu Wei where struggle disappears through letting go and letting your nature take over, to Beowulf and naked will against overwhelming odds (the fight with Grendel).

None of this exists in any textbook or on the internet. It is a fingerprint, a very personal fingerprint. If you were to read the details of these conversations, you would know parts of me intimately — who I am and why I am that way. You would know me to a degree that is usually only reserved for close friends and your partner.

Someone thinking that AI-generated content is impersonal and generic is deeply mistaken. The concept of soulless AI generation is an artifact of less powerful AI, or the mistake of seeing your own generations as what AI can do rather than recognizing it as a skill issue.

And just to make a point: you might have not noticed this, but this entire blog post is almost entirely AI-generated.

## The Process Perspective: Thinking About Automation

### The Basic Calculus of Automation

Before I worked in AI, I worked in the automation industry in Germany. I was automating SCADA systems — integrating data from machines and databases to enable the control of workflows via data and monitoring. Those three years in the automation industry apply directly to automating your own work with agents.

The first important question is: when should you automate versus when should you not? While people always think about automation in terms of full automation, this is almost never the case in practice. You always have a degree of automation.

Here is how to think about useful automation: if you take your current degree of automation and increase it by a new technology, then you improve by a certain percentage. If a task takes 10 hours and you improve the degree of automation by 10%, then it takes 9 hours. It is a simple calculus: how often do you do the task, and how long do you need to automate this task to improve the degree of automation by 10%?

If this calculus leads to a result where the cost of automating something is higher than the gain, then the problem is not primed for automation. It is better to not automate it. There are many tasks that should not be automated because it is not effective.

Additionally, as your workflow changes, it adds overhead. For example, you might save 30 seconds, but if your agent needs 30 seconds to generate that automation, then the effectiveness is 0%. The degree of automation improves by 0%.

Do I want to be someone who automates everything without thinking about whether it actually helps? No, I want to be someone who thinks carefully about where my time goes. The calculus forces that thinking.

### The Method: Process Optimization

In automation, if you want to improve, a very basic method is to be on the factory floor with a stopwatch. You look at and study what workers are doing. You time each step: how they hand off work to another person, when they wait for previous work to complete, how many resources they need.

If you have all these components, you can construct a workflow — a process that reflects the current state of how you work. Based on this, you can think about how to optimize. This thinking is extremely important for automating your own work. You have to think about how you work on a particular problem and how you can change your work with agents. Sometimes you find that the process cannot be optimized much with agents.

Let me give you a concrete example. If I take one minute to read an email and 30 seconds to reply, then it takes 1 minute 30 seconds to complete an email. Now, if I use an agent to help me with my emails, then I need to guide it to process my emails. Then I need to read that content to decide how it should create drafts or answer emails so that I can then edit those drafts. But once you do this exercise, you realize that by using agents, you just shift the process — you still need to read content.

There are certain emails that are easy to automate. There are others that are not. It depends on your process and your underlying inputs to see if using agents and changing your process can actually lead to productivity.

Reading an email or reading AI-generated content has a cost. You need to include that cost to understand if you can benefit from automation. This insight — which seems obvious but is often ignored — is fundamental.

## The Long-Term Perspective: Building Automation Muscles

The process perspective I just gave is a short-term view. You look at the underlying processes and the degree of automation, then think about how long you will need to automate that work and how much you increase the degree of automation. It is a simple calculus. This is classic automation, how it is done in Germany and other countries. Very cost-effective and optimal in the short term.

However, it is very short-sighted because it does not consider long-term consequences.

The long-term view is a Shenzhen-style perspective. It is not about making any automation useful in the short term. It is about making automation useful in the long run by gathering knowledge that improves automation over time.

With the short-term calculus, you need to add: even if the degree of automation is not worth it in the short term, will the skills I build and the tools I develop make future automation effective that was previously ineffective? Does the additional knowledge help me with future automation?

This is exactly what led from Shenzhen-style scrappy factories to highly structured dark factories that are fully automated. Chinese automation is far superior to Western automation, not because of scale, but because the long-term view of automation led to a higher quality and degree of automation.

This is an important concept. You need to optimize both short-term and long-term perspectives to effectively automate your own job. Europe is struggling. The US is struggling in many segments because they did not build the long-term skill set initially — the profitable or unprofitable efforts that help them build the automation muscles to tackle more challenging problems.

In other words, using agents and failing at automating a task effectively is important. You need to gain skills to improve future automation, and that means sometimes trying to automate things that you know you will not be able to automate.

Do I want to be someone who only takes the safe, immediately profitable path? Or do I want to be someone who invests in learning, even when the immediate returns are unclear? I choose the latter, because I have seen where it leads.

## Why Automating Your Job Is Good for You

Software engineers are not replaced. They just level up. The current hiring challenges are driven by COVID and financial dynamics much more than by AI. Software engineers are much more effective at building software more rapidly, and the value of software has not decreased significantly. An engineer that uses agents like a hot knife slicing through butter is actually more valuable because they can produce more software that still has significant value.

A common theme is that this is the current state, but software engineers will become obsolete very soon. I have many friends at frontier labs who had this view about nine months ago, but it has broadly changed. They see that it is difficult to automate their own work and that as they use these tools, new problems open up.

Even if an agent can do everything, agents cannot do everything at the same time. If you have a limited amount of GPUs, you want to direct agents to tasks that are useful for you so they can generate value where you need it. While even that can be partially automated, once your existence is at stake, you probably want to direct what agents do yourself — at least specify the problem and solution you want.

I think it will be a long time until you use an agent to manage your retirement savings by analyzing the stock market and optimizing it fully autonomously. But what is more reasonable is you build a system where you tell an agent what risk you are happy to accept and how to optimize this risk through hedging, so that you might manage your retirement fund with a trade-off between potential upside and risk over time. It would be unwise to fully trust an agent if you do not know the parameters that are important for you and how the agent chooses those parameters.

If resources are limited, you want to decide how those resources are used rather than fully trusting an agent. And if this is true, then directing agents will remain a problem, even if agents can do everything, because agents cannot do everything at once, because resources are finite.

Long story short, because of this resource problem, there will always be work where your personal preferences, decisions, and taste will be needed — even if 90% of the work happens through AI. From software engineering we already see that this work changes, but it will not eliminate our jobs. We also see it will impact jobs: if you do not know how to use agents, you will not have a good job or be able to find a job. Agent use is now an essential skill that you need to develop.

## My Personal Experience with Automating My Own Work

### Where Agents Work Well

#### Custom Tooling and Pipelines

What is most common on Twitter as examples of successful agent use is when people create a tool that is useful for them. Small extensions that help your everyday life — just vibe coding something that you always wanted and that is simple, but nobody provided.

While this is a simplistic way of using agents, it has its importance. This is a problem where agents work really well, and they require very little skill to be used correctly.

For example, I built tools that help me write this blog post. I built tools that help me work with agents. One of the most important tools is a voice tool, which helps me quickly interact with agents, particularly for parallel sessions. A voice tool also helps me because I have carpal tunnel in both my hands. Typing can be painful. I have a very custom keyboard layout and way of working with the keyboard that reduces pain to almost zero, but still it is much more comfortable to just use my voice. And it is not only comfortable, it is faster.

A main advantage is that with voice you can inspect outputs and use your keyboard and mouse while narrating. This is extremely powerful. A key tool that everybody should develop is their own voice tool to use AI in this way where they can do work while narrating.

#### Connected Papers Replication Tool

Another tool I built was to solve the problem of finding related work. The most useful tool I had ever used for this was Connected Papers. It was free at some time, but then became commercial. I need something like this at the beginning of a project and when writing the related work section of a paper. I did not want to pay for the subscription, and I wanted my students to be able to access it. So I just replicated the entire software system.

This was probably not effective for automation in the short term — I could have just paid for Connected Papers. But it gave me an overview of what I can do in the long term: what tools can I build, what is too ambitious, what is less ambitious, how can I be more effective when creating complex tools.

The tool uses the Semantic Scholar API to retrieve data. Then it builds statistics on the citation graph of papers to find papers that are very similar to what Connected Papers finds. The key insight I had is how Connected Papers works: it finds papers that are in conversation. They are often indirectly related through a third paper that cites both of them. They create a chain, a loop of three papers, and this loop is distributed. If you have this loop across three-paper chains that create circles, you have a very good way of finding related papers.

Of course, you want to weigh the paper relationships by the number of citations each paper has, particularly if you normalize over time. A paper from 2020 with 100 citations is more significant than a paper from 2024 with 100 citations. This weighting was the key algorithmic insight that made the tool useful.

But here is where it failed: the user interface. The algorithm works well, but presenting the results in a way that is actually useful turned out to be the hard part. Connected Papers has a beautiful graph visualization that lets you see clusters and relationships at a glance. My tool outputs a list. A list is not the same as a graph — you lose the spatial relationships, the ability to see which papers are central versus peripheral, the intuitive clustering. I underestimated how much of Connected Papers' value comes from the interface, not just the algorithm.

I have not solved this yet. Building a good web-based graph visualization that is interactive and fast is a significant engineering effort — much more work than the core algorithm. This is a common pattern: the "hard" algorithmic part turns out to be easy, and the "easy" interface part turns out to be where you actually fail.

My goal was to make the tool easy to use — host it on the web so that similar to Connected Papers, everybody can just access it and use it. They would not need to run Python commands, have API keys, or deal with any of that friction. But I have not created a pipeline yet that publishes tools on the web in a way that makes them broadly accessible while also ensuring that not everybody has access so they drain my resources or make me run into rate limits with the Semantic Scholar API.

You see that even creating tools can have its own complexity. While not highly successful in the short term, certain automation gives you skills useful for long-term optimization. I would encourage you to spend some time on futile projects just to learn how to improve automation in the future.

#### Tools for Students: Claude Code as an API

Other tools I build are mostly for my students. Here is one that might surprise you: it was recently revealed that quite a bit of Claude Code use is actually by exploiting it as an API. This means you use a Claude Code endpoint just as an API to use it in other work. That gives you API access without needing separate API keys or billing.

My students use this, and when I asked them if they need any GPUs for their projects, they said no — they just generate with the API that we created. It has been a very useful tool. For a research group, having easy access to frontier model capabilities without the friction of API management changes what is possible.

The tools that I build are designed to be easy to use. The easiest approach is just to host them on the web. Similar to Connected Papers, everybody can access and use them — they do not need to run Python commands, manage API keys, or deal with those kinds of friction. But I have not created a pipeline yet that publishes tools on the web, makes them broadly accessible, while also ensuring that not everybody has access so they drain my resources or make me run into rate limits.

#### Other Tooling

Other tooling that is much more straightforward includes infrastructure for Slurm and common infrastructure to analyze experiments. I believe Weights and Biases is total crap and actually harms research — it encourages sloppy experiment tracking habits and creates vendor lock-in for something that should be simple.

A tool I have not developed yet but which my colleagues have mentioned is a review system where students can get feedback on ideas or papers by querying an agent or an agentic pipeline that mimics how an academic advisor would give feedback. Imagine a student being able to get a first-pass critique of their paper draft at 2 AM before our meeting the next morning. This would not replace advising, but it would make our meetings more productive by handling the basic structural and clarity feedback automatically.

While not all of these tools might be useful, and some are more like distractions, it is clear that with the right pipelines, workflow, and tools, productivity for students can be increased dramatically — and this can be driven by an advisor who invests in building these systems.

Similarly, a technical manager can probably develop tools and guide a team in this way. Even if agents cannot do all the work, you need to figure out what work you actually want to do and how you want to build on each other's work as a team. Agents can work independently, but it might not be useful if your team is pulling on different ends of a problem, if coordination is missing. The tools an advisor or manager builds can provide that coordination layer.

All of these examples highlight where tools fail, where tools can be useful, and where tools might not be useful in the short term but give you the skills to improve tools in the future.

#### Writing Tasks: Blog Posts

You might have guessed it already: this blog post is AI-generated. More than 95% of the text comes from an AI model. I did not even type prompts. Most of it was just me rambling into a microphone while doing other things, then transcribing that voice into text, shaping it into a blog post, then doing a style transfer to shape it into my voice, and then adding some small snippets that have character.

The last piece is a cherry on top that converts a blog post that already has my style into a blog post that I truly own. But these edits make less than 5%, maybe even 2% of the overall blog post.

While I am still experimenting with blog posts, this pipeline allows me to write blog posts much more quickly — and blog posts that are much more current. A blog post like this would have taken me days in the past. Now it takes about one and a half hours: one hour to speak content into a microphone, 10 minutes for my agentic workflow, and then 20 minutes to review and edit the passages. It is very fast, and using agents you notice that the quality is pretty good.

#### Writing Tasks: Grant Proposals

Grant proposals are a major time sink as an academic. A CMU student costs $150,000, and I need to find that money by writing grant proposals. A lot of proposals are rejected, so you have to write lots of them.

It is interesting because while you might think the blog post approach should work, it actually does not work that well. Grant proposals need to have a particular structure, and even small deviations read poorly. Good design is familiar design, and good proposals are familiar proposals.

Just like a good abstract — for example, an abstract in Nature has almost always the same structure, sentence by sentence, the same for every paper. That makes it easy to read abstracts because you know where to find information. I am dyslexic, and reading is very slow for me, but I can actually read papers relatively quickly because they have common structure. I can skip sections, skip to particular phrases, and I know here begins an interesting part. If the introduction says "in this paper" or "here," then I know now the contributions begin.

Grant proposals are highly structured similarly. A free-flowing, talkative approach does not work out of the box, but it can be made to work by introducing an abstraction pattern.

This abstraction pattern works as follows: you create sentence-by-sentence extractions of what the grant proposal content should be. For example, for an abstract:
- The first sentence is about the general field and the subfield
- The second sentence mentions the problem, why it is important, and why it has not been solved
- The third sentence states your contributions and your main results
- The fourth sentence explains your main method
- Then, depending on taste, you expand on this method or keep it brief
- Finally, you state the impact and broad implications

If you have an AI model, you can apply this process very easily. What I told an agent was to create a pipeline which gives me particular questions about what content is needed to fill in all these placeholders. Then I smooth it over by doing style transfer using particular proposals that I have written and like.

With this, I can create a four-page grant proposal in about an hour or an hour and a half — very similar to a blog post.

#### Meta Reviews

Machine learning conferences are notorious for bad reviewing. The reviewing system is broken. There have been studies on ICLR and NeurIPS with clear results: reviewing does not work. Reviewing cannot identify the really worst papers and the best papers, but in between it is a coin flip.

The finding from these studies is that reviewing quality is not related to knowledge but related to effort. Undergrad students have much higher quality reviews than PhD students or professors because they have more time and take it more seriously. For PhD students and professors, it is a chore.

Looking at that reality, using agents becomes very straightforward. And there is no concern about doing poor meta review — quite the opposite.

There are two philosophies about being an area chair. One is you bring your own opinions and overwrite decisions. The other is to follow what the reviewers said. I believe the second is more intellectually honest. While I have expertise and sometimes will overwrite reviews, I have not had the depth to read every paper thoroughly, and certain concerns might be valid. A good paper is not a paper that I like, but a paper that is useful for the research community.

What I built is a system to analyze the discussions, the points where reviewers disagree, give summaries of papers, summarize which papers are borderline, and identify which are clear rejects or accepts. The clear accepts or rejects have high score variability. These reviews can be processed quickly — you can understand why people have certain views.

What is more subtle is tracking changes in the discussion. With the rebuttal, even if the score is not increased (which is very common because people do not have time), the rebuttal might contain information that could change the outcome.

From all this discussion about borderline cases, you can easily draft the first meta review. If it looks strange, you can ask the agent to explain, provide more detail, or provide evidence. It is a very interactive way of reviewing and actually mirrors what I would do without AI agents.

All these things can be done by an agent, and they can be done faster and probably more precisely. Understanding a subtle argument of a paper I have not seen before, between reviewers with different perspectives — this is hard if it is 5 PM and I have already had eight meetings and I am just tired. But if I do it with my voice tool and my meta review agent system, this allows me to write high-quality meta reviews.

AI-generated content is highly personal if you do it right. This also goes for reviews. An AI-generated review is your review if you do it right. There is a danger of generic reviews, but at the current state of extremely noisy reviews, this is not the most relevant point. I think we do a disservice to the research community if we do not use agents for reviewing.

### Where Agents Fail

#### Email Automation

I alluded previously that I tried to automate emails for a long time. Over two months, I worked quite a bit on automating emails — for one because I do not like emails, and also because it is now a major part of my work.

I wanted to build a system that helps me manage, prioritize, and draft emails. Probably for most people, the problem is similar: knowing which emails need replies, what needs work, what is important, what can be ignored or replied to later.

Doing this manually is very simple and fast. I can often look at the title and immediately sort it into a category. My initial system was very focused on features. It would be easy to categorize which emails need immediate reply, which can wait. You can also easily categorize emails — student requests to work with me is one category, important emails related to funding partners is another.

But here is the issue: you need to look at those categories. If you create drafts, you need to look at the drafts. In Gmail, it is easy because you know the interface. If an AI does that, it is similar but automated. But you still need to look at what you actually need to do. And this costs time, just like how it costs time to read the title or skim an email to categorize it.

Here, the process optimization view kicks in. If I can categorize an email within five seconds, that is pretty fast. An AI agent needs to beat that in five seconds and be more precise than I am for it to actually be useful. While the reading and categorization can happen in the background, with an AI-generated categorization I still need to skim an email and skim the draft. That might take 10 to 30 seconds, and that might already be slower than just reading the title and deciding I will not reply to this email right now or never.

Something similar goes with drafting emails. Drafts need to be very precise. What I engineered was a system that provides enough context so an AI can draft well, but the editing part — understanding what was going on and if it was precise enough — often took slightly more time than just replying to the email. Because I cannot trust an AI 100%, I need to read the email, read the draft, and then edit the draft. In a workflow where you do all this manually, it is often faster, even for problems where automation might seem to work.

Despite all these edge cases, I did not want to give up. For one, I really do not like emails. But the second part is that for me it was a challenge: can I automate this task? And if not, I will gain valuable experience for the future.

So I made a second attempt. I knew about the process. I knew about the importance of interfaces and how to structure information. Since I am an avid Vim user, I know how to interact with information efficiently. This was a long process — co-designing functionality, agents, and user interface. It improved day by day, but at some point I asked: is Gmail, if I use it the right way, faster? I saw the improvement plateauing.

So I compared time spent on emails between the tool I created and just using Gmail. What I found is that just using Gmail is faster. I could not get any degree of automation improvement by using agents for emails.

But it was an important skill to develop. Sometimes you fail, and that failure teaches you something valuable for the next challenge.

## Conclusion

If you take away one thing from this blog post, let it be this: agent use is a skill, and like any skill, it requires deliberate practice, understanding of when it applies, and acceptance that you will fail often before you succeed.

The hype is real in some domains and misleading in others. Software engineering parallelization is real but not generalizable. The personal nature of AI-generated content is real and profound. The need for process thinking before automation is real and often ignored.

I hope these perspectives have been useful to help you think about how you can use agents, where agents work well, and what is hype and what is not. The key is to think carefully, experiment often, and build skills for the long term.

Do I want to be someone who chases every hype cycle without critical thought? Or do I want to be someone who develops genuine expertise through careful experimentation? I choose the latter, and I hope you will too.
