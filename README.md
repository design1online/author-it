# Author It
AI skills for writers who don't want AI writing their novels for them...

## Overview
This repository contains Claude Code skills for authors. These skills help you plan, develop, and refine your book — but they never write your story for you. Using these skills will classify your work as **AI Assisted** because these are **NOT** generative AI skills.

## Requirements

Claude Code version 1.0.33 or later. Check your version with:

```bash
claude --version
```

To upgrade: `brew upgrade claude-code` (Homebrew) or `npm update -g @anthropic-ai/claude-code` (npm).

---

## Install as a Plugin (Recommended)

Installing as a plugin is the easiest way to use Author It. Skills are available across all your projects with a single install.

**Step 1 — Add the marketplace:**

```
/plugin marketplace add design1online/author-it
```

**Step 2 — Install the plugin:**

```
/plugin install author-it@author-it
```

That's it. Skills are immediately available.

> **Note:** Plugin skills are namespaced to prevent conflicts with other plugins. Invoke them with the `author-it:` prefix (e.g., `/author-it:create-story-bible`).

### Manage the plugin

```
/plugin disable author-it@author-it     # Disable without uninstalling
/plugin enable author-it@author-it      # Re-enable
/plugin uninstall author-it@author-it   # Remove completely
```

---

## Manual Installation (Alternative)

If you prefer not to use the plugin system, you can copy the skills directly into any project.

### Global (available in all projects)

```bash
cp -r skills/* ~/.claude/skills/
```

### Project-level (available in one project only)

```bash
cp -r skills/ /path/to/your/project/.claude/skills/
```

> **Note:** Manually installed skills use short names without a namespace prefix (e.g., `/create-story-bible` instead of `/author-it:create-story-bible`).

---

## Skills

### `/author-it:create-story-bible`

**Usage:** `/author-it:create-story-bible [book-title] [premise]`

Guides you through a systematic, question-driven process to build a complete story bible for your book. It never writes your story — instead it asks targeted questions to help you clarify your premise, characters, world, and market positioning until everything is crystal clear.

The skill creates a structured set of files in a `story-bibles/[book-title]/` folder (or `story-bibles/[series-title]/[book-number]-[book-title]/` for series). Files created include:

| Folder | Files |
|---|---|
| `story/` | premise, genre, tropes, recommendations |
| `characters/` | protagonist, antagonist, relationship, distraction, emotion, reason, support, opposition |
| `world-building/` | geography, flora-fauna, politics, religions, resources, culture-conflicts |
| `outline/` | plot-centered, character-centered, romance, mystery, horror, or short-story beats |
| `marketing/` | analysis, similar-books, ad-copy |

The skill works iteratively — it asks 1–3 targeted questions at a time, states its assumptions, and waits for your confirmation before moving forward. It will not generate final documents until all gaps and ambiguities are resolved.

---
### `/author-it:create-scene`

**Usage:** `/author-it:create-scene`

Creates a standardized template for scenes and helps you write a compelling scenes or evaluates an existing scene.

The report includes:

* Story Beat - which beat this scene covers
* Characters In Scene - a list of all characters in the scene
* Story Question - also known as the promise of the premise, how this scene contributes to the question this story is asking
* Story Pitch - how this story is being marketed in a single sentence
* Theme - the theme of this story
* Story Beat Sentence - a sentence that helps you align what happens in this scene with the scene goal, story beat and story question
* Day - what day this scene takes place in the timeline of the story
* Location - where this scene takes place
* Scene Goal - the ultimate goal of this scene (ie inciting incident, character introduction, character growth, world building, plot development, foreshadowing device, etc).
  * Hook - how the first sentence will grab attention, make the reader ask questions, introduce conflict, tension or stakes.
  * Escalation - a setback or minor problem
  * Pivot - a change of pace, breather, introduction of something new or a change of direction
  * Conflict - a major problem that arises preventing them from reaching their goal
  * Consequences - fallout of the conflict and sets up the strong hook for the next scene or chapter
* Key Points - a list of events, items, or important information that must happen or be included in this scene to help setup later scenes or sub-plots

---

### `/author-it:dev-editor-recommendations`

**Usage:** `/author-it:dev-editor-recommendations [book-title]`

Performs a full developmental editor pass on the story bible files created by `create-story-bible`. It reads all existing story bible documents for the book (and series, if applicable) and compiles a prioritized recommendations report saved to `story/recommendations.md`.

