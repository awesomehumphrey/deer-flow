# Writing "Human Values in Software" with DeerFlow

Your step-by-step guide for using DeerFlow to write the book, from first install to finished chapters.

## Part 0: Prerequisites

Before starting, you need:

- **Docker** (or Apple Container on macOS) installed and running
- **Node.js 22+** and **pnpm** installed
- **uv** (Python package manager) installed
- **nginx** installed
- **AWS credentials** configured (for Claude models via Bedrock)

## Part 1: First-Time Setup

### 1.1 Install Dependencies

```bash
cd ~/Documents/GitHub/deer-flow
make check      # verifies all prerequisites are present
make install    # installs backend (uv sync) and frontend (pnpm install)
```

### 1.2 Pull the Sandbox Container Image

DeerFlow runs agent code inside an isolated container. Pull the image before first use:

```bash
make setup-sandbox
```

### 1.3 Verify Configuration

Your `config.yaml` is already configured with:

- **Sandbox:** AIO container-based (`src.community.aio_sandbox:AioSandboxProvider`)
- **Research mount:** `~/Documents/ValuesWork` mounted at `/mnt/ValuesWork/` (read-write)
- **Models:** Claude Sonnet 4.6 and Claude Opus 4.6 via AWS Bedrock (ap-southeast-2)
- **Skills mount:** `skills/` directory mounted at `/mnt/skills/` (read-only, automatic)

The relevant section of `config.yaml`:

```yaml
sandbox:
  use: src.community.aio_sandbox:AioSandboxProvider
  mounts:
    - host_path: /Users/int21h/Documents/ValuesWork
      container_path: /mnt/ValuesWork
      read_only: false
```

### 1.4 Verify Skills Are Present

Two custom skills power the book writing:

```
skills/public/human-values-book/SKILL.md     # Book-specific context
skills/public/narrative-nonfiction/           # Writing methodology (16 files)
```

Both are in `skills/public/` and enabled by default. You can confirm in the DeerFlow UI under Settings > Skills after starting the server.

### 1.5 API Keys

Your `.env` file needs:

| Key | Purpose |
|-----|---------|
| `AWS_ACCESS_KEY_ID` | Claude models via Bedrock |
| `AWS_SECRET_ACCESS_KEY` | Claude models via Bedrock |
| `AWS_REGION` | Bedrock region (ap-southeast-2) |
| `TAVILY_API_KEY` | Web search (used by deep-research skill) |
| `JINA_API_KEY` | Web page fetching (used by deep-research skill) |

These are already configured in your `.env`.

## Part 2: Starting DeerFlow

```bash
cd ~/Documents/GitHub/deer-flow
make dev
```

This starts four services:

| Service | Port | Role |
|---------|------|------|
| LangGraph server | 2024 | Agent runtime |
| Gateway API | 8001 | Skills, models, memory management |
| Next.js frontend | 3000 | Web interface |
| Nginx reverse proxy | 2026 | Unified entry point |

Open **http://localhost:2026** in your browser.

To stop everything: press `Ctrl+C` in the terminal, or run `make stop` from another terminal.

### Choosing a Mode

Each mode adds capabilities on top of the previous one. The trade-off is speed vs. depth.

| Mode | What it enables | When to use it |
|------|-----------------|----------------|
| **Flash** | Direct responses, no extended reasoning | Quick lookups: "What's in the drafts folder?" |
| **Thinking** | Extended reasoning (chain-of-thought) | Conversational work: Interview, light Explore sessions |
| **Pro** | Thinking + structured task tracking (todo lists) | Multi-step workflows: IngestResearch, BuildBible, WriteChapter, deep Explore, medium Revise |
| **Ultra** | Pro + parallel sub-agents (delegates work) | Batch processing: IngestResearch (many documents), UpdateFromResearch, heavy Revise across chapters |

**Why it matters:**

