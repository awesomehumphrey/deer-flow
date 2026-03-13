# IngestResearch Workflow

Scan research material directories, read and analyse documents, extract key findings, and produce a structured Research Digest that maps evidence to book chapters. This is the bridge between raw materials and the writing process.

## Prerequisites

- Book-specific skill loaded (e.g., `human-values-book`) with research directory paths defined
- Research materials present in the expected directories
- Book Bible exists (from BuildBible workflow), or at minimum a chapter outline exists

## Trigger Phrases

- "Analyse the research materials"
- "Ingest the documents"
- "Read the papers in the folder"
- "What's in the research folder?"
- "Scan my materials"
- "Process the new documents"

## Procedure

### Step 1: Inventory the Research Directories

Scan each research directory and build a file inventory. Use `bash` to list files and `read_file` to read content.

```bash
# List all research directories
ls -la /mnt/ValuesWork/papers/
ls -la /mnt/ValuesWork/interviews/
ls -la /mnt/ValuesWork/notes/
ls -la /mnt/ValuesWork/data/
ls -la /mnt/ValuesWork/bio/
ls -la /mnt/ValuesWork/grants/
ls -la /mnt/ValuesWork/highlights/
```

For each directory, record:

```
INVENTORY:
Directory: papers/
  - [filename] | [file type] | [size] | [status: new/previously-ingested]

Directory: interviews/
  - [filename] | [file type] | [size] | [status]
...
```

If a Research Digest already exists from a previous run, compare the inventory against it to identify **new or changed files only**. Flag these for processing.

**Pause:** Present the inventory to the author. Ask:
- Process all files, or a specific subset?
- Any files to skip?
- Any priority ordering?

### Step 2: Read and Extract

For each file, read the content and extract structured information. The extraction approach depends on file type:

#### Text-based files (.md, .txt, .tex, .bib)

Read directly with `read_file`.

#### PDF files (.pdf)

Use bash to extract text:

```bash
# If pdftotext is available
pdftotext /mnt/ValuesWork/papers/filename.pdf /tmp/filename.txt

# Or use Python
python3 -c "
import subprocess
result = subprocess.run(['pdftotext', '-layout', '/mnt/ValuesWork/papers/filename.pdf', '-'], capture_output=True, text=True)
print(result.stdout)
"
```

If text extraction fails, note the file as requiring manual processing.

#### Spreadsheets (.csv, .xlsx)

```bash
python3 -c "
import csv
with open('/mnt/ValuesWork/data/filename.csv') as f:
    reader = csv.reader(f)
    for i, row in enumerate(reader):
        if i < 50:  # First 50 rows for overview
            print(row)
"
```

#### For Each Document, Extract:

```
DOCUMENT EXTRACT: [filename]
Source type: [paper/interview/note/grant/highlight/data]

BIBLIOGRAPHIC INFO:
  Authors: [if applicable]
  Title: [document title]
  Year: [publication year]
  Venue: [journal/conference/publisher]
  DOI/ISBN: [if available]

KEY FINDINGS:
  1. [Finding with page/section reference]
  2. [Finding with page/section reference]
  ...

KEY QUOTES: (verbatim, with page numbers)
  1. "[Quote]" (p. X)
  2. "[Quote]" (p. X)
  ...

ARGUMENTS:
  - Main argument: [summary]
  - Supporting arguments: [list]
  - Counter-arguments acknowledged: [list]

METHODOLOGY: [if applicable]
  - Approach: [qualitative/quantitative/mixed/theoretical]
  - Data: [what data was used]
  - Limitations: [stated limitations]

CHAPTER RELEVANCE:
  Primary: Chapter [N] - [reason]
  Secondary: Chapter [N] - [reason]
  Tertiary: Chapter [N] - [reason]

POTENTIAL USES:
  - Opening hook: [Y/N - if yes, describe]
  - Key evidence: [for which argument]
  - Counter-argument: [for which chapter]
  - Case study: [Y/N - describe]
  - Quote for epigraph: [Y/N - which quote]

BIBTEX ENTRY:
  [Generate BibTeX entry following Bibliography.md conventions]
```

### Step 3: Cross-Reference and Map

