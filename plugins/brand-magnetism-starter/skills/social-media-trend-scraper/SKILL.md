---
name: social-media-trend-scraper
description: |
  Scrape trending conversations from X (Twitter) and Reddit using Apify, then analyse the results to produce a trend report, content ideas, and ready-to-publish LinkedIn posts — all tailored to YOUR topics and YOUR voice. Use this skill whenever the user asks to scrape social media for trends, research what's trending in their niche, find content ideas from Twitter/X or Reddit, do a social listening sweep, or says things like "what's trending in my space?", "scrape X for content ideas", "do a trend analysis", "find what people are talking about in [topic]", "research social media trends for my content", or "I need fresh content ideas from Twitter." Also trigger when the user wants to turn social media data into LinkedIn posts, or wants a monthly/weekly content research workflow. ALWAYS use this skill for any social media trend scraping and analysis work — it contains the complete pipeline from raw data to publishable content.
---

# Social Media Trend Scraper & Content Idea Generator

A complete pipeline that turns live social media conversations into actionable LinkedIn content. You provide the topics — the skill handles scraping, analysis, ideation, and draft posts.

---

## WHAT THIS SKILL DOES

1. **Scrapes X (Twitter)** for trending conversations across your chosen topics using Apify
2. **Scrapes Reddit** (optional) for deeper community discussions on the same topics
3. **Analyses the data** to identify 3–5 major trends with signals, pain points, and angles
4. **Generates 10 content ideas** mapped to LinkedIn funnel stages (TOFU/MOFU/BOFU)
5. **Writes 3 ready-to-publish LinkedIn posts** with pinned comments and CTAs
6. **Saves everything** as a Markdown file (and optionally a .docx for Google Docs)

---

## BEFORE YOU START

### Required: Apify Connector

This skill uses Apify to scrape social media. The user must have the Apify MCP connector installed. If the Apify tools are not available, tell the user: "This skill needs the Apify connector to scrape social media. Would you like me to help you set that up?"

### Optional: Your LinkedIn Voice Skill

If the user has a `my-linkedin-voice` skill installed, load it before writing posts. This makes the draft posts sound like THEM instead of generic LinkedIn content.

If no voice skill exists, write posts using general LinkedIn best practices (short sentences, conversational, value-first, clear CTA).

---

## THE WORKFLOW

Follow these stages in order. Move briskly — the user wants results, not a play-by-play.

### Stage 0: Gather Topics from the User

Ask the user for 3–5 topic areas to research. Frame it like this:

> "What 3–5 topics should I scrape for trending conversations? These should be the themes your audience cares about — the intersections where your expertise meets their problems."

**If the user has already provided topics** (in their message or from prior context), confirm them and proceed.

**Example topics:**
- "AI + Personal Branding"
- "Black Women in Tech"
- "LinkedIn Growth Strategy"
- "AI Content Creation Tools"
- "Solopreneur Automation"

Also ask (or infer from context):
- **Who is your audience?** (e.g., "Black women in corporate transitioning to entrepreneurship")
- **What do you sell/offer?** (e.g., "AI-powered personal branding programme")

These inform the "angle" section of the trend analysis.

---

### Stage 1: Scrape X (Twitter)

For each topic, run the Apify Twitter scraper:

**Actor:** `xquik/x-tweet-scraper`

**Input per topic:**
```json
{
  "searchTerms": ["<topic search phrase>"],
  "maxItems": 50,
  "tweetLanguage": "en",
  "sort": "Top"
}
```

Tips for search terms:
- Use 2–3 word phrases, not full sentences
- Add the current year to time-sensitive topics (e.g., "LinkedIn growth strategy 2026")
- Combine related terms with quotes for precision

**Run all topics concurrently** (launch all scrapes before waiting for results). Use `async: true` if supported, then poll with `get-actor-run` until complete.

**Collect from results:**
- Tweet text/content
- Engagement metrics (likes, retweets, views)
- Author follower count
- Date posted

Aim for 150–200 total tweets across all topics. If a scrape returns fewer than expected, that's fine — proceed with what you have.

---

### Stage 2: Scrape Reddit (Optional)

If time permits and the user wants depth, also scrape Reddit:

**Actor:** `easyapi/reddit-posts-search-scraper`

**Input per topic:**
```json
{
  "searchTerms": ["<topic>"],
  "maxItems": 100,
  "sort": "relevance",
  "time": "month"
}
```

**Important:** Reddit scrapes can be slow or hit memory limits. If they time out or fail:
- Do NOT block the workflow waiting for Reddit
- Proceed with Twitter data — it's usually sufficient
- Note in the final report that Reddit data was unavailable

---

### Stage 3: Analyse the Data

Read through all scraped content and identify **3–5 major trends**. For each trend, document:

