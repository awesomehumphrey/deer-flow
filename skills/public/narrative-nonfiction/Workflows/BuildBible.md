# BuildBible Workflow

Construct the comprehensive Book Bible: a PRD-based plan that maps the entire book across all seven layers from start to finish.

## Purpose

The Book Bible is the central artefact of the narrative-nonfiction skill. It IS the verification criteria for the book: a comprehensive, layered plan that becomes the reference for every chapter written. This transforms scattered research and ideas into a structured, writable narrative.

## Prerequisites

- Structured input from Interview workflow (or equivalent author-provided content)
- Read `NarrativeLayers.md` for layer definitions
- Read `IntellectualJourneyFramework.md` for research arc construction
- Read `NonfictionStructures.md` for structural scaffolding

## Procedure

### Step 1: Establish Book Parameters

From the Interview output or author input, confirm:

- **Scope:** Essay / Short book / Major work / Multi-part
- **Subject domain:** The topic area (tech, health, finance, etc.)
- **Aesthetic Profile:** From `AestheticProfiles.md`
- **Argument position:** What is the author's thesis? (stated early or developed gradually?)

### Step 2: Build the Intellectual Journey Architecture

Follow the framework in `IntellectualJourneyFramework.md`:

1. Define the initial assumption
2. Establish the author's starting point
3. Set the surface question
4. Set the deeper pattern
5. Define the thesis
6. Map the crisis point (where full scope becomes undeniable)
7. Choose the arc direction (synthesis, tragic, advocacy)
8. Design credibility dynamics
9. Plant mystery hooks
10. Connect to meaning

Create verification criteria for the overall arc:
```
TaskCreate: "ARC: Author transforms from [initial assumption] to [final thesis]"
TaskCreate: "ARC: Evidence builds from [early evidence] to [final synthesis]"
```

### Step 3: Map the Narrative Structure

Using the structures in `NonfictionStructures.md`, choose and adapt a book-level structure:

- Investigation Arc
- Discovery Narrative
- Portrait
- Thesis-Driven

For the chosen structure, map the chapters:

For EACH chapter:
1. What is this chapter's specific question?
2. What evidence or analysis does it present?
3. How does it connect to the previous chapter?
4. What question does it leave open for the next chapter?

Create verification criteria for major chapters:
```
TaskCreate: "CHAPTER-N: Chapter addresses [question] with [evidence type]"
TaskCreate: "CHAPTER-N: Chapter connects to [previous chapter] via [connection]"
```

### Step 4: Design the Mystery Architecture

Map information management across the narrative:

1. **Primary mystery:** What central question drives the whole book?
2. **Chapter mysteries:** What question does each chapter open with?
3. **Evidence plants:** What must be introduced early for later chapters?
4. **Misdirections:** What plausible explanations will later prove incomplete?
5. **Reveal cascade:** How do revelations build on each other?

For each mystery element, track:
- Introduction point
- Development points
- Resolution point
- Reader state at each point

### Step 5: Build the Landscape Framework

Map context elements needed for the book:

1. Institutional forces (companies, regulators, advocacy groups)
2. Historical developments (how we arrived at the present)
3. Economic incentives (what drives the behaviour being described)
4. Regulatory or legal frameworks
5. Geographical or cultural variations

**Rule:** Every landscape element must serve the argument. If removing it changes nothing, remove it.

### Step 6: Map Relationship Arcs

For each key relationship:

1. Author and subject: How does the author's relationship to the material evolve?
2. Between people: The researchers, affected users, corporate actors, policymakers
3. Between institutions: How do companies, regulators, and advocacy groups interact?
4. Author and reader: How does credibility build across the book?

### Step 7: Define Prose Strategy

Based on the Aesthetic Profile:

1. Which rhetorical figures to use at key moments
2. Sentence length and complexity patterns
3. Evidence integration style
4. Personal voice guidelines
5. Description density by section type

### Step 8: Assemble the Full Chapter Map

Now create the FULL chapter map: every chapter with ALL seven layers mapped.

```markdown
## Chapter Map

### Chapter 1: [Title]
- **MEANING:** What thesis element is advanced?
- **INTELLECTUAL JOURNEY:** What does the author learn or revise here?
- **NARRATIVE THREAD:** What question does this chapter answer? What new question does it raise?
- **MYSTERY:** What information is revealed? What is withheld?
- **LANDSCAPE:** What context is established or deepened?
- **RELATIONSHIPS:** Which connections between people, ideas, or institutions are explored?
- **PROSE:** What register and rhetorical emphasis?

### Chapter 2: [Title]
[same structure]

... [continue for all chapters]
```

### Step 9: Create the Book Bible PRD

Write the Book Bible as a PRD file:

**Location:** Project directory `.prd/` or similar

```markdown
---
prd: true
id: PRD-{YYYYMMDD}-{book-slug}
status: IN_PROGRESS
created: {date}
updated: {date}
iteration: 1
scope: [essay | short-book | major-work | multipart]
subject: [domain]
aesthetic: [profile name]
parent: null
children: []
---

# Book Bible: [Title]

> [One sentence: what this book is about thematically]

## STATUS
| What | State |
|------|-------|
| Progress | 0/{N} criteria passing |
| Scope | [scope] |
| Next action | [first writing action] |

## INTELLECTUAL JOURNEY ARCHITECTURE
[Full arc: initial assumption → crisis → synthesis]

## CHAPTER MAP
[Full chapter-by-chapter map with all 7 layers]

## MYSTERY ARCHITECTURE
[Information management timeline]

## LANDSCAPE FRAMEWORK
[Essential context elements]

## RELATIONSHIP ARCS
[Key relationship timelines]

## PROSE STRATEGY
[Aesthetic profile, figure deployment plan]

## CRITERIA
- [ ] C1: [First book criterion]
- [ ] C2: [Second book criterion]
... [all verification criteria]

## LOG
[Session entries]
```

### Step 10: Scale for Multi-Part Works (if applicable)

For multi-part books:

1. Create a PARENT PRD for the series
2. Create CHILD PRDs for each part
3. Map cross-part arcs (how the argument develops across volumes)
4. Track series-level mysteries and their per-part development
5. Ensure each part works as a satisfying standalone AND advances the series

### Step 11: Output and Next Steps

Present the Book Bible to the author with:

1. Summary of what has been mapped
2. Any gaps or decisions still needed
3. Recommendations for which chapter to write first
4. Option to run **Explore** workflow for any layer that needs creative development
5. Option to jump directly to **WriteChapter** for the strongest section

The Book Bible is now the living document that guides all writing.
