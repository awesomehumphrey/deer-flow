# Interview Workflow

Extract the author's vision, research material, and preferences into structured input for the Book Bible.

## Purpose

This is the entry point for authors who have a subject, research, or ideas ranging from a rough concept to years of accumulated material, but need help structuring them into a layered narrative plan.

## Procedure

### Step 1: Consume Available Input

If the author has provided content (existing drafts, research notes, paper outlines, interview transcripts, datasets), read ALL of it first. Also consider relevant external literature and context that may inform the interview questions.

Extract and categorise everything into the seven layers:

- **Meaning signals:** What thesis or argument is present or implied?
- **Intellectual Journey signals:** What questions is the author trying to answer? What assumptions started with?
- **Narrative Thread signals:** What sequence of topics or findings exists?
- **Mystery signals:** What questions does the subject raise? What is still unknown?
- **Landscape signals:** What context, industry, institutions, or history are relevant?
- **Relationship signals:** What connections between people, ideas, or institutions exist?
- **Prose signals:** What voice or style does the author seem to favour?

### Step 2: Assess Completeness

For each layer, rate completeness on a scale:

- **Rich** (60%+ fleshed out): The author has clear vision here
- **Partial** (20-60%): Some material but gaps remain
- **Sparse** (< 20%): Almost empty, needs significant development
- **Empty**: No signal at all

### Step 3: Interview for Missing Layers

Use AskUserQuestion to fill gaps. Interview in this priority order:

**Priority 1: Intellectual Journey (if not rich)**
```
Questions to ask:
- "What made you start looking into this subject?"
- "What did you believe about this topic before you began your research?"
- "What surprised you most in the research?"
- "How has your understanding changed from the start to now?"
```

**Priority 2: Meaning (if not rich)**
```
Questions to ask:
- "What is the single most important thing you want readers to understand by the end?"
- "If someone asked 'what is this book about?' and you couldn't mention the subject, what would you say?"
- "What should readers do or think differently after reading?"
```

**Priority 3: Narrative Thread (if not rich)**
```
Questions to ask:
- "What's the first thing that hooked you into this subject?"
- "How would you explain the subject to a friend over coffee?"
- "What's the central puzzle or question driving the book?"
```

**Priority 4: Evidence (if not rich)**
```
Questions to ask:
- "What sources, data, or interviews are you drawing from?"
- "Are there specific studies, documents, or people that are central to your argument?"
- "What's your access like? Are there sources you wish you could reach?"
```

**Priority 5: Landscape (if sparse/empty)**
```
Questions to ask:
- "What institutional, historical, or economic context is essential to understand?"
- "Are there competing perspectives or schools of thought on this subject?"
- "What has changed over time that the reader needs to understand?"
```

**Priority 6: Relationships (if sparse/empty)**
```
Questions to ask:
- "Who are the key people in this story? Researchers, affected users, corporate actors, policymakers?"
- "Are there particular organisations or institutions at the centre?"
- "What's your relationship to the subject? Personal, professional, academic?"
```

**Priority 7: Prose/Aesthetic (if sparse/empty)**
```
Questions to ask:
- "What non-fiction writers do you admire? Whose style would you want this to feel like?"
- "Should this be serious and urgent, or more measured and curious?"
- "How long do you envision this being? Essay, short book, major work?"
```

### Step 4: Favourite Books Analysis

Ask the author:
```
"What are your 3-5 favourite non-fiction books?
For each: what specifically did you love about them?"
```

Analyse their answers to extract:
- Aesthetic preferences (what kind of prose they respond to)
- Structural preferences (do they like linear narratives? thematic compilations? case studies?)
- Emotional targets (do they want anger? hope? alarm? understanding?)
- Thematic interests (what kinds of arguments resonate with them)

### Step 5: Ideal Reader Experience

Ask directly:
```
"Imagine someone finishes reading your book. What do you want them to feel?
Would they be alarmed? Hopeful? Equipped to take action? Changed in their thinking?
Describe the IDEAL reader reaction."
```

This answer becomes a critical verification criterion.

### Step 6: Scope Assessment

Based on everything gathered, assess scope:

| Scope | Length | Layers Detail |
|-------|--------|-------------|
| **Essay** | 5,000-20,000 words | Focused: 2-3 layers primary |
| **Short book** | 20,000-50,000 words | 3-4 layers active |
| **Major work** | 50,000-100,000 words | All 7 layers active |
| **Multi-part** | 100,000+ words | All 7 layers deep with series arcs |

Use AskUserQuestion to confirm scope with the author.

### Step 7: Compile Structured Output

Create a structured summary organised by layer:

```markdown
# Book Concept: [Working Title]

## Scope: [Essay / Short book / Major work / Multi-part]
## Aesthetic: [Primary profile + any blending]

## Layer 1: Meaning
[Everything extracted about thesis and argument]

## Layer 2: Intellectual Journey
### Author's Starting Point
[What the author believed before research]

### Research Question
[The central question driving the book]

### Evolution
[How understanding has changed through research]

## Layer 3: Narrative Thread
[Known sequence of topics, findings, or chapters]

## Layer 4: Mystery
[Known questions, unresolved gaps, what the reader will learn]

## Layer 5: Landscape
[Institutional, historical, economic context]

## Layer 6: Relationships
[Key people, organisations, institutions]

## Layer 7: Prose
[Style preferences, aesthetic profile, voice]

## Ideal Reader Experience
[What the reader should feel or do after reading]

## Favourite Books Analysis
[What the author's favourites tell us about their taste]
```

### Step 8: Handoff

Output the structured summary and recommend next step:

- If enough detail exists for chapter mapping → recommend **BuildBible** workflow
- If the author wants to explore ideas further → recommend **Explore** workflow
- If they want to start writing immediately from what exists → recommend **WriteChapter** workflow

Store the structured output as the foundation for the Book Bible PRD.
