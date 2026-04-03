---

# Email and Nurture Sequencer
## Designs and writes demand gen email
## sequences across four types:
## Nurture, Campaign, Re-engagement, ABM
## HubSpot-ready output for every sequence

---

## What This Skill Does
Takes a campaign brief, persona, trigger
event, or campaign moment and produces
a complete email sequence — designed
strategically and written in full,
ready to paste into HubSpot.

Handles four distinct email types:

NURTURE — triggered by a specific action
(content download, ad click, form fill,
webinar attendance). Moves a lead from
interested to demo-ready over 2-6 weeks.

CAMPAIGN — standalone send for a specific
moment (webinar invite, case study launch,
product announcement). 2-4 emails
depending on the moment type.

RE-ENGAGEMENT — goes back to cold or
dormant leads who showed interest but
went quiet. Resurfaces interest and
cleans the list.

ABM — targeted sequence for a specific
named account where a trigger event has
fired. Templated with company name and
trigger event filled in. Placeholders
for additional context the campaign
manager or SDR adds before sending.

This skill uses the Campaign Writer
as its writing engine for individual
emails. It designs the sequence logic
first, then writes each email following
the craft rules established in the
Campaign Writer skill.

---

## Step 1 — Read Before Doing Anything

Before asking a single question, read
ALL of these files:

### Required context files

context/icp.md
Pay close attention to:
- Buyer personas — email tone, vocabulary,
  and proof point selection all change
  based on who is receiving the sequence
- What triggers them to start looking —
  nurture sequences triggered by specific
  events need to reference those events
  in the opening email
- The language they actually use —
  subject lines and preview text must
  mirror buyer vocabulary exactly
- Typical objections by segment — the
  sequence must pre-empt objections in
  the right order as the buyer progresses
  through emails

context/brand_voice.md
Pay close attention to:
- Tone by segment — enterprise buyers
  get a different register than growth
  stage SaaS buyers
- Words and phrases to avoid — apply
  to every subject line, preview text,
  and body copy block
- Example sentences — calibrate every
  email against these before writing

context/proof_points.md
If found: use as the primary source
for all statistics and named customer
results used in emails. Never invent
metrics or attribute claims without
evidence in this file.
If not found: pull from icp.md and
customer references in context files.

### Optional deep-dive files — read if found

context/deep/persona_depth.md
Read for: day-in-the-life detail,
information diet (what they read and
where they spend time online), career
anxieties, and what a bad week looks
like. This is what makes email copy
feel written by a practitioner rather
than generated.

context/deep/objection_depth.md
Read for: the exact conversation each
objection surfaces in, the real fear
behind the stated objection, and the
winning response. Use to sequence
objection handling across emails —
earlier emails pre-empt surface
objections; later emails handle
the deeper fears.

context/deep/voice_of_customer.md
Read for: exact buyer quotes and
phrases to use in subject lines and
opening lines. Buyer vocabulary in
the subject line is the single highest
impact lever on open rate.

context/deep/trigger_events.md
Read for: what buyers do immediately
after a trigger fires, what content
they need at that moment, and what
outreach angle resonates without
feeling intrusive.

context/deep/buying_committee.md
Read for: who else is involved in the
decision, what each person needs to
see, and where deals stall. Use for
ABM sequences where multiple contacts
at the same account need different
emails.

context/deep/market_gaps.md
Read for: positioning angles that
no competitor is currently owning.
Use for campaign emails announcing
content that fills a gap.

### Required campaign files

Scan outputs/ for relevant files
matching the active company:

outputs/copy_*_[company]_*.md
If a campaign writer output exists
for this campaign angle, read the
variants for copy style, proof points
used, and awareness level. The email
sequence should feel like a continuation
of the campaign the buyer clicked on —
not a different voice.

outputs/landing_page_brief_*_[company]_*.md
If a landing page brief exists for
this campaign, read it. The first
nurture email should directly reference
the page the buyer just left and
continue the conversation it started.

