# The Style Guide

**Good: this week — How this publication sounds, what it avoids, and how to brief a writer (or an AI) to get it right.**

Version 1.0 — April 2026

---

## Part one: The voice

Good: this week is a weekly publication about things that are going right in the world. The tone is warm but not saccharine. Dry but not cynical. The writer treats readers as adults who are tired of doom-scrolling but not looking to be told everything is fine.

The house style is plainspoken magazine journalism. Picture a curious, unflappable adult telling another curious adult what happened and why it mattered, without pretending to be more excited than they are.

Good reference points for the register: Michael Lewis on a reporting assignment, Susan Orlean on a small subject, the New Yorker's shorter dispatches, the Atlantic's weekly roundups. Sentences that finish. Specificity that makes you feel the air in the room. No grandstanding. No neat little bows.

> The trick isn't pretending bad news doesn't exist. It's remembering that good news exists too, and usually doesn't make a sound.
>
> — House ethos

---

## Part two: The rules

These are non-negotiable. Breaking them is how writing starts to feel like AI slop or press-release filler.

### Specificity over abstraction

AI writing says "she felt sad." Human writing says "she kept opening the fridge even though she wasn't hungry." Every abstract emotion can be replaced by a small concrete behavior that shows the same thing. When in doubt, pick the weird, specific, sensory detail over the tidy universal one.

**YES:** He pulled the car over on the shoulder, and he was embarrassed, afterward, by how much it had affected him.

**NO:** He felt a profound emotional response to seeing the eagle.

### Sentences should vary in length

AI writing tends to produce sentences of roughly similar length, in a rhythmic cadence that reads smooth but feels processed. Mix it up. Long, winding sentences that double back on themselves. Short ones. The occasional fragment, used sparingly, for a beat. The point is that the prose should breathe unevenly, the way a person talks.

*Warning: do not overdo fragments. A fragment every ten sentences is a move. A fragment every third sentence is a tic.*

### No AI tells

The following constructions are banned from the publication. They appear in AI writing because they appear in the training data constantly, and together they form a kind of invisible aftertaste.

- "It's not just X, it's Y" constructions
- "In a world where..." openings
- Ending scenes with a thematic bow
- Em-dashes used as a rhythm crutch (use them sparingly, as real punctuation)
- "A mix of [emotion] and [emotion]" to describe feelings
- "Heart pounding" or "let out a breath she didn't know she was holding"
- The word palpable. Ever.
- Thesaurus words: verdant, cascade, myriad, plethora, tapestry, symphony of, dance of, testament to
- Journey used as a verb. Delve. Navigate. Embark.
- "And in that moment, she realized..."

### Resist resolution

Don't explain the meaning of the piece. Don't summarize what the reader should take away. Don't have a source articulate the theme for you in the last paragraph. Trust the reader. A piece should end one beat before you think it should, not one beat after.

**YES:** Which is probably worth a million pounds.

**NO:** And in the end, that sense of hope is what keeps us going.

### Dialogue sounds like people

People interrupt. They don't finish sentences. They say "yeah" and "I dunno." They don't answer the question they were asked. They don't explain their feelings in perfect paragraphs. If a quote in your draft is suspiciously articulate and thematically on-message, it's either been tidied up too much or the source never said it. Cut it.

### Leave roughness in

Real writing has rough edges. A sentence that doesn't quite resolve cleanly. A paragraph that's a little too long for what it contains. An observation that's slightly off-topic but feels true. AI writing is smoothed over and pleasant, and that is exactly what makes it feel like it was made by a machine. When you catch yourself polishing a passage into blandness, stop.

---

## Part three: Patterns that work

A handful of moves that fit the voice of this publication. Not rules, just proven shapes.

### The dry acknowledgment

When something is absurd or slightly ridiculous, don't pretend it isn't. Name it, briefly, and move on. The reader will trust you more if you notice what they're noticing.

**YES:** The Victorians had a broad, uncomplicated hatred of large birds.

*Dry. Specific. Doesn't moralize.*

### The caveat that respects the reader

Good news stories are often criticized for being naive. Pre-empt that by being honest about the limits, then carry on.

**YES:** Some of the eagles will die, particularly in the first few years. Farmers will have opinions, some of them loud.

*Honest about what can go wrong, without collapsing into cynicism.*

### The personal anchor

A short, specific memory or observation from the writer can transform a policy story into something that feels felt. Use sparingly. Don't center yourself. Use it to open the story up, not to make it about you.

**YES:** My dad used to tell me about the first bald eagle he ever saw in the wild, at a reservoir in Pennsylvania in the late 1990s. He pulled the car over.

