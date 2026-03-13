---
name: human-values-book
description: Custom skill for writing "Human Values in Software" by Dr. Humphrey O. Obie. Contains book structure, research context, citation guidelines, and chapter-specific instructions. Load this skill when working on any aspect of the book.
---

# Human Values in Software - Book Writing Skill

## Overview

This skill provides context and guidelines for writing "Human Values in Software" - a narrative non-fiction book in the style of *The Age of Surveillance Capitalism* (Shoshana Zuboff) or *The Alignment Problem* (Brian Christian), about how software systems violate human values and how we can detect and prevent these violations.

## Language

Write in **British English** throughout (e.g., "behaviour" not "behavior", "recognise" not "recognize", "licence" not "license").

Do **not** use em-dashes (—). Use commas, semicolons, colons, or restructure the sentence instead.

## Author Context

**Dr. Humphrey O. Obie** - Research focusing on:
- Human values in software engineering
- Automated detection of values violations (honesty, transparency, integrity)
- Developer experience with values violations
- Leading values work at HumaniSE Lab — first to carry out concrete implementation and automated detection of values violations in software

### Personal Anecdotes & Stories to Weave In

These are real experiences to draw on for narrative hooks and chapter openings:

1. **RMIT terms and conditions**: Personal experience with RMIT's terms and conditions during recruitment — link to relevant *Black Mirror* episode as a cultural hook on how institutions embed values violations into legal language users never read.

2. **Student privacy policy task**: Giving students the task of developing software to flag issues in privacy policies — use as an illustration of how values violations can be taught, detected, and made visible.

3. **AIware presentation in South Korea**: Presenting at AIware in South Korea to an audience that looked quizzically, seemingly not understanding the issues or their importance — or perhaps they were tired, as the talk was one of the last. Reference the AIware 2025 paper. Use as a reflection on the challenge of communicating values alignment to a technical audience.

4. **Herekind**: Work being done at Herekind — a bereavement concierge service — as a concrete example of building software that respects human values in a deeply sensitive, high-stakes context.

5. **GrapheneOS**: GrapheneOS upholding values (e.g., autonomy, privacy) that mainstream operating systems are violating at will — and the security implications. Use as a case study of values-aligned software done right.

## CV / Bio

Include author's CV and biographical information from `/mnt/ValuesWork/bio/` when writing author notes, preface, or back matter. Frame the research journey as a narrative arc throughout the book.

## Source Materials Location

All research materials are mounted at `/mnt/ValuesWork/`:
```
/mnt/ValuesWork/
├── papers/       ← Academic papers, your publications, OVIS lab papers
├── interviews/   ← Developer interviews, user studies
├── notes/        ← Research notes, ideas
├── data/         ← Datasets, analysis results
├── drafts/       ← OUTPUT: Write chapters here
├── bio/          ← CV and biographical information
├── grants/       ← DECRA, John's DP20, FLOSS ICSE proposal and report
└── highlights/   ← Reading highlights: The Alignment Problem, 2084, Brian Christian
```

## Book Structure

### Core Thesis

Software systems routinely violate human values — values that are deeply human, historically grounded, and well theorised. These violations cause real harm to users. Through systematic research and automated detection, we can identify these violations and build a more value-aligned future. Crucially, software values alignment is a distinct problem from AI alignment — the former is pervasive, under-researched, and already affecting billions of people through the apps and systems they use daily.

