---
name: linkedin-content-engine
description: |
  The complete LinkedIn content creation pipeline — from strategy to post to visual asset — in one workflow. Use this skill whenever the user wants to create a LinkedIn post, plan content for today, write a post with a visual, or says anything like "what should I post today?", "create today's post", "write me a LinkedIn post", "help me with my content", or "I need a post for Monday/Tuesday/Wednesday/Thursday/Friday." This skill auto-detects the day of the week, determines the funnel stage (TOFU/MOFU/BOFU) from the 5-Day Brand Engine, writes a full post using the Post Architecture framework in YOUR voice (loaded from your my-linkedin-voice skill), and then generates the right visual asset prompt — an image prompt for TOFU posts, an infographic prompt for MOFU posts, or asks your preference for BOFU posts. ALWAYS use this skill for any LinkedIn content creation — it replaces the need to manually chain multiple skills together.
---

# LinkedIn Content Engine

**Part of the Brand Magnetism Accelerator by Ngozi Cadmus — AI Success Labs**

The all-in-one content creation pipeline that turns "I need a post" into a complete LinkedIn post plus the right visual asset prompt — every time, with zero guesswork.

This skill orchestrates four systems:

1. **The 5-Day Brand Engine** — decides WHAT type of content to create based on the day of the week and funnel stage
2. **The Post Architecture** — decides HOW to structure the post (Hook → Develop → Deliver → Close)
3. **Your Voice & Style** — decides how the post SOUNDS (loaded from your `my-linkedin-voice` skill)
4. **The Visual Asset Generator** — produces the right visual prompt based on funnel stage

The whole point: you say "I need a post" and the engine handles strategy, structure, voice, AND the visual — without you having to think about which framework to use or which visual type fits.

---

## BEFORE YOU START: Your Voice Skill

This engine needs YOUR voice to write posts that sound like YOU. Before using this skill, you must have a skill called **`my-linkedin-voice`** installed.

If you don't have one yet, there's a template included with this plugin. See the **"How to Create Your Voice Skill"** section at the bottom of this document — it walks you through everything step by step.

**The engine will read your `my-linkedin-voice` skill every time it writes a post.** This is how it knows your tone, your audience, your offers, your credentials, and your voice rules. Without it, the engine will write generic posts that don't sound like you.

---

## THE WORKFLOW

Every time the user asks for a post, follow these stages in order. Don't skip stages, but move through them briskly — the user wants a post, not a lecture.

### Stage 0: Load the Voice

Before writing anything, read the user's `my-linkedin-voice` skill. This gives you:
- Their voice and tone rules
- Their audience / ICP
- Their credentials and proof points
- Their offers and CTAs
- Their formatting preferences
- Their voice don'ts

If the skill doesn't exist, stop and tell the user: "I need your voice skill to write posts that sound like you. Let's set up your `my-linkedin-voice` skill first — I'll walk you through it."

### Stage 1: Detect the Day & Funnel Stage

Check what day of the week it is. Map it to the 5-Day Brand Engine:

| Day | Funnel Stage | Content Type | Visual Asset |
|-----|-------------|--------------|--------------|
| Monday | TOFU (Awareness) | Problem-Aware / Contrarian Take | **Image prompt** (linkedin-image-prompt style) |
| Tuesday | TOFU (Awareness) | Personal Story / Community | **Image prompt** (linkedin-image-prompt style) |
| Wednesday | MOFU (Trust) | Education / How-To | **Infographic prompt** (infographic-prompt style) |
| Thursday | MOFU (Trust) | Deep Value / Framework | **Infographic prompt** (infographic-prompt style) |
| Friday | BOFU (Conversion) | Direct Sell / Lead Magnet | **Ask the user** (could be image, infographic, or carousel) |

Tell the user: "It's [day], which is a [TOFU/MOFU/BOFU] day — [content type]. Here's what I'm going to create for you."

If the user specifies a different day or funnel stage than the current day, go with what they ask for. The auto-detection is a starting point, not a cage.

### Stage 2: Gather the Content

Ask the user what they want to post about. They might:

- Give you a topic or idea ("I want to post about client onboarding systems")
- Upload a document, transcript, or notes
- Say "surprise me" or "you decide" — in which case, suggest 2-3 specific post ideas based on the day's content type and THEIR niche (from their voice skill)

If they've given you enough to work with, move straight to writing.

### Stage 3: Choose the Entry Point & Hook

Before writing, make two strategic decisions:

**Entry Point** (from the Post Architecture):

- **Broad Entry** — opens with something universal, then narrows to the niche. Best for TOFU (Monday/Tuesday) when you want to attract new people.
- **Niche Entry** — opens by speaking directly to the audience. Best for MOFU/BOFU (Wednesday-Friday) when you want to deepen loyalty and convert.

The funnel stage suggests the default, but the content might call for the opposite — use judgment.

**Hook Type** (from the Post Architecture — pick the one that fits the content):

- **The Declaration** — a bold statement that takes a stand
- **The Reveal** — a hidden truth, stat, or experiment result
- **The Moment** — a cultural event or trending topic through your lens
- **The Flip** — a contrarian take that contradicts expectations
- **The Claim** — a personal result stated without apology

The hook must be 12 words maximum. Its only job is to stop the scroll.

### Stage 4: Write the Post

Follow the Post Architecture stages: **Hook → Develop → Deliver → Close.**

#### Hook (Stage 1)
Use the Three-Line Rule:

```
Line 1: Hook — bold, specific, emotional or surprising (~55 chars max)
[blank line]
Line 2: Re-hook — adds tension, contradiction, or curiosity (~55 chars max)
[blank line]
Line 3: Payoff or pivot — makes them NEED to read on
```

The hook must be about the READER or a universal tension — never about you first.

#### Develop (Stage 2)
Build the case using one or more techniques:

- **Evidence Stacking** — stats and data piled up with → formatting
- **Rhythm Building** — repetitive parallel structures that create emotional momentum
- **Story / Narrative** — a specific, concrete example
- **Naming the Invisible** — putting words to what the audience feels but hasn't been able to say

#### Deliver (Stage 3)
The payoff — what the reader gets for staying:

- **The Empowerment Turn** — flip from pain to power (the engine of shareability — this is the single most important technique for virality)
- **The Solution** — steps, tips, actionable breakdown (best for Wednesday/Thursday educational content)
- **The Reframe** — changing how the reader sees the situation entirely

#### Close (Stage 4)
End with action. Pick from:

- **DM Trigger** — "DM me '[KEYWORD]' to [specific action]"
- **Repost Call** — "♻️ Repost if [statement]"
- **Community Call** — rally the audience around shared identity
- **Low-Friction Question** + 👇 — easy to answer (yes/no, a number, one word)

Most posts combine a Low-Friction Question + Repost Call.

**CRITICAL: Apply the user's voice skill throughout.** Use their tone, their language patterns, their formatting preferences, their audience framing. The post must sound like THEM, not like a template.

### The Full Post Output

Structure every post with these four sections:

```markdown
# Post: [Title]

**Type:** [Category]
**Funnel Stage:** [TOFU/MOFU/BOFU]
**Theme:** [One sentence]

---

## The Post Body

[The post — hook, body, question, repost line]

## Pinned Comment

[CTA: opening insight → proof/framework → offer mention → DM trigger]
```

After writing the post body, ALWAYS run the character count to verify it's under 3,000 characters:

```bash
awk '/^## The Post Body$/,/^## Pinned Comment$/' [filename] | grep -v '^## The Post Body' | grep -v '^## Pinned Comment' | sed '/^$/d' | wc -c
```

If over 3,000 — cut. Don't ask. Cut.

### Stage 5: Generate the Visual Asset Prompt

This is the conditional logic that ties it all together:

**If TOFU (Monday/Tuesday) → Generate an image prompt:**

1. Ask for brand colours (hex codes) if not already known — need at least 2
2. Read the post and identify the core tension, emotional engine, and key line
3. Generate a bold headline (max 8 words — declarative, not descriptive)
4. Design a visual metaphor (a visual argument, not a literal illustration)
5. Write 3 concepts, each with colour variants
6. Follow the full linkedin-image-prompt format: editorial illustration style, clean bold lines, graphic novel aesthetic, dramatic lighting, realistic skin tones (brand colours NEVER on skin)