1. **Trend name** — a punchy, descriptive title
2. **What's happening** — 2–3 sentence summary of the conversation
3. **Key signals** — 4–6 specific data points (viral tweets, engagement numbers, notable voices)
4. **Pain point** — what problem or tension does this trend reveal for the audience?
5. **The user's angle** — how does this connect to what THEY teach/sell/offer?

**Analysis principles:**
- Weight by engagement (a tweet with 50K views matters more than one with 200)
- Look for TENSION — the best content comes from opposing viewpoints
- Identify what's NEW — what shifted in the last 2–4 weeks?
- Connect every trend back to the user's expertise and audience
- Note specific people, companies, or events driving the conversation

---

### Stage 4: Generate 10 Content Ideas

From the trends, generate 10 LinkedIn content ideas. Each idea needs:

1. **Title** — working title for the post
2. **Hook** — the opening line (first 1–2 sentences the reader sees before "see more")
3. **Angle** — what's the argument or insight?
4. **Format** — text post, carousel, video script, or poll
5. **Funnel stage** — TOFU (awareness/reach), MOFU (trust/value), or BOFU (conversion/sell)
6. **Hook type** — The Moment, The Claim, The Reveal, The Flip, or The Declaration

**Distribution guideline:** Aim for roughly 4 TOFU, 4 MOFU, 2 BOFU ideas.

**Hook types explained:**
- **The Moment** — anchors to a specific event or news ("X just did Y")
- **The Claim** — bold statement that demands attention ("The biggest lie in [field] is...")
- **The Reveal** — promises hidden information ("Nobody is talking about this...")
- **The Flip** — takes conventional wisdom and inverts it ("You've been told X. The opposite is true.")
- **The Declaration** — takes a firm stand ("I refuse to...")

---

### Stage 5: Write 3 Draft Posts

Select the 3 strongest ideas (one from each funnel stage if possible) and write full LinkedIn posts.

**Post structure (The Post Architecture):**
1. **Hook** (1–3 lines) — stop the scroll, create curiosity
2. **Develop** (body) — build the argument, tell the story, deliver value
3. **Deliver** (the payoff) — the insight, lesson, or framework
4. **Close** (CTA) — engagement prompt + repost ask

**If the user has a `my-linkedin-voice` skill:** Load it and follow their voice rules exactly.

**If no voice skill exists, use these defaults:**
- Short sentences and paragraphs (1–3 lines max)
- Conversational, not corporate
- One idea per post — go deep, not wide
- Use white space generously
- End with a genuine question or engagement prompt
- Include a repost line
- Write a pinned comment with: proof points, programme/offer details, and a DM CTA

**Each post should include:**
- The post body (ready to copy-paste into LinkedIn)
- A pinned comment (the soft sell with social proof + CTA)
- Metadata: funnel stage, entry point (broad/niche), hook type

---

### Stage 6: Package & Deliver

Save the complete analysis as a Markdown file:

```
Social-Media-Trend-Analysis-[Month]-[Year].md
```

Structure:
- **Part 1:** Trend Summary (all 3–5 trends with signals and angles)
- **Part 2:** 10 Content Ideas (table format with hook, angle, format, funnel stage)
- **Part 3:** 3 Ready-to-Publish Posts (with pinned comments)
- **Appendix:** Data sources, date range, search terms, total results

Save to the user's workspace folder.

**If the user asks for a .docx:** Use the `docx` skill to create a formatted Word document.

---

## HANDLING EDGE CASES

- **Apify rate limits or failures:** Report which scrapes failed, proceed with available data. Even 50 tweets is enough to spot trends.
- **Not enough data on a topic:** Note it in the report and suggest the user refine that search term next time.
- **User wants to add Reddit later:** The Markdown file can be updated — just re-run with Reddit data appended.
- **User wants this scheduled:** Suggest using the `schedule` skill to run this monthly (first Monday of month works well for monthly content planning).

---

## EXAMPLE INVOCATIONS

- "Scrape Twitter for trends in AI coaching and personal development"
- "What's trending in the solopreneur AI space? I need content ideas."
- "Do a social media trend analysis for my niche — I focus on HR tech and future of work"
- "Research what people are saying about LinkedIn algorithm changes and turn it into posts"
- "Run my monthly trend scrape — same topics as last time"

---

## OUTPUT QUALITY CHECKLIST

Before delivering, verify:
- [ ] Each trend has specific data points (not vague observations)
- [ ] Pain points are real problems the audience faces (not just "people are talking about X")
- [ ] Content ideas have genuine hooks (would YOU stop scrolling?)
- [ ] Draft posts follow the Post Architecture (Hook → Develop → Deliver → Close)
- [ ] Pinned comments include social proof and a clear, low-friction CTA
- [ ] The user's expertise and offer are woven into the angles (not bolted on)
- [ ] Funnel stages are balanced (not all TOFU)
- [ ] The report includes metadata (date range, search terms, data volume)
