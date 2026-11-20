# Bilingual Content Skill

A Claude Code skill and workflow for turning one English article idea into a full set of English and Chinese marketing content: blog posts, social posts and an email newsletter.

The skill itself is in [`skill/SKILL.md`](skill/SKILL.md). The rest of this repo explains the workflow and shows a worked example.

Each piece of content ships as:
- An **English blog post** (written first)
- A **LinkedIn post** (English social, adapted from the blog)
- A **Chinese blog post** (written fresh in Chinese, not a word-for-word translation)
- **RedNote (Xiaohongshu) cards** (Chinese social, as visual summary images)
- An **HTML email newsletter** (promotes the article to a subscriber list)

---

## Workflow

```
Topic / angle
     │
     ▼
English article (written first, in a plain first-person voice)
     │
     ├──► English blog post (HTML)
     │
     ├──► LinkedIn post (plain text, link in first comment)
     │
     ▼
Chinese adaptation (written fresh in Chinese, same ideas, not translated word for word)
     │
     ├──► Chinese blog post (HTML)
     │
     ├──► RedNote cards (JPEG images, 1440px Retina)
     │         Card 1: key framework or diagram
     │         Card 2: criteria / checklist
     │
     └──► Email newsletter (HTML, Mailchimp-compatible)
               Promotes the article, links back to the blog
```

---

## Why English first?

Starting in English gives one clear source version that is easy to review, edit and approve. The Chinese version is then adapted for a Chinese-speaking professional audience: same ideas, with the examples, phrasing and structure changed so it reads naturally in Chinese. A straight translation tends to sound stiff, so the adaptation step is written fresh, then checked against the English for accuracy.

---

## Use the skill

Copy `skill/SKILL.md` into a folder named `bilingual-content` inside your Claude Code skills folder, then ask for the content set in plain words, for example: "Write a bilingual content set about [topic]." Fill in your voice notes and brand placeholders first. The skill stops at a review gate after the English article and again after the Chinese adaptation.

---

## Output formats explained

### English blog post (`01-english-blog.html`)
Long-form article in a conversational first-person voice. No numbered sections or bullet-point lists, so it reads like a person talking. Includes the two RedNote card images as figures.

### LinkedIn post (`03-linkedin-post.md`)
Plain text post adapted for a LinkedIn feed. No formatting, because LinkedIn buries formatted posts. Includes notes on posting timing and link placement.

### Chinese blog post (`02-chinese-blog.html`)
Long-form article in flowing paragraphs, written in first person, conversational but credible. Chinese and English terms are mixed inline the way professionals actually write, with no special punctuation.

### RedNote cards (`04-rednote-card-01.jpg`, `04-rednote-card-02.jpg`)
Retina-quality JPEG images (1440px wide, about 300KB each) built from HTML and SVG and exported with Chrome headless at 3x device scale. Each card summarizes one key concept from the article visually and is uploaded as a photo on Xiaohongshu alongside the short post text.

### Email newsletter (`05-email-newsletter.html`)
Mailchimp-compatible HTML email. 600px fixed width, table-based layout. Includes a teaser, a callout block with the key insight, a button linking to the full article and a booking footer. Uses `*|FNAME|*` and `*|UNSUB|*` Mailchimp merge tags.

---

## Example

[`examples/b2b-campaign-planning/`](examples/b2b-campaign-planning/): *Before You Pick a Campaign Theme, Do These Things First*

Topic: how to run a campaign planning brainstorm: which teams to involve, what inputs to gather, and what makes a campaign theme strong enough to carry across channels. Applies to both B2B and B2C.

| Order | File | Format | Platform |
|---|---|---|---|
| 1 | `01-english-blog.html` | HTML | Blog (English) |
| 2 | `02-chinese-blog.html` | HTML | Blog (Chinese) |
| 3 | `03-linkedin-post.md` | Markdown | LinkedIn (English social) |
| 4 | `04-rednote-card-01.jpg`, `04-rednote-card-02.jpg` | JPEG | Xiaohongshu (Chinese social) |
| 5 | `05-email-newsletter.html` | HTML | Mailchimp |

---

## Tools used

- Articles drafted and edited with Claude Code
- RedNote cards: HTML and SVG, then Chrome headless (`--force-device-scale-factor=3`), then JPEG via `sips`
- Email: hand-coded HTML, table-based layout, tested in Mailchimp
- Blog: static HTML deployed via Netlify

---

## Limits

- Examples use placeholders (`[Your Brand]`, `[your-site.com]`). Replace them with your own before publishing.
- A native speaker should review the adaptation, since idioms and tone are easy to get slightly wrong.
- This is a workflow and a set of formats, not an automated translation tool.

## License

MIT. See `LICENSE`.
