# AI Success Labs Marketplace

The official Claude plugin marketplace for students of the **Brand Magnetism Accelerator** by Ngozi Cadmus — AI Success Labs.

Build a magnetic LinkedIn brand with AI. Turn your expertise into income, authority, and influence — without hustle culture.

---

## Install in 30 seconds

**In Cowork / Claude desktop:** go to **Customize → Plugins → Add → Add marketplace**, enter `happiworkers-ship-it/ai-success-labs-marketplace`, then add the plugins you want.

**In Claude Code (terminal):**

```
/plugin marketplace add happiworkers-ship-it/ai-success-labs-marketplace
/plugin install brand-magnetism-starter@ai-success-labs-marketplace
/plugin install engagement-engine@ai-success-labs-marketplace
```

💡 **Turn on Sync automatically.** On the marketplace page in **Customize → Plugins**, switch on **Sync automatically**. New skills then reach you without you having to check for them.

---

## The two plugins

| Plugin | What it covers | Start here? |
| :- | :- | :- |
| **brand-magnetism-starter** | Strategy, writing and visuals. Everything that gets the post made. | Yes. Install this first. |
| **engagement-engine** | What happens around the post. Commenting on other people's content, and turning DM conversations into clients. | After the starter. |

They work together. `engagement-engine` reads your voice from the starter, so install the starter first.

---

## brand-magnetism-starter

8 skills working together as one system.

| Skill | What it does |
| :- | :- |
| **linkedin-content-engine** | The all-in-one pipeline, with two modes. Say "what should I post today?" and it runs the full strategy → post → visual pipeline. Or paste your own draft and it follows YOUR lead, polishing your words rather than replacing them. |
| **5-day-brand-engine** | The Monday–Friday LinkedIn content strategy. Tells you what to post each day (TOFU / MOFU / BOFU). |
| **post-architecture** | The Hook → Develop → Deliver → Close framework for every post you write, plus the viral post mechanics library. |
| **my-linkedin-voice** | A template for YOUR voice, audience, offers and credentials. Used by every other skill to make the writing sound like you. See setup below. |
| **linkedin-image-prompt** | Turns any post into 3 editorial image prompts ready to paste into your image generator (Gamma, Midjourney, ChatGPT, etc). |
| **infographic-prompt** | Turns raw content into ready-to-paste infographic prompts for Canva, Napkin AI, Gamma, Piktochart, Visme and more. |
| **linkedin-competitor-scraper** | Pulls posts from competitor LinkedIn profiles and reports what's working for them. Needs Apify, see setup below. |
| **social-media-trend-scraper** | Scrapes trending conversations on X (Twitter) and Reddit in your niche and turns them into content ideas and draft posts. Needs Apify, see setup below. |

---

## engagement-engine

Posting is half of LinkedIn. The other half happens in everyone else's feed, and in your DMs. Two skills you make your own.

| Skill | What it does |
| :- | :- |
| **my-linkedin-comments** | Paste someone else's post and get a comment written in your voice. Five comment types, the three non-negotiables, and a length guide, so you stop leaving "Great post!" and start getting profile clicks. |
| **my-dm-responder** | Paste a message and get a reply in your voice. The eight-step method: read the lead's temperature, qualify the yes, deliver the value message, handle objections, close cleanly, follow up without chasing. |

**Both have a `FILL THIS IN` section at the top.** Complete it before you use them. Everything below that section is the method and works as written.

`my-dm-responder` needs your real offer and your real price. It is built to ask you rather than guess, so fill it in properly and it will never invent a number, a deadline or a discount on your behalf.

⚠️ **It will not pitch someone in crisis.** If a lead is grieving, has been forced out, or is at rock bottom, the skill holds the space and offers what genuinely helps instead. Fill in the crisis section so it has something real to offer.

---

## First step after installing — set up your voice

Every skill in both plugins reads your voice from `my-linkedin-voice`. Without it, everything sounds like nobody.

The easiest way, no files, no folders:

1. Say to Claude: **"Help me set up my LinkedIn voice."**
2. Claude interviews you — who you are, who you write for, how you sound, what you offer — and produces your completed voice file.
3. Save it as your own personal skill: in **Cowork**, **Customize → Skills**; in **Claude Code**, as a `my-linkedin-voice` folder in your skills directory.

⚠️ **Don't edit the `my-linkedin-voice` file inside the installed plugin.** Plugin files are overwritten whenever the marketplace updates. Your personal copy is yours forever.

Then say: **"What should I post on LinkedIn today?"** and the engine takes it from there.

---

## Optional — set up Apify for the two research skills

The two scraper skills (`linkedin-competitor-scraper` and `social-media-trend-scraper`) use **Apify**, an external scraping service. Everything else in both plugins works without this. Set it up only when you want competitor or trend research.

1. Create a free account at [apify.com](https://apify.com)
2. Connect the **Apify connector** to Claude (in Cowork: **Customize → Connectors**, search for Apify)
3. Note: scraping runs use Apify credits. The free tier includes some, heavier use is paid.

If a scraper skill reports an authentication error, check the Apify connector is connected and signed in.

---

## Updates

New skills and improvements are released to this marketplace over the course of the programme.

**In Cowork / Claude desktop:** go to **Customize → Plugins**, open **ai-success-labs-marketplace**, and select **Check for updates**. Any new plugin appears in the list, ready to add.

Turn on **Sync automatically** on that same page and you will not have to check again.

**In Claude Code (terminal):**

```
/plugin marketplace update ai-success-labs-marketplace
```

Then install anything new by name, for example:

```
/plugin install engagement-engine@ai-success-labs-marketplace
```

**A new plugin will not appear until you check for updates or have Sync automatically on.** If a skill you have been told about is missing, that is almost always why.

---

## Need help?

- **Sales page:** https://aisuccesslabs.com/brand-magnetism-accelerator
- **Free guide — The 5 Mistakes Black Women Make on LinkedIn:** https://guide.aisuccesslabs.com/
- **Free profile audit checklist:** https://linkedinchecklist.aisuccesslabs.com
- **LinkedIn:** https://www.linkedin.com/in/ngozicadmus/

---

© Ngozi Cadmus / AI Success Labs / Happiworkers Ltd. All rights reserved. The frameworks and skills in this marketplace are the intellectual property of Ngozi Cadmus and are licensed for personal use by Brand Magnetism Accelerator students. Do not redistribute, resell, or rebrand.
