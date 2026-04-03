# Landing Page Brief
## Strategic landing page specification for
## any campaign — HubSpot-ready, designer-ready,
## and developer-ready

---

## What This Skill Does
Takes a campaign output — ad copy variants,
keyword cluster, and campaign brief — and
produces a complete landing page specification
that any designer, HubSpot builder, or
developer can execute without needing to ask
strategic questions. Every decision in the
brief includes the reasoning behind it so
whoever builds the page understands the intent
and can make good judgment calls when they
need to deviate from the spec.

Also produces a copy-ready content block with
every word that appears on the page written
out exactly as it should appear — ready to
paste into HubSpot, hand to a designer, or
feed to a developer.

Optionally generates a styled HTML prototype
for quick internal review or stakeholder
presentation.

---

## Step 1 — Read Before Doing Anything

Before asking a single question, read ALL
of these files. Do not skip any of them.

### Required context files

context/icp.md
Pay close attention to:
- Typical Objections by Buyer Segment —
  these are the objections the page must
  handle between the click and the form
  submission. The ad got the click. The
  page gets the conversion. Different job.
- What Makes Them Choose One Vendor Over
  Another — these are the proof points
  and signals that need to appear on the
  page to move a visitor from interested
  to converted
- The Language They Actually Use — every
  section header and copy block should
  mirror buyer vocabulary, not product
  vocabulary

context/brand_voice.md
Pay close attention to:
- Tone scale — landing pages should match
  the formality of the ad that drove the
  click. A government-segment ad at 4/5
  formality needs a 4/5 formality page.
  A commercial enterprise ad at 3/5 needs
  a 3/5 page.
- Words and phrases to avoid — same rules
  as copy. The avoid list applies to every
  word on the page including section headers,
  button text, and form labels
- Example sentences — calibrate every
  copy block against the good examples
  before finalizing

context/competitors.md
Pay close attention to:
- Messaging angles competitors already own —
  if the ad established a differentiated
  angle, the page must continue it, not
  drift into commodity language
- Never mention competitor names anywhere
  on the page

context/market.md
Pay close attention to:
- Trends creating urgency — these can
  inform time-sensitive framing in the
  hero section or the CTA without
  feeling manufactured

context/proof_points.md
If found: use this as the primary source
for all proof points, statistics, and
named customer results on the page.
If not found: pull from icp.md and any
relevant output files.

context/deep/objection_depth.md
If found: use for the objection handling map
section — richer detail than icp.md on exact
objection wording, what's really behind each
objection, and what responses work. If not
found, use icp.md objections as normal.

context/deep/persona_depth.md
If found: use for the visitor context and
message match sections — deeper persona
intelligence sharpens the page goal statement
and the psychological framing of each section.
If not found, proceed without it.

### Optional files — scan outputs/ for:

outputs/copy_*_[company]_*.md
The most recent campaign writer output
matching this campaign and the ad
variants that will drive traffic to this
page — the page must continue the
conversation each variant started.

outputs/keywords_*_[company]_*.md
The most recent keyword file matching
this campaign. The primary keyword
cluster driving traffic informs the
page headline, the hero copy, and the
AEO structure.

---

## Step 2 — Show All Questions At Once

After reading all context files, display
ALL questions together in one message.
Wait for answers before proceeding.

Present exactly like this:

---
Before I build the brief, I need a few
details. Answer all of these in one message:

1. CAMPAIGN — which campaign is this page
   for? Either describe it or name the
   output file it connects to.
   (e.g. "the Intel switching objection
   Google ads we just ran" or
   "copy_google_ad_switching_lilt_2026-03-30")

2. PRIMARY OFFER — what is the visitor
   being asked to do on this page?
   - Book a demo
   - Download a case study or asset
   - Watch a video or webinar recording
   - Start a free trial
   - Contact sales
   - Other — describe it

