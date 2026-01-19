# How to Transform Raw Blog Posts into Polished Drafts

## About This Document

This guide is for anyone (human or AI assistant) transforming voice-transcribed blog post dictations into polished, publishable drafts. The author dictates ideas while doing other activities (cooking, walking), resulting in raw transcriptions that need significant cleanup and restructuring.

### The Author's Style

The author writes technical blog posts about machine learning research, often combining:
- Deep technical content (methods, results, comparisons)
- Personal narrative (struggles, failures, lessons learned)
- Practical guidance (what readers can do with this information)

The author prefers:
- First person ("I", "we")
- Direct, clear prose without academic hedging
- Vulnerability about failures and struggles
- Concrete numbers and specific details
- Conversational but authoritative tone

### Folder Structure

```
blog_posts/
├── raw/           # Voice transcriptions and cleanup drafts
│   ├── post_speech.txt    # Original transcription
│   ├── post_draft_v1.md   # Errors fixed
│   └── post_draft_v2.md   # Prose smoothed
├── drafts/        # Polished drafts ready for author review
├── best/          # Reference posts that exemplify good style
│   ├── how_to_choose_your_grad_school.md
│   └── llm_int8_and_emergent_features.md
└── published/     # Final versions after author approval
```

### Using the "Best" Reference Posts

The `best/` folder contains posts the author considers exemplary. **Do not copy their phrases**—instead, read them to understand:
- How they open (what feeling do they create?)
- How they structure information (what makes it easy to follow?)
- How they handle technical content (how deep? how explained?)
- How they include personal elements (where? how much?)
- How they close (what feeling do they leave?)

Different "best" posts may be better references for different new posts. A technical deep-dive might reference `llm_int8_and_emergent_features.md`; a career advice post might reference `how_to_choose_your_grad_school.md`.

---

## Overview of the Pipeline

```
raw/speech.txt → raw/draft_v1.md → raw/draft_v2.md → drafts/post.md → published/
```

| Stage | What Happens | Effort Level |
|-------|--------------|--------------|
| **Raw → v1** | Fix transcription errors, basic structure | Mechanical, straightforward |
| **v1 → v2** | Smooth prose, tighten sentences | Moderate, requires judgment |
| **v2 → Draft** | Add hooks, structure, emotional depth | Creative, requires brainstorming |
| **Verification** | Ensure no content was lost | Careful, detail-oriented |

**Critical Rule**: Each stage must preserve ALL content from the previous stage. Details often get lost in polishing—always verify.

---

## Stage 1: Raw to Draft v1 (Error Fixing)

**Goal**: Create a clean, readable version with all transcription errors fixed. Do NOT restructure or polish yet.

### What to Fix

**Transcription errors** (especially technical terms):
- Model/benchmark names: "Sweebench" → "SWEbench", "Killora" → "QLoRA"
- Institution names: "Dallin Institute" → "Allen Institute for AI"
- Technical terms: "good up issue" → "GitHub issue"
- Numbers: "8-Berry" → "8B" (8 billion)
- Library names: "bits and bites" → "bitsandbytes"
- Person names: Check spelling if uncertain

**Speech artifacts**:
- Filler words: "um", "uh", "like" (when used as filler, not comparison)
- Self-corrections: "No, actually..." or "I mean..."
- Restarts: "So what I want to— what we did was..."
- Verbal tics: Repeated phrases the speaker uses unconsciously

**Grammar and formatting**:
- Expand contractions: "it's" → "it is", "don't" → "do not"
  - *Note*: We expand in early stages for clarity; some may be restored later for tone
- Fix subject-verb agreement
- Fix sentence fragments (unless intentional for emphasis)

**Basic structure**:
- Add section headers following the natural narrative flow
- Do NOT reorganize—just mark where topics change
- Use headers that describe what the section contains

### What NOT to Do in Stage 1

- Do not reorganize or restructure content
- Do not remove any substantive information (even if it seems redundant)
- Do not add opening hooks or framing devices
- Do not add new content beyond what the author said
- Do not smooth prose or combine sentences (that is Stage 2)

### Edge Case: Unclear or Missing Content

If the transcription is unclear or seems to be missing something:
1. Mark it with `[UNCLEAR: description]` or `[MISSING?: seems like there should be X here]`
2. Continue with the rest of the document
3. These can be resolved during brainstorming with the author

