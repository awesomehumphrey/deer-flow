# Explore Workflow

Follow an intellectual thread to discover new connections, test hypotheses, and deepen understanding of a specific question, relationship, or idea. This is the divergent thinking space: open-ended, generative, and grounded in the book's evidence base.

## Purpose

Book writing is not a linear march from plan to prose. Between ingestion and writing, between chapters, after reading a new paper, the author needs a space to think out loud: "What if dark patterns and security vulnerabilities are two expressions of the same structural problem?" or "How does the GrapheneOS example connect to the honesty gap?" These are not interview questions (the author is not being extracted from) and not writing tasks (no prose is being produced). They are intellectual exploration, and they deserve their own workflow.

Exploration produces understanding. That understanding feeds back into the Book Bible, chapter plans, and the author's evolving intellectual journey.

## Prerequisites

- At least one of: Research Digest, Book Bible, existing drafts, or the book-specific skill file
- A question, connection, or idea to explore

## Trigger Phrases

- "Explore the connection between..."
- "What if..."
- "Think through..."
- "How does X relate to Y?"
- "Brainstorm..."
- "What are the implications of..."
- "I'm wondering about..."
- "Help me think about..."
- "What would happen if we..."
- "Can we dig into..."

## Procedure

### Step 1: Frame the Exploration

Identify what is being explored and why it matters for the book. This is brief — just enough to establish direction without constraining the inquiry.

```
EXPLORATION FRAME:
  Question: [The specific intellectual question or connection to explore]
  Origin: [What prompted this — a new paper, a chapter draft, a conversation, a hunch]
  Relevant chapters: [Which chapters this might affect, if known]
  Current understanding: [What the Book Bible or Research Digest currently says about this]
```

If the author's prompt is vague ("I'm thinking about transparency"), ask one clarifying question to sharpen the thread. But only one — do not turn this into an interview.

### Step 2: Gather Context

Load the relevant context from what exists. This is selective, not exhaustive — load what is directly relevant to the question, not the entire evidence base.

Draw from:

1. **Research Digest** — evidence map entries, theme map entries, contradiction map entries relevant to the question
2. **Book Bible** — chapter plans that touch on the topic, intellectual journey arc, mystery architecture
3. **Existing drafts** — passages in drafted chapters that address related ideas
4. **Book-specific skill** — author context, anecdotes, terminology that bears on the question
5. **External knowledge** — broader academic and intellectual context beyond the local materials

Do not present this context dump to the author. Use it silently to inform the exploration.

### Step 3: Follow the Thread

This is the core of the workflow. Follow the intellectual thread wherever it leads, using the evidence base as grounding. The goal is to generate new understanding, not to confirm existing plans.

**Modes of exploration:**

#### 3a: Connection Mapping

When the question is about how two or more ideas relate:

- Trace each idea through the evidence base independently
- Identify where they intersect, contradict, or illuminate each other
- Look for structural parallels (do they follow similar patterns for different reasons?)
- Look for causal links (does one create the conditions for the other?)
- Look for shared root causes (are they symptoms of the same underlying problem?)
- Consider whether the connection strengthens, complicates, or challenges the book's thesis

#### 3b: Hypothesis Testing

When the question is "what if":

- State the hypothesis clearly
- Marshal evidence for it from the Research Digest and broader knowledge
- Marshal evidence against it
- Identify what evidence would be needed to resolve the question
- Assess whether the hypothesis, if true, would change the book's argument or structure

#### 3c: Implication Tracing

When the question is about consequences or implications:

- Start from the established finding or argument
- Trace first-order implications (direct consequences)
- Trace second-order implications (consequences of consequences)
- Identify which implications are supported by evidence and which are speculative
- Assess which implications belong in the book and which are outside its scope

#### 3d: Deep Dive

When the question is about deepening understanding of a single concept:

- Survey what the Research Digest contains on this topic
- Identify what the broader academic and intellectual literature says
- Trace the concept's history and evolution
- Identify competing definitions or frameworks
- Assess how the concept functions in the book's argument versus how it functions in the broader field

### Step 4: Surface Surprises

The most valuable output of exploration is the unexpected. After following the thread, explicitly identify:

```
SURPRISES:
  1. [Something the exploration revealed that was not anticipated]
  2. [A connection that was not in the Book Bible]
  3. [A contradiction that needs resolving]
  ...
```

If the exploration produced no surprises, it may have been too shallow. Consider whether the question needs to be reframed or whether a deeper dive into specific evidence is needed.

### Step 5: Assess Impact

Evaluate what the exploration means for the book:

```
IMPACT ASSESSMENT:

Book Bible:
  - [Does the thesis need refinement?]
  - [Does the intellectual journey arc need adjustment?]
  - [Do any chapter plans need updating?]

Specific chapters:
  - Chapter [N]: [How does this affect the chapter's argument, evidence, or structure?]
  - Chapter [N]: [How does this affect the chapter?]

Mystery architecture:
  - [Does this change what should be revealed when?]

Evidence gaps:
  - [What new evidence would the book need to support the exploration's findings?]
  - [Suggested search terms or source types for filling gaps]

New questions:
  - [What new questions did this exploration raise?]
```

### Step 6: Produce Exploration Notes

Write a concise exploration note. This is the durable output — it captures what was discovered so it can inform future work.

```markdown
# Exploration: [Title]

Date: [date]
Question: [the question explored]

## Thread

[A concise narrative of the exploration: what was examined, what was found, how the thinking evolved. This is prose, not bullet points — it should read as a record of intellectual work.]

## Key Findings

1. [Finding with evidence source]
2. [Finding with evidence source]
...

## Surprises

1. [Unexpected discovery]
...

## Implications for the Book

### Thesis
[Any refinements or complications]

### Chapters Affected
- Chapter [N]: [specific implication]
...

### New Evidence Needed
- [Gap and suggested approach to fill it]

### New Questions
- [Questions raised for future exploration or research]

## Suggested Next Steps

1. [Most valuable follow-up action]
2. [Second action]
```

Save to `/mnt/ValuesWork/notes/exploration-[slug].md` if the author wants to preserve it.

### Step 7: Recommend Next Action

Based on what the exploration found:

- If the exploration suggests Bible changes --> recommend **UpdateFromResearch** (or a targeted Bible update)
- If the exploration identified evidence gaps --> recommend **deep-research** skill or **IngestResearch** after adding new materials
- If the exploration clarified an argument for a specific chapter --> recommend **WriteChapter** (if undrafted) or **Revise** (if drafted)
- If the exploration raised new questions --> recommend another **Explore** session
- If the exploration confirmed existing plans --> note this and recommend proceeding with the next planned workflow

## Usage Patterns

### Before Writing

Explore is valuable between BuildBible and WriteChapter. The Bible maps what each chapter should do; Explore lets the author think through *how* — testing arguments, finding the right angle of approach, discovering which evidence is most compelling.

### Between Chapters

After drafting a chapter, Explore can help the author process what they learned from writing it. Writing often reveals new connections and complications that were not visible in the plan.

### After New Research

After IngestResearch surfaces new evidence, Explore lets the author think through what it means before committing to Bible updates or revisions. This prevents premature structural changes driven by surface-level reactions to new material.

### When Stuck

If a chapter is not working, Explore can help diagnose why. The problem may not be in the prose but in the underlying argument, evidence base, or structural positioning.

## Tone

Exploration should feel like a conversation between intellectual equals. The agent brings the evidence base, broader knowledge, and structural awareness. The author brings domain expertise, personal experience, and editorial judgment. Neither defers to the other. The goal is insight, not agreement.

Challenge assumptions. Follow evidence even when it complicates the plan. Flag when the book's current structure may not be serving the argument. But always ground the exploration in evidence, not speculation.