- **Pro** gives the agent a todo list it can use to track progress through complex workflows. Without this (in Thinking mode), the agent may lose track of where it is in a 9-step process like WriteChapter.
- **Ultra** lets the agent spawn parallel sub-agents to do work simultaneously. This is valuable for ingesting a large research corpus (sub-agents read different documents in parallel), assessing the impact of new research across all chapters at once (UpdateFromResearch), and heavy cross-chapter revisions. Overkill for sequential work like writing a single chapter.
- **Thinking** is enough for conversational workflows (Interview, quick explorations) where the agent does not need to track multi-step progress.

Each phase below specifies which mode to use.

### Choosing a Model

| Model | Strengths | Best for |
|-------|-----------|----------|
| **Claude Sonnet 4.6** | Faster, cheaper | Research ingestion, outlines, iteration, light Revise |
| **Claude Opus 4.6** | Deeper reasoning, better prose | Writing chapters, building the bible, complex analysis, Interview, Explore |

When in doubt, use Opus. Use Sonnet when speed matters more than depth (e.g., processing a large batch of documents).

## Part 3: The Book Writing Workflow

The workflow has nine phases. The first time through, follow them in order (skipping optional phases if you prefer). After that, you will iterate between phases as you add materials, explore ideas, and write chapters.

### Phase 1: Gather Research Materials

Before asking DeerFlow to do anything, populate the research folders. The more material the agent has, the better the book plan and chapters will be. You do not need everything on day one; you can add materials incrementally and re-run IngestResearch. But the richer the initial set, the stronger the first Book Bible.

#### Folder structure

```
~/Documents/ValuesWork/
  papers/       <- Research publications (yours and others)
  interviews/   <- Developer interviews, user study data
  notes/        <- Research notes, ideas, rough outlines
  data/         <- Datasets, analysis results
  bio/          <- CV and biographical information
  grants/       <- Grant applications and reports
  highlights/   <- Reading highlights and annotations
  drafts/       <- OUTPUT: DeerFlow writes chapter drafts here (leave empty)
```

These folders are automatically available inside DeerFlow's sandbox at `/mnt/ValuesWork/`.

#### What to gather: checklist

Work through this list. Tick off what you have; skip what you don't. Items are grouped by priority.

**Priority 1: Core research (gather these first)**

- [ ] Your publications as PDFs or .tex files:
  - "Automated detection, categorisation and developers' experience with violations of honesty in mobile apps" (Empirical SE, 2023)
  - "A Vision for Value-Aligned AI-Driven Systems" (AIware 2025)
  - "ChroniUXMag: A Persona-Driven Framework for Inclusive mHealth Requirements Engineering"
  - Stack Overflow analysis of values violations
  - Android API investigation linking values violations to security
  - Any other publications relevant to the book's themes
- [ ] BibTeX files (.bib) for your publications (if you have them; the agent can generate entries from PDFs if not)
- [ ] Your DECRA application (PDF or Word)
- [ ] John's DP20 grant application
- [ ] FLOSS ICSE proposal and final report

**Priority 2: Evidence and data**

- [ ] Developer interview transcripts (text files, Word docs, or PDFs; if you only have audio, provide any notes or summaries you made)
- [ ] User study data: transcripts, survey results, analysis summaries
- [ ] Datasets and analysis results (CSV, Excel, or summary documents) from your empirical studies
- [ ] OVIS lab papers by collaborators that are relevant to the book's argument (PDFs)

**Priority 3: Context and framing**

- [ ] Your CV or academic bio (helps the agent write about your research journey accurately)
- [ ] Reading highlights and annotations from key books:
  - Brian Christian, *The Alignment Problem* (Kindle highlights export, margin notes, or a summary of what struck you)
  - John Lennox, *2084* (same)
  - Any other books you want to reference or that shaped your thinking
- [ ] Research notes, memos, or rough outlines you have written about the book's themes (any format)
- [ ] Conference presentation slides (especially the AIware talk, which is an anecdote in the book)
- [ ] Teaching materials related to the book's topics (e.g., the privacy policy task you give students)

**Priority 4: Nice to have**

- [ ] Key papers by other researchers that you consider essential reading for the book's argument (the agent can find many of these via `deep-research`, but providing them directly ensures they are ingested accurately)
- [ ] Blog posts, essays, or public writing you have done on these topics
- [ ] Any existing book outlines, chapter drafts, or proposal documents
- [ ] Emails or messages that capture important conversations with collaborators (redact as needed)

