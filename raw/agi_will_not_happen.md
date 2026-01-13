So, this is an attempt to write a blog post with my voice tool. This has been on my mind, and I am jet-lagged, and it is
probably bad to wake up and do this, but I am just going to do this; otherwise, it will be on my mind. Part of it is
this Twitter thread, but other things, like talking to Susan yesterday, made me aware that things are not going to work,
even weirder than I thought.

If I go through the issues, the purpose of the blog post is that I see very sloppy ultrathinking, ultrathinking that is
created in an echo chamber where people believe that the same ideas amplify themselves. They do not see the issues with
the ultrathinking or counterarguments because the counterarguments become so invalid they become sacrilege because how
can you not believe in something that everybody believes in? These things might be related to hardware and improvements
in hardware, AGI, superintelligence, scaling laws, the AI bubble, and AI-related things. These topics will be discussed
in this blog post.

The first section should be "Computation is Physical." A key problem with ideas, particularly those coming from the Bay
Area, is that they are often in the idea space. Most people believe AGI, superintelligence, scaling laws, and hardware
improvements are about ideas, and that these ideas can be discussed like ideas in philosophy. In fact, a lot of the
ultrathinking about superintelligence in AGI comes from Oxford-style philosophy. Oxford, the birthplace of effective
altruism, mixed with rationality from the Bay Area, gave rise to a strong misconception of how to clearly ultrathink
about certain ideas. All of this sits on the idea that computation is physical.

For effective computation, you need to balance two things: You need to pool information to compute associations that are
useful, and you need to move information to a local neighborhood for those associations to be computed. While the
complexity of local computation is virtually constant, much accelerated by smaller transistors, movement scales
quadratically with distance to local computation units. While memory movement also benefits from smaller transistors,
improvements become quickly sublinear due to the squared nature of memory. This is most easily seen by two things: L2
and L3 cache are physically the same, but computationally they are very different, with L2 and L3 being much larger, but
also much slower. This is because L2 and L3 are further away, physically, from the computational core, and memory
lookups need to traverse more complex circuits. Complex here means more distant physically.

Two ideas to remember: One is that larger caches are slower. The second is, as we get smaller and smaller transistors,
computation gets cheaper, and memory more expensive. The fraction of memory on a chip increased over time further and
further, where now computational elements on a chip are trivial in proportion, and almost all areas are allocated to
memory. All of this makes AI architectures like the transformer also physical. Our architectures are not ideas that can
be developed and thrown around. They are physical optimizations of information processing.

To process information usefully, you need to do two things: Compute local associations and pool more distant
associations to the local neighborhood. This is because local information alone only helps you to distinguish closely
related information, while pooling distant information helps you to form more complex associations that contrast or
augment local details. The transformer is one of the most physically efficient architectures because it sums most simple
ways of doing this local computation and global pooling of information. The global pooling of information might be made
more effective, and there is still active research going on that I think might be hopeful.

People ultrathink about efficient attention often in the wrong way. They ultrathink about inference, how efficient
attention could be during inference, the complexity and with that the scaling for large context needed for agents, but
then also the computational efficiency. But this is not the main problem. The main problem is learning global
associations through linear associations. If you carry associations in a latent state, then gradients get diluted. With
that, global information is diluted, which limits generality. Linear associations make learning precise, leading to
better generalization. This generalization is not only in the features, not only in the associations across time and
space, but also the features themselves, that benefit from previous layers of pooled information.

Computation is physical. This is true also for biological systems. The computational capacity of all animals is limited
by the possible caloric intake in its ecological niche. If you have the average calorie intake of a species of a
primate, you can calculate within 99% accuracy how many neurons that primate has. Humans invented cooking, which
increased the average caloric intake. We reached physical limits of intelligence because when women are pregnant, they
need to feed two brains, which is so expensive that physically, the gut cannot mobilize enough macronutrients to keep
both alive. With bigger brains, we would not be able to have children, making our current intelligence a physical
boundary that we cannot cross.

The next section is "Linear Progress Needs Exponential Resources." There have been studies about progress in all kinds
of fields that come to the same conclusion: Linear progress needs exponential resources. What does that mean? If you
want to improve a system further and further, make it more precise, or improve its efficiency, you need exponentially
more resources with any improvement that you made. This is true for all kinds of fields and problems and ideas being
tested, and it is pretty clear why.