The report includes:

- **Plot Holes** — identified issues ranked by urgency with suggested fixes
- **Story Inconsistencies** — contradictions across characters, world-building, and plot
- **Character Development Issues** — passive or underdeveloped characters with fix recommendations
- **Dev Editor Recommendations** — prioritized list (urgent, high, medium, low) with detailed feedback and a checkable suggestion list
- **Overall Developmental Feedback** — strengths and weaknesses across all story elements with an overall rating
- **Publishing Placement Recommendations** — whether the book is a fit for traditional, small press/indie, or self-publishing, including sample query letters
- **Marketing Recommendations** — market fit analysis, niche vs. broad audience considerations

If a `recommendations.md` file already exists, the skill archives it with a date stamp before creating a new one.

---

### `/author-it:query-letter-workshop`

**Usage:** `/author-it:query-letter-workshop`

An experienced literary agent's perspective on your query letter. Guides you through providing the information needed to build a query letter using a proven template, then coaches you on whether it would actually hook an agent — never writing or changing your text for you.

The session walks through:

1. **Intake** — author information, bio, book genre/subgenre, target agent, book details (title, word count, standalone vs. series), elevator pitch, and short summary
2. **Coaching/Feedback** — before generating anything, evaluates whether your bio is brief and authentic, whether your pitch and summary meet genre expectations (and whether the genre is oversaturated), whether the elevator pitch would hook an agent, whether the summary presents a fully developed plot, and a spelling/grammar check
3. **Template Generation** — assembles your answers into a complete, ready-to-send query letter
4. **Final Feedback** — a closing round of feedback on the generated letter's strengths and weaknesses, plus suggestions on whether a different agent might be a better fit

---

### `/author-it:writing-coach`

**Usage:** `/author-it:writing-coach`

A step-by-step writing coach that evaluates the first paragraph or first chapter of your book (up to 5,000 words) and gives constructive criticism — without rewriting your content or training on your data.

The coach walks through seven evaluation stages:

1. **Hook** — Analyzes your first sentence for reader assumptions, questions raised, clichés, and overall hook strength (rated 1–5). Offers targeted word-level suggestions to improve it without rewriting.
2. **Main Character** — Evaluates whether the reader understands who the character is, what they want, their motivation, and what's standing in their way. Flags passive characters.
3. **Setting** — Checks for white room syndrome and evaluates how well the setting grounds the reader.
4. **Sensory Details** — Reviews all eight senses (sight, smell, sound, taste, touch, balance, external body awareness, internal body awareness) for presence and effectiveness.
5. **Prose** — Evaluates purple prose, sentence flow, readability, repetition, strong writing habits (adverbs, passive voice, show vs. tell), and word choice.
6. **Spelling & Grammar** — Lists all spelling and grammar issues with the sentence each is found in.
7. **Overall Impression** — Provides a full reader synopsis, un-put-downable analysis, unanswered questions, plot holes, conflicts, inconsistencies, genre, tone, tropes, target reader, and a final rating.

Each stage lets you dig deeper with clarifying questions or move on. At the end you can generate a downloadable summary of the full coaching session.

---

### `/author-it:strong-writing-checklist`

**Usage:** `/author-it:strong-writing-checklist`

A comprehensive checklist of 35 items used to evaluate your writing to see how strong it is. Generates a report with a star rating out of 5, your writing strengths, weaknesses, and all issues found in a prioritized checklist.

---

### `/author-it:book-market-research`

**Usage:** `/author-it:book-market-research`

A live publishing market analyst that researches genre saturation, identifies underserved gaps, and surfaces 2–3 specific opportunities your story could occupy. Always runs live web searches rather than relying on training data for market trends.

The session walks through four stages:

1. **Research Brief** — collects your premise or genre seed, what you already know, any constraints, and your goal (commercial viability check, gap discovery, or better positioning of an existing idea)
2. **Saturation Map** — categorizes the market into oversaturated, competitive, emerging, and underserved segments with supporting evidence
3. **Gap Opportunities** — ranks 2–3 specific gaps by commercial and creative viability, including reader appetite signals, why the gap exists, risk factors, and writer fit
4. **Handoff** — routes you to brainstorm, pitch, or deeper research based on your findings

At the end of each section you can correct or expand the analysis before moving on. Pairs naturally with `/author-it:storybuilder-brainstorm` and `/author-it:one-line-elevator-pitch`.