#### Supported formats

The agent can read: PDF, plain text (.txt, .md), LaTeX (.tex), BibTeX (.bib), Word (.docx), CSV, Excel (.xlsx), and most common document formats. For reading highlights, export from Kindle or your reading app as text if possible; screenshots of annotations are harder to process.

#### What you do NOT need to provide

- **External academic literature.** The agent uses the `deep-research` skill to find and cite papers by other researchers. Your ValuesWork folder is for *your* materials and materials you specifically want to ground the book in.
- **A finished outline.** The Interview and BuildBible workflows create the book plan from your research. Any rough outlines you have are useful input, but the agent will build the definitive structure.
- **Perfect organisation.** Put files in roughly the right folders. The agent will inventory everything and ask you to confirm before processing.

> **Note:** These personal materials are the *grounding* for the book, not the totality of its research. The agent uses the **`deep-research`** skill to conduct web research, search academic literature, and find external sources as needed. Your ValuesWork folder provides the personal foundation; the broader intellectual landscape is built on top of it.

### Phase 2: Ingest and Analyse the Research

Start a **new chat** in DeerFlow. Select **Ultra** mode and **Claude Opus 4.6**. (Ultra lets the agent spawn parallel sub-agents to read and analyse multiple documents simultaneously rather than processing them one by one. With 14+ papers, grants, and reading highlights, this is a significant speedup. Opus for careful reading. If you only have a handful of documents, Pro mode is sufficient.)

Type:

> Analyse the research materials in the ValuesWork folder.

The agent will:

1. Scan all subdirectories and inventory every file
2. Read each document (PDFs, text, CSVs, BibTeX files)
3. For each document, extract: key findings, important quotes, arguments, methodology, and which chapters it is relevant to
4. Build cross-reference maps: evidence grouped by chapter, recurring themes, contradictions between sources
5. Generate BibTeX entries for a master `references.bib`
6. Produce a **Research Digest** saved to `/mnt/ValuesWork/notes/research-digest.md`

The agent will pause after inventorying files to confirm which ones to process. It will present a summary when finished.

This is the foundation for everything that follows. The chapter structure, the evidence base, and the argument of the book all emerge from the actual research, not from guesses. The Research Digest will also identify evidence gaps, which the agent addresses using the **`deep-research`** skill in later phases.

### Phase 3: Interview

Switch to **Thinking** mode, **Claude Opus 4.6**. (The interview is conversational; no task tracking needed. Opus gives deeper, more insightful questions.)

In the **same chat thread**, type:

> Interview me about my book Human Values in Software. Use the research digest to inform your questions.

The agent loads your book context from `human-values-book/SKILL.md` (author bio, anecdotes, thesis, terminology) and the Interview workflow from `narrative-nonfiction/Workflows/Interview.md`.

It will ask you structured questions about:

- Your thesis and what you want the reader to take away
- Your audience and how technical to be
- Your personal stories and how they connect to the argument
- Which research findings matter most to you
- Tone, voice, and how you want the book to feel
- How chapters should flow

Because the research has already been ingested, the agent can ask specific questions grounded in your actual papers and evidence, not generic questions.

**Output:** A structured interview document capturing your vision across all 7 narrative layers.

### Phase 4: Explore (Optional)

Use **Thinking** mode and **Claude Opus 4.6** for quick explorations. Switch to **Pro** if the exploration is deep and multi-faceted (the task tracking helps the agent keep its thread of reasoning organised).

After the interview, you may want to think through specific ideas, connections, or questions before building the Bible. Type something like:

> Explore the connection between dark patterns and security vulnerabilities.

Or:

> What if software values alignment and AI alignment share a common root problem?

The agent reads `Workflows/Explore.md` and follows the intellectual thread:

1. Frames the question and gathers relevant context from the Research Digest and interview
2. Follows the thread through evidence, counter-arguments, and implications
3. Surfaces surprises and unexpected connections
4. Assesses what the exploration means for the book's argument and structure
5. Produces exploration notes with findings, implications, and suggested next steps