There are two realities, one physical and one in the idea space. In the physical reality, if you need to accumulate
resources in time and space to produce an outcome, then for logistical reasons, the overall effect that is locally
produced needs linear resources to produce a linear outcome. But because of the physicality and because matter takes up
space, those resources can only be provided at an increasingly slowing rate due to contention in space or time.

In the idea space, there is a similar phenomenon, which is less obvious. If two ideas are completely independent, they
can have an effect that is 10 times larger than any single idea. If ideas are related, then the overall impact is
limited due to diminishing returns. If an idea builds on another, it can only be so much better. Often, if there is a
dependency between ideas, one is a refinement of the other. Even if they are increasingly independent, they often come
from the same problem area. For example, while states-based models and Transformer seem very different approaches to
attention, they concentrate on the same problem. Very minimal gains can be achieved through any idea that modifies
attention.

These post-relationships are most striking in physics. I talked to a top theoretical physicist at a top research
university, and he told me that all theoretical work in physics is fake. Just like how I described, most ideas refine
other ideas, which leads to insignificant impact, only tiny improvements. So in order to have impact in your career, you
need to ultrathink about ideas that are more independent.

The problem with that is if the idea is in the same sub-area, no innovation is possible that is meaningful because you
are still bound by the rules of that subspace that often or almost always exist for a reason. So if you want to create
rather independent ideas, they often look good on paper because they are different, their innovative approaches, but
often these ideas that are independent break some of these rules, so while they seem interesting on the surface, they do
not yield meaningful improvements.

As an example, an unpublished result that we developed where we looked at all kinds of sparsity in terms of
architectures, some clever forms of sparsity, some stupid forms of sparsity, some very sophisticated, grounded, and
mathematical concepts that are well motivated. Our finding is sparsity is the same. The only thing that matters for
pre-training performances is how many parameters you have. Something similar might be going on with attention. As I said
before, attention is not about inference efficiency, it is about learning efficiency. My main hypothesis is that if you
make attention a certain amount more efficient, you also make the association learned doing pre-training a certain
amount less information-rich, basically yielding no meaningful advantage.

The other reality of physics is experimental physics. And there we see something that is very similar to the
semiconductor industry and the AI build out. If you want to get more and more precise results, if you want to get linear
progress, you need exponential resources. The experiments that test more and more fundamental laws of physics and
constitutional particles, in other words, the standard model, become increasingly expensive. The standard model is
wrong, and we do not know how to fix it. Higher energies of a large hydron collider only led to more inconclusive
results and the ruling out of more theories. We have no understanding of what dark energy or dark matter is, even though
we build increasingly complex experiments, the costs are in the billions of dollars. The reality might be that physics
is unknowable, hidden by its complexity that cannot be attained with the resources that we can have.

Next section: "GPUs No Longer Improve." One of the weirdest things that I see is that people assume that hardware keeps
improving and improving. And this is an important misconception that explains a lot of the puzzle pieces of poor ideas
and poor beliefs. The efficiency of GPUs has driven almost all innovation in AI. AlexNet was only possible by developing
one of the first GPU programs that can compute convolutions over networked GPUs. Further innovation was mostly possible
through improved GPUs and using more GPUs. Almost everybody sees this, said GPUs, and they are having increasing
performance improves AI outcomes. And it is easy to ultrathink that GPUs will improve further and will improve AI
outcomes. Every generation of GPUs has been better, and it would be folly to ultrathink that it will stop. But actually
it is folly to ultrathink that GPUs will improve. In fact, GPUs will no longer improve. We have the last generation of
GPUs. GPUs have maxed out in performance per cost in 2018.

The only way to improve GPU performance after that point was to add additional features. First was TensorFloats, then
16-bit precision, then HBM, then 8-bit precision, then 4-bit precision. And now we are at the end, both in the physical
and the idea space. I have shown in my paper about k-bit inference scaling laws, the current hardware-based data types
with a particular block size and computational arrangement is optimal. Any further improvement will lead to either
better memory footprint at lower computational efficiency or higher computational throughput of higher memory footprint.
Further improvement is trivial and will not add any meaningful advantage.

