Load The Series Brainstorm
Prompt the user to provide the series brainstorm using the /brainstorm-a-series skill and store it as [braindump].

From the [braindump] locate the [genre_tropes] which we will use later.

Create A Story Bible
Given the above [braindump] information and [genre_tropes], I want you to create a pre-writing [story_bible] that has a list of everything the author will need to fully flesh out the characters, worldbuilding, and outline for [book_title].

Here's what you should include:

Characters:  Make a complete list of characters, including minor ones, needed for this book. Label these as appropriate with their role in the story (protagonist, antagonist, side character, henchman, comic relief, love interest, etc.) Give a brief explanation of who the character is and their role in the story, but don't give too many details just yet. These should be no more than 1-2 sentences per character. When referencing a group of individuals instead of individual characters, make sure you name 3-5 minor characters who are or would be a part of that group, just so the author has named characters to use when writing scenes with members of those groups in them.

Worldbuilding Info: Make a complete list of all locations, objects, and other worldbuilding information that will be needed for this book. Give a brief explanation of what the worldbuilding element is and its role in the story, but don't give too many details just yet. These should be no more than one sentence per worldbuilding element.

Outline: Make a plan on what will be needed to fully outline this book. Do not actually start outlining the book yet, but give instructions on what will be needed and any suggestions you have.

Characters
Given the above [braindump] information, [genre_tropes], and [story_bible], I want you to create a fleshed-out list of all the important characters needed specifically for [book_title].
For each major character, I want you to have the following:

A physical description
Their primary role in the story (i.e. protagonist, antagonist, love interest, henchman, etc.)
Their most appropriate Myers-Briggs profile, Enneagram, and Clifton Strengths.
Their core motivation, what is their heart's desire that is driving them most of the time?
A brief explanation of their background before the start of the story
An interesting quirk, hobby, or something that makes them unique. This should be something that doesn't necessarily fit with the story, but makes the character more interesting.
Dialogue style, how do they talk?
Dialogue examples, I want specific examples of dialogue they might give in relaxed, stressful, thoughtful and exciting situations. These dialogue samples do not have to be part of this particular story, they are just to show off the vocal mannerisms of the character.

For minor characters, just have 1-2 sentences for each that gives us a brief understanding of their background, their core desire, and their relationship to the plot.
Format your [characters] list using Markdown in the following format:

[book_title]
Major Character Name:

Physical Description: [insert details here]
Role in Story: [insert details here]
Personality Profiles: [insert details here]
Core Motivation: [insert details here]
Background: [insert details here]
Quirk: [insert details here]
Dialogue Style: [insert details here]
Dialogue Samples: [insert details here]
[continue this for all major characters]

Minor Characters:

[MINOR CHARACTER NAME]: [1-2 sentence description here]
[MINOR CHARACTER NAME]: [1-2 sentence description here]
[continue for all minor characters]

Only include the asked-for character details. Do not add any preamble, commentary, or anything other than what I've asked for above

Worldbuilding
Given the above [braindump], [genre_tropes], and [story_bible], I want you to create a fleshed-out list of all important setting and worldbuilding elements needed specifically for [book_title].
I want you to organize all worldbuilding elements into categories. Which categories you use will depend on the genre and what you already have available to you in the outline and dossier, however, some of the categories you MIGHT use include:
-High-level Worldbuilding
-Setting(s)/Locations
-Magic Systems/Technology
-Groups/Races
-Gods/Dieties
-Geography/Nature
-Population/Politics
-Culture
-History/Lore
-Religion/Beliefs
-Languages

Do not use a category if it doesn't apply to the book/series, or if there aren't elements in the story bible that apply to that category.

Format your [worldbuilding] list using Markdown in the following format:

[book_title]
WORLDBUILDING CATEGORY HERE:

NAME OF WORLDBUILDING ELEMENT: [insert 3-4 sentences here, make the details specific]
NAME OF WORLDBUILDING ELEMENT: [insert 3-4 sentences here, make the details specific]
NAME OF WORLDBUILDING ELEMENT: [insert 3-4 sentences here, make the details specific]
[continue for each worldbuilding element in this category]

NEXT WORLDBUILDING CATEGORY HERE:

NAME OF WORLDBUILDING ELEMENT: [insert 3-4 sentences here, make the details specific]
NAME OF WORLDBUILDING ELEMENT: [insert 3-4 sentences here, make the details specific]
NAME OF WORLDBUILDING ELEMENT: [insert 3-4 sentences here, make the details specific]
[continue for each worldbuilding element in this category]
[continue for each worldbuilding category]

Only include the asked-for worldbuilding details. Do not add any preamble, commentary, or anything other than what I've asked for above.

Story Outline
Using the above [worldbuilding], [characters], [braindump], [genre_tropes] and [story_bible] relentlessly grill the user into creating a fully fleshed out outline for [book_title]. The summary for each chapter should have specific details rather than vague allusions to what should happen. If the user is struggling provide suggestions and recommendations to help but do not write any of the text for them.

Format your list using Markdown in the following format:

[book_title]
CHAPTER TITLE HERE:
[Add a 200-250 word description of what happens in this chapter here in paragraph format (1-3 paragraphs) using specific details.]

NEXT CHAPTER TITLE HERE:
[Add a 200-250 word description of what happens in this chapter here in paragraph format (1-3 paragraphs) using specific details.]

[continue for each chapter in the outline]
Only include the asked-for outline details. Do not add any preamble, commentary, or anything other than what I've asked for above.

Audit
Once the [story_bible] has been created using the criteria above, prompt the user if they would like to put this [story_bible] content through an audit using the /storybuilder-audit skill to look for inconsistencies, plot holes and flaws.

IMPORTANT

Never generate text for the user, only provide suggestions, examples or recommendations to help them create the story beats that break into an outline and chapters.
Select the appropriate beat sheet based on the information you know going into the session so the chapter outline follows genre and trope expectations.
Take into consideration what you know about the story from the information provided when helping to guide the user, use elements they've already provided (genre, tropes, story dump, character info, world building) in suggestions, examples and recommendations if possible rather than something that falls outside of their genre and tropes.