---

### `/author-it:one-line-elevator-pitch`

**Usage:** `/author-it:one-line-elevator-pitch`

A literary pitch consultant that distills your story into commercially viable, emotionally resonant language — three outputs in one session: a high-concept one-liner, a full 1–2 sentence pitch, and multiple tagline options at different angles.

The session covers:

1. **Story Intake** — collects protagonist, wound, inciting incident, impossible choice, stakes, antagonist, resolution type, and optional comp titles (skips anything already in an existing story bible)
2. **Pitch Analysis** — identifies the story question, how the external conflict aggravates the internal wound, the impossible thing, the specific cost, commercial angle, and pitch risk before generating any language
3. **Pitch Suite** — produces a high-concept one-liner, full pitch, and 3–5 tagline variants with honest strength/weakness ratings and a recommended combination
4. **Comp Title Alignment** — analyzes whether your comp titles set the right reader expectations and suggests alternatives if needed

All outputs are rated honestly. Weak options are named as weak. Iterates until you have language you want to lock.

---

### `/author-it:sentence-workshop`

**Usage:** `/author-it:sentence-workshop`

A line editor for fiction prose at the sentence level. Diagnoses exactly what's weak in a sentence and provides 3–5 tight variants that fix the specific problem — with a clear explanation of every move made. Never rewrites your text; highlights the issues and explains the reasoning so you decide what to change.

Choose a mode or let it run a full diagnostic:

- **Hook strengthening** — first sentence needs to do more work
- **Glue word / filler elimination** — too wordy, soft verbs
- **Subtext layering** — too on the nose; needs to say it without saying it
- **Tension injection** — needs more unease, pressure, or stakes
- **Voice alignment** — needs to sound more like a specific character
- **Rhythm / pacing** — sentence is the wrong length or shape for the moment
- **Tell-to-show conversion** — emotion or state being stated instead of embodied

Works in passage mode for 3+ consecutive sentences, prioritizing the 2–3 highest-impact problems rather than trying to fix everything at once.

---

### `/author-it:dialogue-workshop`

**Usage:** `/author-it:dialogue-workshop`

A dialogue editor specializing in surgical intervention — not full rewrites. Identifies exactly what's wrong with a dialogue exchange and offers tight variants that fix the specific problem. Never rewrites the original; annotates the issues with explanations so you decide how to address them.

Choose a mode or let it run a diagnostic:

- **Subtext** — characters are saying exactly what they mean; needs displacement
- **Voice** — characters sound too similar; can't tell who's speaking
- **Exposition** — dialogue is delivering information neither character would naturally say
- **Tags** — attribution is clunky, overwritten, or adverb-heavy
- **Rhythm** — too smooth, too formal; no interruption, deflection, or trailing off
- **Silence** — something important isn't being said and it needs to be felt
- **Melodrama** — characters are stating their emotions directly

Includes a **Silence Audit** that names what each character isn't saying and identifies where the unsaid nearly surfaces — and a **Full Scene Dialogue Audit** for 300+ word passages that runs a tag audit and voice audit across the entire scene.

---

### `/author-it:deep-pov-workshop`

**Usage:** `/author-it:deep-pov-workshop`

A deep POV specialist that closes the distance between reader and character. Removes the glass wall of the narrator and puts the reader directly inside the POV character's skull. Never rewrites your text; points out the issues with explanations so you decide how to address them.

Choose a mode or let it run a full diagnostic:

- **filter-sweep** — eliminate filter words throughout ("she saw," "he felt," "she knew")
- **distance-calibrate** — narration feels too far or too close; needs deliberate calibration
- **head-hop** — POV is slipping between characters unintentionally
- **interiority** — too much or too little time inside the character's head
- **body-first** — emotional states are being named rather than felt in the body
- **free-indirect** — narration sounds like the author, not the character

Includes a distance calibration reference (tight / close / measured / distant), a Filter Word Index of the most damaging constructions, and an optional Head-Hop Audit for longer passages.

---

### `/author-it:show-dont-tell-workshop`

**Usage:** `/author-it:show-dont-tell-workshop`

A show-don't-tell specialist that annotates exactly what's being told, identifies the showing equivalent, and offers targeted variants the writer can choose between. Never rewrites your passage; marks up the issues with explanations so you decide what to fix.

Uses a **Telling Taxonomy** to categorize and prioritize every instance:

| Type | Example |
|---|---|
| Emotion-telling | "She was furious." |
| Trait-telling | "He was kind." |
| Atmosphere-telling | "It was tense." |
| Relationship-telling | "They'd always had a difficult relationship." |
| Theme-telling | "In the end, everyone pays for their choices." |
| Summary compression | "Weeks passed and nothing changed." |
| Backstory-telling | "He'd grown up in a house full of silence." |

HIGH priority items are addressed first. Each gets 2–3 variants (body/behavior-first, object/environment-anchored, action/consequence-based) plus an honest pick with reasoning. Includes an **Earning Test** for summary and backstory, and a **Theme-Stating Audit** for narration that explains the theme rather than embodying it.

---

### `/author-it:line-editing-workshop`

**Usage:** `/author-it:line-editing-workshop`

Line editing support for a chapter, one chapter at a time. Works best on a single chapter — if you paste a full manuscript, it warns you and processes it chapter by chapter instead. Only ever suggests changes; never edits your text or overrides your judgment.

Works through four rounds, each producing an itemized list with line references and suggested fixes:

1. **Pacing/Flow** — run-on paragraphs, run-on sentences, missing or excessive narrator presence, info dumps
2. **Dialogue** — inconsistent tenses, inconsistent formatting (italics/bold/punctuation), unclear speakers, dialogue tag amount and type, distinct character voice
3. **Repetition** — unique words used too close together, redundancies, overused or nonsensical clichés, idioms, overused phrases or words
4. **Readability** — grade level and complex word count, technical jargon, generic descriptions, told vs. shown situations, initial pronouns/names, sentence starters, filler words

At the end, choose one combined document with each round as a header, or four separate documents (recommended).

---

### `/author-it:chapter-scene-workshop`

**Usage:** `/author-it:chapter-scene-workshop`

Helps you flesh out a chapter by breaking it down into scenes and providing structural guidance, then generates a standardized output you can use in your chapter outline.

Paste your chapter or story content and the skill:

- Analyzes the content for plot holes, contradictions, and missing structural sections
- Breaks the chapter into individual scenes, each with a full template covering: story beat, characters in scene, story question, story pitch, theme, story beat sentence, day and location, scene goal, hook, escalation, pivot, conflict, consequences, and key points
- Identifies gaps you haven't addressed yet and flags missing or contradictory information
- Optionally grills you until all plot holes, contradictions, and missing information are resolved across every scene

Note: a scene doesn't need every structural element, but the collective of all scenes in a chapter must include all of them. Chapters should never end in a resolved, happy place — they should always create tension that hooks the next chapter.

---

### `/author-it:story-architect`

**Usage:** `/author-it:story-architect`

A story development coach, developmental editor, genre consultant, and structural architect in one. Pulls a fully blueprinted story out of you through relentless, focused questioning — one question at a time. Never writes your story. Builds the map you need to write it yourself.

Works through 10 phases, producing structured documents at each stage:

| Phase | Name | Output |
|---|---|---|
| 1 | The Spark | Genre, idea seed, or character fragment |
| 2 | Character Deep-Dive | Protagonist character sheet |
| 3 | Premise & Pitch | Elevator pitch + story question |
| 4 | Story World | World building / magic reference sheet |
| 5 | Conflict Architecture | Antagonist, obstacle, stakes, subplot map |
| 6 | Structural Beat Sheet | Genre-appropriate story beats + act breaks |
| 7 | Contradiction Audit | Dev editor gap/hole report — loops until clean |
| 8 | Genre Reader Review | Trope fit, reader expectation alignment |
| 9 | Supporting Characters | Character sheets for all secondary characters |
| 10 | Chapter Outline | Chapter-by-chapter beat + scene templates |

Core rules: one question at a time, uses your words back to you, flags every contradiction and logic gap before advancing, never assumes.

---

## Storybuilder Suite

The Storybuilder is a complete system for writing a fiction novel with AI assistance without generating a single word of your story for you. **AI-assisted, never AI-generated.**

The recommended flow:

1. `/author-it:storybuilder-brainstorm` — develop your raw idea into a structured series concept
2. `/author-it:storybuilder-bible` — build out characters, worldbuilding, and a full chapter outline
3. `/author-it:storybuilder-bible-audit` — stress-test the story bible for logic gaps and inconsistencies (repeat until clean)
4. `/author-it:storybuilder-character-sheet` — create detailed character sheets for each major character
5. For each chapter: `/author-it:storybuilder-scene` → `/author-it:storybuilder-dev-editor` → `/author-it:storybuilder-improvement-plan`

