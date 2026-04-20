# Good: this week — Project Notes

## For any Claude picking this up

### About the project

Good: this week is a weekly good-news publication. One issue published every Sunday, featuring roughly 8 stories curated from real news sources (Positive News, Good News Network, etc.) rewritten in a plainspoken magazine voice. Darrell Cassell is the writer and publisher. Kaitlyn (his wife) is not involved in this project but is mentioned in about-page context. This is a side project that Darrell intends to run for a long time.

### About Darrell

Darrell is a wedding photographer in Asheville, NC by day. He is a beginner with code — not a developer. Every technical step should be explained thoroughly and literally, with exact commands to run and exact things to click. Assume no prior knowledge. He learns fast but needs things broken down, not summarized.

### How Darrell prefers to work

- Be honest, not a cheerleader. If something won't work or seems like a bad idea, say so and explain why. Pushback is appreciated.
- Before recommending a solution, surface the trade-offs. Don't default to the first answer that comes to mind.
- Don't suggest features or changes that weren't requested. Stay on task.
- Don't rewrite copy or code that wasn't asked about. Surgical edits only.
- When in doubt, ask a clarifying question rather than assuming.
- Keep responses focused. No hype language, no "great question!" openings, no overselling.
- When suggesting code changes, write them as a clear prompt Darrell can paste into Claude Code, not as code blocks for him to manually apply.

### Voice guardrails for anything published

The publication's voice is plainspoken magazine journalism — think New Yorker "Talk of the Town," Michael Lewis, Susan Orlean. Specific over abstract. Sentences vary in length but mostly finish. Dry, warm, specific. Willing to acknowledge what could go wrong without becoming cynical.

Banned from the writing:
- "It's not just X, it's Y" constructions
- Em-dashes used for rhythm (fine as punctuation, sparingly)
- "In a world where" openings
- "Palpable," "verdant," "cascade," "myriad," "tapestry," "symphony of"
- "Journey" as a verb, "delve," "navigate," "embark"
- Moral summaries or "and in that moment, she realized..." endings
- Over-articulate quotes from sources

See `docs/style-guide.md` for the full writing style guide and `docs/instagram-guide.md` for the Instagram visual system.

### Working style rules

- When Darrell says "walk me through this step by step," do exactly that. Numbered steps. Exact commands. Screenshots described in detail. Don't skip to the end.
- When asking for code changes, write a prompt for Claude Code rather than posting code directly. Claude Code has filesystem access and actually makes the change. Copy-pasting code into files is error-prone.
- When something fails or a change doesn't take, assume the cache might be stale before assuming the change didn't happen. Ask Darrell to verify with a hard refresh.
- At the end of each session, offer to update `notes.md` with a new session heading.

---

# Good: this week — Project Notes

Live URL: https://goodthisweek.news
Vercel project name: good-this-week
GitHub repo: github.com/darrellcassell/good-this-week
Instagram: @goodthisweek
Domain registrar: Hover
Subscribe service: Buttondown
Submissions service: Formspree
Deploy workflow: edit files → git add . → git commit -m "..." → git push → live in ~30s

## File structure

- `index.html` — homepage
- `about.html` — about page (letter-style, drop cap)
- Article files (one per story, slug-based):
  - `golden-eagles.html`
  - `coffee-mental-health.html`
  - `ai-bowel-cancer.html`
  - `school-lunch-standards.html`
  - `record-store-day.html`
  - `us-road-deaths.html`
  - `free-electricity-summer.html`
  - `womens-health-strategy.html`
- `favicon.png` — gold "G:" on black
- `images/og-home.png` — homepage social share card
- `images/og-eagles.png` — eagles article social share card

## Reference docs (in repo under `docs/`)

- `docs/style-guide.md` — house voice, banned AI tells, prompt templates for writing articles
- `docs/instagram-guide.md` — Instagram visual system, tile specs, posting rhythm, caption templates
- `docs/launch-plan.md` — 5-step launch roadmap, context briefings, copy-paste prompts for future chats

## Adding Open Graph cards to a new article

1. Make a 1200×630 share image, save as `images/og-[slug].png`
2. Copy the OG/Twitter meta block from an existing article
3. Update the URL, title, description, and image path
4. Save, commit, push
5. Test at opengraph.xyz before sharing

## Useful commands

- `grep [text] [file]` — search for text inside a file
- `git status` — see what's changed
- `git log --oneline -5` — see last 5 commits
- `pwd` — print current folder
- `ls` — list files in current folder

## Weekly workflow

