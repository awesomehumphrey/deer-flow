# Aesthetic Profiles for Narrative Non-Fiction

Configurable prose style profiles that shape how the skill writes. Each profile defines vocabulary range, sentence patterns, descriptive density, pacing, evidence integration style, and rhetorical figure preferences.

## How Profiles Work

1. The writer selects a base profile during Interview or BuildBible
2. Profiles can be blended (e.g., "70% Zuboff, 30% Gladwell")
3. Profiles affect the Prose layer but NOT the other six layers
4. Custom profiles can be defined per project

---

## Built-In Profiles

### Shoshana Zuboff (Systematic Investigative)
**Signature:** Grand-scale institutional analysis; forensic evidence with moral urgency; building an indictment through accumulated detail.

**Characteristics:**
- Long, architecturally complex sentences that mirror the complexity of the systems described
- Extensive direct quotation from primary sources (patents, internal documents, executive statements)
- Technical and economic vocabulary used precisely, then grounded in human consequence
- Chapters build like legal briefs: evidence, analysis, implication
- Repeated conceptual framing ("surveillance capitalism", "behavioural surplus") creates a vocabulary the reader internalises

**Rhetorical figure emphasis:** Anaphora, Amplificatio, Antithesis, Periodic Sentence, Sententia
**Sentence length:** Long (20-40 words), with occasional short declarative sentences for verdicts
**Descriptive density:** High for institutional and economic detail; moderate for personal narrative
**Pacing:** Deliberate and cumulative; each chapter adds weight to the central argument

**Sample register:**
> What is at stake is the human future at the new frontier of power.

---

### Brian Christian (Curious Synthesiser)
**Signature:** Following a complex idea across disciplines with genuine curiosity; making the reader feel the intellectual excitement of discovery.

**Characteristics:**
- Alternates between technical explanation and human story
- Interviews and conversations are presented as dialogues, not summaries
- Analogies drawn from unexpected domains to illuminate technical concepts
- The author is present as a curious guide, not an authority
- Comfortable with complexity; does not oversimplify

**Rhetorical figure emphasis:** Analogy, Paradox, Antithesis, Parenthesis, Chiasmus
**Sentence length:** Medium (12-25 words), conversational rhythm
**Descriptive density:** Moderate; focused on making abstract ideas tangible through concrete examples
**Pacing:** Brisk and varied; technical passages alternate with human stories

**Sample register:**
> The question of how to align an AI system with human values turns out to be, in many ways, the question of what human values are in the first place.

---

### Cathy O'Neil (Activist Analyst)
**Signature:** Data analysis with moral clarity; showing how systems harm real people; accessible mathematics.

**Characteristics:**
- Opens chapters with a person affected by the system, then zooms out to the mechanism
- Technical concepts explained through their consequences, not their mechanics
- Direct, declarative prose; minimal hedging
- Anger channelled through precision rather than rhetoric
- Each chapter is a self-contained case study contributing to a larger argument

**Rhetorical figure emphasis:** Antithesis, Erotesis, Exemplum, Gradatio, Epigram
**Sentence length:** Short to medium (8-18 words), punchy and direct
**Descriptive density:** Low for environment; high for mechanism and consequence
**Pacing:** Fast; each chapter moves from person to system to implication efficiently

**Sample register:**
> The math-powered applications powering the data economy were based on choices made by fallible human beings.

---

### Malcolm Gladwell (Narrative Explainer)
**Signature:** Counterintuitive ideas illuminated through compelling stories; making the reader see the familiar as strange.

**Characteristics:**
- Opens with an irresistible anecdote that embodies the chapter's argument
- Heavy use of academic research, presented as stories about researchers
- The "aha" moment is carefully engineered; the reader reaches the conclusion just before it is stated
- Conversational, almost oral cadence; reads like a spoken narrative
- Light on technical detail; heavy on implication