Use `/author-it:storybuilder` to start the full guided flow, or invoke individual skills directly if you know where you are in the process.

---

### `/author-it:storybuilder`

**Usage:** `/author-it:storybuilder`

The guided entry point for the full Storybuilder suite. Prompts you for your story's title and genre, asks whether you want to go through the complete flow, and routes you to the right skill at each stage. If you already have work in progress, it asks what you're working on and directs you to the appropriate skill.

---

### `/author-it:storybuilder-brainstorm`

**Usage:** `/author-it:storybuilder-brainstorm`

Takes a raw braindump of your story idea — however partial or contradictory — and develops it into a structured series concept ready to hand off to the story bible process. Runs live web searches to research genre trends and tropes before producing any analysis.

The session produces:

- **Premise Extraction** — core "what if," emotional engine, protagonist wound, central conflict type, story question, and thematic question
- **Genre & Trope Research** — live-searched breakdown of must-have tropes, active tropes, oversaturated tropes, and subversion opportunities with comp titles
- **Series Brainstorm Document** — a complete concept document covering premise, story question, genre, protagonist, supporting characters, antagonist, world and setting, themes, series potential, tone, and open questions

Ends with a handoff to story bible, pitch, or audit depending on what you need next.

---

### `/author-it:storybuilder-bible`

**Usage:** `/author-it:storybuilder-bible [book-title]`

Builds a complete story bible from your brainstorm. Relentlessly grills you through characters, worldbuilding, and a full chapter outline — never generating text for you, only providing suggestions and recommendations to help you develop the content yourself.

Produces three sections:

- **Characters** — full dossiers for major characters (physical description, role, personality profiles, core motivation, background, quirk, dialogue style, and dialogue samples) and 1–2 sentence summaries for minor characters
- **Worldbuilding** — organized by category (setting, magic/technology, groups, geography, politics, culture, history, religion, etc.) with 3–4 sentences per element
- **Outline** — chapter-by-chapter summaries of 200–250 words each with specific details, formatted for handoff to scene generation

Uses genre-appropriate beat sheets based on your story's details. Prompts for an audit when the bible is complete.

---

### `/author-it:storybuilder-bible-audit`

**Usage:** `/author-it:storybuilder-bible-audit`

Audits a story bible for logical consistency and plot plausibility. Runs six systematic checks and produces a structured report with specific fixes for every issue found.

The six audit categories:

1. **Premise Logic** — does the core premise hold together internally?
2. **Character-World Fit** — do characters' roles, goals, and capabilities make sense given the worldbuilding?
3. **Worldbuilding Coherence** — do world elements work together logically without internal contradictions?
4. **Setup Plausibility** — are there logistical impossibilities or motivation gaps that would prevent the story from starting?
5. **Convenience Flags** — does the premise rely on unlikely coincidences or characters who exist purely to solve plot problems?
6. **Specific Fixes** — 3–6 concrete, actionable suggestions that address the most critical problems while preserving the story's core appeal

Each issue is formatted with a description, an explanation of exactly what breaks the internal logic, references to the specific story bible elements involved, and a concrete fix. Run repeatedly until no significant issues remain.

---

### `/author-it:storybuilder-character-sheet`

**Usage:** `/author-it:storybuilder-character-sheet [character-name]`

Creates an advanced character sheet for a single character using a slider rubric and your story bible. Grills you relentlessly until the sheet is complete.

The slider rubric maps each trait on a scale from -10 to +10, covering dimensions including:

- Stress / Calm
- Fear / Courage
- Suspicion / Trust
- And additional dimensions pulled from the genre tropes

The character sheet also covers wound/lie, want vs. need, arc direction, physical description, dialogue style, behavioral notes, and how the story will pressure their specific wound. Uses the story bible's genre tropes to ensure the character fits reader expectations.

---

### `/author-it:storybuilder-scene`

**Usage:** `/author-it:storybuilder-scene [chapter]`

Generates a detailed scene brief for a specific chapter in your story bible's outline. All content comes from your answers and story bible — never invented.

The scene brief includes:

- **POV** — which character and why, justified by narrative and emotional importance
- **Genre** — pulled from the story bible
- **Plot + 20–25 Scene Beats** — verbatim plot summary from the outline, broken into granular beats
- **Scene Function** — inciting incident, character introduction, world establishment, foreshadowing device, etc.
- **Characters** — name, role, physical appearance (scene-specific), emotional state and goals, behavioral notes
- **Setting** — sensory-rich environment description (time of day, terrain, sounds, smells, lighting, weather)
- **Main Source of Conflict** — internal, interpersonal, societal, or environmental; how it escalates
- **Tone & Style Notes** — prose voice cues, pacing guidance, foreshadowing direction
- **Symbolism / Thematic Layer** — symbols or archetypal moments to introduce or develop
- **Continuity Considerations** — links to past chapters, foreshadowing for future chapters, worldbuilding consistency

Grills you for missing details rather than inventing them.

---

### `/author-it:storybuilder-dev-editor`

**Usage:** `/author-it:storybuilder-dev-editor`

A developmental editor pass on a chapter — structural evaluation only, no line editing. Evaluates scene function, character motivation, arc progression, pacing, and the visibility of the story's central question. Requires your story bible to be in context.

Produces three outputs:

- **Scene Function Audit** — for each scene: what it does narratively, whether the story question is visible, and a verdict (EARNS ITS PLACE / NEEDS RESTRUCTURING / CANDIDATE FOR CUT)
- **Character Motivation Check** — for each major character: their scene-level goal vs. arc-level desire, motivation alignment, wound pressure, and any off-character moments with specific line quotes
- **Structural Issues Report** — priority-ranked issues (URGENT / HIGH / MEDIUM) with "why it matters" and 2+ concrete fix options per issue; also includes story bible alignment notes and a structural promise tracker

Works chapter-by-chapter. Feeds directly into `/author-it:storybuilder-improvement-plan`.

---

### `/author-it:storybuilder-improvement-plan`

**Usage:** `/author-it:storybuilder-improvement-plan`

A line-by-line chapter critique that identifies specific issues and produces a prioritized improvement plan. Never changes the original text — highlights problems, provides specific examples and recommendations, and leaves the decisions to you.

Checks for:

- **Chapter Flow** — internal structure (hook, tension rise, end-of-chapter promise)
- **Rhythm** — slow pacing, exposition dumps, scene break opportunities
- **Show vs. Tell** — telling instead of showing, exposition blocks, deep POV failures
- **Clichés and Metaphors** — overused constructions and sentence-level bad habits
- **Adverbs and Dialogue Tags** — over-reliance on adverbs; tags other than "said" or "asked"
- **Passive Voice** — flagged instances
- **Fluff and Wordiness** — overly wordy sentences, mushy dialogue, purple prose
- **Voice** — off-character moments, characters sounding too similar, characters speaking out of register
- **Motivation Alignment** — every action should drive plot or character growth
- **Plot Holes and Open Questions** — contradictions, logic gaps, unclear motives
- **Repetition** — word frequency, repeated sentence starters, close reuse
- **Spelling and Grammar** — typos, missing words, tense errors, agreement issues
- **Worldbuilding** — unexplained systems, magic, or objects
- **Tension and Conflict** — internal and external conflict presence; protagonist actively making choices
- **Chapter Ending and Beginning** — does it end and begin where the scene brief specifies?
- **Reader Experience** — does the chapter leave readers eager for the next installment?

---

### `/author-it:storybuilder-prohibited-words`

**Usage:** `/author-it:storybuilder-prohibited-words`

Generates a master wordlist of words that should NOT appear in strong fiction prose, with an explanation for why each word weakens the writing. Use this list to train yourself, run a manual pass over your chapters, or feed it to other skills as a reference.

The output covers:

- **Telling words** — words that name emotions, states, or sensory experiences instead of showing them (e.g. "felt," "realized," "noticed")
- **Vague descriptors** — words that fail to communicate a concrete image (e.g. "nice," "good," "pretty")
- **Filter words** — constructions that insert a narrator between the reader and the character's experience (e.g. "she saw," "he watched," "she noticed")
- **Filler and hedge words** — words that pad sentences without adding meaning (e.g. "just," "really," "basically," "somehow," "slightly")
- **Transition crutches** — words that signal lazy sequencing (e.g. "suddenly," "then," "finally," "next")
- **Redundant phrases** — constructions where the action is implied (e.g. "sat down," "stood up," "faded away")

Each word includes a plain-language explanation of why it weakens the prose and what stronger alternatives look like.