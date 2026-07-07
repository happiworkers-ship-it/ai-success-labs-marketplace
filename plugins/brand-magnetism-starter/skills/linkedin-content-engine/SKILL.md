---
name: linkedin-content-engine
description: |
  The complete LinkedIn content creation pipeline — from strategy to post to visual asset — in one workflow. Use this skill whenever the user wants to create a LinkedIn post, plan content for today, write a post with a visual, or says anything like "what should I post today?", "create today's post", "write me a LinkedIn post", "help me with my content", or "I need a post for Monday/Tuesday/Wednesday/Thursday/Friday." Also use it when the user pastes a rough draft or idea and wants help shaping it. The skill has two modes: Guide-Me (full pipeline: day detection, funnel stage from the 5-Day Brand Engine, Post Architecture structure, YOUR voice from your my-linkedin-voice skill, visual asset prompt) and Follow-Me (the user leads; the skill assists with strategy and voice applied quietly). Use this skill for any LinkedIn content creation — it replaces the need to manually chain multiple skills together.
---

# LinkedIn Content Engine

**Part of the Brand Magnetism Accelerator by Ngozi Cadmus — AI Success Labs**

The content creation pipeline that turns "I need a post" into a complete LinkedIn post — with as much or as little process as the user wants.

This skill orchestrates four systems:

1. **The 5-Day Brand Engine** — WHAT type of content, based on day and funnel stage
2. **The Post Architecture** — HOW to structure the post (Hook → Develop → Deliver → Close)
3. **Your Voice & Style** — how the post SOUNDS (loaded from the user's `my-linkedin-voice` skill)
4. **The Visual Asset Generator** — the right visual prompt per funnel stage

**The prime directive: the user leads, the frameworks serve.** The frameworks exist to make posts better, not to make the user complete a process. When the user's request and the workflow conflict, the user's request wins — every time.

**The golden rule: SPEECH FIRST, STRUCTURE SECOND.** Write the post like the user is saying it out loud to a friend, then check the structure is there underneath. The framework is quality control, not the starting point. If a post reads like it was built from a template, the voice is wrong.

**Division of labour — this skill orchestrates, it does not own the rules:**

- Structure rules (hooks, arc, closes) → `post-architecture` is authoritative
- Day/funnel strategy → `5-day-brand-engine` is authoritative
- Voice, credentials, offers → the user's `my-linkedin-voice` skill is authoritative

If anything in this document ever conflicts with those skills, defer to them.

---

## STEP ZERO: PICK THE MODE

Before doing anything else, read the user's message and decide which mode fits:

**FOLLOW-ME MODE** — the user already knows what they want. Triggers:

- They pasted a draft, partial draft, outline, or specific idea
- They gave specific instructions ("write a post about X that says Y", "punch up this hook", "make this shorter")
- They asked for one specific piece (just a hook, just a rewrite, just a CTA, just a visual prompt)
- They said "just", "quickly", or otherwise signalled they want speed

**GUIDE-ME MODE** — the user wants the engine to drive. Triggers:

- "What should I post today?" / "I need a post" with no topic
- "Plan my content" / "you decide" / "surprise me"
- They explicitly ask for the full pipeline

If genuinely unclear, ask ONE short question: "Want me to run the full pipeline (day → strategy → post → visual), or just take what you've got and shape it?" Never ask this when the message already makes the mode obvious.

The user can switch modes at any time by saying so ("actually, guide me" / "just follow my lead here").

---

## FOLLOW-ME MODE: The User Leads

**Do exactly what was asked. Nothing more, unless offered in one line at the end.**

1. **Load the voice silently** — read their `my-linkedin-voice` skill and apply it, no announcement. If it doesn't exist or is still an unfilled template, do NOT stop: match the voice of whatever they pasted, and add one line at the end offering to set up their voice skill (see Stage 0).

2. **If they gave a draft: edit THEIR draft.** Preserve their words, their angle, their structure wherever it works. Do not rewrite it into Hook/Develop/Deliver/Close. Do not replace their hook with a "hook type." Improve what's weak, keep what's strong, and keep it recognisably theirs.

3. **Apply the frameworks as a silent diagnostic, not a process.** After doing what they asked, quickly check the post against the Post Architecture and the day's funnel stage. If something is genuinely weak or mismatched, flag it in ONE line with a concrete suggestion, e.g.:
   - "Your opening line is 20 words — a tighter version: '[alt]'. Keep yours if you prefer it."
   - "Heads up: this reads as a sell post and it's a Wednesday (MOFU/education day) — fine if intentional."

   Flag at most 2 things. Never restructure without being asked.

4. **No forced steps.** No day announcement. No entry-point/hook-type discussion. No metadata header. No pinned comment unless asked or it's clearly a conversion post. No questions about brand colours, layout, or vibe.

5. **Deliver just the post** (or just the piece they asked for). Then offer extras in a single closing line: "Want a visual prompt or a pinned comment to go with it?"

6. **Character check, quietly.** If the post exceeds 3,000 characters (LinkedIn's limit), say how far over it is and what you'd cut — their call. Don't cut silently.

**The success measure for Follow-Me mode: the user gets a usable post in one exchange.**

---

## GUIDE-ME MODE: The Full Pipeline

Run the stages below. Move briskly — the user wants a post, not a lecture. Even in this mode, if the user redirects mid-pipeline, follow them (that's a live switch to Follow-Me).

### Stage 0: Load the Voice

Read the user's `my-linkedin-voice` skill: voice and tone rules, audience/ICP, credentials and proof points, offers and CTAs, formatting preferences, voice don'ts.

**Placeholder check:** if the skill still contains unfilled placeholders like "[Your Name]" or "[your role/title]", it hasn't been set up — never write posts using placeholders as if they were voice data. Instead, offer the guided setup:

> "Your voice skill isn't filled in yet — that's what makes posts sound like YOU instead of a template. Want me to interview you? I'll ask a few quick questions about who you are, who you write for, and how you sound, then produce your completed voice file ready to save."

If they say yes: interview them (who they are, audience/ICP, tone and energy, credentials they want used, offers and DM trigger words, formatting preferences, 1-2 example posts if they have them), then produce the completed `my-linkedin-voice` SKILL.md content and tell them how to save it as their own personal skill: in Cowork, via Settings → Capabilities → Skills; in Claude Code, as a folder in their skills directory. **Important: they should save it as their own personal skill, NOT edit the file inside the installed plugin — plugin files get overwritten when the marketplace updates.**

If they'd rather just get a post right now: write it from whatever context they give, and note the tradeoff once — no nagging.

### Stage 1: Detect the Day & Funnel Stage

| Day | Funnel Stage | Content Type | Default Visual |
|-----|-------------|--------------|----------------|
| Monday | TOFU (Awareness) | Problem-Aware / Contrarian Take | Image prompt |
| Tuesday | TOFU (Awareness) | Personal Story / Community | Image prompt |
| Wednesday | MOFU (Trust) | Education / How-To | Infographic prompt |
| Thursday | MOFU (Trust) | Deep Value / Framework | Infographic prompt |
| Friday | BOFU (Conversion) | Direct Sell / Lead Magnet | Ask the user |

Announce it in one line: "It's [day] — [TOFU/MOFU/BOFU], [content type]."

Use the TOFU/MOFU/BOFU labels everywhere, including post metadata (TOFU = Awareness, MOFU = Trust, BOFU = Conversion). Don't mix taxonomies.

If the user specifies a different day, stage, or content type, go with what they ask. The mapping is a starting point, not a cage.

### Stage 2: Gather the Content

If the topic isn't already in their message, ask what they want to post about. They might give a topic, upload a document or notes, or say "you decide" — in which case suggest 2-3 specific ideas based on the day's content type and THEIR niche (from their voice skill).

If they've given you enough, move straight to writing. Don't ask questions the message already answers.

### Stage 3: Choose the Entry Point & Hook

**Entry Point** (defaults, not rules):

- **Broad Entry** — universal opening, narrows to niche. Default for TOFU.
- **Niche Entry** — speaks directly to the audience. Default for MOFU/BOFU.

The content might call for the opposite — use judgment.

**Hook Type** — pick what fits: The Declaration, The Reveal, The Moment, The Flip, or The Claim (see `post-architecture` for the full library).

**Hook guideline:** aim for 12 words or fewer — its job is to stop the scroll. This is a strong default, not a law; a 14-word hook that lands beats a 12-word hook that doesn't. If the user supplied a hook, keep it and offer one tighter alternative only if theirs is weak.

### Stage 4: Write the Post

Follow the Post Architecture: **Hook → Develop → Deliver → Close.** (The `post-architecture` skill is the authoritative source for these rules — read it for the full technique library.)

**Exception:** personality-led posts — rants, hot takes, roast lists, banter — can drop the arc entirely and run on conversational energy, with the structure invisible or absent. Speech first, structure second.

#### Hook

Default to the Three-Line Rule:

```
Line 1: Hook — bold, specific, emotional or surprising (aim ~55 chars)
[blank line]
Line 2: Re-hook — adds tension, contradiction, or curiosity (aim ~55 chars)
[blank line]
Line 3: Payoff or pivot — makes them NEED to read on
```

Default: the hook is about the READER or a universal tension, not about the writer first. (Exception: personal-story posts can open in first person if the first line still creates tension.)

#### Develop

Build the case with one or more: Evidence Stacking (stats with → formatting), Rhythm Building (parallel structures), Story/Narrative (a specific example), Naming the Invisible (words for what the audience feels but can't say).

#### Deliver

The payoff: The Empowerment Turn (pain to power — the engine of shareability), The Solution (steps/tips — best for Wed/Thu), or The Reframe.

#### Close

Default options: DM Trigger, Repost Call (♻️), Community Call, or Low-Friction Question + 👇. A Low-Friction Question + Repost Call is a proven combination — but match the close to the post and the user's formatting rules; don't force the same close every time.

**CRITICAL: Apply the user's voice skill throughout.** Their tone, language patterns, formatting, audience framing. The post must sound like THEM, not like a template.

#### Output format (Guide-Me default)

```markdown
# Post: [Title]

**Type:** [Category]
**Funnel Stage:** [TOFU/MOFU/BOFU]
**Theme:** [One sentence]

---

## The Post Body

[The post]

## Pinned Comment

[CTA: opening insight → proof/framework → offer mention → DM trigger]
```

If the user just wants the post text, drop the wrapper.

#### Character check

Verify the post body is under 3,000 characters (LinkedIn's limit). If over: tell the user by how much and which section you'd trim, then cut with their agreement (or cut and show exactly what you removed if they've said to just handle it).

### Stage 5: Generate the Visual Asset Prompt

Included by default in Guide-Me mode; skip if the user says they don't need one.

**Batch the setup questions into ONE message** (brand colours if unknown, plus layout/vibe for infographics) and offer defaults so the user can just say "yes, defaults." Remember answers within the conversation — never re-ask.

**TOFU (Mon/Tue) → image prompt:** use the `linkedin-image-prompt` skill's format — identify the post's core tension, emotional engine, and key line; bold headline (aim ≤8 words, declarative); a visual metaphor (a visual argument, not literal illustration); 3 concepts with colour variants.

**MOFU (Wed/Thu) → infographic prompt:** use the `infographic-prompt` skill's format — extract core sections; structured prompt with title line, design direction, layout, content sections, closing element, footer CTA.

**BOFU (Fri) → ask which type:** image prompt (social proof / bold statement posts), infographic prompt (offer or framework breakdowns), or no visual/carousel.

---

## DEFAULTS vs HARD RULES

**Hard rules (never break):**

- Apply the user's voice skill when it exists (and never write from unfilled placeholders)
- Only use credentials and claims from their voice skill — never exaggerate or invent
- When given example posts for inspiration, use only the STRUCTURE, never the words
- Never cut or change the user's content silently — show or ask first

**Strong defaults (apply unless the user overrides, in the moment or via their voice skill):**

- Hook ≤12 words; opening lines ~55 chars; Three-Line Rule
- Hook about the reader, not the writer
- Value in the post body, selling in the pinned comment (no links/pricing in body)
- Every Guide-Me post gets a visual prompt; TOFU=image, MOFU=infographic, BOFU=ask
- Close with Low-Friction Question and/or Repost Call
- Metadata header + pinned comment output format

If the user overrides a default twice, treat their preference as the new default for the rest of the conversation and suggest adding it to their `my-linkedin-voice` skill so it sticks.

---

## COMMON MISTAKES TO AVOID

1. **Railroading a user who brought a draft** — if they gave you content, edit their content; don't rebuild it through the pipeline
2. **Writing in a generic voice** — load and apply their `my-linkedin-voice` skill whenever it exists
3. **Writing from placeholders** — "[Your Name]" is not a voice; offer the guided setup instead
4. **Narrating carousel content** — the post must stand alone without the visual
5. **Plagiarising hooks** — structure only, never the words
6. **Making it too short or too repetitive** — substantial, not a tweet thread
7. **Over-using emojis** — a few structural markers (📌, →, 👇, ♻️) are fine
8. **Asking questions the user already answered** — re-read their message before asking anything
9. **Selling in the post body** (default) — the post delivers value; the pinned comment sells

---

## QUICK REFERENCE: The Weekly Rhythm

**Monday** (TOFU) → Problem-aware post + Broad entry + Image prompt
**Tuesday** (TOFU) → Personal story post + Broad entry + Image prompt
**Wednesday** (MOFU) → Education/how-to post + Niche entry + Infographic prompt
**Thursday** (MOFU) → Deep value/framework post + Niche entry + Infographic prompt
**Friday** (BOFU) → Conversion post + Niche entry + Ask user for visual type

---

## HOW TO USE THIS SKILL

**"I need a post" / "what should I post today?" (no content given) → Guide-Me:**

1. Load the voice → 2. One-line day/stage announcement → 3. Get or suggest the topic → 4. Entry point + hook → 5. Full post, voice applied, character-checked → 6. Visual prompt → 7. Present the package.

**"Here's my draft/idea — help me with it" → Follow-Me:**

1. Load the voice silently → 2. Do exactly what they asked, preserving their words → 3. Flag at most 1-2 genuine weaknesses with suggested fixes → 4. Deliver the post → 5. One-line offer of extras (visual, pinned comment).

The goal: the right amount of engine for the request. Full package when they want strategy; fast, faithful help when they know what they want.
