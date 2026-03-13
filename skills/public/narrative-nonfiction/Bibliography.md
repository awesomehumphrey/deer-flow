# Bibliography Management

Manage references for a narrative non-fiction book. BibTeX is the master format. References are added incrementally during writing and compiled into a formatted bibliography at the end.

## File Structure

```
project/
  references.bib          # Master BibTeX file (single source of truth)
  drafts/
    ch01.md               # Chapter drafts with in-text citations
    ch02.md
    ...
  bibliography.md         # Generated formatted bibliography (output)
```

## BibTeX Conventions

### Citation Keys

Use a consistent, human-readable key format:

| Author Count | Format | Example |
|---|---|---|
| 1 author | `lastname_year` | `zuboff_2019` |
| 2 authors | `lastname_lastname_year` | `friedman_hendry_2019` |
| 3+ authors | `lastname_etal_year` | `obie_etal_2022` |
| Same author, same year | Append letter | `schwartz_2012a`, `schwartz_2012b` |
| Organisation | `orgname_year` | `acm_2018` |
| No author (website) | `site_shorttitle_year` | `bbc_darkpatterns_2023` |

Keys are lowercase with underscores. No spaces, no special characters.

### Entry Types

Use these BibTeX entry types for the source categories common in narrative non-fiction:

**Academic sources:**
```bibtex
@article{obie_etal_2022,
  author    = {Obie, Humphrey O. and Chua, Caslon and Avazov, Davronbek and Grundy, John},
  title     = {A Study of the Values-Based Methods in Software Engineering},
  journal   = {IEEE Transactions on Software Engineering},
  year      = {2022},
  volume    = {48},
  number    = {10},
  pages     = {3858--3876},
  doi       = {10.1109/TSE.2021.3106248}
}

@book{zuboff_2019,
  author    = {Zuboff, Shoshana},
  title     = {The Age of Surveillance Capitalism},
  publisher = {Profile Books},
  year      = {2019},
  address   = {London},
  isbn      = {978-1781256848}
}

@inproceedings{gray_etal_2018,
  author    = {Gray, Colin M. and Kou, Yubo and Battles, Bryan and Hoggatt, Joseph and Toombs, Austin L.},
  title     = {The Dark (Patterns) Side of {UX} Design},
  booktitle = {Proceedings of the 2018 CHI Conference on Human Factors in Computing Systems},
  year      = {2018},
  pages     = {1--14},
  doi       = {10.1145/3173574.3174108}
}
```

**Non-academic sources:**
```bibtex
@misc{brignull_2010,
  author       = {Brignull, Harry},
  title        = {Dark Patterns: Deception vs. Honesty in {UI} Design},
  year         = {2010},
  howpublished = {\url{https://darkpatterns.org}},
  note         = {Accessed 15 March 2026}
}

@article{nyt_facebook_2018,
  author  = {Confessore, Nicholas},
  title   = {Cambridge Analytica and Facebook: The Scandal and the Fallout So Far},
  journal = {The New York Times},
  year    = {2018},
  month   = apr,
  day     = {4},
  url     = {https://www.nytimes.com/2018/04/04/us/politics/cambridge-analytica-scandal-fallout.html}
}

@misc{interview_chen_2025,
  author = {Chen, Liang},
  title  = {Personal interview with the author},
  year   = {2025},
  month  = jun,
  note   = {Interview conducted 14 June 2025, Melbourne}
}
```

## In-Text Citation Style

Narrative non-fiction uses **author-year** citations woven into prose. The citation should feel natural, not intrusive.

### Preferred Patterns

**Narrative citations** (author is part of the sentence):

```markdown
Zuboff (2019) argues that surveillance capitalism represents a new
economic order that claims human experience as free raw material.

As Schwartz (2012) demonstrated in his foundational taxonomy, human
values form a circular motivational continuum.
```

**Parenthetical citations** (author is not part of the sentence):

```markdown
Dark patterns have been catalogued extensively in recent years
(Gray et al., 2018; Brignull, 2010).

The concept of value-sensitive design emerged in the late 1990s
(Friedman and Hendry, 2019).
```

**Citing specific passages:**

```markdown
Rokeach (1973, p. 5) defined a value as "an enduring belief that a
specific mode of conduct or end-state of existence is personally or
socially preferable."
```

### Conventions

- Use "et al." for 3+ authors after first mention
- First mention of a multi-author source: list all authors (up to 3), then et al.
- Page numbers for direct quotes: `(Author, Year, p. X)` or `(Author, Year, pp. X-Y)`
- Multiple sources in one parenthetical: separate with semicolons, order chronologically
- For the same author, same year: `(Schwartz, 2012a, 2012b)`

### For Pandoc Compatibility

If the manuscript will be processed with pandoc/citeproc for final formatting, use Pandoc citation syntax alongside or instead of the above:

```markdown
[@zuboff_2019]                        # parenthetical
@zuboff_2019 argues that...           # narrative
[@zuboff_2019, p. 45]                 # with page
[@gray_etal_2018; @brignull_2010]     # multiple
```

## Adding References During Writing

When writing a chapter and a new reference is needed:

### Step 1: Identify the Source

Determine what type of source it is:
- Academic paper (use DOI if available)
- Book (use ISBN if available)
- Website or blog post
- News article
- Interview or personal communication
- Government or organisational report

### Step 2: Create the BibTeX Entry

Write a complete BibTeX entry following the conventions above. Required fields vary by type:

| Type | Required Fields |
|---|---|
| `@article` | author, title, journal, year |
| `@book` | author/editor, title, publisher, year |
| `@inproceedings` | author, title, booktitle, year |
| `@misc` | author (or title), year, howpublished or url |
| `@techreport` | author, title, institution, year |
| `@phdthesis` | author, title, school, year |

### Step 3: Check for Duplicates

Before adding, verify the citation key does not already exist in `references.bib`.

### Step 4: Append to references.bib

Add the entry alphabetically by citation key, or append at the end with a comment indicating the chapter:

```bibtex
% === Chapter 3: The Values Gap ===

@article{obie_etal_2022,
  ...
}
```

### Step 5: Use in Prose

Insert the citation in the chapter draft using the in-text citation patterns above.

## Chapter-Level Reference Tracking

At the end of each chapter draft, maintain a reference list:

```markdown
## References Used in This Chapter

- zuboff_2019: Surveillance capitalism framework (Sections 3.1, 3.4)
- obie_etal_2022: Values-based methods study (Section 3.2)
- schwartz_2012: Value theory foundation (Section 3.3)
- interview_chen_2025: Personal anecdote (Section 3.5)
```

This helps track coverage and ensures no orphaned citations.

## Quality Checks

Run these checks before finalising a chapter or the full manuscript:

### Per-Chapter Checks

- [ ] Every factual claim has a citation
- [ ] Every citation key exists in `references.bib`
- [ ] No "studies show" or "research suggests" without specific attribution
- [ ] Page numbers provided for all direct quotes
- [ ] Interviews and personal communications clearly attributed
- [ ] Web sources include access dates

### Full-Manuscript Checks

- [ ] Every entry in `references.bib` that is cited appears in at least one chapter
- [ ] No orphaned entries (in .bib but never cited) unless intentionally included
- [ ] Citation keys are consistent throughout (no `zuboff2019` in one chapter and `zuboff_2019` in another)
- [ ] All DOIs resolve to the correct paper
- [ ] All URLs are accessible

### Common Problems

| Problem | Fix |
|---|---|
| Citation key mismatch between text and .bib | Standardise to the `lastname_year` convention |
| Missing year for web source | Use the publication date; if none, use the access date with a note |
| Interview without date/location | Add month and location to the `note` field |
| Duplicate key (same author, same year) | Append a/b/c suffix |
| Source found online but also published in print | Prefer the print/DOI version; add URL as supplementary |

## Generating the Formatted Bibliography

### Option A: Manual (for drafts)

Sort entries alphabetically by first author surname. Format each entry in a consistent style (e.g., APA 7th, Chicago Author-Date). This is suitable for early drafts and reviews.

### Option B: Pandoc with Citeproc (for final output)

Create a temporary file referencing all cited keys:

```markdown
---
bibliography: references.bib
csl: chicago-author-date.csl
nocite: |
  @zuboff_2019, @obie_etal_2022, @schwartz_2012
---

# References
```

Then run:

```bash
pandoc refs-dummy.md --citeproc -o bibliography.md -t markdown
```

Download CSL files from https://github.com/citation-style-language/styles as needed. Common choices for narrative non-fiction:

| Style | CSL File | Typical Use |
|---|---|---|
| Chicago Author-Date | `chicago-author-date.csl` | Most narrative non-fiction books |
| APA 7th | `apa.csl` | Social science crossover |
| Chicago Notes-Bibliography | `chicago-note-bibliography.csl` | History, humanities |

### Option C: Publisher Formatting

Many publishers reformat the bibliography during production. In that case, ensure the `references.bib` file is complete and accurate; the publisher's typesetting team will handle the rest.

## Integration with WriteChapter Workflow

During **Step 2 (Evidence Planning)** of the WriteChapter workflow:

1. Review the chapter plan for all referenced sources
2. Verify each source exists in `references.bib`
3. Add any missing entries before writing begins
4. Note planned citation style (narrative vs. parenthetical) for key sources

During **Step 4 (Evidence Integration)**:

1. Use specific attribution with citation keys
2. After writing, cross-check all citations against `references.bib`

During **Step 8 (Multi-Pass Critic System)**, the **Evidence Inspector** (Critic #2) should verify:

1. Every claim is supported by a cited source
2. All citation keys resolve to entries in `references.bib`
3. No fabricated or unverifiable sources
4. Appropriate mix of primary research, secondary analysis, and narrative sources