3. VARIANT HANDLING — the campaign may
   have multiple ad variants pointing to
   this page. How do you want to handle it?
   - One page for all variants — the page
     works for anyone who clicked any
     variant
   - One brief per variant — maximum
     message match, separate page per ad
   - One brief per keyword cluster —
     cluster-level pages rather than
     variant-level

4. FUNNEL STAGE of the arriving visitor:
   - Awareness
   - Consideration
   - Decision

5. SEGMENT and PERSONA arriving on
   this page — who clicked the ad?

6. HUBSPOT CONTEXT — optional but useful:
   - Does a landing page template already
     exist in HubSpot for this campaign
     type, or is this a new template?
   - Are there any HubSpot-specific
     constraints I should know about
     (module limitations, form types,
     thank you page redirect rules)?
   (Say "not sure" or "skip" if unknown)

7. BRAND ASSETS — do you have brand
   colors and fonts to include?
   - Yes — they are in context/brand_assets.md
   - Yes — I will provide them now:
     [paste colors and fonts]
   - No — use placeholder styling
---

---

## Step 3 — State Assumptions

Before writing the brief, display this block:

---
My assumptions before writing:

Campaign this page serves:
[campaign name or description]

Ad variants driving traffic:
[list each variant headline from the
campaign output file — or note if file
was not found]

Primary keyword cluster this page targets:
[top 3-5 keywords from keyword file that
this page should be built around — or
note if keyword file was not found]

Visitor mental state on arrival:
[one paragraph describing what the visitor
was thinking when they searched, what the
ad promised them, and what they need to
feel within the first 3 seconds on the
page to stay rather than bounce]

Primary objection to handle:
[the single most likely reason a visitor
from this campaign would leave without
converting — drawn from icp.md]

Proof point I'll anchor the page to:
[most persuasive proof point
for this segment and offer]

Correct anything here before I write.
Type 'proceed' when ready.
---

---

## Step 4 — Write The Brief

Produce the complete landing page brief
in this exact structure:

