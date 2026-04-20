# The Launch Plan

**Good: this week — Where we are, where we're going, and what to do next, in order.**

Handoff doc — April 2026

---

## The situation: Where we are

You have three working files sitting in a folder on your computer. They open in Chrome and look good. But nothing is on the internet yet, nothing can send you an email, and updating the site next week means editing raw HTML by hand.

That's the starting point. This document lays out the steps to turn what you have into a real publication people can actually find, read, and subscribe to.

### What's built

- Homepage with 8 real stories, color legend, location datelines
- Full article page for the golden eagles lead story
- Submission form (front-end only — doesn't send anything)
- Archive section with 3 past-issue cards
- Style guide with prompt templates for future issues
- Instagram mockups (only as chat visuals, not real files yet)

### What's missing

- A real URL on the internet
- A working submission form that actually emails you
- A way to publish new issues each week without editing HTML
- Actual Instagram post and story image files
- Article pages for the other 7 stories
- Real photography (every image slot is a colored box)
- An analytics tool to see if anyone's reading

### The goal

Real publication. 3–5 hours per week. Weekly cadence, published Sundays. Audience: people who want good news without the forced positivity.

---

## The order: What to do, in what order

You ranked these items in a specific order, and the recommended sequence below swaps a few priorities. The logic: get it real first (live URL), then make it functional (form), then make it repeatable (workflow), then expand distribution (Instagram), then add depth (more articles). Each step unlocks the next.

### Priority 1: Get it live on a real URL
**45 min · $12/yr for domain**

Nothing else meaningfully exists until people can visit it. Vercel + a domain. Free hosting, one-time DNS setup.

### Priority 2: Hook up the submission form to email you
**20 min · Free tier available**

Once it's live, people might actually submit something. Formspree or Web3Forms both work in under 30 minutes.

### Priority 3: Add a workflow for publishing new issues weekly
**2–3 hrs · One-time build**

This is the one that decides whether the publication survives. Build a JSON data file that the HTML reads from, so updating an issue means editing a single clean file, not chasing headlines through markup.

### Priority 4: Build Instagram posts and stories as real image files
**2–3 hrs per week until you have a backlog**

Instagram is where people find publications like this. Generate 9 grid tiles and 3–4 story templates. Eventually automate from the weekly data file.

### Priority 5: Build more article pages for the other 7 stories
**30–45 min per article**

Last on the list because each article is a lot of writing, and without the rest of the infrastructure, they sit in a folder. Do these one or two per week as you publish.

---

## Step 1: Get it live

Goal: a URL you can type into a browser that shows your homepage. Target time: 45 minutes, most of it waiting for DNS to propagate.

### What you'll need

- A GitHub account
- A Vercel account connected to that GitHub
- A domain name ($12–$15/yr at Namecheap, GoDaddy, Hover, or Google Domains)

### The steps

1. Create a new folder on your computer called 'good-this-week'
2. Move the three HTML files into it (homepage, article, and rename homepage to index.html)
3. Initialize a git repo and push to a new GitHub repo called 'good-this-week'
4. In Vercel, click 'Add New Project', import from GitHub, pick the repo
5. Vercel auto-deploys. You'll get a URL like good-this-week.vercel.app immediately
6. Buy a domain. In Vercel project settings, add custom domain. Follow their DNS instructions
7. Wait 5–60 minutes for DNS to propagate. Test in Chrome incognito to avoid cache

---

## Step 2: Make the form work

Goal: when someone submits a story through the form, it lands in your inbox. Target time: 20 minutes.

### Recommended: Formspree

Free up to 50 submissions per month. More than enough for a new publication. You sign up with your email, they give you a unique form endpoint URL, you paste that URL into the form's HTML and you're done. No code needed.

### Why not build a custom Resend integration?

You could, and you already have Resend set up from DCP Portal. But for this use case, Formspree saves you an hour of serverless function setup with no real downside. If submission volume grows past 50/month, you can migrate to Resend later with no data lost.

### What needs to change in the HTML

- The current form uses a JavaScript onClick handler that shows a fake success message
- Replace the `<button onclick="handleSubmit()">` with a regular `<form action="https://formspree.io/f/YOUR_ID" method="POST">` wrapping the inputs
- Keep the styling exactly the same
- Formspree redirects to their thank-you page by default; you can set a custom redirect to keep the user on your site

### Spam protection

Formspree has built-in spam filtering. You don't need to add a CAPTCHA, which would break the clean look anyway.

---

## Step 3: Build the publishing workflow

Goal: publishing a new issue should take 30 minutes, not 3 hours. Target time to build: 2–3 hours once, saves 2+ hours every week after.

### The idea

Right now, every headline and description and image is hard-coded into index.html. That means to update next week's issue, you have to find and replace each one by hand. Easy to break something. Easy to miss a piece.

The fix is to separate content from layout. Create a file called `issue-47.json` (and `issue-48.json`, `issue-49.json`, etc.) that holds just the story data. The HTML reads from the current issue file and renders it. Swapping issues becomes: edit one clean JSON file, save, push to GitHub. Vercel deploys automatically.

### What the JSON file looks like (rough shape)

```json
{
  "issue_number": 47,
  "date": "April 19, 2026",
  "tally": {
    "good_things": 9,
    "stats": ["10.01% of ocean protected", "150 years since..."]
  },
  "lead": {
    "category": "Wildlife",
    "color": "amber",
    "headline": "England is trying to bring back...",
    "deck": "The Victorians hunted them out...",
    "location": "Northern England, UK",
    "read_time": "6 min",
    "slug": "golden-eagles"
  },
  "features": [ ],
  "minis": [ ],
  "shorts": [ ]
}
```

### What the weekly process looks like after this is built

1. Sunday morning: scan Positive News, Good News Network for that week's stories
2. Pick 8–9 stories that fit the publication's tone
3. Open a new chat, paste the quick prompt from your style guide, ask for 8 cards plus a lead article
4. Paste the output into the new issue-XX.json file
5. Commit to GitHub. Vercel deploys automatically
6. Post Instagram tiles (once that step is built)

### Real talk

This is the single highest-leverage thing you can build. Without it, you will stop publishing by week 4. With it, you have a real shot at doing this for months.

---

## Step 4: Build Instagram posts and stories

Goal: every week, you post 9 grid tiles to Instagram plus 3–4 story cards. Each matches the week's issue, shares the color system, and drives readers to the site. Target time: 2–3 hours the first week, 30–40 minutes per week after once templates exist.

### Approach

Two options. The quick way: generate each 1080x1080 tile as an SVG converted to PNG, download and upload manually. The proper way: a small template system where you drop the week's data into a file and get all the images out at once. The proper way is better and not much harder.

### What to generate each week

- 9 grid tiles (1080x1080): 1 masthead tile + 8 story tiles, one per story
- 1 "new issue" story announcement (1080x1920)
- 3–4 "tap through" story cards highlighting specific stories (1080x1920)

### Posting rhythm

Instagram's algorithm rewards consistency and carousel posts. Suggested rhythm: drop the 9 grid tiles Sunday morning as a single carousel post (captioned with a link to the full issue). Post the story announcements Sunday afternoon. Reshare 1–2 individual story tiles to Stories throughout the week.

---

## Step 5: Expand the article pages

Goal: every story has a real article page to click into, not just a card that leads nowhere. Target time: 30–45 min per article with Claude, pacing yourself at 1–2 per week.

### Priority order

1. Lead stories first (most traffic): one article per weekly issue as the lead
2. Features next: the two-column cards are the second most-clicked
3. Minis and shorts last: these can stay as cards without click-throughs

### The workflow

- Start a chat, paste the full article prompt from the style guide
- Give Claude the story source links and any specific angle you want
- Claude writes the piece in the house voice
- Copy it into a new article-SLUG.html file using the existing article.html as a template
- Update the card's link on the homepage to point to the new page

### Backlog note

Don't try to build articles for every past story retroactively. Build them going forward. Old issues can have cards-only; nobody will notice.

---

## Starting a new chat: Prompts to paste

When you start a new chat to work on one of these steps, paste the relevant prompt below. Each gives the next Claude everything it needs to pick up without asking you to re-explain.

### For Step 1: Get it live

```
I'm continuing work on a web publication called Good: this week. I have three working HTML files from a previous chat: index.html (homepage), article.html (a feature article), and the style-guide.docx. They're magazine-styled, use Georgia serif fonts and a cream #faf9f5 background, and the publication covers good news stories in a plainspoken journalism voice.

I want to get it live on the internet. I have GitHub and Vercel accounts (username darrellcassell). I'm a beginner with git/terminal. Please walk me through every step, literally, including the exact commands to type and what to click on each screen.

Also help me pick a domain name. I want something that matches an available Instagram handle.
```

### For Step 2: Form setup

```
I'm working on Good: this week, a web publication I recently launched at [YOUR URL]. The homepage has a submission form that currently does nothing — it just shows a fake thank-you message.

I want to hook it up to Formspree so submissions land in my inbox at hello@darrellcassell.com. I'm a beginner with HTML. Please show me exactly what to change in the form, step by step.
```

### For Step 3: Publishing workflow

```
I'm working on Good: this week, a live publication at [YOUR URL]. I want to separate the story content from the HTML so I can publish new issues by editing a single JSON file instead of hand-editing markup.

Please design a simple data file format (issue-XX.json) that holds all the story content for one weekly issue, then refactor my index.html to read from that file and render the page. I'm a beginner with JavaScript. Explain each step clearly and keep it as simple as possible while still working.
```

### For Step 4: Instagram images

```
I'm working on Good: this week, a weekly good-news publication. I need to generate Instagram posts and stories for the current issue. Use the same branding as the website: cream #faf9f5 background, Georgia serif type, black #1a1a1a masthead tiles with gold accents, and category colors (amber for heartwarming, blue for science, teal for health, pink for kindness, purple for wildlife, coral for community, soft pink for technology, green for good laws).

Generate 9 grid tiles (1080x1080) and 3 story cards (1080x1920) based on this week's stories: [PASTE STORIES OR JSON]. Each tile should be downloadable as a PNG.
```

### For Step 5: New article page

```
I'm writing an article for Good: this week in the house voice (plainspoken magazine journalism, specific over abstract, sentences that finish, no AI tells). Reference story: [PASTE URL OR SUMMARY]. Key facts: [LIST].

Write a 600–900 word feature in the style of my existing golden eagles article (golden-eagles.html). Use Darrell as the author byline. Follow all rules in the style guide: no "it's not just X, it's Y", no em-dashes as rhythm, no thesaurus words, no moral/lesson in the final paragraph. End one beat early.

Return the full HTML for the new article page, using my existing article.html as the template.
```

---

## Context for every future chat

Paste this at the start of any Good: this week chat so the next Claude doesn't have to learn everything from scratch.

```
PROJECT: Good: this week — a weekly web publication about good news
AUTHOR: Darrell
TECH STACK: HTML/CSS/vanilla JS (single-page), hosted on Vercel at goodthisweek.news, submissions via Formspree, subscriptions via Buttondown, stories sourced from Positive News and Good News Network

DESIGN: Cream #faf9f5 background, Georgia serif type, magazine layout, bold color blocks per story category. Two-font system: Georgia for all prose/headlines, system sans for kickers and metadata.

CATEGORY COLORS (match across website + Instagram):
- Heartwarming: #FAC775 (amber)
- Science: #378ADD (blue)
- Health: #1D9E75 (teal)
- Kindness: #D4537E (pink)
- Wildlife: #7F77DD (purple)
- Community: #D85A30 (coral)
- Technology: #F4C0D1 (soft pink)
- Good laws: #C0DD97 (green)

VOICE: Plainspoken magazine journalism (New Yorker, Atlantic, Michael Lewis). Specific over abstract. Sentences vary in length but finish. No AI tells. See style-guide.md for full rules.

KNOWN FILES:
- index.html (homepage)
- about.html (about page, letter-style)
- [slug].html files for each article (golden-eagles.html, coffee-mental-health.html, etc.)
- notes.md (running project log)
- docs/style-guide.md (house voice and rules)
- docs/launch-plan.md (this document)

I'M A BEGINNER WITH CODE. Walk me through every step literally, no assumed knowledge.
```

**Pro tip:** Save the prompt above as a note in your phone or a sticky note on your monitor. Every time you start a new chat about this project, paste it first. Saves 10 minutes of re-explaining.

---

## A note for future you

If you follow the order in this document, in about 2 weeks of focused side-project time you'll have a live, functional publication with a working submission form, an efficient publishing workflow, and a growing Instagram presence.

Here's the part nobody warns you about. The hard part is not week 1. Week 1 is fun. The site is new, the design is fresh, you're excited. The hard part is week 7, when you've skipped a week, you feel bad about it, and the temptation is to quit quietly rather than restart imperfectly.

When (not if) that happens: publish the next issue anyway. Late is fine. Shorter is fine. A missed week is fine. The only failure state is stopping forever. Almost every good publication you've ever read went through a version of this and came out the other side because the writer decided to show up again, unglamorously, on a Tuesday.

*Good: this week will be a real publication if you decide it is, and not a second before.*

---

*See you next Sunday.*

**Good: this week · A publication about what's going right**
