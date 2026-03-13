---
name: narrative-nonfiction
description: Layered narrative non-fiction writing system adapted from WriteStory. Constructs books across seven simultaneous narrative dimensions powered by Will Storr's storytelling science and Mark Forsyth's rhetorical figures, adapted for non-fiction argument, evidence, and authorial voice. Modelled on books like The Age of Surveillance Capitalism and The Alignment Problem. Load alongside domain-specific book skills.
---

# Narrative Non-Fiction Writing Skill

## Overview

A layered writing system for narrative non-fiction, adapted from WriteStory (Daniel Miessler). Constructs books across seven simultaneous narrative dimensions, powered by Will Storr's *The Science of Storytelling* and Mark Forsyth's *The Elements of Eloquence*, adapted for non-fiction argument, research narrative, and authorial voice.

## Workflow Routing

Route to the appropriate workflow based on the request.

| Workflow | Trigger | File |
| --- | --- | --- |
| **Interview** | "interview me", "extract my ideas", "help me plan the book" | `Workflows/Interview.md` |
| **BuildBible** | "build book plan", "create book bible", "map the chapters" | `Workflows/BuildBible.md` |
| **Explore** | "explore ideas", "brainstorm", "what if", "find angles" | `Workflows/Explore.md` |
| **WriteChapter** | "write chapter", "draft", "write prose" | `Workflows/WriteChapter.md` |
| **Revise** | "revise", "edit", "improve", "polish", "rewrite" | `Workflows/Revise.md` |

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

## Quick Reference

- **Theoretical Foundation:** Storr (narrative science) + Forsyth (rhetoric) + non-fiction structural frameworks
- **Book Bible:** PRD-based plan mapping all 7 layers chapter by chapter
- **Anti-Cliché:** Built-in freshness system bans generic AI patterns and non-fiction-specific dead prose
- **Aesthetic:** Configurable per project (Zuboff, Christian, O'Neil, Gladwell, Lewis, etc.)
- **Scale:** Essay to multi-part book series
