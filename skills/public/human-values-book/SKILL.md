---
name: human-values-book
description: Custom skill for writing "Human Values in Software" by Dr. Humphrey O. Obie. Contains the evidence-grounded book structure, research context, aesthetic configuration, and chapter-specific instructions. Load this skill alongside narrative-nonfiction when working on any aspect of the book.
---

# Human Values in Software

## Overview

This skill provides the domain context for writing "Human Values in Software", a narrative non-fiction book about how software systems violate human values and how we can detect and prevent these violations. The writing methodology, layer system, and workflows come from the `narrative-nonfiction` skill; this file provides what is specific to _this_ book.

**Companion skill:** `narrative-nonfiction` (must be loaded alongside this skill for all writing work)

## Language Rules

These rules apply to all book output (chapter prose, exploration notes, revision briefs, the Book Bible, the Research Digest) and to book-specific documentation (this file, GETTING-STARTED.md).

Write in **British English** throughout: "behaviour" not "behavior", "recognise" not "recognize", "licence" not "license", "analyse" not "analyze".

Do **not** use em-dashes. Use commas, semicolons, colons, or restructure the sentence instead.

## Author Context

**Dr. Humphrey O. Obie**, Nigerian researcher from Delta State (southern Nigeria), where community is a core cultural value. Research Fellow at Monash University's Faculty of Information Technology, affiliated with HumaniSE Lab and Telstra Health, based in Melbourne, Australia. CTO of Herekind PTY LTD (from February 2025). Sessional Lecturer at Swinburne University.

**Career arc:** PhD at Swinburne (2020) → Research Fellow at Monash under ARC Laureate Professor John Grundy → Telstra Health (2022–present). Did not begin as a values researcher — transitioned from smart cities/IoT research (iSense project) to values-oriented software engineering after identifying the DECRA grant opportunity (DE260100190). Close collaborator with OVIS Lab.

**Research focus:**
- Human values in software engineering
- Automated detection of values violations (honesty, transparency, integrity)
- Developer experience with values violations
- One of the first researchers to pursue empirical, automated detection of human values violations in software systems
- PhD in Computer Science, H-index 10, 353 citations
- 2x ACM Distinguished Paper Awards: (1) "Characterising Human Aspects in Reviews of COVID-19 Apps" (MobileSoft 2022, with Mattia Fazzini et al.) and (2) "On the Violation of Honesty in Mobile Apps" (MSR 2022). Both presented at the same conference week in Pittsburgh, May 2022.
- Patented research

### Personal Anecdotes and Stories to Weave In

These are real experiences to draw on for narrative hooks and chapter openings. More will emerge from the Interview workflow; the list below is a starting set, not exhaustive.

**This list should grow throughout the writing process.** When a chapter needs a personal story, anecdote, or specific memory that is not listed here, ask the author directly. Do not invent or embellish biographical details.

1. **RMIT/Vervoe Terms and Conditions (c.2019–2020)**: Applied for Lecturer role at RMIT; required to complete a Vervoe AI-powered assessment. Read the T&Cs; found broad rights to use candidate data (responses, facial data, voice) for AI training and algorithmic prediction beyond the immediate recruitment purpose. Raised concerns with the Dean, who suggested using any platform with a video link. Walked away from the application. Parallel with Black Mirror's "Joan Is Awful" (S6E1, June 2023): dense T&Cs as consent-washing, obtaining technically-valid-but-substantively-meaningless consent. Key themes: pervasive consent-washing, T&Cs as vector of values violations, AI amplifying power asymmetry. Full details in `/mnt/ValuesWork/notes/anecdote-rmit-vervoe.md`. Email chain: `/mnt/ValuesWork/notes/Gmail - On Concerns with the Use of Vervoe for the Lecturer Position Interview.pdf`. **Use in**: Ch 2 (primary hook), Introduction, Ch 5, Ch 7.

2. **AIware Seoul (20 November 2025)**: Presented "A Vision for Value-Aligned AI-Driven Systems" at AIware 2025 (co-located with ASE 2025). Grand Hall 1, Grand Walkerhill Seoul, 17:06–17:11 KST. Last day, last session ("Responsible, Ethical, and Legal Dimensions of AIware"), mostly empty room. Key audience question: "What is the difference between model alignment and system alignment?" Answer with the 3am phone browsing example: aligned model embedded in exploitative system that extracts time-of-day data and targets users at moments of lowest cognitive defence. The empty room as metaphor: the field does not yet see system alignment as central. Full details in `/mnt/ValuesWork/notes/anecdote-aiware-seoul.md`. **Use in**: Introduction (opening scene), Ch 1, Ch 7, Ch 9.

3. **Student Privacy Policy Task**: Giving students the task of developing software to flag issues in privacy policies. Operationalises the detection research. Illustrates how values violations can be taught, detected, and made visible. **Use in**: Ch 2, Ch 8.

4. **Herekind**: Bereavement concierge service where author serves as CTO. A concrete example of building software that respects human values in a deeply sensitive, high-stakes context. Values-aligned product design in practice. **Use in**: Ch 4 (inclusion), Ch 9 (values-aligned systems).

5. **GrapheneOS**: Values-aligned mobile OS upholding autonomy, privacy, and security that mainstream operating systems violate at will. Case study of values-aligned software done right, and the security implications. **Use in**: Ch 5 (security-as-value), Ch 9 (values-aligned systems).

### CV and Bio

Include your CV and biographical information from `/mnt/ValuesWork/bio/` when writing author notes, preface, or back matter. Frame your research journey as a narrative arc throughout the book.

---

## Author Interview Findings (Complete — 8 Questions)

The following section captures the authoritative answers from the structured author interview conducted during the book-planning phase. These answers define the book's identity and must govern all subsequent writing, structuring, and editorial decisions.

### Q1: What is this book about?

The gap between the values we claim and the values software actually enforces — and the engineering solutions being built to close it. Software is not neutral; it always behaves according to someone's values, and those values are rarely the user's. This book is about making that visible and showing what can be done about it.

### Q2: Who is it for?

**Target reader:** Technically curious general readers, AI practitioners, and policymakers — modelled on Brian Christian's *The Alignment Problem* audience. People who sense something is wrong with their relationship to technology but lack the language and evidence to articulate it. Readers should not need a computer science degree to follow the argument. The book aims to give them eyes for what they've been living inside without seeing.

### Q3: What do critics get wrong?

Critics treat values as abstract philosophical principles or one-time compliance checks. Dr. Obie treats them as **engineering problems requiring engineering solutions**.

- The **VASS framework** says: "You are solving the wrong layer." Model alignment ≠ system alignment. The Five Pillars (measurable indicators, architectural integration, auditable by design, participatory alignment, accessible tools) reframe values as a systems engineering problem.
- The **DECRA grant** (DE260100190) says: "Here is how to solve the right layer." Four Research Tasks operationalise the vision: audit framework taxonomy (RT1), measurable value indicators with ML/Deep Belief Networks (RT2), static/dynamic analysis tools integrated into CI/CD pipelines (RT3), and validation (RT4).

Together: VASS provides the architectural vision; DECRA provides the engineering programme to realise it.

### Q4: Characters

The book uses a cast of real pseudonymised participants from interview research, plus the narrator and one hypothetical scenario device:

| Character | Level | Status | Role |
|-----------|-------|--------|------|
| **Dr. Obie** (narrator) | Research & vision | Real | Throughout — the researcher following a thread |
| **Cendo** | Production floor | Real, pseudonymised | Recurring — structural manufacture of dishonesty, cross-cultural values, leaving a company over culture |
| **Seth** | Design & architecture | Real, pseudonymised | Recurring — fence parable, values as project-level not personal, bounded transparency, classified projects |
| **Harry** | Operations & maintenance | Real, pseudonymised | Recurring — normalisation of violations ("it always happens to us"), root cause analysis, trusted access |
| **Cindy** | End-user impact | Hypothetical (from VASS paper) | Recurring illustrative device — 76-year-old woman, AI health app drift, not a real person |
| **Andrew** | Junior developer voice | Real, pseudonymised | Episodic — hierarchy overrides personal values, Facebook targeted ads after opting out |
| **Afzal** | Confessional/cultural | Real, pseudonymised | Episodic — honesty about mistakes, developer wellbeing, institutional support |

### Q5: Central Tension (Authoritative)

The book's central conflict operates on **three nested levels**:

1. **The reader's body** — they already feel the violation (3am browsing, the Terms and Conditions click, the app that knew too much). The book names what they already sense.
2. **The field's blind spot** — software engineering has been optimised for speed, reliability, and scale, but not for what products *do to people*. The field believes it builds tools; it actually builds value-laden systems that extract, manipulate, and exclude at scale, wrapped in Terms of Service.
3. **The model-versus-system distinction** — the AI alignment community is solving the wrong layer. Model safety ≠ system safety. A perfectly aligned model inside an exploitative system is still an exploitative system.

**Core friction:** What the field *believes* it is doing vs. what it is *actually* doing.

**Unresolved question that drives the book forward:** Will the field wake up before the damage becomes irreversible?

### Q6: Reader Transformation (Authoritative — Seven Perceptual Shifts)

By the end of the book, the reader should have undergone seven perceptual shifts, ordered from most accessible to most conceptually demanding:

1. **The architecture of extraction** — timing, sequencing, friction as deliberate design, not accident. (→ Cendo's chapter, dark patterns)
2. **System, not just the model** — look past the AI model to the wrapping system. (→ VASS chapter, intellectual core of the book)
3. **Terms and conditions as a weapon** — consent asymmetry; technically real, substantively meaningless. (→ Vervoe/RMIT, Joan Is Awful)
4. **The honesty gap in action** — stated values vs. actual design contradictions; the reader can name the pattern. (→ MSR 2022 honesty paper)
5. **The inclusion gap as evidence** — who was not in the room; absence as evidence of values violation. (→ COVID-19 apps, Seth's fence parable)
6. **The 3am moment** — cognitive-vulnerability targeting as designed, not accidental; visceral chapter. (→ emotional core)
7. **Values in every technical decision** — values are always present, never added on top; musician hearing chord progressions as capstone image. (→ capstone chapter)

**Closing thesis:** *From seeing software as neutral tools that sometimes behave badly to seeing software as value-laden systems that always behave according to someone's values — and those values are rarely the user's.*

**Back-cover sentence:** "Whose values does this serve?" — and now the reader can see the answer in the design itself.

**Craft note:** Seven shifts ordered from most accessible → most conceptually demanding = the right pedagogical arc. Early chapters hook through recognition; later chapters reward with a new way of seeing.

### Q7: The Research Thread (Authoritative — Six-Stage Discovery Arc)

The research enters the book as **discovery narrative** — each finding is a moment of discovery in the author's intellectual journey, not a citation. The register is: "I found this, it surprised me, it changed what I was looking for next." Technical detail is the story of how you came to know something, not a methods section. Numbers are revelations, not statistics. The taxonomy is a map of discovered territory. The framework is the architecture for a solution built because the problem demanded it.

**The six-stage research arc IS the book's spine:**

| Stage | Paper/Work | Discovery Moment | Register |
|-------|-----------|-----------------|----------|
| 1. The unexpected pattern | ICSE 2021 | "I was studying something else. The data kept showing me something I couldn't explain." | Surprise |
| 2. Signal, not noise | MSR 2022 (honesty) | "I needed to know if this was noise or signal. So I built a way to tell." | Structure |
| 3. The stakes become real | COVID-19 apps (MobileSoft 2022) | "If pandemic apps can't get this right, who can?" | Urgency |
| 4. The depth of the problem | Stack Overflow + Android APIs | "Developers aren't just building violations — they're normalising them." | Widening |
| 5. An architecture for the solution | VASS framework | "If the problem is structural, the solution must be too." | Possibility |
| 6. The path forward | DECRA audit vision | "Teaching machines to find what humans have been blind to." | Forward-looking |

**Dual influence:**
- **Zuboff stacking principle:** Findings accumulate like a legal brief — each piece of evidence builds on the last, the argument tightens, the reader feels the weight accumulate. The book earns its solutions by making the reader live through the problem.
- **Christian presence principle:** The narrator is not an authority delivering conclusions but a researcher following a thread, being surprised, revising, sometimes being wrong. The moments of self-correction (prior assumptions overturned, first categorisations inadequate, understanding of where the problem lives revised) are gold for narrative non-fiction — they make the narrator trustworthy.

**Key example of register difference:**
- Academic: "25% of app reviews contain values violations."
- This book: "One in four. I had expected violations to be edge cases — the bad actors, the careless startups. Instead, the data was showing me something structural."

### Q8: The Voice (Authoritative)

**Overall character:** A researcher who has spent years following a thread into territory much larger and more troubling than expected, now trying to show the reader what they found — not with academic distance, but with the urgency of someone who believes this matters and the patience to make sure the reader actually sees it.

**Core tone:** Warm but urgent. Patient in argument, urgent in stakes.

**Five registers the book moves between:**

1. **The curiosity register** (default mode) — warm, open, inviting. "I found something, and I think you need to see it too." How most paragraphs begin. How the reader comes to trust the narrator.

2. **The urgency register** — the stakes surface. 3am targeting, pandemic apps, 7 billion smartphone users. Not panic — the controlled voice of someone who has seen the data and knows what it means.

3. **The anger register** — rare, precise, earned. Not performative. Appears when the evidence makes any other response dishonest. The Vervoe walkout. The T&Cs that make violation legal. The empty room. When anger appears, the reader should feel it was *inevitable*, not chosen.

4. **The humour register** — dry, observational, sparing. The absurdity of clicking "I agree" to 47 pages of legalese. The quizzical looks in Seoul. Works by recognition — the reader laughs because they've been there, and the laugh sharpens the point rather than softening it.

5. **The explanatory register** — patient, analogy-driven, never condescending. Where VASS, the honesty taxonomy, and technical methodology enter. The reader feels they're being walked through a discovery, not taught a lesson. Christian's influence is strongest here.

**Rhythm principle:** Long, architecturally complex sentences when building the case (Zuboff's accumulative pressure). Short sentences when the point lands (Christian's clarity). The alternation is the heartbeat of the prose — the long sentence builds the case, the short sentence drives it home.

**Voice models:**

- **Brian Christian, *The Alignment Problem*** (gold standard): Technical research as human discovery. Present throughout, curious, surprised, patient. Dialogue, analogy, personal observation make abstract concepts concrete.
- **Shoshana Zuboff, *The Age of Surveillance Capitalism***: Moral urgency, systematic accumulation of evidence, the sense of unveiling something the reader has been living inside without seeing. But less dense, more conversational.
- **Rebecca Solnit**: The essayistic voice that moves between personal observation and structural analysis, the specific and the universal. The ability to make the reader see the familiar differently.

**The contract with the reader:** The author is not claiming to have all the answers. He is claiming to have followed a thread far enough to show the reader something they need to see. That is enough.

**Read-aloud test:** The book should sound like a conversation between someone who has been inside a problem and someone who has not, where the person inside is trying to show the other what they saw — not by dumping data, but by walking them through the experience of discovery. The reader should feel they are walking alongside the author, not being lectured at.

### Interview Cross-Participant Themes (from Developer Interviews)

These 16 themes emerged from the five pseudonymised interview participants and should thread through the narrative. The first 11 were confirmed in early synthesis; themes 12–16 were added after full transcript reads of Seth and Harry.

1. **Honesty at every SDLC phase** — unanimous; requirements dishonesty cascades through the entire lifecycle
2. **Transparency is nuanced** — Seth/Afzal allow temporary/partial opacity during development (managed opacity ≠ deception, but threshold matters)
3. **Curiosity = career survival** — all participants; Seth explicitly frames it as bounded by confidentiality obligations
4. **Hierarchy of stakeholders** — external client values take precedence (Afzal); hierarchy varies by participant
5. **Normalisation of violations** — Harry's "it always happens to us"; resignation rather than outrage
6. **Root cause analysis as ethical practice** — Harry and Seth both emphasise investigating why violations occur, not just fixing symptoms
7. **Validation threshold** — ~80% company standard (Seth); edge cases require experienced human judgement
8. **Personal violations as lived experience** — LinkedIn (Harry), Facebook ads (Andrew), McDonald's Wi-Fi (Cendo)
9. **Bad coding = values problem** — Seth's fence parable (removing fences without asking why they were built); Cendo's hard-coding under deadline pressure
10. **Structural dishonesty** — incentive-driven, not individual moral failure; the system manufactures the violation
11. **Developer wellbeing** — Afzal advocates institutional support; Cendo left a company over culture
12. **Fix verification methods vary** — QA confirmation reports (Seth); different teams have different verification cultures
13. **Prioritisation frameworks** — data privacy first, then financial harm (Afzal); participants hold implicit triage hierarchies
14. **Third-party libraries as invisible values violation** — Cendo: imported libraries collect unknown data; developer is unaware; indirect dishonesty invisible to the builder
15. **Version change without user notification as designed opacity** — Cendo/BMW: undisclosed system change is a transparency failure, not a technical necessity; framed as system design choice
16. **Data generation has outpaced ethics infrastructure** — Seth: "generating more data in the last 10 years than in all previous centuries combined"; the ethics lag is structural, not a failure of individual will

---

### Named Scenes (Developer Interviews — Final Complete Set)

These are the anchored scenes from interview participants. Each must be treated as a primary narrative unit, not background illustration. Chapter assignments are confirmed.

| Participant | Scene | Primary Chapter | Function |
|---|---|---|---|
| Seth | The fence parable | Ch 1 (signal) + Ch 6 (anchor) | Lack of curiosity as values problem; project-level not personal |
| Harry | "It always happens to us" | Ch 6 (anchor) | Normalisation; resignation not outrage |
| Andrew | Facebook ad opt-out failure | Ch 6 (personal violation) | Hierarchy overrides individual values |
| Afzal | Data centre shutdown; 6 months wasted on bad project | Ch 6 (confessional honesty) | Institutional honesty; developer wellbeing |
| Cendo | BMW/IFS version change; competitive internship; McDonald's Wi-Fi | Ch 6 (structural + personal) | Designed opacity; third-party library problem |

---

### Key Interview Content Per Participant

**Seth:**
- Fence parable: developers remove fences without asking why they were built = lack of curiosity as a values problem; connects to Winner's "Do Artifacts Have Politics?"
- Bad coding = values problem; bad commenting = undisclosed opacity (a form of dishonesty)
- Transparency is context-dependent: ~80% as working threshold; classified/commercial contexts require bounded opacity
- Independently articulates VASS logic without knowing the framework: violations need to be detectable and fixable at system level
- Fix verification via QA confirmation reports
- "Generating more data in the last 10 years than in all previous centuries combined" — ethics lag framing (use in Ch 7)
- Values are project-level, not personal moral choices

**Harry:**
- "It always happens to us" — only participant to frame normalisation so explicitly; resignation not outrage
- "Lied to the customer's face" — only participant to use explicit moral language in a professional context; breaks the normalisation and is therefore remarkable
- Root cause analysis as ethical practice: investigating why violations recur, not just patching them
- Independently articulates need for VASS/DECRA: standard violations list would help developers who lack vocabulary
- LinkedIn premium: charged after trial without prior notification; personal violation
- Personalised response from hierarchy = more credibility (management engaged with individuals, not just policies)

**Afzal:**
- Software should be accurate, unbiased, non-manipulative, privacy-respecting
- External client values take precedence over internal stakeholder preferences
- Violations = companies should be fined; advocates accountability mechanisms
- Ethical hackers for vulnerability detection
- Prioritisation: data privacy first, then financial harm
- Realistic timelines matter for ethical practice (rushed work = values shortcuts)
- Developer personal wellbeing should be institutionally supported, not individually managed

**Cendo:**
- BMW/IFS version change = undisclosed change = transparency failure as system design choice (not accident)
- Competitive internship culture overriding honesty: blame-shifting at integration; colleagues chose deception over accountability
- Team worked until 4am rather than hard-code under deadline pressure (ethical resistance to shortcut)
- Third-party libraries as hidden values violation: collect unknown data; developer is indirect participant in dishonesty they cannot see
- McDonald's Wi-Fi personal violation
- GDPR as surveillance of developer (ironic inversion)
- Additional values named: creativity, equality, privacy

**Andrew:**
- Facebook ad opt-out failure: opted out of personalised ads; Facebook continued serving them; central personal violation scene
- Hierarchy overrides individual developer values: the higher the role, the more institutional pressure
- Open source as partial accountability mechanism

---

## Source Materials

Your personal research materials are mounted at `/mnt/ValuesWork/`. This folder provides the grounding for the book: your own publications, interviews, grants, reading highlights, and lived experience. It is **not** the limit of the book's research scope. Use the **`deep-research`** skill to conduct web research, search academic literature, and find external sources appropriate to a serious academic trade book. Think of ValuesWork as the personal foundation; the broader intellectual landscape is built on top of it using `deep-research`.

```
/mnt/ValuesWork/
├── papers/
│   ├── Mine/          ← 13 publications by Dr. Obie (values violations, dark patterns, detection, privacy, security)
│   ├── Colleagues/    ← 6 papers by collaborators (Grundy, Khalajzadeh et al.)
│   └── Other authors/ ← Seminal works (Munn, Winner, Schwartz)
├── presentations/     ← AIware 2025 presentation (.pdf, .pptx, .txt)
├── interviews/        ← Developer interviews, user studies (to be populated)
├── notes/             ← Anecdote files, research notes, Research Digest output
├── data/              ← Datasets, analysis results (to be populated)
├── drafts/            ← OUTPUT: Chapter drafts written here
├── bio/               ← CV and biographical information
├── grants/            ← DECRA (DE260100190), DP20, FLOSS ICSE proposal and report
├── my_student_projects/ ← FLoS (ICSE SCORE 2023), Project 1 2023 (privacy policy ML)
└── highlights/        ← Reading highlights: 2084, The Alignment Problem, IT and Moral Values
```

## Aesthetic Profile

This book uses a **blended aesthetic profile** (see `narrative-nonfiction/AestheticProfiles.md`):

```
Profile: 45% Zuboff + 45% Christian + 10% Solnit
```

- **Zuboff:** Systematic institutional analysis with moral urgency. Long, architecturally complex sentences that mirror the systems described. Chapters build like legal briefs: evidence, analysis, implication. The moral weight accumulates; the reader feels the necessity of solutions.
- **Christian:** Genuine curiosity and accessibility. Conversations presented as dialogues. Analogies from unexpected domains. The author is present as a curious guide, not just an authority. The gold standard for making technical research feel like human discovery.
- **Solnit:** The essayistic voice that moves between personal observation and structural analysis, between the specific and the universal. The ability to make the reader see the familiar differently. Provides the movement between scales — a single app review and a global system, Delta State and Melbourne and Seoul — without the seams showing.

**Five voice registers** (see Q8 in Author Interview Findings for full descriptions):
1. **Curiosity** (default) — warm, inviting, "I found something, and I think you need to see it too"
2. **Urgency** — controlled, stakes-driven, "the data says this matters now"
3. **Anger** — rare, precise, earned by evidence, never performative
4. **Humour** — dry, observational, sparing; sharpens the point through recognition
5. **Explanatory** — patient, analogy-driven, never condescending; Christian's influence strongest

**Rhythm principle:** Long sentences build the case (Zuboff), short sentences drive the point home (Christian). The alternation is the heartbeat of the prose.

**Rhetorical figure emphasis:** Anaphora, Amplificatio, Antithesis, Periodic Sentence, Analogy, Paradox, Chiasmus
**Sentence length:** Variable; long (20–40 words) for systems analysis, medium (12–25 words) for human stories, short (5–12 words) when the evidence lands
**Pacing:** Deliberate and cumulative, with brisk narrative passages for human stories

## Core Thesis

Software systems routinely violate human values — values that are deeply human, historically grounded, and well theorised. These violations cause real harm to users. Through systematic research and automated detection, we can identify these violations and build a more value-aligned future.

**The central tension operates on three nested levels** (from Q5, authoritative):

1. **The reader's body** — they already feel the violation (3am browsing, the Terms and Conditions click, the app that knew too much). The book names what they already sense.
2. **The field's blind spot** — software engineering has been optimised for speed, reliability, and scale, but not for what products do to people. The field extracts, manipulates, and excludes at scale, wrapped in Terms of Service.
3. **The model-versus-system distinction** — the AI alignment community is solving the wrong layer. A perfectly aligned model inside an exploitative system is still an exploitative system. **Model safety ≠ System safety.**

**Core friction:** What the field *believes* it is doing vs. what it is *actually* doing.

**Unresolved question that drives the book:** Will the field wake up before the damage becomes irreversible?

**Closing thesis** (from Q6): *From seeing software as neutral tools that sometimes behave badly to seeing software as value-laden systems that always behave according to someone's values — and those values are rarely the user's.*

## Target Audience

Modelled on Brian Christian's *The Alignment Problem* readership:

- **Primary:** Technically curious general readers — people who sense something is wrong with their relationship to technology but lack the language and evidence to articulate it. No CS degree required.
- **Secondary:** AI practitioners, software developers, and product managers — who build these systems and want to build them better.
- **Tertiary:** Policymakers interested in tech ethics and regulation — who need to understand the distinction between model alignment and system alignment.
- **Academic crossover:** Researchers in adjacent fields (HCI, STS, digital ethics) who will engage with the evidence base.

**The reader should feel smart for following, never patronised.** The book gives them eyes for what they have been living inside without seeing.

## Narrative Architecture

### Dual-Thread Design

The book weaves two threads throughout:

1. **The Human Thread** — practitioners' lived experiences with values violations, told through pseudonymised characters (Cendo, Seth, Harry, Andrew, Afzal) and the hypothetical Cindy. These are the stories that make the reader *feel* what values violations mean.

2. **The Research Thread** — Dr. Obie's six-stage discovery narrative (Q7), where each paper is a moment of discovery, not a citation. This is the intellectual spine of the book.

The two threads braid: a human story raises a question; the research thread provides a revelation; the next human story deepens the implication. The reader moves between *feeling* the problem and *understanding* it.

### Key Design Principles

- **Opening image:** Dr. Obie reading the Vervoe Terms and Conditions during an RMIT recruitment process, seeing the extraction machine for what it is, and walking away. Not a dramatic gesture; a quiet refusal that crystallised everything the book would become about. The AIware Seoul empty room (secondary) provides the institutional echo: the field has not yet arrived at what this researcher has found.
- **Ending image:** The reader as the musician who now hears chord progressions — they cannot unsee values in design.
- **Zuboff stacking:** Evidence accumulates like a legal brief; weight builds; the reader feels the necessity of solutions.
- **Christian presence:** The narrator follows a thread, is surprised, revises, is sometimes wrong. Self-correction builds trust.
- **Numbers as revelations:** "One in four" — not "25% of reviews contained violations."
- **Pedagogical arc:** Seven perceptual shifts (Q6) ordered from most accessible → most conceptually demanding.

---

## The Seven Narrative Layers

Every chapter is constructed across seven simultaneous layers (see `narrative-nonfiction/NarrativeLayers.md` for full definitions):

1. **Meaning**: What thesis element does this chapter advance?
2. **Intellectual Journey**: What do you learn or revise here?
3. **Narrative Thread**: What question does this chapter answer? What new question does it raise?
4. **Mystery**: What information is revealed? What is withheld?
5. **Landscape**: What context is established or deepened?
6. **Relationships**: Which connections between people, ideas, or institutions are explored?
7. **Prose**: What register and rhetorical emphasis?

Every chapter must advance at least 3 layers. The Intellectual Journey (your evolving understanding) is the primary engine.

---

## Book Structure (v2 — Approved and Locked)

**Version:** v2, confirmed approved. This replaces all prior structure drafts.

**Source file:** `/mnt/ValuesWork/drafts/reworked-structure-v2.md`

**Governing principle:** This book is about systems alignment, not AI/model alignment. A perfectly aligned model inside an exploitative system is still exploitative. This distinction threads every chapter and must never be blurred.

**Voice formula:** 45% Zuboff + 45% Christian + 10% Solnit. British English. No em-dashes.

**Full v2 Chapter Map:**

```
INTRODUCTION: The Empty Room
PART I: WHAT WE BUILT
  Ch 1: One in Four               (ICSE 2021; Schwartz; Winner)
  Ch 2: The Honesty Gap           (MSR 2022; Vervoe mechanics; consent-washing)
PART II: WHAT IT COSTS
  Ch 3: Designed to Deceive       (MobileSoft 2022; dark patterns; req smells; FTC/DSA/CNIL)
  Ch 4: Who Gets Left Behind      (accessibility; FLoS; Herekind; Global South thread)
  Ch 5: Trusted and Betrayed      (Android APIs; GrapheneOS; Air Canada; DPD; transparency paradox)
PART III: WHY IT LASTS
  Ch 6: Building Under Pressure   (developer surveys; Stack Overflow; all five interviews)
  Ch 7: The Performance of Ethics (Munn; ethics-washing; AIware empty room)
PART IV: WHAT WE SEE NOW
  Ch 8: Teaching Machines to See  (ML/NLP detection; DECRA RT1; DP20; Student Project 1)
  Ch 9: The Aligned System        (VASS five pillars; DECRA RT2–RT4; Cindy; Herekind; GrapheneOS)
EPILOGUE: The Choice
```

**Part titles (v2 approved):**
- Part I: What We Built
- Part II: What It Costs
- Part III: Why It Lasts
- Part IV: What We See Now (alternative: "What Comes Next" — Dr. Obie's choice between the two)

**Chapter title change notes (v2 vs previous version):**
- Ch 7: "The Uselessness of Ethics" → **"The Performance of Ethics"** — Munn's argument is that performed ethics is useless, not that ethics itself is useless. This title is more precise and avoids misreading the argument.
- Ch 9: "Value-Aligned Systems" → **"The Aligned System"** — declarative rather than descriptive; names a destination rather than a category. The definite article signals this is a specific architectural vision, not a general aspiration.

**Six-stage discovery arc (the book's spine):**

| Stage | Research | Narrator moment |
|---|---|---|
| 1 | ICSE 2021 | "I was studying something else. The data kept showing me something I couldn't explain." |
| 2 | MSR 2022 | "I needed to know if this was noise or signal. So I built a way to tell." |
| 3 | MobileSoft 2022 | "If pandemic apps can't get this right, who can?" |
| 4 | Stack Overflow + Android APIs | "Developers aren't just building violations — they're normalising them." |
| 5 | VASS | "If the problem is structural, the solution must be too." |
| 6 | DECRA | "Teaching machines to find what humans have been blind to." |

The original evidence-grounded synthesis is archived at `/mnt/user-data/outputs/book-synthesis-and-chapter-structure.md`.

---

### Introduction: The Empty Room
*Write last. Opens with the AIware Seoul scene.*

- **Opening scene (v2):** Grand Walkerhill Seoul, 17:06 KST, 20 November 2025. The AIware empty room. The audience question about model vs system alignment. The field has not yet arrived at what this researcher has found. The empty room is the book's controlling metaphor: the absence of attention where attention is urgently needed.
- **Secondary scene:** Dr. Obie reading Vervoe's Terms and Conditions during an RMIT Lecturer recruitment process (c.2019–2020). Dense T&Cs granting broad rights over facial data, voice, and interview performance. The quiet refusal to proceed. The Black Mirror "Joan Is Awful" parallel.
- **Thesis statement:** Software values alignment is distinct from AI alignment, pervasive, and urgent.
- **Intellectual history:** Rokeach → Schwartz → the gap between knowing values and embedding them
- **Roadmap:** What the book will argue, chapter by chapter
- **Primary anecdotes:** AIware Seoul (opening hook), Vervoe/RMIT (secondary scene)
- **Key quotation:** Lennox: "Systems have to have values built in, and someone has to decide what those values are." (Confirmed placement: Introduction. The Orwell vs Huxley contrast from Lennox belongs in the Epilogue.)

---

### Part I: The Foundations

#### Chapter 1: What We Value
*The theoretical bedrock: arming the reader intellectually.*

| Layer | Content |
|-------|---------|
| Meaning | Establishes the values taxonomy and the core software-vs-AI alignment distinction |
| Intellectual Journey | From "values are vague philosophical concerns" → "values are concrete, universal, measurable, and already violated" |
| Landscape | Academic research context; Schwartz's cross-cultural value studies |

**Core content:**
- Schwartz's 10 universal value types and circular motivational continuum (conflict/compatibility)
- Winner's "Do Artifacts Have Politics?" — Moses's bridges, nuclear power, two types of technological politics
- The core distinction: software values alignment vs AI alignment
- "Model safety ≠ System safety" — the 3am phone browsing example

**Evidence anchors:**
- Schwartz, "An Overview of the Schwartz Theory of Basic Values"
- Winner, "Do Artifacts Have Politics?" (1980)
- Author's AIware 2025 paper
- Lennox, *2084*: Orwell vs Huxley contrast (p.12); "AI computer systems have no conscience" (p.145)
- Christian, *The Alignment Problem*: Goodhart's Law, distributional shift

#### Chapter 2: The Honesty Gap
*The most violated value, empirically demonstrated.*

| Layer | Content |
|-------|---------|
| Meaning | Honesty is the frontline of values violations |
| Mystery | Reveals the scale of violations (readers will not expect how pervasive this is) |
| Relationships | Author ↔ Vervoe; Users ↔ Developers; Consent ↔ Deception |

**Opening hook:** The Vervoe/RMIT anecdote. Reading the T&Cs. Walking away. The Black Mirror parallel.

**Core content:**
- First look at values violations in app reviews (ICSE 2021): taxonomy, frequency, honesty as dominant
- Violation of honesty in mobile apps (MSR 2022): deep dive
- Automated detection and developer experience (ESE 2023): developers know but lack tools
- Privacy policy analysis: incompleteness, vagueness, dark patterns
- Consent-washing as systemic mechanism

**Evidence anchors:**
- "A first look at human values-violation in app reviews" (ICSE 2021, 62 citations)
- "On the violation of honesty in mobile apps" (MSR 2022, 24 citations)
- "Automated detection, categorisation and developers' experience with violations of honesty" (ESE 2023)
- Author's privacy policy papers
- Student Project 1 2023 (ML classification of privacy policies; uses Vervoe clause as example)
- IT and Moral Values: Trust requires reducing deception, not just secrecy (O'Neill)
- Christian: "Providing overwhelming amounts of information without adequate structure or documentation is not transparency" (loc.1215)

**Anecdotes:** Vervoe/RMIT (primary), Black Mirror "Joan Is Awful", Student privacy policy task

---

### Part II: The Hidden Costs

#### Chapter 3: Dark Patterns at Scale
*The industry of manipulation.*

| Layer | Content |
|-------|---------|
| Meaning | Violations are industrialised, not incidental |
| Landscape | The app economy; design culture; growth hacking |

**Core content:**
- Systematic dark patterns catalogue across mobile, web, IoT
- Anti-patterns taxonomy: violations designed, not accidental
- Requirements smells: linguistic markers predicting violations
- EU regulation and industry responses
- The normalisation of manipulation

**Evidence anchors:**
- Author's dark patterns papers (systematic catalogue)
- Author's requirements smells papers
- Stack Overflow analysis of values violations
- Brignull's taxonomy (external, via deep-research)

#### Chapter 4: Who Gets Left Behind
*Accessibility, inclusion, and universalism.*

| Layer | Content |
|-------|---------|
| Meaning | Inclusion is a values problem, not a features checklist |
| Intellectual Journey | From "accessibility is a nice-to-have" → "exclusion is a values violation" |
| Relationships | Developers ↔ Diverse users; Western defaults ↔ Global reality |

**Core content:**
- Accessibility as underrepresented in values literature
- Universalism as Schwartz value: inclusion is a universal human need
- FLoS project: internationalisation failures as operationalised universalism
- Grundy et al.: human-centric SE, diversity factors (age, gender, culture, emotion)
- Khalajzadeh et al.: localisation/universalism

**Evidence anchors:**
- Author's accessibility/inclusion papers
- FLoS project (ICSE SCORE 2023)
- Grundy et al. on human-centric SE
- Khalajzadeh et al. on localisation

**Anecdotes:** Herekind (bereavement concierge — high-stakes inclusion context)

#### Chapter 5: Trust Betrayed
*Security as a human value.*

| Layer | Content |
|-------|---------|
| Meaning | Security is a value, and its violation enables all other violations |
| Mystery | Reveals the security–values connection (most readers will not see this coming) |

**Core content:**
- Android API investigation linking values violations to security vulnerabilities
- Security violations as values violations: not a separate category
- The transparency paradox: radical user transparency vs opaque corporate algorithms
- GDPR right to explanation; users' right to see and alter preference models
- GrapheneOS as values-aligned security case study

**Evidence anchors:**
- Author's Android API / security papers
- IT and Moral Values: transparency paradox, Mason's PAPA framework
- Christian: GDPR right to explanation (loc.1325–1330), preference model rights (loc.4149)
- Lennox: "people readily 'worship' such systems" (p.204)

**Anecdotes:** GrapheneOS (primary), Vervoe (security implications of broad data rights)

---

### Part III: Why It Persists

#### Chapter 6: Building Under Pressure
*The developer's dilemma.*

| Layer | Content |
|-------|---------|
| Meaning | The problem is systemic, not individual |
| Intellectual Journey | From "developers should do better" → "the system makes it nearly impossible" |
| Relationships | Developers ↔ Management; Ideals ↔ Deadlines |

**Core content:**
- Developer surveys: awareness but lack of tools and time
- Organisational pressure, sprint culture, technical debt
- The gap between ethics training and practice

**Evidence anchors:**
- Author's developer survey papers
- ESE 2023 (developer experience section)
- Lennox: "it is one thing to have a mission statement... it is another thing to get them owned" (p.78)
- Grundy et al. on human-centric SE (tool-support side)

#### Chapter 7: The Performance of Ethics
*Ethics-washing and the performance of concern.*

| Layer | Content |
|-------|---------|
| Meaning | The existing response is worse than inadequate — it provides cover |
| Intellectual Journey | From "ethics guidelines are a good start" → "they may be actively harmful" |
| Narrative Thread | If ethics guidelines fail, what actually works? (drives reader to Part IV) |

**Core content:**
- Munn's "The Uselessness of AI Ethics": three failures (meaningless, isolated, toothless)
- Ethics principles as not just useless but a dangerous distraction
- The AIware empty room as metaphor
- Consent-washing (Vervoe), ethics-washing (industry), the performance of concern
- Current approaches that fall short: ethical guidelines, privacy-by-design, post-deployment audits, compliance checklists

**Evidence anchors:**
- Munn, "The Uselessness of AI Ethics" (2023)
- AIware presentation: "current approaches fall short"
- Lennox: conscience and morality quotations (p.145)
- Christian: Goodhart's Law, predictive policing, Elaine Herzberg / self-driving Uber

**Anecdotes:** AIware empty room (secondary use)

---

### Part IV: A Way Forward

#### Chapter 8: Teaching Machines to See
*Automated detection of values violations.*

| Layer | Content |
|-------|---------|
| Meaning | Detection is possible, scalable, and already working |
| Intellectual Journey | From "violations are invisible" → "machines can learn to see them" |
| Mystery | Reveals accuracy and limitations of current detection |

**Core content:**
- Automated detection in app reviews: classifying violations by Schwartz value type
- Automated detection in privacy policies: flagging incompleteness, vagueness, deception
- Requirements smells detection: catching violations before code is written
- Developer tools: making detection actionable
- Student Project 1 2023 as proof of concept

**Evidence anchors:**
- Author's ML/NLP detection papers (multiple)
- DECRA grant (DE260100190)
- DP20 grant (automated values defect detection/fixing)
- Student Project 1 2023
- FLoS (detection of internationalisation failures)

#### Chapter 9: The Aligned System
*The VASS framework and the future.*

| Layer | Content |
|-------|---------|
| Meaning | The architectural vision for value-aligned systems |
| Intellectual Journey | From "we can detect violations" → "we can build systems that prevent them" |
| Narrative Thread | Answers "what actually works?" posed at end of Chapter 7 |

**Core content:**
- The VASS framework's five pillars:
  1. **Measurable Indicators** — bridge abstract values to metrics (autonomy = override frequency, option diversity, exit options)
  2. **Architectural Integration** — value-aware services, value-preserving data flows, constraint-based enforcement
  3. **Auditable by Design** — 4 levels: architectural, behavioural, interactional, detection
  4. **Participatory Alignment** — value priority specification, contextual adaptation, multi-stakeholder negotiation, community governance
  5. **Accessible Tools** — visual config, template patterns, guided workflows, explainable decisions
- AI makes it harder (adaptive, non-deterministic, opaque) but also makes detection more powerful
- "Cindy" health assistant scenario: optimises for engagement over autonomy
- Herekind as real-world values-aligned product
- Open research questions: context-robust metrics, cross-component value coordination, alignment drift, cross-cultural value mapping, human-in-the-loop tools
- Coherent extrapolated volition (Yudkowsky via Christian): instil not what humans do but what they would want

**Evidence anchors:**
- AIware 2025 paper and presentation (primary)
- Christian: coherent extrapolated volition (loc.4149+), user rights
- Grundy et al.: tool-support for human-centric SE
- Herekind (practical case study)
- GrapheneOS (values-aligned OS case study)

**Anecdotes:** Herekind (primary), GrapheneOS, the "Cindy" scenario

---

### Epilogue: The Choice
*A call to action.*

- The choice is not whether software will embed values, but whose values and with what accountability
- Winner's insight: the things we make, make us
- Closing reflection: from the empty room in Seoul to a future where system alignment is central
- Calls to action for: developers (use detection tools, demand time), policymakers (regulate systems not just models), users (demand transparency), researchers (the field is wide open)
- Lennox: the Orwell/Huxley warning — oppression imposed or oppression loved, or something better?

---

## Core Thesis Threading (v2)

The distinction between software values alignment and AI alignment threads through every chapter. The table below replaces the previous threading table; chapter titles are v2 approved.

| Chapter | Core Thread |
|---------|-------------|
| Ch 1: One in Four | Values debt introduced; Schwartz taxonomy; Winner's artifacts; software ≠ AI alignment |
| Ch 2: The Honesty Gap | Honesty as most violated value; consent-washing; Vervoe hook |
| Ch 3: Designed to Deceive | Engineered indifference (first use); dark patterns industrialised; req smells |
| Ch 4: Who Gets Left Behind | Who gets left behind; inclusion as universalism; Global South thread |
| Ch 5: Trusted and Betrayed | Trust betrayed; security as value; transparency paradox |
| Ch 6: Building Under Pressure | Why violations persist; developer pressure; all five interviews; structural not individual |
| Ch 7: The Performance of Ethics | Engineered indifference (second use); ethics-washing; performance of concern; AIware empty room |
| Ch 8: Teaching Machines to See | Values blindness (diagnostic); detection is possible; DECRA programme |
| Ch 9: The Aligned System | The aligned system; VASS five pillars; pays the debt |

**Software vs AI alignment threading note:** Each chapter should carry a version of this distinction appropriate to its material — not as a repeated disclaimer, but as a structural backbone. The distinction is most explicit in Ch 1 (introduction), Ch 7 (the performance critique), and Ch 9 (the constructive resolution).

## Key Research Publications (by chapter)

### Author's Core Papers

| Paper | Primary Chapter(s) |
|-------|-------------------|
| "A first look at human values-violation in app reviews" (ICSE 2021) | Ch 2, Ch 8 |
| "On the violation of honesty in mobile apps" (MSR 2022) | Ch 2 |
| "Automated detection, categorisation and developers' experience with violations of honesty" (ESE 2023) | Ch 2, Ch 6, Ch 8 |
| "A Vision for Value-Aligned AI-Driven Systems" (AIware 2025) | Ch 1, Ch 9 |
| Dark patterns papers (systematic catalogue) | Ch 3 |
| Requirements smells papers | Ch 3, Ch 8 |
| Privacy policy papers | Ch 2, Ch 8 |
| Android API / security papers | Ch 5 |
| Developer survey papers | Ch 6 |
| Accessibility / inclusion papers | Ch 4 |

### Colleagues' Papers

| Paper / Author | Primary Chapter(s) |
|----------------|-------------------|
| Grundy et al.: human-centric SE | Ch 4, Ch 6, Ch 9 |
| Khalajzadeh et al.: localisation/universalism | Ch 4 |

### External Seminal Works

| Work | Primary Chapter(s) |
|------|-------------------|
| Schwartz: basic values theory | Ch 1 |
| Winner: "Do Artifacts Have Politics?" | Ch 1, Epilogue |
| Munn: "The Uselessness of AI Ethics" | Ch 7 |

### Book Highlights

| Book | Key Quotations / Concepts | Primary Chapter(s) |
|------|--------------------------|-------------------|
| Lennox, *2084* | "Systems have to have values built in" (p.59); Orwell vs Huxley (p.12); conscience (p.145); worship (p.204); mission statements (p.78) | Intro, Ch 1, Ch 5, Ch 6, Epilogue |
| Christian, *The Alignment Problem* | Goodhart's Law; "not transparency" (loc.1215); GDPR (loc.1325); preference models (loc.4149); predictive policing; Elaine Herzberg; coherent extrapolated volition | Ch 1, Ch 2, Ch 5, Ch 7, Ch 9 |
| *IT and Moral Values* | Transparency paradox; Mason's PAPA; trust and deception (O'Neill) | Ch 2, Ch 5 |

### Student Projects

| Project | Primary Chapter(s) |
|---------|-------------------|
| FLoS (ICSE SCORE 2023) | Ch 4, Ch 8 |
| Project 1 2023 (privacy policy ML) | Ch 2, Ch 8 |

### Grants

| Grant | Role in Book |
|-------|-------------|
| DECRA (DE260100190) | Ch 8: frames the research programme |
| DP20 (ValuesDefectAppFixing) | Ch 8: larger team context |

## Terminology Consistency

| Term | Definition | Use |
|------|-----------|-----|
| Values violations | Actions by software that conflict with human values | Primary term throughout |
| Human values | Honesty, transparency, integrity, inclusivity, autonomy, etc. | Define early (Ch 1) using Schwartz, use throughout |
| Dark patterns | Deceptive UI design | Ch 3 and when discussing industry practices |
| Value-aligned | Software that respects human values | For solutions sections (Ch 8–9) |
| Software values alignment | Ensuring software systems respect user values | Distinguish clearly from AI alignment |
| System alignment | Alignment of the entire software system, not just its AI model | Core thesis term; introduced Ch 1 |
| Model alignment | Alignment of an AI/ML model's outputs | Contrasted with system alignment |
| VASS | Value-Aligned Software Systems framework | Ch 9 (introduced), referenced thereafter |
| Consent-washing | Using T&Cs to obtain technically-valid-but-meaningless consent | Ch 2, Ch 7 |
| Ethics-washing | Performative ethics guidelines that lack enforcement | Ch 7 |

---

## Coinage Decisions (Confirmed)

Three terms are confirmed for this book. These are not general-purpose academic coinages; they are the book's conceptual anchors and must be used with precision.

### Decision 1: Primary Coinage — Values Debt

**Term:** Values Debt

**Attribution history:** The term was coined by Waqar Hussain (former HumaniSE group member, co-author on ICSE-SEIS 2021) in a July 2019 IEEE Software Blog post. Hussain defined it as "value deficiencies or omissions in software." The post has approximately five citations. There is no peer-reviewed formalisation, no measurement instrument, no lifecycle model, and no detection taxonomy in the six years since the blog post was published.

**Dr. Obie's position:** First formalisation of the term. This follows the Kruchten/Petrozzino move: a term named informally in the field acquires scientific rigour when someone builds the measurement framework. The attribution framing is: "Hussain named it; this work makes it operational."

**What operationalisation means here:** VASS is the architectural framework for detecting and managing values debt. DECRA (DE260100190) provides the first engineering programme for values debt detection and remediation. Together they constitute the formalisation.

**Book arc use:** Parts I and II show how values debt accumulates; Parts III and IV show why it persists and how to pay it down. The term should appear explicitly by the end of Part I and recur as an organising concept through the remainder of the book.

**Why this term over alternatives:**
- Inherits engineering precision from technical debt (familiar to developers)
- Implies accumulation over time, not one-off error
- Implies structural origin, not individual moral failure
- Demands a correction mechanism (you do not "address" debt; you pay it down)
- Accessible to general readers without requiring prior technical debt knowledge
- Connects to the book's arc: detect, understand, remediate

**Note on adjacent terms:** Social Debt (Tamburri et al., CHASE 2013) is fully operationalised. Ethical Debt (Petrozzino, AI & Ethics 2021) is crowded and contested. Alignment Debt (Oyemike et al., arXiv November 2025) is brand new, narrow, and user-burden framed. Values Debt is the only term that is (a) already in the field's vocabulary, (b) directly attributable to the author's research lineage, and (c) not yet operationalised.

---

### Decision 2: Supporting Term — Engineered Indifference

**Term:** Engineered Indifference

**Definition:** The deliberate design of systems that are indifferent to human values — not through negligence but through intentional architecture. Dark patterns and ethics-washing are not accidents; the indifference is built in.

**Use:** Chapter 3 (dark patterns section) and Chapter 7 (ethics-washing section). This is a chapter-level conceptual handle, not the book's primary coinage.

**Argument it carries:** The opposite of "it's just a bug" or "we didn't mean to." When indifference is a design specification, it is no longer a failure — it is a feature. The term captures this and makes it nameable.

---

### Decision 3: Reserve Term — Values Blindness

**Term:** Values Blindness

**Definition:** The systemic inability to perceive or recognise values violations as they accumulate. Where values debt is the condition, values blindness is why it is not being addressed.

**Use:** Introduction or Chapter 8 (when the detection argument begins). This is a diagnostic complement to values debt, not a replacement for it.

**Argument it carries:** Detection research (VASS, DECRA) exists precisely because the field has values blindness. You cannot pay down what you cannot see. The term creates the intellectual setup for Part IV.

---

### Adjacent Terms Landscape

For reference when positioning values debt in the manuscript or in academic contexts:

| Term | Originator | Year | Status |
|---|---|---|---|
| Values Debt | Hussain, IEEE Software Blog | 2019 | Named; Dr. Obie = first formalisation |
| Social Debt | Tamburri et al., CHASE | 2013 | Fully operationalised |
| Ethical Debt | Petrozzino, AI & Ethics | 2021 | Crowded, contested in literature |
| Fairness Debt | de Souza Santos et al., arXiv | 2024 | Narrow; AI/bias framing only |
| Privacy Debt | Larrucea, IET Software | 2021 | Narrow; partial treatment |
| Alignment Debt | Oyemike et al., arXiv | Nov 2025 | Brand new; user-burden framing |

## Writing Workflow

The recommended sequence for writing this book:

1. **Add research materials** to `/mnt/ValuesWork/` subdirectories
2. **Ingest and analyse**: run IngestResearch to produce a Research Digest
3. **Interview**: extract your vision, thesis, and narrative priorities
4. **Explore** (optional): think through connections, test ideas, follow intellectual threads before committing to a plan
5. **Build Bible**: create the full chapter map grounded in the actual research evidence (replaces the provisional chapter scaffold above)
6. **Write chapters**: draft prose following the Book Bible, one chapter at a time (WriteChapter for initial composition)
7. **Revise**: apply critic feedback, integrate new evidence, polish prose (Revise for targeted changes to existing drafts)
8. **Iterate**: add more materials, re-ingest, explore implications, update the Bible, and revise drafts

| Document              | What it is                                                    | How it is produced                                  |
| --------------------- | ------------------------------------------------------------- | --------------------------------------------------- |
| Research Digest       | Structured analysis of all ingested research materials        | Output of IngestResearch workflow                    |
| Book Bible            | Master plan mapping all 7 layers across all chapters          | Output of BuildBible workflow                        |

The `narrative-nonfiction` skill provides the detailed workflows for each step. This skill provides the domain context those workflows need.

## Quick Commands

| What you want                  | What to type                                                                |
| ------------------------------ | --------------------------------------------------------------------------- |
| Analyse all research materials | "Analyse the research materials in the ValuesWork folder"                   |
| Process only new files         | "I have added new papers, process them"                                     |
| Plan the book (interview)      | "Interview me about my book Human Values in Software"                       |
| Explore an idea or connection  | "Explore the connection between dark patterns and security vulnerabilities"  |
| Think through implications     | "What if software values alignment and AI alignment share a common root?"   |
| Create the master plan         | "Build the book bible based on our interview and the research digest"        |
| Update plan from new research  | "Update the book from the research"                                         |
| Write a chapter                | "Write chapter 3 following the book bible"                                  |
| Write just the opening         | "Draft the opening scene for chapter 1"                                     |
| Revise a chapter               | "Revise chapter 1 based on the critic feedback"                             |
| Integrate a specific paper     | "Integrate the AIware 2025 paper into chapter 7"                            |
| Polish prose                   | "Polish the prose in chapter 2, section 3"                                  |
| Check consistency              | "Review the draft of chapter 2 for consistency with the book bible"         |
| Brainstorm examples            | "Brainstorm concrete examples for the inclusion gap chapter"                |

## Output Format

When writing chapters, save as Markdown to `/mnt/ValuesWork/drafts/chapter-NN-slug.md`:

```markdown
# Chapter N: Title

## Opening

[Concrete scene, person, or moment that hooks the reader]

## [Section Title]

[Prose: each section advances the chapter's argument through evidence,
narrative, and analysis. Every paragraph serves at least one of the 7 layers.
Sections correspond to the chapter plan in the Book Bible.]

## [Section Title]

[Continue as needed]

---

## Chapter Notes

### Layer Summary

| Layer                | What this chapter accomplished               |
| -------------------- | -------------------------------------------- |
| Meaning              | [Thesis element advanced]                    |
| Intellectual Journey | [What was learnt or revised]                 |
| Narrative Thread     | [Question answered; new question raised]     |
| Mystery              | [Information revealed; information withheld] |
| Landscape            | [Context established or deepened]            |
| Relationships        | [Connections explored]                       |
| Prose                | [Register, key rhetorical figures deployed]  |

### Critic Pass Summary

| Critic              | Confidence (1–5) | Key action taken |
| ------------------- | ---------------- | ---------------- |
| Layer Auditor       |                  |                  |
| Evidence Inspector  |                  |                  |
| Rhetoric Examiner   |                  |                  |
| Freshness Inspector |                  |                  |
| Reader Surrogate    |                  |                  |

### References Used

- `citationKey`: role in this chapter (e.g. primary evidence for Section 2)

### New BibTeX Entries

[Any entries added to references.bib during this chapter's writing]

### Book Bible Updates

[Any new connections, structural changes, or layer adjustments the Bible should reflect]

### Gaps and Open Questions

- [Evidence still missing]
- [Questions for you to resolve]
- [Suggested external research to fill gaps]

### Recommended Next Step

[Which chapter to write next, or which revision to undertake]
```

---

## Source Notes: Honesty Journal Paper (EMSE 2023)

**Full citation:** Obie, H.O., et al. "Automated detection, categorisation and developers' experience with the violations of honesty in mobile apps." *Empirical Software Engineering* 28, 134 (2023). DOI: 10.1007/s10664-023-10361-4

**Primary chapter relevance:** Ch 2 (The Honesty Gap), Ch 3 (Designed to Deceive), Ch 6 (Building Under Pressure)
**Secondary relevance:** Ch 7 (The Performance of Ethics), Ch 8 (Teaching Machines to See), Intro (scale/prevalence framing)

**What the paper contributes to the book:** This is the primary empirical anchor for the developer-side narrative. A mixed-methods study of 73 practitioners (70 surveyed, 3 interviewed) establishes five causal drivers of honesty violations, documents the blame-cascade dynamic where responsibility flows downward from product owners to developers, and reveals that only 2 of 73 developers had systematic tools for handling violations. The data provides the strongest evidence for Engineered Indifference (SP37's R&D-for-manipulation account) and for the structural argument that violations are systemic, not individual. Cross-study convergence with the book's own 5 interview participants strengthens the findings.

**Full extraction:** `notes/emse-2023-honesty-developers.md` — includes all RQ3 findings, five causal driver taxonomy, consequences by stakeholder, avoidance and fixing strategies, automatic detection benefits, 12 key quotes flagged for chapter deployment, 9 named themes, convergence table with book interview data, and narrative deployment notes.