---

## Stage 2: Draft v1 to Draft v2 (Prose Smoothing)

**Goal**: Make the text flow well while preserving ALL content. This is about sentence-level improvements, not structural changes.

### What to Do

**Consolidate repetition**:
- When the same idea is stated 2-3 times in different ways, keep the clearest version
- EXCEPT: Keep repetition that serves emphasis or shows thought progression
- When in doubt, keep it—better to have too much than lose something

**Smooth choppy sentences**:
- Combine fragments that are clearly parts of the same thought
- Add transitional words between paragraphs ("However", "This meant", "From there")
- Break up run-on sentences

**Tighten verbose passages**:
- Remove unnecessary words ("very", "really", "basically" when they add nothing)
- Convert passive to active voice where natural
- But preserve the author's voice—do not make it sound robotic

**Preserve conversational tone**:
- The result should still sound like the author speaking
- Some contractions may be restored if the expanded form sounds stilted
- Keep the "I" voice and personal perspective

### What NOT to Do in Stage 2

- Do not remove technical details or explanations (even if they seem obvious)
- Do not remove personal anecdotes or emotional content
- Do not add opening hooks or structural framing (that is Stage 3)
- Do not reorganize sections (that is Stage 3)
- Do not add content the author did not say

### How to Know You Are Done

Read v2 aloud. It should:
- Sound natural, like someone explaining clearly
- Contain all the information from v1
- Flow from one idea to the next without jarring jumps
- Not yet have a polished "blog post" feel—that comes in Stage 3

---

## Stage 3: Draft v2 to Polished Draft (Structural Transformation)

**Goal**: Transform the smoothed content into a compelling blog post with strong opening, clear structure, emotional depth, and satisfying close.

### Critical Principle: Feel Over Phrases

Read a relevant "best" post before starting. Then **match the FEEL, not the phrases**.

