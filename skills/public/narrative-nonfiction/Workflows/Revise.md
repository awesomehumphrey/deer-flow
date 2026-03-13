# Revise Workflow

Apply targeted changes to an existing chapter draft. This workflow takes a specific revision input — critic feedback, a revision brief from UpdateFromResearch, a directive from the author, or new evidence to integrate — and makes focused changes without rewriting the chapter from scratch.

## Purpose

Revision is a different cognitive activity from initial composition. WriteChapter builds a chapter from nothing, working through evidence planning, layer articulation, prose composition, and full critic passes. Revise takes an existing draft that already has structure, voice, and argument, and makes it better in specific ways.

Running the full WriteChapter process for "strengthen the evidence in section 3" or "integrate this new paper" is like demolishing a house to fix a window. Revise provides the targeted tools.

## Prerequisites

- An existing chapter draft (in `/mnt/ValuesWork/drafts/` or provided by the author)
- At least one revision input (see Step 1)
- Book Bible (for consistency checking)
- Read `AntiCliche.md`: freshness enforcement for new/changed text
- Read `Critics.md`: targeted critic passes on changed sections
- Read `Bibliography.md`: citation conventions for new references

## Trigger Phrases

- "Revise chapter N..."
- "Fix the evidence in..."
- "Strengthen the argument in..."
- "Integrate [source] into chapter N"
- "Apply the revision brief"
- "The [critic] gave a low score; fix..."
- "Polish the prose in..."
- "Improve the opening of..."
- "Tighten section N"
- "Add the [anecdote/example/data] to chapter N"
- "Rewrite section N" (targeted rewrite of a section, not the whole chapter)

## Procedure

### Step 1: Identify the Revision Input

Determine what is driving this revision. There are five types, and the scope of work differs for each:

| Revision Type | Input | Typical Scope |
|---|---|---|
| **Critic feedback** | Critic pass results from WriteChapter or a previous Revise | 2-5 targeted changes per critic |
| **Revision brief** | Structured brief from UpdateFromResearch | Additions, revisions, removals as specified |
| **Author directive** | A specific instruction ("strengthen X", "add Y", "cut Z") | As specified |
| **Evidence integration** | New source to incorporate into an existing chapter | 1-3 sections affected |
| **Consistency fix** | Contradiction or inconsistency flagged by Continuity Editor or author | Targeted corrections across sections |

```
REVISION INPUT:
  Type: [critic feedback / revision brief / author directive / evidence integration / consistency fix]
  Source: [where the revision input came from]
  Scope: [which sections/passages are affected]
  Priority: [what matters most in this revision]
```

### Step 2: Read the Existing Draft

Read the full chapter draft. While reading, note:

1. **Current structure:** Section breakdown, argument flow, evidence used
2. **Current strengths:** What is working well and must be preserved
3. **Affected sections:** Which specific passages will be changed
4. **Surrounding context:** Text before and after the affected sections (changes must blend seamlessly)

```
DRAFT ASSESSMENT:
  Chapter: [N] — [Title]
  Word count: [current]
  Sections: [list with brief summary]
  Strengths to preserve: [what is already working]
  Sections to revise: [specific sections with reason]
```

### Step 3: Plan the Changes

Before making any changes, plan them explicitly. This prevents cascading edits that destabilise the chapter.

For each change:

```
CHANGE PLAN:

Change 1:
  Location: Section [N], paragraph beginning "[first few words]..."
  Type: [addition / revision / removal / restructure]
  What: [specific description of the change]
  Why: [what revision input drives this change]
  Risk: [what could go wrong — e.g., disrupting argument flow, creating inconsistency]
  Dependencies: [does this change require other changes elsewhere in the chapter?]

Change 2:
  ...
```

**Ordering rule:** Apply structural changes before content changes, content changes before prose changes. This prevents doing detailed prose work on a passage that later gets moved or cut.

**Scope discipline:** If the change plan grows beyond 8-10 individual changes, consider whether this has become a rewrite rather than a revision. If so, recommend WriteChapter instead.

### Step 4: Apply Changes

Work through the change plan in order. For each change:

#### 4a: Additions

When inserting new material (evidence, examples, analysis, narrative):

1. Write the new passage in the chapter's established voice and register
2. Match the Aesthetic Profile — new text should be indistinguishable from existing text
3. Ensure the new passage connects to the surrounding paragraphs (transitions in and out)
4. If adding evidence, follow the attribution conventions in `Bibliography.md`
5. If adding a new BibTeX entry, append it to `references.bib`

#### 4b: Revisions

When changing existing text:

1. Preserve the author's voice — revise the content, not the style (unless the revision is specifically about style)
2. Maintain argument flow — if changing an evidence point, ensure the analysis still follows
3. Check that the revised passage still serves the same layers it served before (consult the chapter's layer summary)
4. If the revision changes the chapter's argument, flag this for the author

#### 4c: Removals

When cutting material:

1. Check that removing the passage does not break the argument chain
2. Check that removing the passage does not leave orphaned references (citations mentioned later but no longer introduced)
3. If the removed material is valuable but belongs elsewhere, note this in the output: "Suggest moving to chapter [N]"
4. Verify transitions still work after the cut

#### 4d: Restructuring

When reordering sections or changing the chapter's architecture:

1. Verify the new order maintains cause-and-effect logic (Narrative Thread layer)
2. Check that the Mystery layer still works — information should not be referenced before it is introduced
3. Update all internal cross-references
4. Rewrite transitions between moved sections

### Step 5: Scoped Anti-Cliche Sweep

Run the Anti-Cliche checklist from `AntiCliche.md` **only on new or changed text**. Do not re-sweep passages that were not touched.

For each new or changed passage, verify:

- [ ] No phrases from any Banned list
- [ ] Every new claim is attributed to a specific source
- [ ] New evidence is shown, not just asserted
- [ ] Abstract concepts are grounded in specific examples
- [ ] Any new analogies are original
- [ ] Strong, active verbs throughout new text
- [ ] No AI-specific patterns
- [ ] New text contains at least one specific, surprising detail per paragraph

### Step 6: Scoped Critic Passes

Run critic passes **targeted to the type of revision**, not the full 5-8 pass sequence. The revision type determines which critics are needed:

| Revision Type | Critics to Run |
|---|---|
| **Critic feedback** | Re-run only the critic(s) that flagged problems, on the changed sections |
| **Revision brief** | Evidence Inspector + Layer Auditor on changed sections |
| **Author directive** | Reader Surrogate on changed sections (does the change work?) |
| **Evidence integration** | Evidence Inspector on new evidence; Layer Auditor on affected sections |
| **Consistency fix** | Continuity Editor on the full chapter (consistency requires whole-chapter awareness) |

Each critic produces:

- 1-3 suggestions (scoped to changed sections)
- A confidence rating for their dimension on the changed sections only
- Confirmation that the revision improved the chapter (or a flag if it introduced new problems)

**Escalation:** If a scoped critic pass reveals problems beyond the changed sections (e.g., the Evidence Inspector finds that the revision exposed a pre-existing attribution gap elsewhere), note these as follow-up items rather than expanding the current revision scope.

### Step 7: Update Chapter Metadata

After applying changes, update the chapter's metadata:

#### Layer Summary

Review the chapter's layer summary table. If any changes affected a layer, update the summary:

```
LAYER UPDATES:
  [Layer]: [previous] → [updated]
```

If no layers changed, confirm: "Layer balance unchanged."

#### References

1. Add any new citation keys to the chapter's "References Used" section
2. Remove any citation keys for evidence that was cut
3. If new BibTeX entries were created, list them

#### Critic Pass Summary

If previous critic pass results exist, update them:

```
UPDATED CRITIC SUMMARY:
  [Critic]: [previous rating] → [new rating] (changed sections only)
```

### Step 8: Output

Present the revision with:

1. **Change summary:** What was changed and why (brief, not a full diff)
2. **The revised chapter** (full text with changes integrated, or just the changed sections if the author prefers)
3. **Layer updates:** Any changes to the layer summary
4. **References:** New citations added, citations removed
5. **New BibTeX entries:** If any
6. **Critic pass results:** Scoped critic confidence ratings
7. **Follow-up items:** Problems discovered but not addressed in this revision (out of scope)
8. **Recommended next step:** Another Revise pass, proceed to the next chapter, or Explore a question raised by the revision

Save the revised draft to the same location as the original, overwriting it:

```
/mnt/ValuesWork/drafts/chapter-NN-slug.md
```

If the author wants to preserve the previous version, save a backup first:

```bash
cp /mnt/ValuesWork/drafts/chapter-NN-slug.md /mnt/ValuesWork/drafts/chapter-NN-slug.v[N].md
```

## Revision Depth Guide

Not every revision is the same size. Use this guide to calibrate effort:

| Depth | Trigger | Typical Changes | Critics |
|---|---|---|---|
| **Light** | Prose polish, minor fixes, typos | Word- and sentence-level edits | Reader Surrogate only |
| **Medium** | Critic feedback, single evidence integration, author directive | Paragraph- and section-level edits | 1-2 targeted critics |
| **Heavy** | Revision brief from UpdateFromResearch, structural changes | Multiple section-level edits, possible restructuring | 2-3 targeted critics |
| **Rewrite** | Fundamental argument change, critic rating of 1/5 | Beyond this workflow's scope | Use **WriteChapter** instead |

If a revision escalates from medium to heavy during execution, pause and confirm with the author before proceeding.

## Relationship to Other Workflows

- **UpdateFromResearch** produces revision briefs --> **Revise** consumes them
- **WriteChapter** produces initial drafts with critic feedback --> **Revise** addresses that feedback
- **Explore** may identify implications for existing chapters --> **Revise** applies them
- **IngestResearch** surfaces new evidence --> **Revise** integrates it into existing drafts (for new chapters, use **WriteChapter**)

## Iterative Revision

A chapter may go through multiple Revise passes. This is expected and healthy. Each pass should be scoped and purposeful:

1. First pass: Apply the revision brief or address critic feedback
2. Second pass: Integrate additional evidence or address follow-up items
3. Third pass: Prose polish and final freshness check

Resist the temptation to combine all passes into one. Focused passes produce better results than trying to fix everything simultaneously.