---
LANDING PAGE BRIEF
─────────────────────────────────────────
Campaign: [name]
Offer: [primary CTA]
Segment: [segment]
Persona: [persona]
Funnel stage: [stage]
Primary keyword cluster: [top terms]
Brief created: [today's date]
Source campaign file: [filename or "not found"]
─────────────────────────────────────────

### Page goal
One sentence on what this page must
accomplish — not the offer, but the
psychological job. Example: "Move a
Head of Localization from 'switching
sounds painful' to 'this is manageable
and worth doing' before they hit the form."

### Visitor context
Two to three sentences on who is arriving,
what they were promised by the ad, and
what the page builder needs to make good
decisions when they deviate from the spec.

---

### MESSAGE MATCH MAP

For each ad variant driving traffic to
this page, show exactly how the page
continues the conversation that variant
started:

Variant [N]: [variant headline]
Ad promise: [what the ad implied the
page would deliver]
Page continuation: [which page section
delivers on that promise and how]
Risk if mismatched: [what happens if
the page doesn't continue this specific
conversation — why it matters]

---

### ABOVE THE FOLD

Everything the visitor sees without
scrolling. This section determines whether
they stay or leave. Specify every element:

Headline:
[exact copy — outcome first, under
10 words where possible, never start
with "We"]
Why this headline: [one sentence on
why this specific headline continues
the ad's promise for the arriving visitor]

Subheadline:
[exact copy — expands the headline with
one specific proof point or clarification.
Answers "so what does that mean for me"]
Why this subheadline: [one sentence]

Hero copy:
[2-3 sentences maximum — the first thing
they read after the headline. Validates
that they are in the right place. Uses
buyer vocabulary from icp.md.]
Why this copy: [one sentence]

Primary CTA button:
[exact button text — benefit-oriented,
never "Submit" or "Click here"]
Placement: [above the fold, sticky
header, or both]
Why this CTA text: [one sentence]

Trust signals above the fold:
[list 2-3 — named customer logos,
a specific metric, a security credential,
a social proof stat. Never generic badges.]
Why these trust signals: [one sentence
on why these specific signals matter for
this visitor at this funnel stage]

---

### PROOF POINT HIERARCHY

List every proof point that appears on
the page in the order it should appear,
with placement and rationale:

Position 1 — [above fold / hero section]
Proof point: [exact copy]
Why here: [one sentence — what doubt
this eliminates at this moment in the
page flow]

Position 2 — [after hero / first section]
Proof point: [exact copy]
Why here: [one sentence]

[Continue for each proof point]

Rule: The strongest proof point for
this specific objection goes first.
Named customer results always outperform
statistics. Statistics outperform claims.
Claims outperform nothing.

---

### OBJECTION HANDLING MAP

List each objection a visitor from this
campaign is likely to have, where on
the page to handle it, and exactly how:

Objection 1: [exact phrasing from icp.md]
Where to handle it: [page section]
How to handle it: [exact copy or approach]
Format: [FAQ item / callout block /
inline copy / social proof / guarantee]
Why here: [one sentence on why this
position in the page flow is the right
moment to address this objection]

Objection 2: [repeat structure]

[List all relevant objections for this
segment from icp.md — typically 3-5
for decision stage, 1-2 for awareness]

---

### COPY-READY CONTENT BLOCK

Every word that appears on the page
written out exactly as it should appear —
ready to paste into HubSpot or hand to
a designer. No placeholders. No [insert
here]. Real copy throughout.

Structure:

**HERO SECTION**
Headline: [exact]
Subheadline: [exact]
Body: [exact — 2-3 sentences]
CTA button: [exact]

**SOCIAL PROOF BAR**
[3-4 named customer logos or a stat —
specify exactly what appears]

**SECTION 1: [section name]**
Header: [exact]
Body: [exact — 3-5 sentences or
3-4 bullet points if a list is
genuinely clearer than prose]
Why this section exists: [one sentence
— what job it does in the page flow]

**SECTION 2: [section name]**
[repeat structure]

[Continue for every section on the page]

**OBJECTION SECTION**
Format: FAQ or callout block
[List each Q and A exactly as they
should appear on the page]

**FINAL CTA SECTION**
Header: [exact — restate the value
in different words from the hero]
Body: [1-2 sentences — final push]
CTA button: [exact — can differ from
hero CTA if appropriate]
Below-CTA friction reducer: [exact —
e.g. "No commitment required. 30-minute
conversation."]

---

### FORM FIELD RECOMMENDATIONS

Specify exactly what the form collects
and what it does not ask:

Recommended fields:
[list each field with a one-line
rationale for including it]

Fields to avoid:
[list fields that create friction
for this specific persona and why —
e.g. "Company revenue — this persona
doesn't know this number and will
abandon the form rather than guess"]

Form header: [exact copy above the form]
Submit button: [exact — never "Submit"]
Privacy note: [exact — one line below
the submit button, required for
enterprise buyers with data concerns]

Recommended field count: [number]
Why: [one sentence — decision stage
enterprise buyers tolerate more fields
than awareness stage; specify the
reasoning for this campaign]

---

### THANK YOU PAGE BRIEF

What happens immediately after the
form is submitted:

Page goal: [one sentence — what should
the visitor feel and do next]

Headline: [exact — confirms the action,
sets expectation for what happens next.
Never "Thank you for your submission."]

Body: [2-3 sentences — what happens
next, when they will hear back, and
what to do in the meantime]

Next step CTA: [what to offer them
while they wait — a relevant piece of
content, a video, a related case study.
Keep them engaged rather than sending
them away.]

Why this matters: [one sentence on
why the thank you page is part of the
conversion, not the end of it]

---

### AEO STRUCTURE NOTES

How to structure this page for AI
search discovery — low effort,
forward-looking competitive advantage:

Primary question this page answers:
[the exact question a buyer would ask
an AI assistant that this page should
be the answer to]

Recommended page structure for AEO:
- Opening summary paragraph: [one sentence
  on what this paragraph should say —
  a direct answer to the primary question
  in 2-3 sentences, appearing early on
  the page before any scrolling is required]
- Entity definitions: [list any technical
  terms on the page — TMS, LSP, MTPE —
  that should be briefly defined inline
  so AI systems can parse them correctly]
- Declarative claim structure: [note which
  sections should use complete declarative
  sentences rather than fragments or
  bullets — AI systems cite complete
  sentences more reliably than fragmented
  copy]
- Structured FAQ: [confirm the objection
  FAQ section doubles as AEO content —
  question and answer format is the most
  reliably cited structure by AI search]

What this buys you: [one sentence on
the specific advantage this page structure
creates as AI search grows — keep it
concrete, not generic]

---

### SKILLS THAT WOULD IMPROVE THIS BRIEF

Optional files that were missing:
[List any optional files checked but
not found, with one sentence on what
each would have contributed]

Data that would sharpen this brief:
[List 2-3 specific data points —
conversion rate benchmarks for this
offer type, heatmap data from existing
pages, form abandonment rates — that
would make the recommendations more
precise. Note these require live data
and cannot be generated from context
files alone.]

Skills worth building next:
[List 2-3 skills not yet in the toolkit
that would meaningfully improve landing
page quality or the brief-to-page
workflow. Base these on what was actually
missing from this run.]

---

## Step 5 — HTML Prototype Option

After displaying the complete brief, ask:

"Would you like me to generate an HTML
prototype of this page?

The prototype will:
- Apply brand colors and fonts from
  context/brand_assets.md if found,
  or use placeholder styling if not
- Include all copy from the content
  block exactly as specified
- Be responsive and openable directly
  in any browser for immediate review
- Be saveable as a file to share
  with stakeholders or hand to a
  developer as a starting point

Note: HTML generation uses significantly
more credits than the brief alone.
Recommended when you need a visual
for internal review or stakeholder
sign-off rather than going straight
to HubSpot.

Type 'generate html' to proceed or
'skip' to go straight to saving
the brief."

If 'generate html':
Generate a complete, styled, responsive
HTML file using all copy from the
content block. Apply brand assets from
context/brand_assets.md if found.
If brand assets are not found, use
clean professional placeholder styling
with a neutral color palette and
system fonts. Include a visible note
at the top of the rendered page:
"PROTOTYPE — copy and layout subject
to brand review before production."

Save HTML as:
landing_page_[theme]_[company]_[date].html

Save brief as:
landing_page_brief_[theme]_[company]_[date].md

If 'skip':
Save brief only as:
landing_page_brief_[theme]_[company]_[date].md

---

## Step 6 — Confirm Before Saving

After the HTML decision, ask:

"Would you like to adjust anything
before saving?

You can ask me to:
- Rewrite any copy block
- Add or remove a page section
- Adjust the objection handling
  for a specific objection
- Change the form field recommendations
- Add a different proof point
- Adjust the AEO structure notes

Or type 'save' and I will write
the output file."

Only save after explicit confirmation.
Never save without confirmation.

---

## Rules This Skill Must Always Follow

Every copy block must be ready to use
as-is — no placeholders, no [insert here],
real copy throughout.

Every specification must include the
reasoning behind it — the "why this"
note is not optional. It is what prevents
whoever builds the page from making
innocent decisions that kill conversion.

The message match map must reference
the actual ad variant headlines from
the campaign output file — never generic
placeholder variants.

The objection handling map must draw
from the icp.md Typical Objections by
Buyer Segment section — not generic
objections.

Proof points must come from
context/proof_points.md if it exists —
never invent metrics or attribute
claims to customers without evidence
in the context files.

The thank you page brief is not optional —
it is part of the conversion, not the
end of it.

AEO notes must always be included —
they cost nothing to add and create
compounding advantage over time.

Always use the file naming convention
from CLAUDE.md for all output files.

Always read the active company name
from context/icp.md before naming files.

Never mention competitor names anywhere
in the page copy or brief specifications.

If any required context file is missing,
stop and say so before proceeding.
