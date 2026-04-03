---
name: human-values-book
description: Custom skill for writing "Human Values in Software" by Dr. Humphrey O. Obie. Contains book structure, research context, aesthetic configuration, and chapter-specific instructions. Load this skill alongside narrative-nonfiction when working on any aspect of the book.
---

# Human Values in Software

## Overview

This skill provides the domain context for writing "Human Values in Software", a narrative non-fiction book about how software systems violate human values and how we can detect and prevent these violations. The writing methodology, layer system, and workflows come from the `narrative-nonfiction` skill; this file provides what is specific to _this_ book.

**Companion skill:** `narrative-nonfiction` (must be loaded alongside this skill for all writing work)

## Language Rules

These rules apply to all book output (chapter prose, exploration notes, revision briefs, the Book Bible, the Research Digest) and to book-specific documentation (this file, GETTING-STARTED.md).

Write in **British English** throughout: "behaviour" not "behavior", "recognise" not "recognize", "licence" not "license", "analyse" not "analyze".

Do **not** use em-dashes. Use commas, semicolons, colons, or restructure the sentence instead.

## Author Context

**Dr. Humphrey O. Obie**, research focusing on:

- Human values in software engineering
- Automated detection of values violations (honesty, transparency, integrity)
- Developer experience with values violations
- Former member of HumaniSE Lab; close collaborator with OVIS Lab (whose members include friends and co-authors)
- First to carry out concrete implementation and automated detection of values violations in software

### Personal Anecdotes and Stories to Weave In

These are real experiences to draw on for narrative hooks and chapter openings. More will emerge from the Interview workflow; the list below is a starting set, not exhaustive.

1. **RMIT terms and conditions**: Personal experience with RMIT's terms and conditions during recruitment. Link to relevant _Black Mirror_ episode as a cultural hook on how institutions embed values violations into legal language users never read.

2. **Student privacy policy task**: Giving students the task of developing software to flag issues in privacy policies. Use as an illustration of how values violations can be taught, detected, and made visible.

3. **AIware presentation in South Korea**: Presenting at AIware in South Korea to an audience that looked quizzically, seemingly not understanding the issues or their importance (or perhaps they were tired, as the talk was one of the last). Reference the AIware 2025 paper. Use as a reflection on the challenge of communicating values alignment to a technical audience.

4. **Herekind**: Work being done at Herekind, a bereavement concierge service, as a concrete example of building software that respects human values in a deeply sensitive, high-stakes context.

5. **GrapheneOS**: GrapheneOS upholding values (e.g., autonomy, privacy) that mainstream operating systems are violating at will, and the security implications. Use as a case study of values-aligned software done right.

### CV and Bio

Include your CV and biographical information from `/mnt/ValuesWork/bio/` when writing author notes, preface, or back matter. Frame your research journey as a narrative arc throughout the book.

## Source Materials

Your personal research materials are mounted at `/mnt/ValuesWork/`. This folder provides the grounding for the book: your own publications, interviews, grants, reading highlights, and lived experience. It is **not** the limit of the book's research scope. Use the **`deep-research`** skill to conduct web research, search academic literature, and find external sources appropriate to a serious academic trade book. Think of ValuesWork as the personal foundation; the broader intellectual landscape is built on top of it using `deep-research`.

```
/mnt/ValuesWork/
├── papers/       ← Your publications, OVIS lab papers, cited works
├── interviews/   ← Developer interviews, user studies
├── notes/        ← Research notes, ideas, Research Digest output
├── data/         ← Datasets, analysis results
├── drafts/       ← OUTPUT: Chapter drafts written here
├── bio/          ← CV and biographical information
├── grants/       ← DECRA, John's DP20, FLOSS ICSE proposal and report
└── highlights/   ← Reading highlights: The Alignment Problem, 2084, Brian Christian
```

## Aesthetic Profile

This book uses a **blended aesthetic profile** (see `narrative-nonfiction/AestheticProfiles.md`):

```
Profile: 60% Zuboff + 40% Christian
```

- **Zuboff (dominant):** Systematic institutional analysis with moral urgency. Long, architecturally complex sentences that mirror the systems described. Chapters build like legal briefs: evidence, analysis, implication.
- **Christian (secondary):** Genuine curiosity and accessibility. Conversations presented as dialogues. Analogies from unexpected domains. The author is present as a curious guide, not just an authority.

**Rhetorical figure emphasis:** Anaphora, Amplificatio, Antithesis, Periodic Sentence, Analogy, Paradox, Chiasmus
**Sentence length:** Variable; long (20-40 words) for systems analysis, medium (12-25 words) for human stories
**Pacing:** Deliberate and cumulative, with brisk narrative passages for human stories