1. Find 7 stories from Positive News / Good News Network
2. Claude writes them in house voice (use style guide prompts)
3. Claude Code creates article files from existing template
4. Verify, push, live in 30s
5. Update `notes.md` at end of session

---

## Session log

### April 19, 2026 — Launch day (Issue No. 1)

Shipped:
- Site live at goodthisweek.news with custom domain and HTTPS
- 8 articles (1 deep-dive feature + 7 shorter pieces), all using house voice
- Working Buttondown subscribe flow (with double opt-in confirmation)
- Working Formspree story submission form
- OG share cards (homepage + eagles article)
- Custom favicon (gold "G:" on black)
- Clean homepage with honest archive placeholder ("starts here")

Documents created (stored outside repo):
- Full style guide (voice, rules, banned AI tells, prompt templates)
- Launch plan (5-step roadmap, context briefings for future chats)
- About page built as letter-style layout with drop cap

Bug fixes same day:
- Renamed `article.html` template to slug-based filenames
- Removed "No doom. No scroll. Just news that doesn't hurt." from masthead tagline
- Changed all author bylines from "Darrell C." to "Darrell"
- Fixed dead links in footers (About, Archive, Instagram)
- Wired Subscribe link in top bar to open subscribe modal
- Replaced archive section with "starts here" placeholder

Known issues to revisit:
- Article hero images still pending (plan: Gemini-generated)
- Buttondown firewall blocked test IPs during testing — real subscribers from fresh IPs should work; email support@buttondown.email if issues persist
- Consider custom sending domain (mail.goodthisweek.news) once on paid Buttondown tier
- Instagram announcement post pending polish check on mobile

### April 19, 2026 — Mobile layout fixes (evening)

Fixed:
- Homepage horizontal overflow (page was swiping sideways on mobile) — added `overflow-x: hidden` to body
- Lead story meta row overflow — stacked vertically on mobile instead of horizontally
- Color legend clipping on right side — changed from 4-column to 2-column on mobile
- "Seven days of receipts" numbers section clipping — stacked to 1 column on mobile
- "More good from this week" heading + kicker cramping on article pages — stacked vertically on mobile

### April 20, 2026 — Instagram brand guide

Built `docs/instagram-guide.md` — a complete Instagram brand guide covering the visual system, posting rhythm, tile specs, and captions.

Key decisions made this session:
- Instagram strategy centered on text-based carousels and stories. No Reels.
- Sunday carousel is the weekly anchor (6–8 permanent feed slides). Mon–Sat is one disappearing story per day. Optional 1–2 mid-week permanent singles, reused from the Sunday carousel.
- Carousel designed as a swipe-through sequence, not a 3×3 profile grid. Slide 1 is always a scroll-stopping headline (no "Issue N" masthead on slide 1 — that was the original mockup's approach and we moved away from it).
- Five tile types defined: headline, stat, pull quote, shorts roundup, CTA. Decision rule for which tile type a story gets is in Part three.
- Warm/cool color alternation rule added to prevent muddy-looking carousels.
- Bio link points directly to goodthisweek.news — no Linktree, no /instagram landing page.
- Captions aim for read-right-now over subscribe-right-now (the site's subscribe modal handles subscription once they land).
- Caption first line must work above the "... more" cutoff (~125 chars). Three to six hashtags, no more.

Open items on the Instagram guide (worth revisiting after first real week):
- Typography sizes in Part four are best-guess proportional, not measured from mockup. First real carousel at 1080×1080 will likely reveal some need tuning by 10–20%.
- Soft ink hex values in the color table were partially invented — worth a second look against the actual website CSS.
- Technology (soft pink) ink color is specified as black; no mockup example existed for that category. May need a deep-pink alternative.
- Shorts roundup tile format is new — not in the original mockup. Works on paper, needs a real test.

Also updated:
- `docs/launch-plan.md` — added Instagram guide to the "KNOWN FILES" list, added a sixth copy-paste prompt for weekly Instagram generation.
- `notes.md` — this entry, plus updated references from `.docx` (the old pre-repo format) to `.md` (current repo paths).

### Next session to-dos

- [ ] Generate hero images for each article (Gemini)
- [ ] Mobile polish walkthrough — look for any remaining clipping after today's fixes
- [ ] Generate Issue No. 1 Instagram content using the new guide (first real test of the system)
- [ ] Confirm Buttondown subscribe flow works for real subscribers from fresh IPs
- [ ] First non-self subscriber test
- [ ] After first real Instagram week: revisit instagram-guide.md typography sizes and soft-ink colors based on what rendered well vs. what didn't