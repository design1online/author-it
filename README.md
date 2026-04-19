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

Helps you create a standardized template you can use to help you write compelling scenes or evaluate an existing scene. This skill generates a report that provides:

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