## Core Thesis

Software systems routinely violate human values: values that are deeply human, historically grounded, and well theorised. These violations cause real harm to users. Through systematic research and automated detection, we can identify these violations and build a more value-aligned future.

Crucially, software values alignment is a distinct problem from AI alignment. The former is pervasive, under-researched, and already affecting billions of people through the apps and systems they use daily. The latter is largely future-facing. Conflating them obscures the urgency.

## Target Audience

- Tech-literate general readers (like readers of Zuboff, Brian Christian, Cathy O'Neil)
- Software developers and product managers
- Policy makers interested in tech ethics
- Academics in adjacent fields

## The Seven Narrative Layers

Every chapter is constructed across seven simultaneous layers (see `narrative-nonfiction/NarrativeLayers.md` for full definitions):

1. **Meaning** : What thesis element does this chapter advance?
2. **Intellectual Journey** : What do you learn or revise here?
3. **Narrative Thread** : What question does this chapter answer? What new question does it raise?
4. **Mystery** : What information is revealed? What is withheld?
5. **Landscape** : What context is established or deepened?
6. **Relationships** : Which connections between people, ideas, or institutions are explored?
7. **Prose** : What register and rhetorical emphasis?

Every chapter must advance at least 3 layers. The Intellectual Journey (your evolving understanding) is the primary engine.

## Proposed Chapters

> **PROVISIONAL:** The chapter structure below is a rough scaffold based on paper titles and early conversations. It has NOT been validated against the actual research materials. Once the research documents are added to `/mnt/ValuesWork/` and analysed via the IngestResearch workflow, this entire section should be **rebuilt from the evidence**. The BuildBible and UpdateFromResearch workflows will replace this scaffold with a proper, research-grounded chapter map across all 7 narrative layers.

**Introduction**

- Frame the book's purpose and personal narrative
- Establish the intellectual history of human values: Rokeach (terminal vs. instrumental values), Schwartz (universal values model), and older philosophical traditions (Aristotle, Kant, Mill)
- Distinguish software values alignment from AI alignment
- Set the tone and voice of the book
- Write this LAST, after all other chapters are drafted

**Part I: The Problem**

1. **Dark Patterns at Scale**: The industry of manipulation. Opens with the world the general reader already inhabits: apps they use daily, patterns they have felt but could not name. Establishes the scale and normalisation of deception before introducing research evidence. References Brignull's dark patterns taxonomy, EU regulation, and industry-wide behaviour.

2. **The Honesty Gap**: How apps deceive users. Brings in the empirical research as rigorous evidence behind what Ch. 1 has already made the reader feel. Your detection methodology and findings now land with weight.

**Part II: The Human Cost** 3. **The Inclusion Gap**: Who gets left behind 4. **Trust Betrayed**: When software lies

**Part III: The Developer's Dilemma** 5. **Building Under Pressure**: Why developers ship violations 6. **The Security Connection**: Values violations as attack vectors

**Part IV: Toward Solutions** 7. **Automated Detection**: Teaching machines to find violations 8. **A Value-Aligned Future**: What comes next

**Epilogue**

- Closing reflections on the journey
- A call to action for developers, policymakers, and users

## Key Research to Reference

> **Note:** The specific publications listed below are known references from early conversations. The full list will be determined by the IngestResearch workflow after all materials are added. The Research Digest will provide the authoritative mapping of sources to chapters.

### Your Publications (cite throughout)

- "Automated detection, categorisation and developers' experience with violations of honesty in mobile apps" (Empirical Software Engineering, 2023)
- "A Vision for Value-Aligned AI-Driven Systems" (AIware 2025)
- "ChroniUXMag: A Persona-Driven Framework for Inclusive mHealth Requirements Engineering"
- Stack Overflow analysis of values violations
- Android API investigation linking values violations to security

### Grant Documents (provide research framing and scope)

- Your DECRA application
- John's DP20
- FLOSS ICSE proposal and report

### OVIS Lab Papers

- Include relevant papers by members of the OVIS lab (your collaborators)

### Key Reading Highlights (for intertextual references)

- Brian Christian, _The Alignment Problem_
- John Lennox, _2084_
- Brian Christian (other works)

## Terminology Consistency

| Term                      | Definition                                                    | Use                                                 |
| ------------------------- | ------------------------------------------------------------- | --------------------------------------------------- |
| Values violations         | Actions by software that conflict with human values           | Primary term throughout                             |
| Human values              | Honesty, transparency, integrity, inclusivity, autonomy, etc. | Define early using Schwartz/Rokeach, use throughout |
| Dark patterns             | Deceptive UI design                                           | Use when discussing industry practices              |
| Value-aligned             | Software that respects human values                           | For solutions sections                              |
| Software values alignment | Ensuring software systems respect user values                 | Distinguish clearly from AI alignment               |
| Initial assumption        | What the reader or author believed before the evidence        | Intellectual Journey Framework term                 |
| Research Digest           | Structured analysis of all ingested research materials        | Output of IngestResearch workflow                   |
| Book Bible                | Master plan mapping all 7 layers across all chapters          | Output of BuildBible workflow                       |

## Writing Workflow

The recommended sequence for writing this book:

1. **Add research materials** to `/mnt/ValuesWork/` subdirectories
2. **Ingest and analyse**: run IngestResearch to produce a Research Digest
3. **Interview**: extract your vision, thesis, and narrative priorities
4. **Explore** (optional): think through connections, test ideas, follow intellectual threads before committing to a plan
5. **Build Bible**: create the full chapter map grounded in the actual research evidence (replaces the provisional chapter scaffold above)
6. **Write chapters**: draft prose following the Book Bible, one chapter at a time (WriteChapter for initial composition)
7. **Revise**: apply critic feedback, integrate new evidence, polish prose (Revise for targeted changes to existing drafts)
8. **Iterate**: add more materials, re-ingest, explore implications, update the Bible, and revise drafts

The `narrative-nonfiction` skill provides the detailed workflows for each step. This skill provides the domain context those workflows need.

## Output Format

When writing chapters, save as Markdown to `/mnt/ValuesWork/drafts/chapter-NN-slug.md`:

```markdown
# Chapter N: Title

## Opening

[Concrete scene, person, or moment that hooks the reader]

## [Section Title]

[Prose: each section advances the chapter's argument through evidence,
narrative, and analysis. Every paragraph serves at least one of the 7 layers.
Sections correspond to the chapter plan in the Book Bible.]

## [Section Title]

[Continue as needed]

---

## Chapter Notes

### Layer Summary

| Layer                | What this chapter accomplished               |
| -------------------- | -------------------------------------------- |
| Meaning              | [Thesis element advanced]                    |
| Intellectual Journey | [What was learnt or revised]                 |
| Narrative Thread     | [Question answered; new question raised]     |
| Mystery              | [Information revealed; information withheld] |
| Landscape            | [Context established or deepened]            |
| Relationships        | [Connections explored]                       |
| Prose                | [Register, key rhetorical figures deployed]  |

### Critic Pass Summary

| Critic              | Confidence (1-5) | Key action taken |
| ------------------- | ---------------- | ---------------- |
| Layer Auditor       |                  |                  |
| Evidence Inspector  |                  |                  |
| Rhetoric Examiner   |                  |                  |
| Freshness Inspector |                  |                  |
| Reader Surrogate    |                  |                  |

### References Used

- `citationKey`: role in this chapter (e.g. primary evidence for Section 2)

### New BibTeX Entries

[Any entries added to references.bib during this chapter's writing]

### Book Bible Updates

[Any new connections, structural changes, or layer adjustments the Bible should reflect]

### Gaps and Open Questions

- [Evidence still missing]
- [Questions for you to resolve]
- [Suggested external research to fill gaps]

### Recommended Next Step

[Which chapter to write next, or which revision to undertake]
```

## Quick Commands

| What you want                  | What to type                                                                |
| ------------------------------ | --------------------------------------------------------------------------- |
| Analyse all research materials | "Analyse the research materials in the ValuesWork folder"                   |
| Process only new files         | "I have added new papers, process them"                                     |
| Plan the book (interview)      | "Interview me about my book Human Values in Software"                       |
| Explore an idea or connection  | "Explore the connection between dark patterns and security vulnerabilities" |
| Think through implications     | "What if software values alignment and AI alignment share a common root?"   |
| Create the master plan         | "Build the book bible based on our interview and the research digest"       |
| Update plan from new research  | "Update the book from the research"                                         |
| Write a chapter                | "Write chapter 3 following the book bible"                                  |
| Write just the opening         | "Draft the opening scene for chapter 1"                                     |
| Revise a chapter               | "Revise chapter 1 based on the critic feedback"                             |
| Integrate a specific paper     | "Integrate the AIware 2025 paper into chapter 7"                            |
| Polish prose                   | "Polish the prose in chapter 2, section 3"                                  |
| Check consistency              | "Review the draft of chapter 2 for consistency with the book bible"         |
| Brainstorm examples            | "Brainstorm concrete examples for the inclusion gap chapter"                |