---

## Step 2 — Show All Questions At Once

After reading all files, display ALL
questions in one message. Do not ask
questions one at a time. Wait for
all answers before proceeding.

---
Before I design the sequence, I need
a few details. Answer all in one message:

1. EMAIL TYPE — which type of sequence
   is this?
   - Nurture — triggered by a specific
     action (tell me what the trigger
     action was)
   - Campaign — specific moment
     (tell me what the moment is:
     webinar, case study launch,
     product announcement, other)
   - Re-engagement — dormant leads
     (tell me how long they have been
     inactive and what they originally
     engaged with)
   - ABM — named account sequence
     (tell me the company name and
     what trigger event fired)

2. PERSONA — who is receiving this
   sequence?
   - Head of Localization / Director
   - VP of Marketing / CMO
   - CTO / VP Engineering
   - Mixed — multiple personas at
     the same account (ABM only)
   - Other — describe it

3. FUNNEL STAGE of the enrollee
   at the point of enrollment:
   - Awareness — knows they have
     a problem, doesn't know solutions
   - Consideration — evaluating options,
     knows platforms exist
   - Decision — ready to buy, comparing
     final vendors

4. SEGMENT:
   - Commercial Enterprise
   - High-Growth Tech (Series B-D)
   - US Federal / Defense
   - Mixed

5. CAMPAIGN ANGLE — what is the
   primary message or proof point
   this sequence should build on?
   (e.g. "vendor management tax,"
   "switching objection," "Intel
   case study," "Lilt Assist launch,"
   "AI transformation mandate")

6. PRIMARY CTA — what do you want
   the recipient to do?
   - Book a demo
   - Download a case study or asset
   - Register for a webinar
   - Watch a recording
   - Contact sales
   - Read a blog post or content piece
   - Other — describe it

7. HUBSPOT CONTEXT — optional but
   useful for workflow notes:
   - What list or segment will be
     enrolled in this sequence?
   - Are there any suppression lists
     I should note? (e.g. current
     customers, active opportunities)
   - Is there a specific HubSpot
     workflow this connects to?
   (Say "skip" if unknown)

8. EXISTING CAMPAIGNS — are there
   any sequences already running
   for this segment and persona
   that I should avoid duplicating
   angles with?
   (Say "none" or "not sure")
---

---

## Step 3 — Determine Sequence Structure

After receiving answers, determine
the right sequence structure before
writing anything. Apply these rules:

### Nurture sequence length rules

Awareness stage enrollee:
4-6 emails over 3-4 weeks
Reasoning: buyer needs education
before they are ready for a product
conversation. Moving too fast to
a demo ask creates friction.

Email 1: Validate the problem
Email 2: Expand the problem with data
Email 3: Introduce the category
  of solution (not the product yet)
Email 4: Introduce the product with
  peer proof
Email 5: Handle the primary objection
Email 6: Closing move (see rules below)

Consideration stage enrollee:
4-5 emails over 2-3 weeks
Reasoning: buyer already knows
solutions exist. Skip education,
move faster to differentiation
and proof.

Email 1: Lead with strongest proof
  point for this persona
Email 2: Address the primary objection
  for this segment
Email 3: Peer story — named customer
  at comparable company
Email 4: Differentiation against
  most likely competitor
Email 5: Closing move

Decision stage enrollee:
3-4 emails over 1-2 weeks
Reasoning: buyer is ready. Long
sequences lose them. Short, direct,
specific.

Email 1: Acknowledge where they are
  and remove the last objection
Email 2: Proof point that closes
  the specific fear
Email 3: Make the ask directly
Email 4 (optional): Closing move
  if no response to Email 3

### Campaign email count rules

Webinar or event invitation:
Email 1: Announcement (2-3 weeks out)
Email 2: Value reminder (1 week out)
Email 3: Last chance (24-48 hours out)
Email 4: Recording follow-up
  (day after, for non-attendees)
Total: 3-4 emails

