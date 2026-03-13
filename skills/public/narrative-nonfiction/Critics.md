# Critic Profiles for Multi-Pass Review

The WriteChapter workflow's revision step runs the completed chapter through multiple critic passes. Each critic examines the prose from a single focused angle and produces specific, actionable suggestions to tighten the draft.

This is adapted from WriteStory's fiction-focused critic system for non-fiction narrative.

## Rules for All Critics

1. **Suggestions, not rewrites.** Each critic suggests changes; the author decides whether to apply them. Preserve the author's voice.
2. **Specific and locatable.** Every suggestion references a specific paragraph, section, or passage. "The evidence in section 3 could be stronger" is acceptable. "The chapter needs more evidence" is not.
3. **2-5 suggestions per pass.** This prevents both laziness and over-criticism. If a critic finds more than 5 issues, they prioritise the 5 most impactful.
4. **Confidence rating (1-5).** Each critic rates how well the chapter serves their dimension:
   - 5: Exceptional. No changes needed.
   - 4: Strong. Minor polish suggestions.
   - 3: Adequate. A few meaningful improvements possible.
   - 2: Weak. Significant gaps in this dimension.
   - 1: Failed. This dimension needs substantial rework.
5. **Do not duplicate.** If a previous critic already flagged an issue, the next critic should not repeat it. Build on each other.
6. **Preserve voice.** No suggestion should flatten the author's chosen Aesthetic Profile. A Zuboff-style chapter should not be criticised for complex sentences. A Gladwell-style chapter should not be criticised for light-footnote apparatus.

## Output Format (per critic)

```
[CRITIC NAME] — Rating: [N]/5
- [Suggestion 1]: [specific location] → [what to change and why]
- [Suggestion 2]: [specific location] → [what to change and why]
...
```

---

## Mandatory Critics (run on every chapter)

### 1. The Layer Auditor

**Focus:** Seven-layer completeness and interaction
**Personality:** Methodical, structural thinker. Sees the architecture beneath the prose.

**Asks:**
- Does every chapter advance at least 3 layers (not just the Narrative Thread)?
- Is any layer completely absent from the chapter?
- Are layers interacting (e.g., Landscape detail that illuminates the Intellectual Journey) or merely present in isolation?
- Does the chapter's layer balance match what the Book Bible prescribed for this chapter?
- Is the Meaning (thesis) emerging through evidence, or is it being stated?

**Red flags:**
- A chapter that only advances the Narrative Thread (textbook chapter, not narrative non-fiction)
- A chapter with no Intellectual Journey movement
- Thesis stated through exposition rather than through evidence
- A layer present in the Book Bible but absent from the actual prose

---

### 2. The Evidence Inspector

**Focus:** Quality, attribution, and credibility of evidence
**Personality:** The fact-checker. Verifies that claims are supported and sources are credible.

**Asks:**
- Is every substantive claim supported by evidence?
- Are sources attributed specifically (not "studies show" but "Chen et al. 2023 showed")?
- Is the evidence current, or are outdated sources being used?
- Are statistics presented with appropriate context and caveats?
- Is the evidence from primary sources, or only from secondary summarisation?
- Are there gaps where evidence is needed but missing?

**Red flags:**
- Unattributed claims presented as facts
- Statistics without context or source
- Heavy reliance on secondary sources when primary sources exist
- Evidence that contradicts the author's argument but is presented without acknowledgment

---

### 3. The Rhetoric Examiner

**Focus:** Rhetorical figure deployment and prose musicality
**Personality:** The ear. Hears rhythm, notices patterns, feels cadence.

**Asks:**
- Were rhetorical figures deployed at the planned impact moments?
- Are figures present in both analysis sections and narrative sections?
- Is there figure variety, or did the writer lean on the same 2-3 techniques throughout?
- Do the deployed figures match the Aesthetic Profile's emphasis?
- Are memorable lines actually memorable: would a reader quote them?
- Does sentence rhythm vary deliberately for pacing, or has it fallen into monotony?

**Red flags:**
- A chapter with zero identifiable figures in key passages
- Over-deployment that makes the prose feel performative
- Rhythm monotony: all sentences of similar length
- A climactic passage that lacks any rhetorical engineering

---

### 4. The Freshness Inspector

**Focus:** Cliché detection, originality, concrete specificity
**Personality:** Allergic to the generic. Demands the unexpected.

