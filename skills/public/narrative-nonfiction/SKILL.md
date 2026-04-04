---
name: narrative-nonfiction
description: Layered narrative non-fiction writing system adapted from WriteStory. Constructs books across seven simultaneous narrative dimensions powered by Will Storr's storytelling science and Mark Forsyth's rhetorical figures, adapted for non-fiction argument, evidence, and authorial voice. Seven workflows cover the full cycle from research ingestion through exploration, planning, composition, and revision. Modelled on books like The Age of Surveillance Capitalism and The Alignment Problem. Load alongside domain-specific book skills.
---

# Narrative Non-Fiction Writing Skill

## Overview

A layered writing system for narrative non-fiction, adapted from WriteStory (Daniel Miessler). Constructs books across seven simultaneous narrative dimensions, powered by Will Storr's *The Science of Storytelling* and Mark Forsyth's *The Elements of Eloquence*, adapted for non-fiction argument, research narrative, and authorial voice.

## Workflow Routing

Route to the appropriate workflow based on the request.

| Workflow | Trigger | File |
| --- | --- | --- |
| **IngestResearch** | "analyse the research", "ingest documents", "read the papers", "scan my materials" | `Workflows/IngestResearch.md` |
| **Interview** | "interview me", "extract my ideas", "help me plan the book" | `Workflows/Interview.md` |
| **Explore** | "explore", "what if", "think through", "how does X relate to Y", "brainstorm", "implications of" | `Workflows/Explore.md` |
| **BuildBible** | "build book plan", "create book bible", "map the chapters" | `Workflows/BuildBible.md` |
| **UpdateFromResearch** | "update the book from research", "revise bible from materials", "incorporate research", "sync book with research" | `Workflows/UpdateFromResearch.md` |
| **WriteChapter** | "write chapter", "draft", "write prose" | `Workflows/WriteChapter.md` |
| **Revise** | "revise", "fix", "strengthen", "integrate X into", "apply revision brief", "polish", "improve", "tighten" | `Workflows/Revise.md` |

**Distinguishing WriteChapter from Revise:** WriteChapter is for initial composition — building a chapter from the Book Bible when no draft exists. Revise is for targeted changes to an existing draft, whether driven by critic feedback, revision briefs from UpdateFromResearch, new evidence, or author directives. If a revision escalates to a fundamental rewrite (e.g., the chapter's core argument is changing), switch to WriteChapter.

## Author Queries

Narrative non-fiction depends on the author's personal experience, memories, and knowledge. The Interview workflow is the primary extraction point, but it is not the only one. **Any workflow may pause to ask the author for input** when it encounters a need that only the author can fill.

Pause and ask the author when:

1. **A personal anecdote would strengthen a passage.** If a section is abstract, analytical, or lacking a human hook, and the author's experience might provide one, ask: "Do you have a personal experience related to [topic]? This section would benefit from a concrete story."
2. **A fact needs verification.** If the text references a specific event from the author's life (a presentation, a conversation, a teaching moment), verify the details: "You mention the AIware presentation in South Korea. Was it the last talk of the session? Roughly how many people were in the room?"
3. **A chapter opening needs a scene.** The best non-fiction chapters open with concrete moments. If the Book Bible specifies a personal opening but the details are thin, ask for them before writing.
4. **A relationship or interaction needs specifics.** If the text discusses a collaboration, a disagreement, or a turning point in the author's research journey, ask for the human details that make it vivid.
5. **The author's opinion or judgment is needed.** When the evidence supports multiple interpretations and the book needs the author to take a position, ask rather than assume.

**How to ask:** Be specific. "Do you have any stories about X?" is too vague. "In your experience teaching the privacy policy task to students, did any student reaction surprise you? What did they say or do?" is concrete enough to get a useful answer.

**When NOT to ask:** Do not pause for information that can be found in the Research Digest, the Book Bible, or through the `deep-research` skill. Only ask the author for things only the author knows: personal experiences, opinions, memories, and unpublished details.

## The Seven Narrative Layers

Every chapter and the book as a whole is constructed across seven simultaneous layers. See `NarrativeLayers.md` for full definitions and mapping templates.

1. **Meaning** — Core thesis, philosophical argument, the "so what" for the reader
2. **Intellectual Journey** — The author's evolving understanding; questions that drove the research and how answers changed thinking
3. **Narrative Thread** — The cause-and-effect chain connecting chapters; what propels the reader forward
4. **Mystery** — Information management: what the reader does not yet know, how revelation is sequenced
5. **Landscape** — The world being described: industry dynamics, social context, institutional forces
6. **Relationships** — Between author and subject, between ideas across chapters, between the people whose stories are told
7. **Prose** — Rhetorical figures, sentence rhythm, voice, register, and style

## Core References

| Reference | File | Purpose |
| --- | --- | --- |
| Layer Architecture | `NarrativeLayers.md` | Seven-layer system adapted for non-fiction |
| Intellectual Journey Framework | `IntellectualJourneyFramework.md` | Storr's framework adapted: research arc, revelation management, reader curiosity |
| Rhetorical Figures | `RhetoricalFigures.md` | Full 125-figure catalogue (identical to fiction — directly applicable) |
| Anti-Cliché System | `AntiCliche.md` | Freshness enforcement adapted for non-fiction prose patterns |
| Non-Fiction Structures | `NonfictionStructures.md` | Book-level and chapter-level structural frameworks |
| Aesthetic Profiles | `AestheticProfiles.md` | Voice profiles modelled on landmark non-fiction writers |
| Critic Profiles | `Critics.md` | Multi-pass review system adapted for non-fiction |
| Bibliography Management | `Bibliography.md` | BibTeX conventions, citation style, reference workflow |

## Quick Reference

- **Theoretical Foundation:** Storr (narrative science) + Forsyth (rhetoric) + non-fiction structural frameworks
- **Book Bible:** PRD-based plan mapping all 7 layers chapter by chapter
- **Anti-Cliché:** Built-in freshness system bans generic AI patterns and non-fiction-specific dead prose
- **Aesthetic:** Configurable per project (Zuboff, Christian, O'Neil, Gladwell, Lewis, etc.)
- **Scale:** Essay to multi-part book series
- **Seven workflows:** IngestResearch, Interview, Explore, BuildBible, UpdateFromResearch, WriteChapter, Revise
