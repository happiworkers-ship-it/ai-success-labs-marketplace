---
name: infographic-prompt
description: |
  Generate ready-to-paste infographic prompts from raw content. Use this skill whenever the user asks to create an infographic, turn content into an infographic, make a visual summary, build an infographic prompt, or wants to prepare content for an infographic generator tool (Canva, Napkin AI, Gamma, Piktochart, Visme, or any other). Also trigger when the user uploads transcripts, notes, documents, or structured data and says anything like "turn this into an infographic", "make this visual", "create an infographic from this", or "I want to use this for an infographic." ALWAYS use this skill for any infographic-related work — it contains a proven prompt structure and extraction process that produces significantly better generator outputs than writing a prompt from scratch.
---

# Infographic Prompt Generator

This skill takes raw content — transcripts, voice notes, documents, structured data, bullet points, or rough ideas — and transforms it into a polished, structured prompt that can be pasted directly into any infographic generator tool.

## Why This Skill Exists

Infographic generators produce dramatically better results when given a well-structured prompt with clear sections, design direction, and content hierarchy. Most people paste in raw content and get mediocre results. This skill bridges the gap — it extracts the substance from messy input, organises it into a clear visual structure, and outputs a prompt that generators can actually work with.

---

## THE PROCESS

Every infographic prompt follows the same creation process. Do not skip steps.

### Step 1: Understand the Raw Input

Read whatever the user provides — transcript, document, notes, data, or verbal explanation. Identify:
- The core message (what is this infographic actually about?)
- The key sections or steps (what are the distinct chunks of information?)
- The natural hierarchy (is there a flow? a funnel? a comparison? a list?)
- Any frameworks, models, or data that should be visualised

### Step 2: Ask Clarifying Questions

Before writing the prompt, always ask the user:

1. **Audience** — Who is this for? (Do not assume. Different audiences need different framing.)
2. **Layout preference** — What structure works best? Offer options based on the content:
   - Vertical flow with numbered steps (for processes, how-tos)
   - Funnel/tiered layout (for strategies with stages)
   - Side-by-side comparison columns (for versus/comparison content)
   - Grid layout (for multiple equal-weight items like post types or tools)
   - Full feature breakdown (for detailed, data-rich content)
3. **Design vibe** — What feeling should it convey? Offer options like:
   - Bold and empowering (strong colours, confident energy)
   - Clean and professional (minimal, modern, polished)
   - Warm and approachable (earthy tones, inviting feel)
   - Or a combination

If the user has already expressed preferences in the conversation (e.g., they said "for Black women" or "make it bold and clean"), do not re-ask — use what they have given you.

### Step 3: Write the Prompt

Structure every infographic prompt using the template below. This is the proven format that generators respond to best.

---

## THE PROMPT TEMPLATE

Every prompt must include these components in this order:

### 1. Title Line
```
Create a [design vibe] infographic titled "[Title]"
```
- The title should be specific and direct — not generic
- If there is a clear audience, name them in the title
- No subtitle unless the user specifically requests one

### 2. Design Direction
A short paragraph that tells the generator:
- Typography style (strong, clean, bold)
- Colour palette guidance (specific tones, not just "colourful")
- White space and layout feel
- The overall impression it should give

**Template:**
```
Design direction: [Vibe description]. Strong typography with generous white space.
[Colour palette — be specific: e.g., "deep teal or navy with gold or copper accents
on a light/cream background"]. Each section should be visually distinct.
The overall feel should say "[one sentence that captures the energy]."
```

### 3. Layout Instruction
One clear line telling the generator how to arrange the content:
```
Layout: [Structure type — e.g., "Vertical flow with 5 numbered steps",
"3-column comparison", "Funnel with 3 tiers narrowing top to bottom"]
```

### 4. Content Sections
This is the body of the infographic. Each section needs:
- **A clear heading** — bold, descriptive
- **A tag line or context line** (optional) — one sentence that frames the section
- **The actual content** — written in short, punchy statements. Not paragraphs. Infographics need scannable text.
- **Examples where relevant** — concrete, specific, in quotes

