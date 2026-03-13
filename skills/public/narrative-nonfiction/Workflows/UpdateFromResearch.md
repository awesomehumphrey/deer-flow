# UpdateFromResearch Workflow

Take the Research Digest (from IngestResearch) and systematically update the Book Bible, chapter outlines, and existing chapter drafts to incorporate new evidence, arguments, and narrative material.

## Prerequisites

- Research Digest exists (from IngestResearch workflow)
- Book Bible exists (from BuildBible workflow)
- Read `NarrativeLayers.md` for layer definitions
- Read `Bibliography.md` for citation conventions
- Know which chapters already have drafts (check `/mnt/ValuesWork/drafts/`)

## Trigger Phrases

- "Update the book from the research"
- "Revise the bible based on the new materials"
- "Incorporate the research into the chapters"
- "Update chapters from analysed documents"
- "Sync the book with the research digest"

## Procedure

### Step 1: Load Current State

Read and hold in context:

1. **Research Digest** (from IngestResearch) — the evidence map, theme map, contradiction map
2. **Book Bible** — the current chapter map with all 7 layers
3. **Existing drafts** — list which chapters have been drafted

```bash
# Check for existing drafts
ls -la /mnt/ValuesWork/drafts/
```

Produce a status summary:

```
CURRENT STATE:
  Research Digest: [date generated, N sources]
  Book Bible: [date, version/iteration]
  Drafted chapters: [list with word counts]
  Undrafted chapters: [list]
```

### Step 2: Assess Impact per Chapter

For each chapter, compare the Research Digest evidence map against what the Book Bible currently specifies. Categorise the impact:

```
IMPACT ASSESSMENT:

Chapter [N]: [Title]
  Impact level: [HIGH / MEDIUM / LOW / NONE]
  New evidence:
    - [source] → [finding] → [how it changes or strengthens the chapter]
  New narrative material:
    - [source] → [scene/quote/story] → [where it fits]
  Argument changes:
    - [Does new evidence change the chapter's argument? Strengthen, nuance, or challenge it?]
  Structure changes:
    - [Does the chapter need new sections, reordering, or removal of sections?]
  Draft status:
    - [Not yet drafted / Drafted, needs revision / Drafted, no changes needed]
```

**Pause:** Present the impact assessment. Ask the author:
- Agree with the impact levels?
- Any chapters to prioritise or skip?
- Any new chapters or structural changes needed?

### Step 3: Update the Book Bible

Apply changes to the Book Bible, working through each of the 7 layers:

#### 3a: Update MEANING Layer

Review whether new research changes the book's thesis or any chapter's thematic work:
- Does new evidence strengthen or refine the core argument?
- Do any chapters need their meaning layer adjusted?
- Are there new implications the book should address?

#### 3b: Update INTELLECTUAL JOURNEY Layer

Review the author's research arc:
- Do new sources change the trajectory of discovery?
- Are there new "turning points" where understanding shifted?
- Does the crisis point need adjustment?

#### 3c: Update NARRATIVE THREAD Layer

Review cause-and-effect connections between chapters:
- Do new materials suggest reordering chapters?
- Are there new connections between chapters that should be made explicit?
- Do any chapter transitions need reworking?

#### 3d: Update MYSTERY Layer

Review information management:
- Do new findings change what should be revealed when?
- Are there new surprises or misdirections to plant?
- Does the reveal cascade need restructuring?

#### 3e: Update LANDSCAPE Layer

Review contextual elements:
- Do new sources add institutional, historical, or economic context?
- Are there new actors or forces to introduce?
- Does any context need updating or correcting?

#### 3f: Update RELATIONSHIPS Layer

Review connections:
- Do new interview or case study materials introduce new people or perspectives?
- Are there new institutional relationships to map?
- Does the author-subject relationship evolve differently with new evidence?

#### 3g: Update PROSE Layer

Review style implications:
- Do new materials suggest different rhetorical approaches for certain chapters?
- Are there powerful quotes that should anchor specific sections?
- Does the evidence density change the pacing plan?

#### 3h: Write the Updated Chapter Map

For each chapter that changed, rewrite its 7-layer specification:

```markdown
### Chapter [N]: [Title] [UPDATED]

Changes from previous version:
- [Change 1]
- [Change 2]

- **MEANING:** [updated if needed]
- **INTELLECTUAL JOURNEY:** [updated if needed]
- **NARRATIVE THREAD:** [updated if needed]
- **MYSTERY:** [updated if needed]
- **LANDSCAPE:** [updated if needed]
- **RELATIONSHIPS:** [updated if needed]
- **PROSE:** [updated if needed]

New evidence to incorporate:
- [source] → [role in chapter]

New narrative material:
- [source] → [where in chapter]
```

#### 3i: Update Book Bible Metadata

Update the Book Bible PRD header:

```markdown
updated: [today's date]
iteration: [increment by 1]
```

Add a LOG entry:

```markdown
## LOG
### [Date] — Research Integration Update
- Sources integrated: [N new sources]
- Chapters affected: [list]
- Major changes: [summary]
- New gaps identified: [if any]
```