**If MOFU (Wednesday/Thursday) → Generate an infographic prompt:**

1. Ask about audience (if not obvious), layout preference, and design vibe
2. Extract the core sections from the post content
3. Write a structured infographic prompt with: title line, design direction, layout instruction, content sections, closing element, footer CTA
4. Follow the full infographic-prompt template format — scannable, no paragraphs, dashes not bullets

**If BOFU (Friday) → Ask the user which visual type they want:**

Present the options:
- **Image prompt** — for posts led by social proof, testimonials, or a bold statement
- **Infographic prompt** — for posts that break down an offer, framework, or results
- **No visual / carousel** — for posts using screenshots, photos, or a separate carousel

Then generate accordingly using the relevant format above.

---

## COMMON MISTAKES TO AVOID

1. **Writing in a generic voice** — always load and apply the user's `my-linkedin-voice` skill. If it doesn't exist, help them create it before writing any posts.
2. **Narrating carousel content** — the post must stand alone without the visual
3. **Plagiarising hooks** — when given example posts for inspiration, use only the STRUCTURE, not the words
4. **Making it too short or too repetitive** — the post should feel substantial, not like a tweet thread
5. **Over-using emojis** — a few structural markers (📌, →, 👇, ♻️) are fine. Don't litter every line
6. **Forgetting the visual** — every post gets a visual asset prompt. TOFU gets image, MOFU gets infographic, BOFU gets asked. Never skip this stage.
7. **Selling in the post body** — the post delivers value. The pinned comment does the selling. No links, no "sign up here," no pricing in the post body.

---

## QUICK REFERENCE: The Weekly Rhythm

**Monday** (TOFU) → Problem-aware post + Broad entry + Image prompt
**Tuesday** (TOFU) → Personal story post + Broad entry + Image prompt
**Wednesday** (MOFU) → Education/how-to post + Niche entry + Infographic prompt
**Thursday** (MOFU) → Deep value/framework post + Niche entry + Infographic prompt
**Friday** (BOFU) → Conversion post + Niche entry + Ask user for visual type

---

## HOW TO USE THIS SKILL

When someone says "I need a post" or "what should I post today":

