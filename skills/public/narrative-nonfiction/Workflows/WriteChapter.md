# WriteChapter Workflow

Transform Book Bible chapter plans into actual prose. This is where all seven layers converge into the written chapter. Every paragraph must serve at least one layer. Memorable lines are engineered using rhetorical figures. The Anti-Cliché filter ensures freshness. Multi-pass critics tighten the final draft.

## Prerequisites

- Book Bible exists (from BuildBible workflow)
- Read `RhetoricalFigures.md`: the toolbelt for this workflow
- Read `AntiCliche.md`: mandatory freshness enforcement
- Read `AestheticProfiles.md`: the configured style guide
- Read `Critics.md`: multi-pass review profiles
- Read `Bibliography.md`: citation conventions and reference management
- Know which chapter(s) this output covers
- Verify `references.bib` exists and contains entries for planned sources

## Procedure

### Step 1: Load the Chapter Context

Read the Book Bible and extract for the target chapter:

For the target chapter:
- **MEANING:** What thesis element is this chapter advancing?
- **INTELLECTUAL JOURNEY:** What does the author learn or revise in this chapter?
- **NARRATIVE THREAD:** What question does this chapter answer? What new question does it raise?
- **MYSTERY:** What information is revealed? What is withheld?
- **LANDSCAPE:** What context is established or deepened?
- **RELATIONSHIPS:** Which connections between people, ideas, or institutions are explored?
- **PROSE:** What register and rhetorical emphasis?

### Step 2: Evidence Planning

Before writing, plan the evidence for this chapter:

1. **Primary evidence:** What is the main evidence or analysis for this chapter's argument?
2. **Supporting evidence:** What secondary evidence supports the primary evidence?
3. **Source attribution:** Are all sources specifically attributed?
4. **Counter-evidence:** What alternative perspectives or counter-arguments does this chapter address?
5. **Gaps:** What evidence is missing that the reader might expect?
6. **Bibliography check:** Verify every planned source has a BibTeX entry in `references.bib`. Add any missing entries now, before writing begins. See `Bibliography.md` for conventions.

#### Rhetorical Figure Strategy

Identify the moments where rhetorical figures will have maximum impact. Figures can be deployed in both analytical passages and narrative sections.

For each key moment:

1. Identify 1-3 highest-impact moments (a key finding, a turning point, a memorable formulation)
2. Consult the **Figure Deployment by Moment** table in `RhetoricalFigures.md`
3. Select candidate figures matched to each moment type and the Aesthetic Profile
4. Record the plan:

```
FIGURE PLAN:
Section 1: [moment description] → [figure names] → [target: analysis/prose/narrative]
Section 2: [moment description] → [figure names] → [target: analysis/prose/narrative]
...
```

**Rules:**
- Minimum 2-3 figure deployments per substantial section
- At least 1 deployment in prose (not just data presentation)
- Combine 2-3 figures for maximum impact on key statements
- NOT every sentence needs a figure: save them for moments that matter

### Step 3: Layer Articulation Map

Before writing begins, explicitly commit to what each of the seven layers is doing in this chapter. This is the composition contract.

For the chapter, write:

```
CHAPTER LAYER MAP:
MEANING:      [What thematic work this chapter does]
INTELLECTUAL JOURNEY:  [How the author's understanding advances]
NARRATIVE THREAD:      [What question is answered, what is raised]
MYSTERY:       [What the reader learns, what remains unknown]
LANDSCAPE:     [What context is added]
RELATIONSHIPS: [What connections are explored]
PROSE:         [Register, pacing, planned figure deployments]
```

### Step 4: Evidence Integration

For sections with data, interviews, or research:

1. **Source presentation:** Lead with the most striking finding, then provide context
2. **Attribution:** Name sources specifically; avoid "studies show"
3. **Context:** Ground statistics in human stories where possible
4. **Analysis:** Go beyond reporting: explain what the evidence means
5. **Limitations:** Acknowledge what the evidence does not show

### Step 5: Prose Composition with Voice

Write the actual prose following the Aesthetic Profile. This step integrates rhetorical figure execution, evidence integration, and layer awareness.

#### Sentence-Level Craft

- Vary sentence length deliberately (short punchy sentences for impact, longer sentences for nuanced argument)
- Open paragraphs with strong hooks (not throat-clearing)
- End paragraphs with hooks or thematic resonance
- Use active voice as default; passive voice only for strategic effect

#### Evidence Presentation

- Lead with the finding, follow with the source
- Use specific attribution: "Chen et al. found..." not "researchers found..."
- Contextualise statistics: provide scale, compare to benchmarks
- Ground abstract data in concrete examples where possible