### Step 4: Update Existing Chapter Drafts

For each chapter that has been drafted AND has HIGH or MEDIUM impact:

#### 4a: Produce a Revision Brief

Do not rewrite the chapter wholesale. Instead, produce a targeted revision brief:

```
REVISION BRIEF: Chapter [N]

ADDITIONS (new material to insert):
  1. Section [X]: Insert [evidence/quote/example] from [source]
     Location: After paragraph beginning "[first few words]..."
     Suggested text: [1-2 sentence preview of what to add]

  2. Section [Y]: Add new subsection on [topic]
     Location: Between sections [A] and [B]
     Content outline: [bullet points]

REVISIONS (existing text to change):
  1. Section [X], paragraph [N]: Update [claim] with new evidence from [source]
     Current text: "[first few words of paragraph]..."
     Issue: [why it needs changing]
     Suggested direction: [how to revise]

  2. Section [Y]: Strengthen argument by adding [counter-argument] and [rebuttal]
     Source: [citation]

REMOVALS (material to cut or relocate):
  1. Section [X]: [paragraph/sentence] is now superseded by [new evidence]
     Recommendation: [remove / move to chapter N / condense]

CITATION UPDATES:
  New citations to add: [list of BibTeX keys]
  Citations to update: [if any findings have been superseded]

STRUCTURAL CHANGES:
  [Any section reordering, new sections, or merged sections]
```

#### 4b: Apply Revisions (if requested)

If the author approves the revision brief, apply the changes using the **Revise** workflow:

1. Hand off the revision brief to the **Revise** workflow with the existing draft
2. Revise reads the draft, plans the changes, and applies them with scoped critic passes
3. This is more efficient than running the full WriteChapter process for targeted changes

Alternatively, if the author prefers to revise manually, save the revision brief alongside the draft:

```
/mnt/ValuesWork/drafts/chapter-01-dark-patterns.md           # existing draft
/mnt/ValuesWork/drafts/chapter-01-dark-patterns-revisions.md  # revision brief
```

### Step 5: Identify New Chapters or Structural Changes

Based on the full research integration, assess whether the book structure itself needs updating:

```
STRUCTURAL ASSESSMENT:

New chapters needed: [Y/N]
  If yes: [proposed chapter title, position, and justification]

Chapters to merge: [Y/N]
  If yes: [which chapters, why]

Chapters to split: [Y/N]
  If yes: [which chapter, how to split]

Reordering needed: [Y/N]
  If yes: [proposed new order, justification]

Parts reorganisation: [Y/N]
  If yes: [proposed new part structure]
```

**Pause:** Present structural recommendations to the author for approval before making changes.

### Step 6: Update Bibliography

Ensure all new sources from the Research Digest are in `references.bib`:

1. Read current `references.bib`
2. Compare against the Research Digest's new BibTeX entries
3. Add any missing entries
4. Verify no duplicate keys
5. Report what was added

### Step 7: Produce the Update Summary

Write a concise summary of all changes made:

```markdown
# Book Update Summary

Date: [date]
Research Digest: [date of digest used]
Sources integrated: [N]

## Book Bible Changes
- Iteration: [old] → [new]
- Chapters affected: [list with brief description of changes]
- Structural changes: [none / describe]

## Chapter Draft Revisions
- Chapter [N]: [revision brief produced / revisions applied / no changes needed]
- Chapter [N]: [status]
...

## Bibliography Updates
- New entries added: [N]
- Total entries: [N]

## Next Steps
1. [Most important next action]
2. [Second action]
3. [Third action]

## Outstanding Gaps
- [Any evidence still missing]
- [Any chapters still under-supported]
```

Save to `/mnt/ValuesWork/notes/update-summary-[date].md`.

### Step 8: Recommend Next Action

Based on the update, recommend the author's next step:

- If a chapter is now well-supported and undrafted --> **WriteChapter**
- If a drafted chapter needs targeted revision --> **Revise** with the revision brief as input
- If the update raised questions worth thinking through --> **Explore** to follow the intellectual thread before committing to changes
- If new research gaps were identified --> **deep-research** skill for targeted web research, or external literature review to fill gaps beyond the local materials
- If structural changes are pending --> Author review and decision
- If more materials are expected --> Wait, then re-run **IngestResearch**

## Handling Conflicts

When new research contradicts existing drafted content:

1. **Flag, do not silently overwrite.** Always present contradictions to the author.
2. Provide both the existing position and the new evidence.
3. Offer options: revise to match new evidence, acknowledge the contradiction in the text, or investigate further.
4. The author makes the final decision on how to handle contradictions.

## Iterative Use

This workflow is designed to be run multiple times as research accumulates:

1. First run: Establishes the baseline Book Bible with initial research
2. Subsequent runs: Incrementally updates the Bible and drafts as new materials are added
3. Each run produces a dated update summary for the author to track the book's evolution

The Research Digest and Update Summaries together form a log of how the book's evidence base grew over time, which itself can inform the intellectual journey narrative. Note that this evidence base includes both local materials and external sources discovered through web research and literature review.