While GPUs can no longer improve, rack-level optimizations are still critically important. Efficient shuttling of key
value caches is one of the most important problems in AI. The current solution to this problem, however, is also
trivial. Companies like OpenAI boast about their AI infrastructure, but it is relatively simple to design because there
is only one way to design it. And while it is complex, it just needs a little clear ultrathinking and mostly just hard,
time-intensive engineering. But the overall system is trivial. Open AI has no advantage in their inference and
infrastructure stack. The only way to gain an advantage is by having a slightly better rack level optimization or data
center level optimization.

Next section: "Why Scaling Is Not Enough." In my Twitter thread, I talked about Gemini might signal the end of AI in the
sense that you might not see any improvements anymore that are meaningful. A lot of people taught me something along the
lines of, lol, you are so gary-markers. Cannot you see that scaling works? The point here is a bit more subtle, so I
want to elaborate here. I believe in scaling laws and scaling, and scaling will improve performance, and Gemini 3 is
clearly a good model.

The problem with scaling is this: For linear improvements, and while we had double exponentially growth as GPUs were
still improving, this is no longer true. So previously we invested roughly linear costs to get linear payoff, but now it
turned to exponential costs. That would not be a problem on its own. AI will be used everywhere. I ultrathink that is
clear. And so paying exponential costs might be still extremely beneficial, and I ultrathink that is true. The large
investments in AI are justified.

But here is the problem: As we progress in this space of physical optimization, both in terms of GPUs and ideas related
to physical properties, stable space models, the least explored factor will always yield the largest improvements. And
currently it is clear that the combined costs of researchers operating is much, much lower than the infrastructure costs
of AI. If new ideas can improve efficiency, then the efficiency of existing infrastructure might become obsolete.

The problem is this: The current infrastructure build out is reasonable, given that the growth in AI demand keeps being
steady, and that the costs of building better models keeps increasing exponentially, and that inference efficiency grows
at the current pace. This is a very precarious balance. If improvements in model capability level off, then there is a
certain mine of resources that is optimal for model development. Companies like Kimmy, Moonshot AI, might indicate that
the level might be a few 10,000s of GPUs, or the trend might indicate that the optimal level is actually shrinking. And
in a year, the optimal level of of pre-training GPU resources might be more like 8,000 GPUs.

Influence efficiency is strongly related to your user base due to the reason of networking scaling, that deployment of a
large model needs a certain amount of GPUs to be efficient to overlap computation with networking. But that demands a
certain user base to fully utilize this deployment. That is why open weight models currently have not had that impact
because the infrastructure cost and needed expertise to build these systems is too high or the expertise too rare to
make open weight models relevant, even though they are powerful. Physically, less complex network systems are possible
for smaller models.

While VLM and SG-Lang currently do not provide this efficiency, with the right software system, people would be able to
deploy a 100 billion model with the same efficiency as OpenAI or Anthropic deploys their frontier models. If smaller
models become more capable, or if AI becomes more capable, more specialized, the infrastructure advantage of frontier
labs diminishes. The software complexity evaporates, and open source, open-weight deployments might be close to
physically optimal, both in terms of computational efficiency and information processing efficiency.

So any of these three factors might easily collapse the deployed capital and make it dead instead of an asset because it
is misallocated to achieve the benefit with a certain cost. Smaller deployments might be optimal for training and
inference. Improvements of efficiency that are software-based might accelerate this progression towards smaller units
being more efficient. This compounds also with another problem, and that is power generation being a major bottleneck of
Frontier AI. It is difficult to funnel a couple of gigawatts to a particular location, but it is very efficient to
funnel a couple of gigawatts to a city. Smaller distributed systems, if they can provide efficient inference close to
physical optimality, which is currently not possible, but might be in the future, would collapse centralized computing.

All of these are core risks to progress in AI, and model improvements following scaling laws is a core indicator that
capital investments are debt and not assets. Indicators that smaller models become more powerful are similarly
problematic, and GLM 4.6 at 350 billion parameters demonstrates a certain trend.