Case study or content launch:
Email 1: Launch announcement
Email 2: Different angle or excerpt
  (5-7 days later, to openers only
  if HubSpot segmentation allows)
Total: 2 emails

Product announcement:
Email 1: Announcement to full segment
Email 2: Deeper dive for engaged
  openers (7 days later)
Total: 2 emails

Seasonal or time-limited offer:
Email 1: Offer announcement
Email 2: Midpoint reminder
Email 3: Final day urgency
Total: 3 emails

### Re-engagement sequence rules

3 emails maximum. If no response
after 3, remove from active nurture.

Email 1: Low-pressure check-in
  referencing what they originally
  engaged with
Email 2: New proof point or content
  that wasn't available when they
  first engaged
Email 3: Permission to close
  (see closing move rules below)

### ABM sequence rules

3-5 emails targeting 1-2 contacts
at the named account.

Email 1: Reference the trigger event
  directly but not intrusively.
  "I saw [company] recently [event
  signal]. Here's what [comparable
  company] did in the same situation."
  Never reference the trigger in a way
  that feels like surveillance.
Email 2: Relevant proof point for
  this account's specific situation
Email 3: Different persona if buying
  committee map suggests multiple
  contacts
Email 4: Soft ask — not a demo,
  a lower-commitment offer
  (a relevant case study, a 15-minute
  call, a specific piece of content)
Email 5: Closing move if no response

---

## Step 4 — Determine The Closing Move

The final email in every sequence
must be chosen deliberately.
Apply these rules:

### When to use the Permission to Close email

Use when:
- The sequence has been 4+ emails
- The buyer has not engaged with
  any prior email
- The sequence is re-engagement
- The ABM sequence has had no reply

What it does: removes pressure at
the moment the buyer is most fatigued.
Paradoxically gets more replies than
another push because it respects
the buyer's time and signals
confidence.

Template structure:
Subject: Should I stop reaching out?
Body: Acknowledge you've sent several
emails. Tell them you don't want to
keep filling their inbox if the
timing isn't right. Give them an
easy out. Leave one door open with
one specific proof point or offer.
No pressure. Their choice.

### When to use the Hard CTA with urgency

Use when:
- Genuine urgency exists (webinar
  closing, cohort starting, pricing
  change, deadline)
- Manufactured urgency is NOT
  acceptable — enterprise buyers
  see through it immediately and
  it damages trust
- Decision stage enrollees only

### When to use the One Specific Thing email

Use when:
- The sequence has been content-heavy
  with multiple proof points
- The buyer needs simplicity not
  more information
- Earlier emails covered the full
  case; this email strips it back

What it does: one sentence setup,
one proof point, one link. No
context, no explanation. The most
compelling single thing you know
about their situation.

### When to use the Sales Handoff email

Use when:
- ABM sequence targeting a named
  account where the goal is to open
  a sales conversation
- The buyer has engaged with content
  but not converted
- An SDR or AE is assigned to
  this account

What it does: explicitly introduces
the sales contact by name and frames
the handoff as helpful, not pushy.
"I'm going to let [Name] take it
from here — they work specifically
with [industry/segment] companies
at your stage and will have more
relevant content than I can cover
in an email."

### When to use the Different Angle email

Use when:
- Prior emails have focused on one
  pain point and it hasn't resonated
- The buyer profile suggests multiple
  potential pain points
- Decision stage where one objection
  has been pre-empted but another
  may be blocking

What it does: pivots to a completely
different angle without acknowledging
the pivot. The buyer doesn't know
you tried three other angles. This
one might land where the others didn't.

---

## Step 5 — Produce The Sequence Map

Before writing any emails, display
the sequence map. Wait for approval
before proceeding to write individual
emails.

Format exactly as follows:

---
SEQUENCE MAP
─────────────────────────────────────────
Type: [email type]
Persona: [persona]
Segment: [segment]
Funnel stage at enrollment: [stage]
Campaign angle: [angle]
Primary CTA: [CTA]
Total emails: [number]
Total duration: [weeks]
Active company: [read from icp.md]
─────────────────────────────────────────

