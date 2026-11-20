---
name: bilingual-content
description: Turn one English article into a full bilingual content set: English blog post, LinkedIn post, a Chinese blog post written fresh in Chinese (not translated word for word), RedNote card copy and a Mailchimp email. Use when asked to write or adapt marketing content for both English and Chinese audiences, or to repurpose one article across blog, social and email.
---

# Bilingual Content

Starts from English, then adapts to Chinese. Each step ends at a review gate. Nothing is published or sent by this skill.

## Before you start: set your voice
Fill these in once (or ask the user) and reuse them:
- **Audience:** who reads the English version and who reads the Chinese version
- **Voice notes:** for example "first person, conversational, no numbered sections", plus any words to avoid
- **Brand placeholders:** `[Your Brand]`, `[your-site.com]`, `[booking-page]`. Never invent real names, links or numbers.

## Workflow

1. **Topic and angle.** Confirm the point of the article in one sentence.
2. **English article.** Write it in the voice above. Strong opening, one idea per paragraph, a forward-looking last line. Show the full article for approval. **Gate: user approves.**
3. **English outputs.**
   - English blog post (HTML or markdown)
   - LinkedIn post: plain text, no formatting, link goes in the first comment
4. **Chinese adaptation.** Write it fresh in Chinese for a Chinese-speaking professional audience. Keep the same ideas, but change examples, phrasing and structure so it reads naturally. Do not translate sentence by sentence. Mix English terms inline the way professionals do, with no dashes or brackets around them. Show the full article. **Gate: user approves, ideally a native speaker.**
5. **Chinese outputs.**
   - Chinese blog post
   - RedNote post copy (dense paragraphs, about 900 to 1,050 characters) plus two cards for the extra content
   - Email newsletter (600px, table-based, Mailchimp merge tags `*|FNAME|*`, `*|UNSUB|*`)
6. **Final check** (see below), then hand the files to the user to publish.

## Quality checks
- Same facts, same numbers and same claims in both languages. List any difference.
- No invented statistics, quotes, names or links. Use placeholders.
- Read each paragraph aloud. If it sounds like a bullet point dressed up as a sentence, rewrite it.
- No hashtags in blog posts.
- Cards: readable at phone size, one idea per card, no personal or employer information.
- Whenever an article is revised, show the **whole updated article**, not only the changed part.

## Output files (suggested names)
`01-english-blog`, `02-chinese-blog`, `03-linkedin-post`, `04-rednote-card-01`, `04-rednote-card-02`, `05-email-newsletter`

See `examples/` for a worked set.
