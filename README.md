# Bilingual Content Ops

A repeatable system for producing bilingual (Chinese + English) marketing content across multiple platforms from a single article idea.

Each piece of content ships as:
- A **Chinese blog post** (long-form, for a Chinese-speaking professional audience)
- An **English blog post** (adapted for an English-speaking audience — not a translation)
- **RedNote (Xiaohongshu) cards** — visual summary images for short-form social
- A **LinkedIn post** — adapted for a professional English-speaking feed
- An **HTML email newsletter** — promotes the article to a subscriber list

---

## Workflow

```
Topic / angle
     │
     ▼
Chinese article (long-form, ~950 chars for RedNote, longer for blog)
     │
     ├──► Chinese blog post (HTML)
     │
     ├──► RedNote cards (JPEG images, 1440px Retina)
     │         Card 1: key framework or diagram
     │         Card 2: criteria / checklist
     │
     ├──► Email newsletter (HTML, Mailchimp-compatible)
     │         Promotes the article, links back to blog
     │
     ▼
English adaptation (written fresh in English voice, not translated)
     │
     ├──► English blog post (HTML)
     │
     └──► LinkedIn post (plain text, link in first comment)
```

---

## Why Chinese first?

The primary audience for these articles is Chinese-speaking marketing professionals in North America. Writing Chinese first ensures the content is grounded in that voice and context. The English version is then written independently for a broader English-speaking audience — same ideas, different framing and tone.

---

## Output formats explained

### Chinese blog post (`01-chinese-blog.html`)
Long-form article in flowing paragraphs, no numbered sections or bullet points. Written in first-person, conversational but credible. Mix of Chinese and English terms inline — natural, no special punctuation. Hosted on a blog and shared to RedNote as a link.

### English blog post (`02-english-blog.html`)
Adapted from the same topic — not a translation. Written directly in English in a conversational first-person voice. Same ideas, different structure and examples where appropriate.

### RedNote cards (`03-rednote-card-01.jpg`, `03-rednote-card-02.jpg`)
Retina-quality JPEG images (1440px wide, ~300KB each) built from HTML/SVG and exported via Chrome headless at 3x device scale. Designed in a navy/gold/cream color system. Each card summarizes one key concept from the article visually — uploaded as photos on Xiaohongshu alongside the short-form post text.

### Email newsletter (`04-email-newsletter.html`)
Mailchimp-compatible HTML email. 600px fixed width, table-based layout. Includes a teaser, a callout block with the key insight, a CTA button linking to the full article, and a booking CTA footer. Uses `*|FNAME|*` and `*|UNSUB|*` Mailchimp merge tags.

### LinkedIn post (`05-linkedin-post.md`)
Plain text post adapted for a LinkedIn feed. No formatting — LinkedIn buries formatted posts. Includes notes on posting timing and link placement.

---

## Example

[`examples/b2b-campaign-planning/`](examples/b2b-campaign-planning/) — *Before You Pick a Campaign Theme, Do These Things First*

Topic: how to run a campaign planning brainstorm — which teams to involve, what inputs to gather, and what makes a campaign theme strong enough to carry across channels. Applies to both B2B and B2C.

| File | Format | Platform |
|---|---|---|
| `01-chinese-blog.html` | HTML | Blog (Chinese) |
| `02-english-blog.html` | HTML | Blog (English) |
| `03-rednote-card-01.jpg` | JPEG | Xiaohongshu |
| `03-rednote-card-02.jpg` | JPEG | Xiaohongshu |
| `04-email-newsletter.html` | HTML | Mailchimp |
| `05-linkedin-post.md` | Markdown | LinkedIn |

---

## Tools used

- Articles written and edited in Claude Code
- RedNote cards: HTML/SVG → Chrome headless (`--force-device-scale-factor=3`) → JPEG via `sips`
- Email: hand-coded HTML, table-based layout, tested in Mailchimp
- Blog: static HTML deployed via Netlify