Exploration is deliberately open-ended. It is the divergent thinking space: testing ideas before committing to a plan. You can run multiple Explore sessions on different questions.

**Output:** Exploration notes saved to `/mnt/ValuesWork/notes/exploration-[slug].md`. Includes findings, surprises, implications for the book, and new questions raised.

Explore is useful at any point in the process, not just here. Use it between chapters, after ingesting new research, or when you are stuck.

### Phase 5: Build the Book Bible

Switch to **Pro** mode, **Claude Opus 4.6**. (Building the bible is an 11-step process; task tracking keeps it on track. Opus gives the depth needed for intellectual journey architecture and mystery design.)

Still in the **same chat thread**, type:

> Build the book bible for Human Values in Software based on our interview and the research digest.

The agent reads `Workflows/BuildBible.md` and constructs the master plan:

- **Intellectual journey architecture**: your research arc from initial assumption to final thesis
- **Full chapter map**: every chapter with all 7 narrative layers specified (Meaning, Intellectual Journey, Narrative Thread, Mystery, Landscape, Relationships, Prose)
- **Mystery architecture**: what is revealed when, how information builds across the book
- **Landscape framework**: institutional, historical, and economic context needed
- **Relationship arcs**: between you and the subject, between people in the stories, between ideas
- **Prose strategy**: aesthetic profile, rhetorical figure deployment plan
- **Verification criteria**: checkable criteria for the book and each chapter

This replaces the provisional chapter scaffold in the skill file. The chapter structure, parts, and ordering are now grounded in the actual research evidence.

**Output:** A Book Bible PRD document. This is the living reference for all writing.

### Phase 6: Write Chapters

Use **Pro** mode, **Claude Opus 4.6**. (WriteChapter is a 9-step process with evidence planning, layer articulation, composition, and 5 critic passes. Task tracking is essential. Opus writes the best prose.)

Now write, one chapter at a time. Type:

> Write chapter 1 following the book bible.

The agent reads `Workflows/WriteChapter.md` and:

1. Loads the chapter plan from the Book Bible
2. Checks the Research Digest for all evidence mapped to this chapter
3. Verifies all planned sources exist in `references.bib`
4. Builds a layer articulation map (what each of the 7 layers does in this chapter)
5. Plans rhetorical figure deployment (where to use specific figures for maximum impact)
6. Writes the prose following your aesthetic profile
7. Manages information and mystery across the chapter
8. Runs the **anti-cliche sweep** (catches generic AI prose, dead phrases, unsupported claims)
9. Runs **5 mandatory critic passes**:
   - Layer Auditor (structural completeness)
   - Evidence Inspector (source attribution and credibility)
   - Rhetoric Examiner (figure deployment and prose rhythm)
   - Freshness Inspector (cliche detection, concrete specificity)
   - Reader Surrogate (engagement, clarity, forward momentum)
10. Saves the draft to `/mnt/ValuesWork/drafts/`

**Output:** The chapter prose, layer notes, critic pass summary with confidence ratings, references used, new BibTeX entries, and a recommendation for what to write next.

For high-stakes chapters (opening, midpoint, climactic), the agent also runs 3 optional critics: Subtext Analyst, Continuity Editor, and Pacing Surgeon.

### Phase 7: Add More Materials and Update