**Asks:**
- Did anything from the `AntiCliche.md` banned lists survive?
- Are there familiar phrasings that passed the first filter?
- Is every description filtered through the author's specific perception, or are there "default camera" descriptions?
- Could any abstract noun be replaced with a concrete example?
- Are emotions shown through evidence or stated directly?
- Is there at least one genuinely surprising detail per section?
- Are there any AI-specific prose patterns (tapestry of, complex landscape, moving the needle)?

**Red flags:**
- "Studies have shown..." without specific attribution
- "In today's world..." opening
- Abstract statements that should be grounded in evidence
- A passage where any author writing about any topic could have written the same sentence

---

### 5. The Reader Surrogate

**Focus:** Engagement, clarity, emotional impact, information flow
**Personality:** The gut. Reads for pleasure and learning, not craft.

**Asks:**
- Where did my attention wander? (These are pacing problems.)
- Where was I confused? (These are clarity problems.)
- Where was I most engaged? (Protect these moments.)
- Where was I least engaged? (These need work.)
- Did the chapter ending make me want to read the next chapter?
- Was the information flow clear: did I know what I needed to know when I needed to know it?
- Did any section feel like it was marking time rather than advancing the argument?

**Red flags:**
- A section where nothing changes or advances
- An ending that resolves everything with no forward momentum
- A passage where the reader must re-read to understand the argument
- Evidence peaks that do not land because the setup was insufficient

---

## Optional Critics (for high-stakes chapters: opening, midpoint, climax, finale)

### 6. The Subtext Analyst

**Focus:** What is unsaid, implied, and layered beneath the surface
**Personality:** Reads between every line. Obsessed with gaps and silence.

**Asks:**
- In analytically charged sections, is the author showing the evidence or just asserting conclusions?
- Are there moments where a concrete example would be stronger than an abstract statement?
- Could any section gain power by being more direct?
- Does the author acknowledge counter-arguments adequately?
- Is there enough personal voice (the author's perspective) or is the prose too detached?

**Red flags:**
- Assertions without evidence to support them
- No acknowledgment of alternative interpretations
- A chapter that reads as a detached academic paper rather than narrative non-fiction

---

### 7. The Continuity Editor

**Focus:** Internal consistency and Book Bible compliance
**Personality:** The memory. Remembers every detail from every chapter.

**Asks:**
- Does the timeline add up? (Dates, chronology of events)
- Does each piece of evidence retain its original context, or has it been distorted?
- Are statistics consistent with earlier chapters?
- Does the chapter deliver what the Book Bible's chapter map prescribed?
- Is the author's Intellectual Journey consistent: do their stated positions align with earlier chapters?

**Red flags:**
- A statistic quoted differently in different chapters
- Evidence presented that contradicts earlier evidence without acknowledgment
- The author's stated position shifting without explanation
- A chapter that contradicts the Book Bible's plan

---

### 8. The Pacing Surgeon

**Focus:** Rhythm, timing, and proportionality
**Personality:** Feels the pulse of the prose. Knows when to speed up and when to let the reader breathe.

**Asks:**
- Does sentence length vary deliberately, or has it fallen into a monotonous pattern?
- Are dense analytical passages punctuated by narrative relief?
- Is any section disproportionately long or short for its narrative importance?
- Where does prose bloat? (Unnecessary qualification, over-explained evidence, redundant transitions)
- Where does prose rush? (Complex ideas that deserve more space, transitions that skip too fast)
- Are paragraph breaks and section breaks used to control rhythm?

**Red flags:**
- Three consecutive paragraphs with the same sentence length pattern
- A dense ten-page section of analysis with no narrative relief
- An emotional or narrative peak compressed into a single sentence when it deserves more space
- A transitional passage that runs longer than the substantive passages

---

## Pass Ordering

Run critics in this order: structural issues before polish, craft before gut-check.

1. **Layer Auditor** first (fix structural gaps before refining prose)
2. **Evidence Inspector** second (verify credibility before polishing style)
3. **Rhetoric Examiner** third (craft-level improvements)
4. **Freshness Inspector** fourth (catches clichés the first three may have introduced)
5. **Reader Surrogate** last of the mandatory five (final engagement gut-check)
6-8. **Optional critics** after the mandatory five, in any order

## Efficiency

Each critic pass produces 2-5 brief, actionable notes. This is a tightening pass, NOT a second draft. The total overhead of the 5 mandatory passes should be a focused review cycle producing 10-25 specific suggestions, not a rewriting process.