**Formatting rules for section content:**
- Write in direct, active voice
- Keep bullet points to one sentence each
- Use dashes not bullet symbols (generators handle dashes better)
- Include specific examples in quotes where they add clarity
- If the content has a "what it does / why it works" pattern, use that structure consistently

### 5. Closing Element
A bold, memorable line that ties the whole infographic together. One sentence. Centred at the bottom.

### 6. Footer CTA
Attribution and call to action:
```
"Follow [Name] | [Brand] for [what they do for their audience]."
```

---

## CONTENT EXTRACTION PRINCIPLES

When working with raw transcripts or messy input, follow these principles:

### Extract, Do Not Copy
The user's raw content is source material, not copy-paste content. Your job is to:
- Pull out the core insights and rewrite them for visual consumption
- Remove filler, repetition, and conversational padding
- Restructure rambling points into clear, hierarchical sections
- Preserve the user's specific frameworks, terms, and examples

### Honour the User's Thinking
If the user has a specific model, framework, or structure (e.g., a 4-stage brand model, a 5-day content engine, a funnel), map the infographic sections to their framework — do not invent your own structure on top of theirs.

### Keep It Scannable
Infographics are not articles. Every piece of text should be:
- Short enough to read in 3 seconds
- Clear enough to understand without the surrounding context
- Specific enough to be useful (no vague platitudes)

### Avoid Generic Filler
Do not pad sections with obvious statements like "This is important because it matters." Every line should earn its place on the infographic.

---

## LAYOUT SELECTION GUIDE

Use this to recommend the right layout based on content type:

| Content Type | Recommended Layout | Why |
|---|---|---|
| Step-by-step process | Vertical numbered steps | Natural top-to-bottom flow |
| Strategy with stages | Funnel / tiered layout | Shows progression and narrowing |
| Tool or product comparison | Side-by-side columns | Easy to scan across |
| Multiple equal items (post types, tips) | Grid (2x3, 3x3) | No hierarchy implied |
| Feature-rich explainer | Full breakdown with sections | Room for tables, examples, workflows |
| Before/after or contrast | Split view (two columns) | Visual tension drives the point |

---

## COMMON PATTERNS

These patterns come up frequently. Use them as building blocks:

### The Comparison Infographic
- Title names the comparison clearly
- Each column has: what it is, what it does, strengths, limitations
- A decision section at the bottom ("Use X when... Use Y when...")

### The Framework Infographic
- Title names the framework
- Sections map 1:1 to the framework stages
- Each stage has: what it means, what it looks like in practice, an example
- Closing line ties the stages together

### The How-To Infographic
- Title starts with "How to..." or names the outcome
- Numbered steps, each with a heading and 2-3 lines of explanation
- Optional contrast section at the bottom (what people see vs what it took)
- Closing line is motivational but specific

### The Post Types / Content Types Infographic
- Title names the collection ("5 Posts Every X Needs")
- Grid or tiered layout grouping by category (e.g., funnel stage)
- Each type has: name, what it does, why it works, one example
- Summary strip at the bottom with the rhythm or system

---

## WHAT NOT TO DO

- Do not include a subtitle unless the user asks for one
- Do not add "opening hooks" or large quote blocks — they waste visual space
- Do not copy content verbatim from reference infographics the user shares — extract patterns and create original content
- Do not add sections the user did not ask for (e.g., "Who It's For" if they want to write that themselves)
- Do not use generic colour guidance like "make it colourful" — always specify a palette direction
- Do not write section content in long paragraphs — everything should be scannable

---

## OUTPUT FORMAT

The final output is always a single text block — the prompt — that the user can copy and paste directly into their infographic generator. Use markdown formatting (bold headings, dashes for lists) so it reads clearly in the conversation, but the content itself should be plain enough that any generator can interpret it.

Always end by asking: "Ready to paste. Want me to adjust anything?"