### Target Audience
- Tech-literate general readers (like readers of Zuboff, Brian Christian, Cathy O'Neil)
- Software developers and product managers
- Policy makers interested in tech ethics
- Academics in adjacent fields

### Proposed Chapters

**Introduction**
- Frame the book's purpose and personal narrative
- Establish the intellectual history of human values: Rokeach (terminal vs. instrumental values), Schwartz (universal values model), and older philosophical traditions (Aristotle, Kant, Mill)
- Distinguish software values alignment from AI alignment: the former is happening *now*, at scale, to billions of users; the latter is largely future-facing — conflating them obscures the urgency
- Set the tone and voice of the book

**Part I: The Problem**
1. **Dark Patterns at Scale** - The industry of manipulation
   - Opens with the world the general reader already inhabits — apps they use daily, patterns they've felt but couldn't name. Establishes the scale and normalisation of deception before introducing research evidence. References Brignull's dark patterns taxonomy, EU regulation, and industry-wide behaviour.

2. **The Honesty Gap** - How apps deceive users
   - Brings in the empirical research as rigorous evidence behind what Ch. 1 has already made the reader feel. Your detection methodology and findings now land with weight rather than having to hook a cold general audience alone.

**Part II: The Human Cost**

3. **The Inclusion Gap** - Who gets left behind

4. **Trust Betrayed** - When software lies

**Part III: The Developer's Dilemma**

5. **Building Under Pressure** - Why developers ship violations

6. **The Security Connection** - Values violations as attack vectors

**Part IV: Toward Solutions**

7. **Automated Detection** - Teaching machines to find violations

8. **A Value-Aligned Future** - What comes next

**Epilogue**
- Closing reflections on the journey
- A call to action for developers, policymakers, and users

## Writing Style Guide

### Voice
- **Curious and investigative** - following the research journey
- **Accessible but rigorous** - explain technical concepts clearly
- **Personal where appropriate** - your research journey matters
- **Respectful of users' experiences** - their stories are central
- Modelled on *The Age of Surveillance Capitalism* and *The Alignment Problem* in terms of depth, ambition, and narrative rigour

### Structure Per Chapter
1. **Opening scene** - A concrete moment or person
2. **The question** - What are we trying to understand?
3. **The investigation** - Research journey, methods, findings
4. **Technical core** - Key concepts explained accessibly
5. **Human impact** - Back to real people and consequences
6. **Implications** - So what? What should change?

### Citation Approach
- Integrate citations naturally into prose
- Use footnotes/endnotes for academic references
- Maintain a master bibliography
- When citing your own work, frame as discovery narrative

## Chapter Writing Workflow

When asked to write a chapter:

1. **Read relevant sources** from `/mnt/ValuesWork/papers/` and `/mnt/ValuesWork/notes/`
2. **Load complementary skills**: `narrative-nonfiction`, `deep-research`, `writing-skills`, `doc-coauthoring`
3. **Draft to** `/mnt/ValuesWork/drafts/chapter-XX-title.md`
4. **Include**: Opening scene, research narrative, technical explanation, human stories, implications
5. **End with**: Transition to next chapter's themes

## Key Research to Reference

### Dr. Obie's Publications (cite throughout)
- "Automated detection, categorisation and developers' experience with violations of honesty in mobile apps" (Empirical Software Engineering, 2023)
- "A Vision for Value-Aligned AI-Driven Systems" (AIware 2025)
- "ChroniUXMag: A Persona-Driven Framework for Inclusive mHealth Requirements Engineering"
- Stack Overflow analysis of values violations
- Android API investigation linking values violations to security

### Grant Documents (provide research framing and scope)
- Dr. Obie's DECRA application — load from `/mnt/ValuesWork/grants/`
- John's DP20 — load from `/mnt/ValuesWork/grants/`
- FLOSS ICSE proposal and report — load from `/mnt/ValuesWork/grants/`

### OVIS Lab Papers
- Include relevant papers by members of the OVIS lab — load from `/mnt/ValuesWork/papers/`

### Key Reading Highlights (for intertextual references)
- Brian Christian, *The Alignment Problem* — highlights at `/mnt/ValuesWork/highlights/`
- John Lennox, *2084* — highlights at `/mnt/ValuesWork/highlights/`
- Brian Christian (other works) — highlights at `/mnt/ValuesWork/highlights/`

## Terminology Consistency

| Term | Definition | Use |
|------|------------|-----|
| Values violations | Actions by software that conflict with human values | Primary term |
| Human values | Honesty, transparency, integrity, inclusivity, autonomy, etc. | Define early using Schwartz/Rokeach, use throughout |
| Dark patterns | Deceptive UI design | Use when discussing industry |
| Value-aligned | Software that respects human values | For solutions sections |
| Software values alignment | Ensuring software systems respect user values | Distinguish clearly from AI alignment |

## Output Format

When writing chapters, save as Markdown:
```
# Chapter N: Title

## Opening

[Scene or hook]

## [Section Title]

[Content]

---

### Notes
- Sources used: [list]
- Questions for author: [list]
- Gaps to fill: [list]
```

## Quick Commands

- "Analyse the research materials" → Scan `/mnt/ValuesWork/`, read all documents, produce a Research Digest mapping evidence to chapters
- "Update the book from the research" → Take the Research Digest and update the Book Bible and existing chapter drafts
- "I've added new papers, process them" → Incrementally ingest only new/changed files and update the digest
- "Write Chapter 1 outline" → Produce detailed outline with sources needed
- "Draft Chapter 1 opening" → Write the hook/opening scene
- "Integrate [paper] into Chapter X" → Weave research into narrative
- "Review draft for consistency" → Check against book style guide
- "Suggest examples for [concept]" → Find concrete illustrations