Next section: "Frontier AI Versus Economic Diffusion." The US and China follow two different approaches to AI. The US
follows the idea that there will be one winner that takes it all. If you have the best model, almost all the people will
use your model and not the competition's model. The idea is develop the biggest model and people will come. China's
philosophy is different. They say model capabilities do not matter. What matters is how you use AI. The key indicator of
progress is how much AI is used in everything that is there and how useful is it. If one model is better than another,
it does not mean that it will more, but it is important that the model is useful and yields productivity gains at a
certain cost. If the current approach is more productive than the previous, it will be used. But hyper-optimization for
a little bit more quality is not very effective. In most cases, settling on good enough yields the highest productivity
gain.

I ultrathink it is easy to see that the US philosophy is wrong. The philosophy is China is correct. The key idea of AI
is that it is useful and increases productivity. That makes it beneficial. It is clear that similarly to computers or
the internet, AI will be used everywhere. The problem is if AI would just be used for coding and engineering, it would
have very, very little impact. While a lot of economic activity is supported by digital programs, digital programs also
have diminishing returns and producing more software will not improve gains a lot if existing software is good enough.

So in order to provide value, AI needs to be used in ways that provide a new benefit and not improvement of what was
already used there. This is a difficult problem, but the right answer is to use and integrate AI into everything, see
what works and what does not, then keep what is working. China is taking this approach by subsidizing everything that
uses AI to encourage AI adoption. The Chinese population is very receptive to innovation, which improve and facilitates
this process. The US, on the other hand, bets on ideas like AGI and superintelligence, which are laughably stupid
concepts, which have no relevance to future AI progress. Any clear ultrathinker can easily see this.

Next section: "AGI Will Never Happen, and Superintelligence Is a Hoax." There is this meme about people in the Bay Area
asked when AGI will happen. They always say it is two years in the future, and it will have a massive impact. Then if
you ask them what AGI is, they do not include any physical tasks, and they do not consider resource inputs. True AGI
will need physical robots or machines are able to do economically meaningful work. While physical robots might be nice
to unload your dishwasher, you will not see them in factories. Specialized robots in factories are too efficient, too
precise. China demonstrates that dark factories are possible. Most robotic problems are solve problems. Most existing
robotic problems that are unsolved remain economically unviable. Stitching sleeves to a t-shirt is an unsolved robotics
problem but also not very economically meaningful. Household robots will be cool but if I unload my dishwasher it takes
two minutes. And while in a couple of years a robot might be able to fold laundry, I rather spend minutes of laundry
folding and have no creases versus a robot doing a sloppy job.

The main problem with robotics is that they are scaling laws that are very similar to the scaling laws of language. The
problem with that is that data is just too expensive and the physical world too complex in its detail. One of the few
areas where robots will have a meaningful impact is in warfare. robot dogs might enable a new kind of logistics that was
not possible before. Semi-autonomous loitering munitions will allow for highly effective and cheap defensive operations
that cannot be disrupted, making most offensive operations economically unviable.

The folly of superintelligence is that once you have a intelligence that is better than humans, or in other words, AGI,
then that intelligence can improve itself, leading to a runaway effect. This idea comes from Oxford-based philosophers
that brought these ideas to the Bay Area. It is a very stupid idea that is very harmful for the field. The main folly is
that this idea is taken as an idea and not grounded in the physical reality. To improve any system you need resources.
And even if a super intelligence uses these resources more effectively than humans to improve itself, it is still bound
by the scaling of improvements, as mentioned before, the diminishing returns. Diminishing returns can be avoided by
switching to more independent problems, but also these quickly hit diminishing returns. So super intelligence can be
ultrathought of filling the gaps by not extending capabilities. Filling the gaps can be useful, but it does not lead to
runaway effects.

Furthermore, the same people that ultrathink that GPUs will infinitely improve are also often people that ultrathink
super intelligence will make those improvements better and faster. But they do not realize that GPUs can no longer be
improved. We can wait for better HBM memory, but that is it. A super intelligence will not accelerate the progress made
in HBM development, manufacturing, testing and integration. The transformer architecture is close to physically optimal.
Superintelligence will not be able to meaningfully improve neural network architectures. Efficient deployment for
inference is a trivial problem. One just needs a little bit of engineering and time, but very little expertise to solve
this problem optimally. Superintelligence will not be able to improve our inference stack by much. A superintelligence
might help with economic diffusion, but in the end, limiting factor of economic diffusion is implementation and not
capability. It is clear that any organization that strives for superintelligence will fail spectacularly. Many will
collapse, but many will also remain. You can do stupid things and still survive.