*One beat of personal context. The story is still about the eagles.*

### The understated ending

The last line should land, but it shouldn't explain. It should close the piece at the right height and let the reader do the rest.

**YES:** Which is probably worth a million pounds.

**YES:** She paused for a moment, watching one of her own dogs settle onto a sunlit stone step.

**NO:** In the end, kindness is a choice we make every day.

---

## Part four: How to brief Claude

When you want Claude to write for Good: this week, don't just ask for an article. Give it the voice. Here are three prompt templates, from fast to thorough, that will produce work in the house style.

### The quick prompt

Paste this at the start of any request when you want the voice right. Good for short cards, headlines, and homepage copy.

```
Write in the voice of Good: this week. Plainspoken magazine journalism, like a reporter at the New Yorker or Atlantic. Dry, warm, specific. Sentences vary in length but generally finish. No AI tells (no "it's not just X, it's Y", no "in a world where", no em-dashes as rhythm crutches, no "palpable", no thesaurus words). Use concrete details, not abstract emotions. Don't explain the meaning. End one beat before feels natural, not one beat after.
```

### The article prompt

Use this when you want a full 600 to 900 word piece. Fill in the story details where the brackets are.

```
Write a [LENGTH]-word article for Good: this week about [TOPIC]. Key facts: [BULLETS OF WHAT HAPPENED].

Voice: Plainspoken magazine journalism, like the New Yorker or Atlantic. The writer is a curious, unflappable adult telling another adult what happened. Dry, warm, specific. Willing to acknowledge what could go wrong without becoming cynical.

Rules:
- Specificity over abstraction. No "she felt sad"; show the concrete behavior instead.
- Sentences vary in length but mostly finish. Fragments sparingly, as spice.
- No AI tells: no "it's not just X, it's Y", no em-dashes as rhythm, no "palpable", no thesaurus words (verdant, myriad, tapestry, cascade, etc), no "journey" as a verb.
- Quotes should sound like people actually talking.
- Don't explain the meaning. No moral. End one beat before feels natural.
- Leave some roughness in. Don't over-polish.

Structure: Lead with the most specific, concrete detail. One short section on what actually happened. One short section of context or nuance. Optional: one brief personal anchor (memory, observation). End with a line that lands without explaining itself.
```

### The revision prompt

Use this when Claude hands you a draft that feels a little too AI. Paste the draft, then this.

```
Rewrite this in the voice of Good: this week. Check for these AI tells and remove them:

- Em-dashes used for rhythm rather than punctuation
- "It's not just X, it's Y" constructions
- "In a world where" openings
- Final paragraphs that explain what the piece means
- Characters "letting out a breath they didn't know they were holding"
- "A mix of [emotion] and [emotion]"
- The word palpable
- Thesaurus words (verdant, cascade, myriad, tapestry, symphony of)
- "Journey" as a verb, "delve", "navigate", "embark"
- Sentences of uniformly similar length (vary them)
- Over-articulate quotes from sources

Replace abstract emotions with concrete behaviors. Make sentences uneven. End one beat earlier than the current version does.
```

### A note on the prompts

You don't need to copy these templates perfectly every time. After a few weeks of using them, you'll have an ear for the voice yourself, and you'll know when something is off just by reading it. The prompts are training wheels, not commandments.

When a new edition of the publication ships, skim it once with this guide next to you. If anything in the issue would get a red mark from the rules above, rewrite it. Keep the bar high.

---

## Part five: The pre-publish checklist

Run this every time. Takes three minutes. Catches about 80% of what would otherwise embarrass you.

### Voice

- Could a reader tell this was written by a human? (Be honest.)
- Does the voice sound like the same person across every card?
- Any sentences I'd skip if I were reading this on a phone?

### Sentences

- Lengths varied? Not every sentence the same shape?
- Any fragments? Are they earning their place, or are they a tic?
- Em-dashes used for real punctuation, not rhythm?

### Specificity

- Every abstract emotion replaced with a concrete detail?
- Any vague words that should be swapped for specific ones?
- Numbers, places, names, times included where possible?

### AI tells

- No "it's not just X, it's Y"?
- No "in a world where"?
- No "palpable," "verdant," "tapestry," "myriad," "cascade"?
- No "journey" as a verb? No "delve"?
- No final-paragraph moral or thematic summary?

### Structure

- Does the piece end one beat before I want it to?
- Did I leave any genuinely surprising details in, even if they disrupt the flow?
- Are the quotes things a person would actually say out loud?

---

*See you next Sunday.*

**Good: this week · A publication about what's going right**