1. **Load the voice** → read their `my-linkedin-voice` skill
2. **Detect the day** → announce the funnel stage and content type
3. **Ask for the topic** (or suggest ideas if they don't have one)
4. **Choose entry point + hook type** based on funnel stage and content
5. **Write the full post** — all four sections, character count verified, in their voice
6. **Generate the visual asset prompt** — image, infographic, or ask (based on funnel stage)
7. **Present everything together** — the post and the visual prompt, ready to use

The goal: one request in, complete content package out.

---

---

## HOW TO CREATE YOUR VOICE SKILL

Your voice skill is what makes this engine write posts that sound like YOU — not like a template, not like someone else. This is the most important setup step.

### What You Need

Create a skill called **`my-linkedin-voice`** with a file called `SKILL.md` inside it. The engine looks for this exact name every time it writes a post.

### Step-by-Step Guide

**Step 1: Create the skill folder**

In your Claude skills directory, create a folder called `my-linkedin-voice` with a `SKILL.md` file inside it.

**Step 2: Fill in each section below**

Copy the template below and fill in every section with YOUR information. Be specific — the more detail you give, the better your posts will sound.

---

### THE TEMPLATE

```markdown
---
name: my-linkedin-voice
description: |
  My personal LinkedIn voice and style rules. This skill defines how I sound,
  who I write for, what I offer, and the rules for writing posts in my voice.
  Used by the linkedin-content-engine to write posts that sound like me.
---

# My LinkedIn Voice

## WHO I AM

[Write 2-3 sentences about who you are professionally. Include your name, what you do, and what you're known for.]

Example: "I'm [Name], a [role/title] who helps [audience] achieve [outcome]. I'm known for [your thing — your approach, your perspective, your unique angle]."

## WHO I WRITE FOR (My Audience / ICP)

[Describe your ideal reader. Be specific — not just "entrepreneurs" but what kind, what stage, what they're struggling with.]

- Who are they?
- What industry or niche?
- What's their biggest pain point?
- What do they want but don't have yet?

## MY VOICE

[Describe how you sound when you write. Think about the posts you've written that felt most "you." What made them sound like you?]

Fill in each:

- **Tone:** [e.g., "Direct and warm," "Bold but empathetic," "Conversational with authority," "Calm and strategic"]
- **Energy:** [e.g., "High energy and passionate," "Measured and thoughtful," "Fiery and unapologetic"]
- **Language style:** [e.g., "British English," "American English," "Casual with industry terms," "No jargon ever"]
- **Sentence style:** [e.g., "Short punchy sentences. Rhythm matters." or "Longer, flowing sentences with nuance." or "A mix — short for impact, long for explanation."]
- **Paragraph style:** [e.g., "No paragraph longer than 2-3 sentences" or "I write in longer paragraphs with detail" or "One sentence per line, lots of white space"]

## VOICE DON'TS

[What should the AI NEVER do when writing as you? These are the things that would make a post sound fake or off-brand.]

Examples:
- Don't use [specific words or phrases that aren't you]
- Don't sound like [a type of voice you hate — e.g., "a LinkedIn guru," "a corporate newsletter," "a motivational poster"]
- Don't use [specific formatting you dislike — e.g., "excessive emojis," "numbered lists for everything," "ALL CAPS for emphasis"]
- Never claim [things that aren't true about you]
- Never reference [topics that aren't your lane]

## MY CREDENTIALS & PROOF POINTS

[List the specific claims, numbers, and credentials the AI is allowed to use. Be exact — these will appear in posts.]

Examples:
- "[Specific revenue number] generated from [specific source]"
- "[Number] clients/customers helped"
- "[Specific achievement — award, stage, feature, collaboration]"
- "[Years of experience] in [field]"
- "[Qualification or certification]"

**Important:** Only list things that are TRUE and that you want to appear in posts. The AI will use these exact claims — don't exaggerate.

## MY OFFERS & CTAs

[List what you sell or promote, and how you want the AI to reference them in pinned comments.]

For each offer, include:
- **Name:** [The offer name]
- **What it is:** [One sentence description]
- **Who it's for:** [Specific audience]
- **How to reference it:** [The language you want used — e.g., "my 12-week programme" not "my course"]
- **DM trigger word:** [The keyword people DM you — e.g., "STRATEGY," "BLUEPRINT," "START"]

## MY FORMATTING RULES

[Any specific formatting preferences for your LinkedIn posts.]

Examples:
- "Always end with a low-friction question + 👇"
- "Always include a ♻️ Repost line"
- "Use → arrows for lists, not bullet points"
- "Never use hashtags in the post body"
- "Maximum 3 emojis per post"
- "Pinned comment always ends with a DM trigger"

## EXAMPLE POSTS (Optional but Powerful)

[Paste 2-3 of your best-performing LinkedIn posts here. These give the AI the clearest signal of how you actually write. The more examples you provide, the better the AI will match your voice.]

### Example Post 1:
[Paste the full post text here]

### Example Post 2:
[Paste the full post text here]

### Example Post 3:
[Paste the full post text here]
```

---

### Tips for a Great Voice Skill

1. **Be specific, not vague.** "I'm direct and warm" is better than "I have a nice tone." "Short punchy sentences, one idea per line" is better than "I like good formatting."

2. **Include your real credentials.** The AI will only claim what you put here. If you say "£50K in revenue," it won't say "£100K." Accuracy builds trust.

3. **Paste your best posts.** Seriously — example posts are the single most powerful thing you can add. The AI learns your rhythm, your word choices, your hooks, everything.

4. **Update it as you grow.** Your voice will evolve. Your offers will change. Your credentials will grow. Update your voice skill every month or whenever something significant changes.

5. **Test it.** After creating your voice skill, ask the engine to write a post and see if it sounds like you. If something's off, add more detail to the relevant section. This is iterative — your first version won't be perfect, and that's fine.
