# AI Success Labs Marketplace

The official Claude plugin marketplace for students of the **Brand Magnetism Accelerator** by Ngozi Cadmus — AI Success Labs.

> Build a magnetic LinkedIn brand with AI. Turn your expertise into income, authority, and influence — without hustle culture.

## Install in 30 seconds

**In Claude Code** (terminal):

```
/plugin marketplace add happiworkers-ship-it/ai-success-labs-marketplace
/plugin install brand-magnetism-starter@ai-success-labs-marketplace
```

**In Cowork / Claude desktop:** open Settings → Capabilities, add this marketplace (`happiworkers-ship-it/ai-success-labs-marketplace`), then install the **brand-magnetism-starter** plugin.

That's it. You now have the full Brand Magnetism Accelerator student toolkit.

## What's inside

The `brand-magnetism-starter` plugin gives you 8 skills working together as one system:

| Skill | What it does |
|-------|--------------|
| **linkedin-content-engine** | The all-in-one pipeline, with two modes. Say "what should I post today?" and it runs the full strategy → post → visual pipeline. Or paste your own draft and it follows YOUR lead — polishing your words, not replacing them. |
| **5-day-brand-engine** | The Monday–Friday LinkedIn content strategy. Tells you what to post each day (TOFU / MOFU / BOFU). |
| **post-architecture** | The Hook → Develop → Deliver → Close framework for every post you write — plus the viral post mechanics library. |
| **my-linkedin-voice** | A template for YOUR voice, audience, offers, and credentials. Used by the engine to make every post sound like you. See setup below. |
| **linkedin-image-prompt** | Turns any post into 3 editorial image prompts ready to paste into your image generator (Gamma, Midjourney, ChatGPT, etc). |
| **infographic-prompt** | Turns raw content into ready-to-paste infographic prompts for Canva, Napkin AI, Gamma, Piktochart, Visme, and more. |
| **linkedin-competitor-scraper** | Pulls posts from competitor LinkedIn profiles and reports what's working for them. *Needs Apify — see setup below.* |
| **social-media-trend-scraper** | Scrapes trending conversations on X (Twitter) and Reddit in your niche and turns them into content ideas and draft posts. *Needs Apify — see setup below.* |

## First step after installing — set up your voice

The engine needs YOUR voice to write posts that sound like YOU. The easiest way — no files, no folders:

1. Say to Claude: **"Help me set up my LinkedIn voice."**
2. Claude interviews you — who you are, who you write for, how you sound, what you offer — and produces your completed voice file.
3. Save it as your own personal skill: in **Cowork**, Settings → Capabilities → Skills; in **Claude Code**, as a `my-linkedin-voice` folder in your skills directory.

⚠️ Don't edit the `my-linkedin-voice` file inside the installed plugin — plugin files are overwritten whenever the marketplace updates. Your personal copy is yours forever.

Then say: *"What should I post on LinkedIn today?"* — and the engine takes it from there.

## Optional — set up Apify for the two research skills

The two scraper skills (`linkedin-competitor-scraper` and `social-media-trend-scraper`) use **Apify**, an external scraping service. Everything else in the toolkit works without this — set it up only when you want competitor or trend research.

1. Create a free account at [apify.com](https://apify.com)
2. Connect the **Apify connector** to Claude (in Cowork: Settings → Connectors; search for Apify)
3. Note: scraping runs use Apify credits — the free tier includes some, heavier use is paid

If a scraper skill reports an authentication error, check the Apify connector is connected and signed in.

## Updates

When new skills or improvements are released:

```
/plugin marketplace update ai-success-labs-marketplace
```

(In Cowork: Settings → Capabilities → update the marketplace.)

## Need help?

- Sales page: https://aisuccesslabs.com/brand-magnetism-accelerator
- Free guide — *The 5 Mistakes Black Women Make on LinkedIn:* https://guide.aisuccesslabs.com/
- Free profile audit checklist: https://linkedinchecklist.aisuccesslabs.com
- LinkedIn: https://www.linkedin.com/in/ngozicadmus/

---

© Ngozi Cadmus / AI Success Labs / Happiworkers Ltd. All rights reserved. The frameworks and skills in this marketplace are the intellectual property of Ngozi Cadmus and are licensed for personal use by Brand Magnetism Accelerator students. Do not redistribute, resell, or rebrand.