**Rhetorical figure emphasis:** Exemplum, Paradox, Diacope, Bathos, Prolepsis (narrative)
**Sentence length:** Short to medium (8-20 words), highly varied for rhythm
**Descriptive density:** High for people and scenes; low for systems and institutions
**Pacing:** Fast, story-driven; each chapter reads almost like a short story

**Sample register:**
> The key to good decision making is not knowledge. It is understanding.

---

### Michael Lewis (Character-Driven Investigator)
**Signature:** Complex systems explained through the people who inhabit them; vivid character portraits as entry points to institutional analysis.

**Characteristics:**
- Characters are drawn with novelistic detail (physical description, verbal tics, backstory)
- Institutional mechanics revealed through the experience of individuals navigating them
- Dialogue reconstructed with journalistic rigour
- Narrative suspense maintained even when the outcome is known
- Dry humour used to leaven dense material

**Rhetorical figure emphasis:** Prosopographia, Ethopoeia, Diacope, Syllepsis, Litotes
**Sentence length:** Variable; short for action and dialogue, long for institutional description
**Descriptive density:** Very high for people; moderate for institutions; low for abstract ideas
**Pacing:** Fast, propulsive; structured like a thriller

**Sample register:**
> The willingness of a Wall Street investment bank to pay him hundreds of thousands of dollars to dispense his investment advice to grown-ups remains one of the great mysteries of the age.

---

### Rebecca Solnit (Lyrical Essayist)
**Signature:** Poetic precision; weaving personal experience, cultural criticism, and political argument into a seamless whole.

**Characteristics:**
- Sentences that function as compressed arguments; every clause earns its place
- Personal experience used as evidence, not self-indulgence
- Historical and cultural references deployed with the assumption of an intelligent reader
- Comfortable with ambiguity and paradox
- The essay form extended to book length without losing intimacy

**Rhetorical figure emphasis:** Paradox, Antithesis, Extended Metaphor, Chiasmus, Apostrophe
**Sentence length:** Medium to long (15-30 words), rhythmically precise
**Descriptive density:** High for landscape and mood; moderate for people and institutions
**Pacing:** Measured, contemplative; builds through accumulation rather than speed

**Sample register:**
> Hope is not a lottery ticket you can sit on the sofa and clutch, feeling lucky. Hope is an axe you break down doors with in an emergency.

---

## Custom Profile Template

Writers can define their own aesthetic profile:

```markdown
### [Profile Name] ([Category])
**Signature:** [One sentence defining the voice]

**Characteristics:**
- [Sentence structure preference]
- [Vocabulary range and register]
- [Evidence integration style]
- [Author presence level]
- [Thematic emphasis]

**Rhetorical figure emphasis:** [3-6 primary figures from RhetoricalFigures.md]
**Sentence length:** [Short/Medium/Long/Variable + typical range]
**Descriptive density:** [Low/Moderate/High + what gets described most]
**Pacing:** [Fast/Moderate/Slow/Variable + pattern]

**Sample register:**
> [One representative sentence that captures the voice]
```

## Profile Blending

Profiles can be blended with weighted percentages:

```
Profile: 60% Zuboff + 40% Christian
Result: Systematic institutional analysis with genuine curiosity and
        accessibility. Complex sentences for systems, conversational
        passages for human stories. Evidence presented as discovery.
```

Blending rules:
- The dominant profile (highest %) controls sentence structure and pacing
- The secondary profile adds flavour through vocabulary and evidence style
- Descriptive density averages between profiles
- Author presence follows the more present profile

## Subject-Default Profiles

| Subject Domain | Default Profile | Why |
|---------------|----------------|-----|
| Tech/institutional critique | Zuboff | Systematic analysis, moral urgency |
| Science/ideas | Christian | Cross-disciplinary curiosity, accessibility |
| Data/algorithms | O'Neil | Mechanism through consequence, moral clarity |
| Social science | Gladwell | Story-driven explanation, counterintuitive framing |
| Finance/institutions | Lewis | Character-driven, novelistic |
| Culture/politics | Solnit | Lyrical precision, personal-political weave |

These defaults can always be overridden.