[For each email in the sequence:]

EMAIL [N]: [Email Name]
Send timing: [Day X — recommended
  day of week and time]
Job: [one sentence — what this email
  must accomplish. Not what it says —
  what it must make the reader feel
  or do.]
Angle: [the specific angle this email
  takes — what pain point, proof point,
  or objection it addresses]
Proof point: [which named customer
  result or statistic anchors this email]
Subject line direction: [not the final
  subject line — the strategic direction.
  e.g. "buyer vocabulary mirror using
  'vendor management tax' phrase" or
  "curiosity gap on the cost of inaction"]
Opening line direction: [how the email
  opens — what the first sentence does
  psychologically. e.g. "validates the
  trigger that enrolled them" or
  "opens with the Intel quote before
  naming the product"]
CTA for this email: [specific ask —
  may be softer than the primary CTA
  for earlier emails in long sequences]
Awareness level: [Schwartz level 1-5]
Why this email at this position:
  [one sentence on why this specific
  email comes here in the sequence —
  what the prior email set up and
  what this one needs to do before
  the next one can land]

[Repeat for each email]

─────────────────────────────────────────

SEQUENCE LOGIC NOTES

Objection handling sequence:
[Which objections are handled in which
emails and why in that order. Earlier
emails handle surface objections.
Later emails handle the deeper fears
once trust is established.]

Proof point progression:
[How proof points build across the
sequence. Generally: name the category
of outcome early, introduce the named
customer mid-sequence, use the specific
metric to close.]

Closing move chosen: [which closing
move and why based on the rules above]

HubSpot enrollment trigger:
[Specific trigger — what action
enrolls someone in this sequence.
e.g. "Downloaded the Intel case study
from the switching objection landing
page" or "Attended the vendor
management webinar"]

HubSpot exit conditions:
[What removes someone from the sequence
before it ends. Common examples:
contact replies, books a demo, becomes
an active opportunity in Salesforce]

Suppression recommendation:
[Who should be excluded from this
sequence and why]

─────────────────────────────────────────
Does this sequence structure look right?
Type 'proceed' to write all emails.
Or tell me what to adjust before I start.
─────────────────────────────────────────
---

---

## Step 6 — Write Individual Emails

After 'proceed', write every email
in the sequence in full. No placeholders
in body copy. Every word ready to
paste into HubSpot.

For each email use exactly this
structure:

---
EMAIL [N] OF [TOTAL]: [Email Name]
─────────────────────────────────────────
Send timing: Day [X] — [day of week],
[time recommendation and reasoning]

SUBJECT LINES (3 variants for A/B testing)
A: [subject line — direct, specific]
B: [subject line — curiosity or question]
C: [subject line — buyer vocabulary mirror]

PREVIEW TEXT
[45-100 characters — the snippet
visible in inbox before opening.
Should complement the subject line,
not repeat it. Creates a second
hook before the open.]

─────────────────────────────────────────
BODY COPY

[Full email written out. Apply these
rules for every email:]

Opening line rule: Never start with
"I hope this finds you well" or any
variant. Never start with the company
name or a feature claim. Open with
something the reader recognises from
their own experience — a situation,
a frustration, a question, or a
specific piece of data that validates
their reality before asking anything
of them.

Length rule by funnel stage:
- Awareness: 150-250 words. More
  education needed; earn the next
  open before asking for anything.
- Consideration: 100-175 words.
  Buyer knows the category; get to
  the point faster.
- Decision: 75-125 words. Buyer
  is ready; long emails create friction
  at the wrong moment.

Paragraphs kept short and separated
for emphasis. Wall-of-text emails
do not get read.

Proof point rule: One named proof
point per email maximum. Multiple
proof points in one email dilute
each other. Save additional proof
points for subsequent emails.

Brand voice rule: Apply brand_voice.md
avoid list to every word. No vague
superlatives, no hype language, no
generic AI claims. Every claim must
be earnable from the context files.

Competitor rule: Never name a
competitor in email copy — not even
in displacement sequences. Let the
buyer fill in the blank.

Signature: Sign off as the brand,
not a specific individual — this is
a marketing automation email, not
a personal send. Use "The [Company]
team" or "[Company]" as the sender.
Exception: ABM sequences and sales
handoff emails where a named sender
is appropriate — flag this in the
HubSpot notes.

[Full email body copy here]

─────────────────────────────────────────
CTA SECTION

Primary CTA button text: [exact
  wording for HubSpot button]
Secondary CTA (optional): [softer
  ask for emails where the primary
  CTA is a big commitment]

─────────────────────────────────────────
PERSONA REASONING

Why this email is structured this way
for [persona] at [funnel stage]:
[2-3 sentences on the specific persona
insight that shaped this email's
structure, angle, and proof point
selection. Reference the specific
file this reasoning came from —
persona_depth.md, objection_depth.md,
voice_of_customer.md — so whoever
is optimising this sequence later
knows where to look if performance
doesn't match expectations.]

─────────────────────────────────────────
HUBSPOT NOTES FOR THIS EMAIL

Delay from previous email: [X days]
Recommended send day: [day] at [time]
Personalization tokens to add:
  [List HubSpot tokens that should
  be added — {{contact.firstname}},
  {{company.name}}, etc.]
Conditional content note:
  [If this email should show different
  content to different segments in
  HubSpot, describe the exact condition]
Branching note:
  [If the sequence should branch based
  on behaviour after this email — e.g.
  "if clicked, move to decision-stage
  sequence; if not clicked, continue
  to Email N+1" — flag it here]
─────────────────────────────────────────

[Repeat for every email in the sequence]

---

## Step 7 — Full Sequence Summary

After all emails are written, produce
a summary block:

---
SEQUENCE SUMMARY
─────────────────────────────────────────
[Company] — [Sequence Name]
Type: [email type]
Total emails: [number]
Total duration: [weeks]
─────────────────────────────────────────

HUBSPOT WORKFLOW SETUP

Enrollment trigger:
[Exact trigger — specific enough
that someone could set it up in
HubSpot without asking a question]

Enrollment criteria:
[Any contact property or lifecycle
stage filters to apply before enrolling]

Exit conditions:
☐ Contact replies to any email
☐ Contact books a demo
☐ Contact is added to an active
   opportunity in Salesforce/CRM
☐ Contact unsubscribes
☐ [Any sequence-specific exit
   condition]

Suppression lists:
☐ Current customers
☐ Active opportunities (already
   in sales process)
☐ [Any other suppression relevant
   to this sequence]

Sender recommendation:
[Marketing alias (e.g. team@lilt.com)
for nurture and campaign sequences.
Named sender for ABM and sales
handoff sequences — explain why.]

─────────────────────────────────────────

SEQUENCE PERFORMANCE NOTES

Primary metric to watch: [open rate,
click rate, reply rate, or conversion
rate — specify which matters most
for this sequence type and why]

Secondary metric: [what to watch
if primary metric looks good but
conversion is still low]

When to optimise: [specific threshold
— e.g. "if Email 1 open rate is
below 25% after 50 sends, test
Subject Line B before making
structural changes"]

What good looks like: [honest
benchmarks for this specific email
type and funnel stage. Be honest
about what is achievable vs.
aspirational.]

─────────────────────────────────────────

SKILLS THAT WOULD IMPROVE THIS SEQUENCE

Optional files that were missing:
[Any optional deep-dive files not
found, with one sentence on what
each would have contributed]

Assets that would improve performance:
[Content assets that don't exist yet
but would meaningfully improve this
sequence — a case study, an ROI
calculator, a webinar recording.
Note these as gaps, not blockers.]

Skills worth building next:
[2-3 skills not yet in the toolkit
that would connect to or improve
this sequence — e.g. Trigger Monitor
feeding ABM enrollment, Landing Page
Brief for the sequence destination,
LinkedIn Campaign Organiser running
in parallel]

─────────────────────────────────────────

---

## Step 8 — Save Confirmation

After displaying all emails, ask:

"Would you like to adjust anything
before saving?

You can ask me to:
- Rewrite any email in full
- Change a subject line variant
- Add or remove an email from
  the sequence
- Change the CTA in any email
- Change the closing move
- Tighten or expand the length
  of any email
- Add a branching email for
  a specific behaviour

Or type 'save' to write the output file."

Save as:
email_[type]_[angle]_[persona]_[company]_[date].md

Save to outputs/.

Only save after explicit confirmation.
Never save without confirmation.

---

## Email Craft Rules
## Apply to every email written

### Subject line rules

Under 50 characters performs better
on mobile — flag any subject line
over 50 characters.

Never use all caps. Never use
excessive punctuation. Never use
"Re:" or "Fwd:" prefixes to fake
familiarity — enterprise buyers
recognise this and it damages trust.

The three subject line variants
must test genuinely different
hypotheses — not just word swaps.
Variant A tests a direct approach.
Variant B tests curiosity or a
question. Variant C tests buyer
vocabulary mirroring.

Numbers in subject lines outperform
vague claims: "40% cost reduction"
outperforms "significant savings."

Personalisation in subject lines
({{company.name}}, first name)
improves open rate for ABM and
decision-stage sequences. Use
sparingly for awareness-stage
mass sends.

### Opening line rules

The opening line is read in the
preview pane before the email is
opened. It must earn the open.

Never waste the opening line on
pleasantries. The reader decides
in 2 seconds whether to open.

The best opening lines do one of:
- State a specific fact the reader
  did not know that is immediately
  relevant to their situation
- Ask a question they have not
  asked themselves but immediately
  recognise as relevant
- Reference something they did
  ("You downloaded X") or something
  happening in their world ("You're
  expanding into [market]") without
  being intrusive
- Open with a buyer quote from
  voice_of_customer.md that makes
  them think "that's exactly what
  I say"

### Closing move selection reminder

Apply the closing move rules from
Step 4 consistently. Never end a
sequence with another generic CTA
push if prior emails have already
made the same ask without response.
Respect the buyer's inbox.

### What to never write in email

- "I hope this email finds you well"
  or any variant
- "I wanted to reach out" or any
  variant
- "Just checking in"
- "Per my last email"
- "Circle back" or "touch base"
- "Synergy," "leverage," "utilize"
- Any vague claim without a named
  proof point to support it
- Competitor names — ever
- Manufactured urgency ("offer
  expires Friday") for enterprise
  audiences

---

## Rules This Skill Must Always Follow

Always read all context files before
asking a single question.

Always produce the sequence map
and wait for 'proceed' before writing
individual emails — never skip
directly to writing.

Always write every email in full —
no placeholders in body copy.

Always produce 3 subject line variants
per email — never just one.

Always include preview text —
it is the second subject line and
is often skipped by other tools.

Always include HubSpot notes for
every email — the sequence is only
useful if someone can set it up
in HubSpot without asking questions.

Always include persona reasoning —
it is what allows whoever optimises
this sequence later to understand
why it was written this way.

Always apply the closing move rules —
never end a sequence with a generic
CTA push if prior emails have made
the same ask without response.

Never use placeholders in body copy —
every word must be ready to use.
Exception: ABM sequences where
[COMPANY NAME] and [TRIGGER EVENT]
are filled in from the brief but
[ADD CONTEXT HERE] brackets are
left for the campaign manager.

Never save without explicit
confirmation.

Never name competitors in any email.

Always read the active company name
from the first line of context/icp.md
before naming output files.

Follow the file naming convention
in CLAUDE.md for all output files.

If any required context file is
missing, stop and say so before
proceeding.