**WRONG**: Copy phrases like "If you are reading this, you probably..."
**RIGHT**: Understand what the phrase achieves (connecting with reader's situation) and create something original that achieves the same effect.

### Step 3.1: Brainstorm (With Author if Possible)

Before writing, clarify these elements. If working asynchronously, make your best choices and mark them for author review.

**1. The Opening Hook**
- What is a memorable analogy or image for this post's central tension?
- What concrete moment captures the emotional journey?
- Questions to ask the author:
  - "What moment showed you this was working?"
  - "What is the contrast between how others do this and how you did it?"
  - "What would grab someone scrolling past?"

**2. The Emotional Stakes** (if the post has personal narrative)
- What struggles should be surfaced?
- What were the specific costs and consequences?
- What was the vindication or resolution moment?
- Questions to ask:
  - "What did you have to give up or sacrifice?"
  - "What was the lowest point?"
  - "What moment made it feel worth it?"

**3. Structure and Escape Routes**
- What are the 3-5 major sections?
- Which sections can readers skip if they just want the results?
- For long technical posts, readers need permission to skip
- Questions to ask:
  - "If someone only has 5 minutes, what section should they read?"
  - "What is the dependency between sections?"

**4. The "What This Means For You" Section** (for technical/research posts)
- What can readers actually do with this information?
- What practical details matter? (code, costs, deployment)
- What is the broader implication?

**If you cannot brainstorm with the author**:
- Make reasonable choices based on the content
- Mark your choices clearly: `[HOOK: I chose X because Y—please confirm]`
- Provide alternatives if you are uncertain

### Step 3.2: Write the Opening

A strong opening includes:
- A memorable analogy, image, or concrete detail
- The central tension or challenge
- A preview of the payoff (what will readers get from this?)
- Acknowledgment of what will be shared (struggles, technical details, practical guidance)

**Length**: Usually 2-4 paragraphs before the table of contents.

**Example** (from SERA post—technical post with resource constraints theme):
```
If you look at how people produce coding agents today, they have an industrial
kitchen: large-scale reinforcement learning systems with many components for
efficiency that span hundreds of GPUs... We had the equivalent of a hot plate
and a frying pan: 32 GPUs and three bright-eyed researchers who wanted to cook
state-of-the-art coding agents.

This blog post is about how we cooked that coding agent.
```

### Step 3.3: Add Signposting with Escape Routes

Create a "What This Post Covers" section after the opening:
- List the major parts (3-5)
- Briefly describe each (one line)
- Provide explicit skip links for readers who want specific sections

**When to include escape routes**:
- Posts longer than ~2000 words
- Posts with distinct technical and narrative sections
- Posts where readers might have different goals

**When escape routes are unnecessary**:
- Short posts (<1000 words)
- Posts with a single linear argument
- Purely narrative posts

**Example**:
```
This post has four parts:

1. **The Struggle**: Switching fields, the costs of starting over...
2. **Getting a Foothold**: My early work on coding agents...
3. **Data Generation Methods**: Three approaches we tried... If you want to skip
   to what actually worked, jump straight to the [SERA section].
4. **What This Means For You**: How to deploy these models...
```

### Step 3.4: Build Emotional Depth (For Posts with Personal Narrative)

Not all posts need this—skip for purely technical posts without personal narrative.

Go beyond stating facts—add:
- Specific costs and consequences (not "it was hard" but what specifically was hard)
- The feeling of those moments
- Concrete details that make it real (names, timeframes, specific events)

**Weak**:
```
Switching fields was hard. People were disappointed.
```

**Strong**:
```
That was disappointing to many who hoped I might help with their problems. That
was particularly painful because I disappointed many people that I liked and
respected. And the costs accumulated. I had not published anything in about a
year. Students in this PhD admission cycle who might have wanted to work with me
did not know about my coding agent work because nothing had been released yet.
I watched as people paid less attention, as I became irrelevant. That is a
particular kind of loneliness in research—knowing you are working on something,
but having nothing to show for it.
```

**Where to add depth**:
- The opening "struggle" section if there is one
- Key turning points in the narrative
- The resolution/vindication moment

**Where NOT to add depth**:
- Technical explanation sections (keep these clear and focused)
- Sections readers might skip (don't bury important emotional content)

### Step 3.5: Use "But..." Transitions to Build Tension

In technical sections, structure with tension and resolution. This keeps readers engaged through complex material.

**Pattern**: [Achievement or approach] + "But" + [Complication or limitation] + [Resolution]

**Examples**:
```
This two-step approach seemed efficient. But we realized the editing step alone
was as computationally expensive as doing everything end-to-end.
```

```
Fine-tuning on just 500 samples from this task makes 8 billion models almost as
good as frontier models at searching codebases. But while search needs only 500
examples for near-frontier performance, editing is different.
```

```
At first this seemed like a problem. But we embraced it, and that led to
something unintuitive.
```

**When to use**:
- Transitioning between approaches/methods
- Introducing complications or failures
- Setting up surprising discoveries

**When not to overuse**:
- Not every paragraph needs this
- Pure explanation sections can be straightforward
- Do not create false tension

### Step 3.6: Close with Callback to Opening

Return to the opening analogy or image. This creates a sense of completion.

**Example** (callbacks to the industrial kitchen analogy):
```
This is how we cooked our coding agent with a hot plate and a frying pan. The
industrial kitchen is nice, but it is not required. Sometimes constraints force
you to find simpler solutions—and sometimes those solutions turn out to be better.
```

**If the post does not have an opening analogy**:
- Summarize the key insight
- End with forward-looking implications
- Or end with a reflection/question for the reader

---

## Stage 4: Verify Content Preservation

**This step is critical.** Polishing often loses details. Always verify before considering the draft complete.

### How to Verify

1. Open `draft_v2.md` and the polished draft side by side
2. Go through `draft_v2.md` section by section
3. For each paragraph in v2, confirm the polished draft contains:
   - The main point
   - All supporting details
   - All numbers and specific claims
   - All explanations of WHY (not just WHAT)
4. Mark anything missing and add it back

### What Gets Lost Most Often

- **Explanations of WHY**: Polished version says "This saves 50%" but loses "because bug generation is complex—instead of compute for both bug generation and one rollout, we have two rollouts and one bug generation"
- **Specific numbers**: "60 times cheaper" becomes "much cheaper"
- **Qualifications**: "This works for most cases" becomes "This works"
- **Secondary points**: The second or third point in a paragraph disappears
- **Technical details**: Specific method steps get summarized away

### Example of Content Loss

**Draft v2**:
```
This is efficient because bug generation is complex—instead of compute for both
bug generation and one rollout, we have two rollouts and one bug generation.
The GitHub issue creation is trivial once you have the trajectory. This saves
about 50%.
```

**Polished draft (BEFORE fix)**:
```
This saves about 50% of compute.
```

**What was lost**: The entire explanation of WHY it saves 50%.

**Polished draft (AFTER fix)**:
```
This is efficient because bug generation is complex—instead of compute for both
bug generation and one rollout, we have two rollouts and one bug generation.
The GitHub issue creation is trivial once you have the trajectory. This saves
about 50%.
```

---

## Edge Cases and Variations

### Short Posts (<1000 words)

- May not need "What This Post Covers" section
- May not need escape routes
- Opening can be shorter (1-2 paragraphs)
- Still needs a hook and satisfying close

### Purely Technical Posts (No Personal Narrative)

- Skip the "emotional depth" guidance
- Focus on clear explanation and practical value
- Still use "But..." transitions for engagement
- "What This Means For You" section is especially important

### Posts Without a Clear "Struggle" Arc

- Not every post is a hero's journey
- Can open with a question, surprising finding, or practical problem
- Structure around the question/answer or problem/solution instead

### Posts Where Raw Content is Incomplete

If the transcription seems to be missing important content:
1. Mark gaps with `[MISSING?: description of what seems needed]`
2. Note your assumption: `[ASSUMED: X, please confirm]`
3. If possible, ask the author to fill gaps before Stage 3
4. Do not invent technical content—only add structural/transitional elements

### Posts with Multiple Distinct Topics

- Consider whether it should be multiple posts
- If kept as one, use very clear section breaks
- Escape routes become essential
- May need a framing device that connects the topics

---

## Checklists

### Stage 1: Raw → Draft v1
- [ ] Fix all transcription errors (technical terms, names, numbers)
- [ ] Remove filler words and self-corrections
- [ ] Expand contractions
- [ ] Fix grammar issues
- [ ] Add basic section headers following narrative flow
- [ ] Mark any unclear or potentially missing content
- [ ] Verify no substantive content was removed

### Stage 2: Draft v1 → Draft v2
- [ ] Consolidate clear repetition (keep emphatic repetition)
- [ ] Smooth choppy sentences
- [ ] Add paragraph transitions
- [ ] Tighten verbose passages
- [ ] Read aloud to check flow
- [ ] Verify no content was removed

### Stage 3: Draft v2 → Polished Draft
- [ ] Read a relevant "best" post for feel (not phrases)
- [ ] Brainstorm or decide on: opening hook, emotional stakes, structure, practical section
- [ ] Write opening with analogy/hook and preview
- [ ] Add "What This Post Covers" with escape routes (if needed)
- [ ] Expand struggle/emotional sections with specific details (if applicable)
- [ ] Add "But..." transitions in technical sections
- [ ] Write "What This Means For You" section (for technical posts)
- [ ] Close with callback to opening
- [ ] Mark any choices for author review

### Stage 4: Verification
- [ ] Compare polished draft to draft_v2 section by section
- [ ] Verify all technical details preserved
- [ ] Verify all explanations of WHY preserved
- [ ] Verify all numbers and comparisons preserved
- [ ] Verify all qualifications and caveats preserved
- [ ] Add back any lost content
- [ ] Final read-through for flow

---

## Common Mistakes to Avoid

1. **Template copying**: Using phrases from "best" posts verbatim. Match feel, not words.

2. **Content loss**: Technical details vanishing during polishing. Always verify.

3. **Over-condensing**: Making sections too short. If v2 has a paragraph, the polished version should usually have at least that much.

4. **Premature polishing**: Adding hooks in Stage 1 or restructuring in Stage 2. Follow the stages.

5. **Generic emotion**: "It was hard" instead of specific costs and feelings.

6. **Missing escape routes**: Long technical posts need skip links.

7. **Inventing content**: Adding technical claims the author did not make. Only add structural elements.

8. **Ignoring post type**: Applying personal-narrative techniques to purely technical posts.

9. **Skipping verification**: Assuming polishing preserved everything. It usually does not.

10. **Overusing "But..."**: Not every transition needs tension. Use judiciously.
