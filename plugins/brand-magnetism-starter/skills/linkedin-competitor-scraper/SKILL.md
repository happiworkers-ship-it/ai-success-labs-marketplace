---
name: linkedin-competitor-scraper
description: >
  Scrape LinkedIn posts from competitor profiles using Apify and generate an engagement-driven content analysis report. Use this skill whenever the user wants to scrape LinkedIn posts, analyze competitor content, research what's working on LinkedIn, study other creators' posts, build a swipe file from LinkedIn, or says things like "scrape LinkedIn", "what are my competitors posting", "analyze their LinkedIn content", "pull posts from these profiles", "competitor research on LinkedIn", or "what's working for other creators." Also trigger when the user pastes LinkedIn profile URLs and asks for analysis, or mentions Apify in the context of LinkedIn scraping. This skill handles the full pipeline: scraping via Apify, data extraction, theme analysis, and report generation. ALWAYS use this skill for any LinkedIn scraping or competitor content analysis work.
---

# LinkedIn Competitor Scraper & Content Analyzer

This skill scrapes LinkedIn posts from competitor profiles using Apify and produces a consolidated content analysis report — both as an in-chat summary and a formatted .docx file.

## Default Competitor Profiles

These are the default profiles to scrape. The user can override, add to, or replace this list at any time.

| Creator | LinkedIn URL |
|---------|-------------|
| Kasey Brown | https://www.linkedin.com/in/kasey-brown-384001b5/ |
| Fatima Khan | https://www.linkedin.com/in/fatima-rasheed-khan/ |
| Jasmin Alic | https://www.linkedin.com/in/alicjasmin/ |
| Lara Acosta | https://www.linkedin.com/in/laraacostar/ |
| Jennifer Orji | https://www.linkedin.com/in/jennifer-orji-ces/ |

**Default settings:** 10 posts per profile, no time limit, exclude reposts.

## Workflow

### Step 1: Confirm Scope

Before scraping, quickly confirm with the user:
- Are we using the default competitor list, or do they want to change it?
- How many posts per profile? (default: 10)
- Any time range filter? (default: no limit)

If the user's message already specifies profiles or says "the usual" / "the defaults", skip confirmation and go straight to scraping.

### Step 2: Scrape via Apify

Use the Apify MCP tools. The actor to use is `harvestapi/linkedin-profile-posts`.

1. **Load the Apify tools** — Use ToolSearch to load `mcp__Apify__call-actor` and `mcp__Apify__get-actor-output` before calling them.

2. **Call the actor** using `call-actor` with this input structure:

```json
{
  "actor": "harvestapi/linkedin-profile-posts",
  "input": {
    "targetUrls": ["<list of LinkedIn profile URLs>"],
    "maxPosts": 10,
    "includeQuotePosts": true,
    "includeReposts": false
  }
}
```

3. **Retrieve results** using `get-actor-output` with the returned `datasetId`. Request these specific fields to keep the response lean:

```
author.name,content,postedAt.date,engagement.likes,engagement.comments,engagement.shares,linkedinUrl
```

Set a limit of 100 (or higher if scraping more than 10 profiles).

4. **Read the full output** — The results may be persisted to a file if they're large. Use the Read tool to access the full dataset from the persisted output path.

### Step 3: Classify Each Post

Before writing the report, classify each post into one of these content types based on its content:

| Type | What to look for |
|------|-----------------|
| Personal Story | Vulnerability, transformation narrative, "I used to... now I..." |
| Framework/Education | Numbered steps, how-tos, repeatable systems |
| Results/Proof | Specific revenue figures, follower counts, client outcomes |
| Testimonial | Client success stories, member spotlights |
| CTA/Promo | Direct program promotion, enrollment pushes, "DM me" |
| Listicle/Resource | Curated tool lists, free resource roundups |
| Industry News | Platform updates, trend commentary |
| Motivational | Encouragement, mindset, "keep going" energy |
| Sponsored/Ad | Paid partnerships, #ad, brand mentions |
| Contrarian/Thought Leadership | Challenging conventional wisdom, bold opinions |
| Milestone/Celebration | Follower milestones, community celebrations |

### Step 4: Write the Analysis Report

The analysis report has a specific purpose: help the user understand what content themes are driving engagement and why, so they can apply these insights to their own content strategy.

#### In-Chat Summary

Write a conversational but substantive analysis covering:

1. **Creator performance overview** — Which creators are generating the most engagement and why. Include average likes, comments, and shares per creator.

2. **Top content themes** (4-6 themes, ranked by average total engagement) — For each theme:
   - What the theme is and how creators are using it
   - Why it resonates (go beyond surface-level observation — explain the psychological or strategic reason it works in this niche)
   - 2-3 specific post examples with engagement numbers (likes, comments, shares) and a direct LinkedIn link

3. **Key takeaways** — Actionable insights the user can apply to their own content strategy. Be specific: "lead with personal story, close with the lesson" is better than "post more personal content."

Follow this analysis prompt as your north star:

> You will be given a list of recent LinkedIn posts and some metadata about them. Please write a consolidated report on the content themes that are driving the most engagement, along with commentary on why those themes are resonating. Include engagement numbers for each post and a direct link to the post as well.

#### .docx Report

After the in-chat summary, generate a formatted Word document. Use the docx skill (read the docx SKILL.md) for creation instructions. The report should include:

- Title page with date and "Prepared for Ngozi Cadmus | AI Success Labs"
- Creator performance overview table (avg likes, comments, shares per creator)
- Theme-by-theme analysis sections with top posts, engagement data, and LinkedIn links
- Key takeaways section with actionable insights
- Data source footer noting the scrape date and methodology

Save the .docx to the user's workspace folder and provide a `computer://` link.

### Step 5: Offer a Spreadsheet (Optional)

After delivering the report, offer to also create an Excel spreadsheet with the raw data (all posts, filterable by creator and post type) if the user wants to dig deeper. Only create it if they say yes — the report is the primary deliverable.

## Handling Errors

- **Apify authentication error**: Ask the user to check their Apify connector in Cowork settings. They may need to disconnect and reconnect with a fresh API token.
- **No posts returned for a profile**: The profile URL may be incorrect or the account may be private. Note which profiles returned no data and proceed with the rest.
- **Large output persisted to file**: When `get-actor-output` returns a persisted output path, use the Read tool to access the full data.

## Cost and Technical Notes

- The Apify actor `harvestapi/linkedin-profile-posts` does NOT require LinkedIn cookies or login credentials.
- Cost: approximately $0.002 per post scraped. A full default run (5 profiles x 10 posts) costs ~$0.10.
- Always include direct LinkedIn post URLs so the user can click through to the actual posts.
- Total engagement = likes + comments + shares. Sort themes by average total engagement (highest first).
