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
skills/public/narrative-nonfiction/           # Writing methodology (14 files)
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

The chat input bar has mode options. Use:

| Mode | Best for | What it enables |
|------|----------|-----------------|
| **Flash** | Quick questions, lookups | Minimal reasoning |
| **Thinking** | Interview, brainstorming, exploring ideas | Extended reasoning |
| **Pro** | BuildBible, WriteChapter, IngestResearch | Planning with task tracking |
| **Ultra** | UpdateFromResearch, multi-chapter work | Planning + parallel sub-agents |

### Choosing a Model

Both models are available in the model selector:

| Model | Best for |
|-------|----------|
| **Claude Sonnet 4.6** | Faster responses; good for research ingestion, outlines, iteration |
| **Claude Opus 4.6** | Deeper reasoning; best for writing prose, building the bible, complex analysis |

## Part 3: The Book Writing Workflow

The workflow has seven phases. The first time through, follow them in order. After that, you will iterate between phases 3-7 as you add materials and write chapters.

### Phase 1: Gather Research Materials

Before asking DeerFlow to do anything, populate the research folders:

```
~/Documents/ValuesWork/
  papers/       <- Your publications, OVIS lab papers, cited works (PDFs, .tex, .bib)
  interviews/   <- Developer interviews, user study transcripts
  notes/        <- Research notes, ideas, rough outlines
  data/         <- Datasets, analysis results (CSV, Excel)
  bio/          <- Your CV, biographical information
  grants/       <- DECRA application, John's DP20, FLOSS ICSE proposal/report
  highlights/   <- Reading highlights (Brian Christian, John Lennox, etc.)
  drafts/       <- OUTPUT: DeerFlow writes chapter drafts here
```

Put everything you have in the appropriate folders. The more material the agent has, the better the book plan and chapters will be.

These folders are automatically available inside DeerFlow's sandbox at `/mnt/ValuesWork/`.

> **Note:** These personal materials are the *grounding* for the book, not the totality of its research. The agent will also conduct web research, search academic literature, and cite external works as needed. Your ValuesWork folder provides the personal foundation; the broader intellectual landscape is built on top of it.

### Phase 2: Ingest and Analyse the Research

Start a **new chat** in DeerFlow. Select **Pro** mode and **Claude Opus 4.6**.

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

This is the foundation for everything that follows. The chapter structure, the evidence base, and the argument of the book all emerge from the actual research, not from guesses. The Research Digest will also identify evidence gaps, which the agent addresses through web research and external literature review in later phases.

### Phase 3: Interview

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

### Phase 4: Build the Book Bible

Still in the **same chat thread**, type:

> Build the book bible for Human Values in Software based on our interview and the research digest.

The agent reads `Workflows/BuildBible.md` and constructs the master plan:

- **Intellectual journey architecture** — your research arc from initial assumption to final thesis
- **Full chapter map** — every chapter with all 7 narrative layers specified (Meaning, Intellectual Journey, Narrative Thread, Mystery, Landscape, Relationships, Prose)
- **Mystery architecture** — what is revealed when, how information builds across the book
- **Landscape framework** — institutional, historical, and economic context needed
- **Relationship arcs** — between you and the subject, between people in the stories, between ideas
- **Prose strategy** — aesthetic profile, rhetorical figure deployment plan
- **Verification criteria** — checkable criteria for the book and each chapter

This replaces the provisional chapter scaffold in the skill file. The chapter structure, parts, and ordering are now grounded in the actual research evidence.

**Output:** A Book Bible PRD document. This is the living reference for all writing.

### Phase 5: Write Chapters

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

### Phase 6: Add More Materials and Update

As your research continues, add new documents to the `~/Documents/ValuesWork/` folders. Then type:

> I have added new papers. Process them and update the book.

This chains two workflows:

1. **IngestResearch** (incremental) — only reads new or changed files, merges into the existing Research Digest
2. **UpdateFromResearch** — assesses the impact on each chapter, updates the Book Bible, and for already-drafted chapters produces targeted **revision briefs** (what to add, change, or remove) rather than rewriting from scratch

The agent will:

- Rate the impact on each chapter (HIGH / MEDIUM / LOW)
- Update all 7 narrative layers in the Book Bible where needed
- Increment the Bible version and log the changes
- For drafted chapters: produce revision briefs with specific insertion points, suggested text, and citations
- Flag any contradictions between new evidence and existing content for your decision
- Assess whether the book structure itself needs changes (new chapters, merges, splits, reordering)

### Phase 7: Revise

To revise an existing chapter based on critic feedback or new research:

> Revise chapter 1 based on the critic feedback.

Or more targeted:

> Integrate the new OVIS lab paper on transparency into chapter 4.

The Revise workflow applies changes from revision briefs, runs the anti-cliche sweep and critic passes on changed sections, and updates the chapter's reference list.

## Part 4: The Iterative Loop

Once the initial bible and first chapters are written, the ongoing process is:

```
Add documents to ~/Documents/ValuesWork/
        |
        v
"Analyse the new materials"          --> IngestResearch (incremental)
        |
        v
"Update the book from the research"  --> UpdateFromResearch
        |                                 (updates bible + revision briefs)
        v
"Write chapter N"                    --> WriteChapter
        |                                 (uses updated bible + evidence)
        v
Add more documents, repeat
```

Each cycle:

- New evidence is ingested incrementally (only new or changed files)
- The Book Bible evolves with each update (versioned, with a change log)
- Drafted chapters get targeted revision briefs, not full rewrites
- The Research Digest and Update Summaries form a record of how the book's evidence base grew over time

## Part 5: Quick Command Reference

| What you want | What to type |
|---|---|
| Analyse all research materials | "Analyse the research materials in the ValuesWork folder" |
| Process only new files | "I have added new papers, process them" |
| Plan the book (interview) | "Interview me about my book Human Values in Software" |
| Create the master plan | "Build the book bible based on our interview and the research digest" |
| Update plan from new research | "Update the book from the research" |
| Write a chapter | "Write chapter 3 following the book bible" |
| Write just the opening | "Draft the opening scene for chapter 1" |
| Revise a chapter | "Revise chapter 1 based on the critic feedback" |
| Integrate a specific paper | "Integrate the AIware 2025 paper into chapter 7" |
| Explore an idea | "Explore the connection between dark patterns and security vulnerabilities" |
| Check consistency | "Review the draft of chapter 2 for consistency with the book bible" |
| Brainstorm examples | "Suggest concrete examples for the inclusion gap chapter" |

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
| Update summaries | `~/Documents/ValuesWork/notes/update-summary-[date].md` |
| Master bibliography | `~/Documents/ValuesWork/references.bib` |
| Book Bible | Agent workspace (also ask the agent to save a copy to `~/Documents/ValuesWork/notes/`) |

### Agent Pauses

The agent is designed to pause at key decision points and ask for your confirmation:

- After inventorying research files (before processing)
- After assessing the impact of new research on each chapter (before updating)
- When contradictions are found between new evidence and existing content
- When structural changes to the book are recommended

This keeps you in control of the book's direction.

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

Provides the **writing methodology** with 13 files:

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
| `Workflows/Interview.md` | Extract author vision |
| `Workflows/BuildBible.md` | Create the book plan |
| `Workflows/IngestResearch.md` | Analyse research materials into a structured digest |
| `Workflows/UpdateFromResearch.md` | Update the bible and chapters from new research |
| `Workflows/WriteChapter.md` | Transform plan into prose (also handles revision) |

The agent loads these files progressively as needed. You do not need to reference them directly; the agent reads them when your message matches the workflow triggers.