#### Rhetorical Figure Execution

Execute the figure plan from Step 2:

- Figures are deployed in introductions, conclusions, key statements, and transitional moments
- Reference the Figure Plan
- After writing each section, verify at least 1-2 figure deployments appeared

#### Layer Awareness During Composition

While writing, keep the Layer Articulation Map visible. After completing each major section, do a quick inline check:

```
SECTION [N] LAYER CHECK:
MEANING: [landed? Y/N]  INTELLECTUAL JOURNEY: [Y/N]  NARRATIVE THREAD: [Y/N]
MYSTERY: [Y/N]  LANDSCAPE: [Y/N]  RELATIONSHIPS: [Y/N]  PROSE: [Y/N]
Any N → weave it in now, before moving to the next section.
```

### Step 6: Mystery Layer Integration

During writing, maintain information management:

1. **What does the reader know now?** (track accumulated knowledge)
2. **What question drives this chapter?** (chapter-level mystery)
3. **Plant something.** Every chapter should plant at least one detail or question that will matter later
4. **End with a question.** Chapter endings should leave at least one thread unresolved

### Step 7: Anti-Cliché Sweep

Before the critic passes, run the Anti-Cliché checklist from `AntiCliche.md`:

- [ ] No phrases from any Banned list
- [ ] Every claim is attributed to a specific source
- [ ] Evidence is shown, not just asserted
- [ ] Abstract concepts are grounded in specific examples
- [ ] Analogies are original to this book
- [ ] Strong, active verbs used throughout
- [ ] No AI-specific patterns
- [ ] Each paragraph contains at least one surprising detail
- [ ] Opening hooks are concrete, not generic

### Step 8: Multi-Pass Critic System

After composition and the anti-cliché sweep, the draft goes through multiple critic passes. Each critic reads from a single focused angle and produces actionable suggestions.

#### Procedure

1. Run **5 mandatory passes** on every chapter
2. For high-stakes chapters (opening, midpoint, climactic), run all **8 passes**
3. Each critic produces:
   - 2-5 specific, section-level or paragraph-level suggestions
   - A confidence rating (1-5) for their dimension
   - No rewriting: suggestions only
4. After all passes complete, apply suggestions that improve the prose without losing existing strengths
5. If any critic gives a 1-2 confidence rating, that dimension needs targeted revision

#### The 5 Mandatory Critics

| # | Critic | Focus |
|---|--------|-------|
| 1 | **The Layer Auditor** | Seven-layer completeness and balance against Book Bible |
| 2 | **The Evidence Inspector** | Source attribution, credibility, and coverage |
| 3 | **The Rhetoric Examiner** | Figure deployment density, variety, and prose rhythm |
| 4 | **The Freshness Inspector** | Cliché hunt, concrete specificity, AI pattern detection |
| 5 | **The Reader Surrogate** | Engagement, clarity, forward momentum |

#### The 3 Optional Critics (high-stakes chapters)

| # | Critic | Focus |
|---|--------|-------|
| 6 | **The Subtext Analyst** | Unsaid meaning, counter-arguments, author voice |
| 7 | **The Continuity Editor** | Consistency with earlier chapters, Book Bible compliance |
| 8 | **The Pacing Surgeon** | Sentence rhythm, section proportionality, bloat detection |

#### Pass Ordering

Run in this order: structural issues before polish, evidence before style, craft before gut-check.

1. Layer Auditor (structural)
2. Evidence Inspector (credibility)
3. Rhetoric Examiner (craft)
4. Freshness Inspector (catches what the first three introduced)
5. Reader Surrogate (final gut-check)
6-8. Optional critics in any order

### Step 9: Output

Present the written chapter with:

1. The prose itself
2. A brief note on which layers were advanced and how
3. **Critic pass summary:** confidence ratings from each critic and a 1-sentence summary of changes applied
4. Any Book Bible updates needed (if writing revealed new connections)
5. **References used:** List all citation keys used in this chapter with a brief note on their role (see `Bibliography.md` for the chapter-level reference tracking format)
6. **New BibTeX entries:** Any entries added to `references.bib` during this chapter's writing
7. Recommendation for what to write next
8. Updated verification criteria (mark completed criteria)

### Chapter Length Guidelines

| Format | Target Chapter Length |
|--------|---------------------|
| Essay | 1,000-3,000 words |
| Short book | 2,000-5,000 words |
| Major work | 3,000-7,000 words |

These are guidelines, not rules. Chapter length should serve the argument.
