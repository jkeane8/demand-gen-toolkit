# Skill: Copy Generator

## What This Skill Does
Generates on-brand marketing copy for LILT or any
company whose context files are loaded in context/.
Produces multiple variants across different formats,
displays them for review and iteration, then saves
to outputs/ only after explicit confirmation.

## What To Read Before Writing Anything
Read ALL of these files before producing a single
word of copy. Do not skip any of them.

1. context/icp.md
   Pay specific attention to:
   - The exact vocabulary and phrases buyers use
   - Pain points by segment — match the language
     to whichever segment is being targeted
   - The "Typical Objections by Buyer Segment"
     section — good copy often addresses or
     pre-empts these directly
   - What triggers them to start looking — use
     these as hooks and angles

2. context/brand_voice.md
   Pay specific attention to:
   - The "Words and Phrases to Avoid" section —
     treat this as a hard rule, not a suggestion
   - The three example sentences that sound like
     the brand and the three that do not — use
     these to calibrate tone before writing
   - The tone scale (3/5) — professional and
     direct, not casual, not stiff corporate
   - Always anchor technical terms to a business
     outcome, never use jargon for its own sake

3. context/competitors.md
   Pay specific attention to:
   - Messaging angles competitors already own —
     avoid these entirely
   - Positioning gaps and vulnerabilities — these
     are the angles worth leaning into
   - Never mention competitor names in copy

4. context/market.md
   Pay specific attention to:
   - Market trends that create urgency or context
   - Use these to make copy feel timely and
     relevant, not evergreen and generic

## What To Ask Me When Activated

Ask these questions one at a time and wait for
my answer before proceeding:

1. What FORMAT do you want?
   Options:
   - LinkedIn ad (headline + body + CTA)
   - Email subject line (subject only, no body)
   - Cold outreach email (subject + full body)
   - Google search ad (headline 1 + headline 2
     + description, character limits apply)
   - Landing page headline + subheadline
   - Webinar promotional copy (title +
     promotional blurb + CTA)
   - Other (I will describe what I need)

2. Which BUYER SEGMENT are we targeting?
   Options based on context/icp.md:
   - Commercial Enterprise / Fortune 500
   - High-Growth Tech / Series B-D SaaS
   - US Federal Government and Defense
   - AI/ML Companies buying training data
   - Other (I will describe)

3. Which PERSONA within that segment?
   (Day-to-day champion like Head of
   Localization, or Executive Sponsor like
   VP of Marketing or CTO — or both)

4. What is the OFFER or TOPIC?
   (What are we promoting or talking about?
   Example: a product demo, a case study,
   a webinar, a specific feature, a campaign
   theme)

5. What FUNNEL STAGE is this for?
   - Awareness (they don't know us yet)
   - Consideration (they are evaluating options)
   - Decision (they are close to buying)

6. How many VARIANTS do you want?
   (Any number — I will produce exactly that
   many distinct approaches, not variations
   of the same angle)

7. Any SPECIFIC ANGLES, CONSTRAINTS, or
   REFERENCES to include or avoid?
   (Optional — press Enter to skip)

## How To Write The Copy

### General rules
- Lead with outcomes and proof, not features
  ("Intel reduced costs by 40%" not "our AI
  is fast and accurate")
- Use specific metrics wherever possible —
  reference real numbers from context files
  when relevant
- Every variant must take a genuinely different
  angle — not the same message reworded
- Match vocabulary exactly to the segment and
  persona — use the buyer's own language from
  context/icp.md, not generic SaaS copy
- Write as if briefing a senior executive:
  clear, direct, evidence-backed, no fluff
- Never use words from the avoid list in
  context/brand_voice.md

### Format-specific rules

**LinkedIn ads**
- Headline: under 70 characters, hook-first
- Body: 150 words maximum
- CTA: one clear action, no passive language
- Best angles for this format: pain-led hooks,
  stat-led hooks, or provocative questions
  that name a specific frustration

**Email subject lines**
- Under 50 characters for mobile
- Avoid clickbait — this audience is senior
  and will delete anything that feels like
  a trick
- Best performers for this ICP: specificity
  ("40% cost reduction at Intel"),
  direct questions naming a pain
  ("Still managing 6 LSPs?"),
  or relevance signals ("For heads of
  localization at enterprise SaaS")

**Cold outreach emails**
- Subject: under 50 characters
- Opening line: no "I hope this finds you
  well" — open with something relevant to
  them specifically
- Body: under 150 words — this audience
  has no patience for long emails
- One CTA only — never give multiple options
- Reference a specific pain point from their
  segment in context/icp.md

**Google search ads**
- Headline 1: 30 characters maximum
- Headline 2: 30 characters maximum
- Description: 90 characters maximum
- Use the buyer's own search vocabulary from
  context/icp.md — write to match intent
- Include a metric or proof point where
  character limit allows

**Landing page headline + subheadline**
- Headline: outcome-first, under 10 words
  where possible
- Subheadline: expand the headline with
  one specific proof point or clarification
- Avoid starting with "We" — lead with the
  buyer's outcome, not the company's claim

**Webinar promotional copy**
- Title: specific outcome or question, not
  a generic topic name
- Blurb: 100 words maximum, lead with why
  this matters right now
- CTA: time-specific where possible
  ("Register before [date]")

### For Government and Defense segment only
- Increase formality to 4/5 on the tone scale
- Use mission-critical, compliance, and
  security language prominently
- Reference specific requirements: FedRAMP,
  IL levels, air-gapped deployment, ITAR,
  cleared linguists, audit trails
- Avoid startup-casual phrasing entirely
- Lead with security and compliance proof,
  not speed or cost

## How To Display Output

After producing all variants:

1. Display everything clearly in the terminal
   with each variant numbered and labeled
   with its angle so I can compare them

2. For each variant include:
   - The angle or strategic approach in one
     sentence (why this one is different)
   - The copy itself, properly formatted
   - One sentence on who this variant works
     best for and why

3. After displaying all variants ask:
   "Would you like to iterate on any of these
   before saving? You can ask me to adjust
   tone, swap an angle, make it shorter,
   add a specific proof point, or rewrite
   a specific variant entirely."

4. Only after I confirm I am happy with the
   output, ask:
   "Ready to save? I will create a file in
   outputs/ named copy_[format]_[segment]
   _[today's date].md"

5. Save only after I say yes.

## Output File Format
When saving, structure the file as:

---
Date: [today's date]
Format: [format name]
Segment: [segment name]
Persona: [persona name]
Offer/Topic: [what was being promoted]
Funnel Stage: [awareness/consideration/decision]
Variants produced: [number]
---

Then each variant with its angle label,
the copy, and the "best for" note.

## Rules This Skill Must Always Follow
- Never save anything without explicit
  confirmation from me
- Never mention competitor names in copy
- Never use words from the avoid list in
  context/brand_voice.md
- Always produce genuinely distinct variants —
  different angles, not different wording
- Always read all four context files before
  writing — never skip this step
- If context files are missing or empty,
  stop and tell me before proceeding
- Name output files with today's actual date,
  not a placeholder