After extracting from all documents, build a cross-reference map:

#### Evidence Map by Chapter

For each chapter in the Book Bible:

```
CHAPTER [N]: [Title]

EVIDENCE AVAILABLE:
  Strong evidence:
    - [source] → [finding] → [how it supports this chapter's argument]
  Supporting evidence:
    - [source] → [finding] → [supporting role]
  Counter-evidence:
    - [source] → [finding] → [what it challenges]

NARRATIVE MATERIAL:
  Opening hooks:
    - [source] → [scene/moment/quote that could open this chapter]
  Human stories:
    - [source] → [person/case that illustrates the chapter's theme]
  Case studies:
    - [source] → [detailed example for analysis]

GAPS IDENTIFIED:
  - [What evidence is missing for this chapter's argument]
  - [What types of sources would strengthen the chapter]

NEW CONNECTIONS:
  - [Unexpected links between sources that suggest new angles]
```

#### Theme Map

Identify themes that cut across multiple sources:

```
THEME: [theme name]
  Sources: [list of sources touching this theme]
  Chapters: [chapters where this theme is relevant]
  Strength: [strong consensus / emerging / contested]
  Note: [any surprising patterns]
```

#### Contradiction Map

Flag where sources disagree:

```
CONTRADICTION: [description]
  Source A: [position] ([citation])
  Source B: [position] ([citation])
  Resolution: [how to handle in the book: acknowledge both, adjudicate, present as open question]
  Relevant chapter: [N]
```

### Step 4: Update the Bibliography

For every source processed:

1. Generate a BibTeX entry following `Bibliography.md` conventions
2. Check for duplicates against existing `references.bib`
3. Append new entries to `references.bib` (or present them for the author to add)

```
NEW BIBTEX ENTRIES:
  [list of entries to add to references.bib]

DUPLICATE CHECK:
  [any entries that may already exist under different keys]
```

### Step 5: Produce the Research Digest

Write the complete Research Digest as a structured document:

**Location:** `/mnt/ValuesWork/notes/research-digest.md` (or project directory)

```markdown
# Research Digest

Generated: [date]
Sources processed: [N]
New sources since last digest: [N]

## Inventory Summary
[Table of all files processed with status]

## Evidence Map by Chapter
[From Step 3]

## Theme Map
[From Step 3]

## Contradiction Map
[From Step 3]

## Individual Document Extracts
[From Step 2, ordered by chapter relevance]

## Bibliography Updates
[New BibTeX entries]

## Recommended Actions
1. [Most impactful action: e.g., "Chapter 2 now has strong evidence from 3 new papers; ready for drafting"]
2. [Second action]
...

## Gaps Requiring Additional Research
1. [Gap description] → Suggested search: [search terms or source types]
2. ...
```

### Step 6: Present and Confirm

Present the Research Digest summary to the author with:

1. **Headlines:** Most significant findings across all materials
2. **Chapter readiness:** Which chapters now have enough evidence to write or revise
3. **Surprises:** Unexpected connections or contradictions discovered
4. **Gaps:** What is still missing
5. **Recommended next step:** Typically, run `UpdateFromResearch` to revise the Book Bible

**Pause:** Ask the author:
- Does the chapter mapping look right?
- Any sources assigned to the wrong chapter?
- Ready to update the Book Bible and chapters? (→ triggers `UpdateFromResearch` workflow)

## Incremental Ingestion

When run again after new materials are added:

1. Compare the current file inventory against the previous Research Digest
2. Process only new or modified files
3. Merge new extracts into the existing Research Digest
4. Update the evidence map, theme map, and contradiction map
5. Re-evaluate chapter readiness

This allows the author to add materials gradually and re-run ingestion without reprocessing everything.

## Handling Large Document Sets

If the research directory contains more documents than can be processed in a single session:

1. **Prioritise by chapter:** Process documents for the next chapter to be written first
2. **Prioritise by type:** Papers and interviews first (highest evidence density), then notes and highlights
3. **Batch processing:** Process 5-10 documents per session, saving progress in the Research Digest
4. **Track progress:** Mark each file as `ingested` or `pending` in the digest inventory