Switch to **Ultra** mode, **Claude Opus 4.6**. (UpdateFromResearch needs to assess impact across all chapters simultaneously. Ultra's parallel sub-agents can evaluate multiple chapters at once rather than working through them one by one.)

As your research continues, add new documents to the `~/Documents/ValuesWork/` folders. Then type:

> I have added new papers. Process them and update the book.

This chains two workflows:

1. **IngestResearch** (incremental): only reads new or changed files, merges into the existing Research Digest
2. **UpdateFromResearch**: assesses the impact on each chapter, updates the Book Bible, and for already-drafted chapters produces targeted **revision briefs** (what to add, change, or remove) rather than rewriting from scratch

The agent will:

- Rate the impact on each chapter (HIGH / MEDIUM / LOW)
- Update all 7 narrative layers in the Book Bible where needed
- Increment the Bible version and log the changes
- For drafted chapters: produce revision briefs with specific insertion points, suggested text, and citations
- Flag any contradictions between new evidence and existing content for your decision
- Assess whether the book structure itself needs changes (new chapters, merges, splits, reordering)

### Phase 8: Revise

Use **Pro** mode, **Claude Opus 4.6** for most revisions. For light prose polish, **Thinking** mode with **Sonnet** is faster and sufficient. For heavy revisions spanning multiple chapters, consider **Ultra**.

To revise an existing chapter based on critic feedback, a revision brief, or new research:

> Revise chapter 1 based on the critic feedback.

Or more targeted:

> Integrate the new OVIS lab paper on transparency into chapter 4.

Or for prose polish:

> Polish the prose in chapter 2, section 3.

The agent reads `Workflows/Revise.md` and applies targeted changes:

1. Identifies the revision input (critic feedback, revision brief, author directive, new evidence, or consistency fix)
2. Reads the existing draft and identifies what needs to change
3. Plans the changes explicitly before making them
4. Applies additions, revisions, removals, and restructuring as needed
5. Runs the anti-cliche sweep on new or changed text only
6. Runs scoped critic passes targeted to the type of revision (not the full 5-8 pass sequence)
7. Updates the chapter's layer summary, references, and critic scores
8. Saves the revised draft

The Revise workflow is lighter than WriteChapter because it works with what exists rather than building from scratch. It runs only the critic passes relevant to the revision type, and only on changed sections.

**When to use Revise vs. WriteChapter:** Use Revise for targeted changes to an existing draft. Use WriteChapter only when a chapter needs to be fundamentally rewritten from the ground up (e.g., the core argument has changed). If a revision escalates beyond 8-10 individual changes, the agent will flag this and recommend switching to WriteChapter.

## Part 4: The Iterative Loop

Once the initial bible and first chapters are written, the ongoing process is:

```
Add documents to ~/Documents/ValuesWork/
        |
        v
"Analyse the new materials"          --> IngestResearch (incremental)
        |
        v
"Explore [question or connection]"   --> Explore (optional, but valuable)
        |
        v
"Update the book from the research"  --> UpdateFromResearch
        |                                 (updates bible + revision briefs)
        v
"Write chapter N" / "Revise chapter N"
        |
        |-- New chapter?   --> WriteChapter (initial composition)
        |-- Existing draft? --> Revise (targeted changes from revision briefs)
        |
        v
Add more documents, repeat
```

Each cycle:

- New evidence is ingested incrementally (only new or changed files)
- The Book Bible evolves with each update (versioned, with a change log)
- Exploration sessions between ingestion and writing help the author think through implications before committing to changes
- New chapters are written with WriteChapter (full composition from the Bible)
- Existing chapters get targeted revision through Revise (not full rewrites)
- The Research Digest, Exploration Notes, and Update Summaries form a record of how the book's evidence base and argument grew over time

## Part 5: Quick Command Reference

| What you want | What to type |
|---|---|
| Analyse all research materials | "Analyse the research materials in the ValuesWork folder" |
| Process only new files | "I have added new papers, process them" |
| Plan the book (interview) | "Interview me about my book Human Values in Software" |
| Explore an idea or connection | "Explore the connection between dark patterns and security vulnerabilities" |
| Think through implications | "What if software values alignment and AI alignment share a common root?" |
| Create the master plan | "Build the book bible based on our interview and the research digest" |
| Update plan from new research | "Update the book from the research" |
| Write a chapter | "Write chapter 3 following the book bible" |
| Write just the opening | "Draft the opening scene for chapter 1" |
| Revise a chapter | "Revise chapter 1 based on the critic feedback" |
| Integrate a specific paper | "Integrate the AIware 2025 paper into chapter 7" |
| Polish prose | "Polish the prose in chapter 2, section 3" |
| Apply a revision brief | "Apply the revision brief for chapter 4" |
| Check consistency | "Review the draft of chapter 2 for consistency with the book bible" |

## Part 6: Practical Tips

### Thread Management

- **Use the same thread** for related work (e.g., Ingest -> Interview -> BuildBible -> first few chapters). State persists across messages within a thread.
- **Start a new thread** when the context gets too long, when switching to a different phase of work, or when you want a fresh start on a chapter.
- If starting a new thread for chapter writing, tell the agent to load the Book Bible first: "Read the book bible and then write chapter 3."

### Where Files End Up

| What | Location on your machine |
|------|--------------------------|
| Chapter drafts | `~/Documents/ValuesWork/drafts/` |
| Research Digest | `~/Documents/ValuesWork/notes/research-digest.md` |
| Exploration notes | `~/Documents/ValuesWork/notes/exploration-[slug].md` |
| Update summaries | `~/Documents/ValuesWork/notes/update-summary-[date].md` |
| Master bibliography | `~/Documents/ValuesWork/references.bib` |
| Book Bible | Agent workspace (also ask the agent to save a copy to `~/Documents/ValuesWork/notes/`) |

### Agent Pauses

The agent is designed to pause at key decision points and ask for your input:

- After inventorying research files (before processing)
- After assessing the impact of new research on each chapter (before updating)
- When contradictions are found between new evidence and existing content
- When structural changes to the book are recommended
- **When a chapter needs a personal anecdote, story, or memory** that is not already in the book-specific skill file or Research Digest
- **When biographical details need verification** (dates, names, what happened at a specific event)
- When a revision requires your judgment on how to handle competing interpretations

The agent will not invent biographical details or fabricate personal stories. If it needs something only you know, it will ask. The more specific you are in your answers, the better the prose will be.

### Logs

DeerFlow logs are saved to:

```
~/Documents/GitHub/deer-flow/logs/
  langgraph.log    # Agent runtime
  gateway.log      # API gateway
  frontend.log     # Web interface
  nginx.log        # Reverse proxy
```

### Stopping and Restarting

```bash
# Stop
make stop

# Or Ctrl+C in the terminal where make dev is running

# Restart
make dev
```

Chat history is persisted in a SQLite database (`checkpoints.db`). Your threads and conversations survive restarts.

## Part 7: What the Skills Do

Two skills work together:

### human-values-book

Provides **book-specific context** that the agent uses to understand your project:

- Author biography, research focus, and personal anecdotes
- Core thesis and terminology
- Target audience
- Aesthetic profile selection (60% Zuboff + 40% Christian)
- The seven narrative layers (summary and link to full definitions)
- Provisional chapter structure (to be rebuilt from research)
- Known publications, grants, and key reading highlights
- British English and no-em-dashes rules
- Research directory paths and scope clarification

### narrative-nonfiction

Provides the **writing methodology** with 16 files:

| File | Purpose |
|------|---------|
| `SKILL.md` | Index and workflow routing |
| `NarrativeLayers.md` | 7-layer system for non-fiction |
| `IntellectualJourneyFramework.md` | Research arc construction (adapted from Storr) |
| `AestheticProfiles.md` | Voice profiles (Zuboff, Christian, O'Neil, Gladwell, Lewis, Solnit) |
| `NonfictionStructures.md` | Book and chapter structural frameworks |
| `AntiCliche.md` | Freshness enforcement for non-fiction prose |
| `Critics.md` | Multi-pass review system (8 critic profiles) |
| `RhetoricalFigures.md` | 125 rhetorical figures catalogue |
| `Bibliography.md` | BibTeX conventions, citation style, reference workflow |
| `Workflows/IngestResearch.md` | Analyse research materials into a structured digest |
| `Workflows/Interview.md` | Extract author vision |
| `Workflows/Explore.md` | Follow intellectual threads, test ideas, discover connections |
| `Workflows/BuildBible.md` | Create the book plan |
| `Workflows/UpdateFromResearch.md` | Update the bible and chapters from new research |
| `Workflows/WriteChapter.md` | Initial composition: transform plan into prose |
| `Workflows/Revise.md` | Targeted revision of existing chapter drafts |

The agent loads these files progressively as needed. You do not need to reference them directly; the agent reads them when your message matches the workflow triggers.
