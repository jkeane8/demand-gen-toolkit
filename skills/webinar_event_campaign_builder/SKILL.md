# Webinar and Event Campaign Builder
## Pre-event promotion. During-event assets. Three post-event tracks.
## One brief. Complete event campaign package.

---

## What This Skill Does

Takes an event brief and produces every asset needed to promote,
run, and follow up on a webinar or in-person event. The output
covers three phases: pre-event promotion assets that drive
registrations, during-event assets that support delivery and
capture engagement signals, and three post-event email tracks
that route contacts based on their behaviour.

All content is derived from context files at runtime. No company
names, product names, competitor names, or industry terms are
hardcoded in this skill. Every reference to the company, its
customers, its buyers, and its market comes from the files
found in context/.

---

## Step 1 — Read Before Building

Read all of the following files before producing any output.
These files are the intelligence layer this skill draws from.

Required files:
- context/icp.md — buyer personas, pain points, segment
  definitions, ICP vocabulary, trigger events, and objection
  summaries
- context/brand_voice.md — tone scale by segment, vocabulary
  to use and avoid, and calibration sentences showing on-brand
  and off-brand copy
- context/proof_points.md — named customer results, specific
  metrics, and case study outcomes available for use in copy
- context/market.md — market category, current trends,
  competitive landscape overview

Optional files (read if present):
- context/deep/voice_of_customer.md — exact buyer quotes and
  copy-ready phrases that can be used verbatim in subject lines,
  registration page headlines, and follow-up email hooks
- context/deep/persona_depth.md — day-in-the-life detail, career
  anxieties, and information diet for each priority persona —
  use these to make copy feel personally relevant
- context/deep/objection_depth.md — surface objections, real
  underlying fears, and what backfires — use these to pre-empt
  resistance in registration page copy and nurture follow-up
- context/deep/buying_committee.md — all roles involved in a
  purchase decision and their priorities — use this to inform
  which personas to target in paid promotion and which post-event
  track to route each role into

Before producing output, display a pre-flight block:

---
WEBINAR / EVENT CAMPAIGN BUILDER — PRE-FLIGHT
─────────────────────────────────────────────────────────────────
Event type detected: [Webinar / In-person / Hybrid]
Event name: [from brief]
Target persona: [from brief or inferred from icp.md]
Target segment: [from brief or inferred from icp.md]
Campaign objective: [registrations / attendance / pipeline /
  post-event nurture]
Funnel stage: [awareness / consideration / decision]

Context files loaded:
[✓ or ✗] context/icp.md
[✓ or ✗] context/brand_voice.md
[✓ or ✗] context/proof_points.md
[✓ or ✗] context/market.md
[✓ or –] context/deep/voice_of_customer.md
[✓ or –] context/deep/persona_depth.md
[✓ or –] context/deep/objection_depth.md
[✓ or –] context/deep/buying_committee.md
(– = not found, will proceed without)

Active company: [read from first line of context/icp.md]

Assets this run will produce:
PRE-EVENT
  [ ] Registration page brief
  [ ] Pre-event email sequence (3 emails)
  [ ] LinkedIn organic posts (3 posts)
  [ ] LinkedIn paid promotion brief
  [ ] Paid social promotion brief (if applicable)
DURING-EVENT
  [ ] Webinar chat prompts and poll questions (webinar only)
  [ ] Engagement capture brief (in-person only)
POST-EVENT
  [ ] Track 1: Attendee follow-up (3 emails, 10 days)
  [ ] Track 2: No-show re-engagement (3 emails, 14 days)
  [ ] Track 3: Highly engaged — sales acceleration (2 emails,
      4 days)
  [ ] HubSpot workflow architecture for all three tracks

Type 'run' to start. Or correct anything above before proceeding.
─────────────────────────────────────────────────────────────────
---

---

## Step 2 — Gather Inputs

Extract the following from the brief. Make reasonable
inferences from context files if not stated. Do not ask
the human multiple questions — ask one clarifying question
only if a critical input is genuinely ambiguous.

From the brief, identify:

**Event name** — the title or working title of the webinar
or event. If not given, propose a title based on the topic
and persona derived from context files. Mark it as proposed.

**Event type** — webinar (default) or in-person. Determine
from the brief. Default to webinar if not stated.

**Event topic** — the core problem, trend, or question the
event addresses. Used to derive registration page copy,
speaker framing, and post-event content angles.

**Target persona** — read from context/icp.md. Match to
the personas defined there. If the brief names a role,
map it to the closest persona in icp.md.

**Target segment** — read from context/icp.md. Match to
the segment definitions there.

**Funnel stage** — the stage the target audience is at.
Default to consideration if not stated. Affects the level
of product reference permitted in pre-event copy.

**Event date** — if provided, use it to date-stamp
pre-event email timing. If not provided, note that timing
is relative (e.g., 14 days before event, 7 days before
event) and the human should substitute actual dates at
implementation.

**Registration goal** — a number if provided. Use for
the LinkedIn paid promotion brief. If not provided,
note "not specified — LinkedIn paid budget should be
set based on target registration volume."

**Speaker or host** — name and title if provided. Use
in promotional copy. If not provided, write "[Speaker
Name, Title]" as a placeholder throughout.

---

## Step 3 — PRE-EVENT ASSETS

Produce all pre-event assets in sequence. Each asset
is fully written and ready for use — not a brief
or a template. Do not produce briefs within briefs.
The output of this step is usable copy.

---

### 3A — Registration Page Brief

The registration page brief is a full page specification.
It is a brief for whoever builds the page, not the page
copy itself. The copy sections within it are fully written.

Structure:

**Page objective:** One sentence stating what this page
must do and who it is for.

**Above-the-fold specification:**
- Headline: Write 3 options. Each uses a different
  formula: (1) outcome-led, (2) problem-led, (3) question-
  led. All derived from ICP vocabulary — the exact words
  the persona uses to describe this problem, not marketing
  language about it.
- Subheadline: Expands the headline with the specific
  payoff the persona gets from attending. One sentence.
  No hype words.
- Webinar date and time field: [placeholder — fill at
  scheduling]
- Primary CTA button copy: Write 2 options. Default is
  action-led ("Reserve my spot"). Alternative is outcome-
  led ("Get the [topic] playbook").

**What you will learn section:**
Write 3–4 bullet points. Each bullet names a specific
takeaway — a decision, a framework, a comparison, or a
number the attendee will leave with. Not "learn how to...".
Derived from the event topic and what the target persona
needs to move to the next stage of their buying journey.

**Speaker section:**
Write the speaker bio framing. If speaker is named:
position them as a practitioner or peer, not a vendor.
If speaker is a placeholder: write [Speaker Name] is
[Title] at [Company name from icp.md]. [One sentence on
their direct experience with this problem.]

**Social proof element:**
Select the most relevant proof point from proof_points.md
for this persona and topic. Write it as a one-line pull
quote or stat. Label it with the named customer. If no
directly relevant proof point exists, note "no directly
relevant proof point found — consider a relevant
third-party statistic or omit this element."

**Registration form fields:**
Recommend exactly which fields to include. Standard
recommendation: First name, Work email, Company name,
Job title. Flag any additional fields and explain the
tradeoff (every additional field reduces conversion).

**Thank you page brief:**
- Confirmation message copy (2–3 sentences)
- One next action: what to offer the registrant
  immediately after sign-up (relevant content piece,
  pre-event resource, or add-to-calendar link)
- Note whether to fire a HubSpot workflow enrollment
  trigger from this page confirmation event

---

### 3B — Pre-Event Email Sequence

Three emails sent between registration and the event.
All three are fully written — subject line variants,
preview text, full body copy, CTA.

**Email 1 — Confirmation and Value Set**
Send timing: Immediately after registration (automated)
Objective: Confirm the registration, set expectations,
and give the registrant a reason to look forward to
the event. This is not a generic "you're registered"
email — it should make the persona feel the event
was built for them.

Write:
- Subject line: [2 options — one that names the topic,
  one that uses an ICP vocabulary phrase as the hook]
- Preview text: [1 option, under 90 characters]
- Body copy: 3–4 short paragraphs. Open with the
  specific problem this event addresses, framed in
  the persona's words. Confirm the event details.
  Preview the most valuable takeaway. Close with
  the add-to-calendar CTA.
- CTA: Add to calendar [link placeholder]
- HubSpot note: Enrollment trigger = form submission
  on registration page. Set delay = 0 minutes.

**Email 2 — Build Anticipation**
Send timing: 3–5 days before the event
Objective: Remind the registrant why they signed up
and increase the likelihood they show up. Give them
something valuable before the event — a framing
question, a short relevant resource, or a pre-read.

Write:
- Subject line: [2 options — one curiosity-led,
  one resource-led]
- Preview text: [1 option, under 90 characters]
- Body copy: 2–3 paragraphs. Open with a question
  the event will answer — framed from the persona's
  perspective, in ICP vocabulary. Provide the
  pre-event resource or framing context. Reinforce
  the event date and time.
- CTA: Add event to calendar [link placeholder]
  OR link to pre-event resource if one is specified
- HubSpot note: Set delay = [event date minus 4 days].
  Check for reply or calendar add before sending —
  suppress if already engaged.

**Email 3 — Day-Before Reminder**
Send timing: Morning of the day before the event
Objective: Make attendance feel easy. Remove friction.
Give one clear action: join the event.

Write:
- Subject line: [2 options — one urgency-led,
  one value-led]
- Preview text: [1 option, under 90 characters]
- Body copy: 2 short paragraphs only. Event is tomorrow.
  Here is what to expect. Here is the link. Keep it
  brief — this is a functional email, not a persuasion
  email.
- CTA: Join the event [link placeholder]
- HubSpot note: Set delay = [event date minus 1 day],
  send at 9am in contact's timezone if available.
  Add a second send at 1 hour before event start
  for contacts who have not clicked. Suppress both
  sends if contact has already clicked join link.

---

### 3C — LinkedIn Organic Posts (Pre-Event)

Three posts published before the event to drive
registrations from organic LinkedIn reach.

Each post is fully written. Each uses a different
content format and is appropriate for the persona's
information diet as described in persona_depth.md
(or inferred from icp.md if persona_depth.md is
not available).

**Post 1 — Problem Framing Post**
Publish timing: 10–14 days before event

Format: Hook + context + announcement
Length: 150–200 words

Write the full post. Open with a one-line hook that
names the problem the target persona faces — in the
vocabulary they use, not product language. Follow
with 2–3 sentences of context establishing why this
problem matters now. Close with the event announcement
and registration link placeholder.

Do not open with "I am excited to..." or "We are
thrilled to..." — these are brand voice violations
in all segments. Open with the problem or the
consequence.

Annotation: [Formula: Problem → Context → Invitation |
Awareness level: [Schwartz level from brief context]]

**Post 2 — Peer Proof or Data Post**
Publish timing: 5–7 days before event

Format: Insight or statistic + relevance + CTA
Length: 100–150 words

Write the full post. Lead with a named proof point
from proof_points.md or a relevant third-party
statistic if no proof point matches the event
topic closely. Connect the proof point to the
event topic in one sentence. Close with a soft
CTA to register.

If no suitable proof point is found: note "No
directly relevant proof point found in
proof_points.md — replace [STAT] with a
relevant third-party statistic before publishing."

Annotation: [Formula: Proof → Relevance → CTA |
Proof source: [named customer or placeholder]]

**Post 3 — Day-Before Urgency Post**
Publish timing: Day before the event

Format: Last call + what you will get + link
Length: 80–120 words

Write the full post. Short, direct. "Event is
tomorrow." One sentence on what attendees will
leave with. Registration link. No padding.

Annotation: [Formula: Last Call → Payoff → CTA]

---

### 3D — LinkedIn Paid Promotion Brief

A brief for the paid LinkedIn campaign supporting
event registrations. Not a full LinkedIn Campaign
Organiser output — this is a concise setup brief
that can be handed to whoever manages the LinkedIn
account.

Structure:

**Campaign objective:** Lead Generation (LinkedIn
Lead Gen Form) or Website Conversions depending
on whether registration is handled on LinkedIn
or on a landing page.

**Audience targeting:**
- Job titles to include: [derived from persona in
  icp.md — list the specific titles]
- Job titles to exclude: [derived from icp.md
  exclusions — junior titles, irrelevant functions]
- Seniority levels: [list — Senior, Director,
  VP, C-Suite as appropriate to persona]
- Company size: [read from segment definition in
  icp.md]
- Industries: [read from icp.md]
- Geography: [read from icp.md or infer as
  primary market — flag if not specified]

**Estimated audience size:**
Note: LinkedIn requires a minimum audience of
50,000 members for reliable delivery with CPM
bidding. Assess whether the combination of
job titles, seniority, company size, and
geography is likely to produce 50K+ members.
If the estimated size is below this threshold,
flag it and suggest one of: (a) expand geography,
(b) broaden job title list, (c) accept smaller
audience with awareness objective rather than
lead gen.

**Ad format:** Single Image Ad for primary.
Document Ad (carousel) as secondary if a
relevant content asset exists.

**Copy direction:**
Write 2 ad copy options. Each must conform to
brand_voice.md tone scale for the target segment.
Each must observe the funnel stage — awareness
stage holds product references; consideration and
decision stages may introduce named proof points
and direct CTAs.

Ad copy option 1: Problem-led hook. Names the
pain the persona feels. CTA to register.

Ad copy option 2: Outcome-led hook. Names the
specific result the persona can expect. CTA
to register.

For each option, write: headline (70 characters
max), introductory text (150 characters max),
and CTA button label.

**Bid strategy:** Maximum Delivery for awareness
objective. Manual CPM with bid cap for lead gen
objective. Note the recommended bid range for
B2B SaaS lead gen on LinkedIn: $8–$15 CPL is
ambitious; $15–$30 CPL is typical; above $40
CPL warrants creative or audience review.

**Run dates:** [From campaign start to event date.
Pause or switch to post-event track on event date.]

**Budget guidance:**
If registration goal was provided: estimate
required spend as [target registrations × $25
CPL] for a realistic baseline, noting this
assumes average B2B SaaS LinkedIn lead gen
performance and should be adjusted based on
the active company's historical performance
if available in outputs/performance/.
If registration goal was not provided: note
"Set budget based on target registration volume.
Rule of thumb: multiply target registrations
by $25 for an initial budget estimate."

**Prerequisite checklist:**
[ ] Registration page live with confirmed URL
[ ] LinkedIn Lead Gen Form created (if using
    native lead capture) with form fields
    matching the registration form spec in 3A
[ ] LinkedIn Insight Tag installed on website
[ ] Conversion tracking configured for
    registration page confirmation event
[ ] UTM parameters set on all ad destination URLs

---

## Step 4 — DURING-EVENT ASSETS

Produce different assets depending on event type.

---

### 4A — Webinar: Chat Prompts and Poll Questions

For webinar format only.

These assets are used by the host or moderator
during the live event to drive engagement, gather
intelligence on where attendees are in their
buying journey, and surface questions that create
natural transitions to post-event follow-up.

**Opening poll (launch at event start):**
Write 1 poll question with 4 answer options.
Objective: learn where the audience stands on
the topic. Not a product question. A situation
question that maps to the trigger event
definitions in trigger_events.md (or inferred
from icp.md if trigger_events.md is not found).

Example structure (do not use this verbatim —
derive from context files):
"Where are you with [the core problem this
event addresses]?"
- Still evaluating options
- In the middle of a change or initiative
- Hit a wall with our current approach
- Looking for a faster path

Annotation: [Intelligence this poll captures
and how it can be used to route contacts into
the correct post-event track.]

**Mid-event engagement question (post in chat):**
Write 1 question to post in the webinar chat
at a natural midpoint. Objective: invite the
audience to share their situation, normalise
the pain, and increase engagement metrics that
signal high intent. Derived from voice_of_
customer.md vocabulary if available.

**Closing CTA slide brief:**
Write the text for the closing CTA slide.
This slide appears at the end of the webinar
before Q&A. Structure: (1) what attendees
can do next — one specific action, (2) CTA
copy — short, direct, no hype language,
(3) destination — registration page,
content asset, or meeting booking link
[placeholder].

**Post-event chat message:**
Write the message posted in the webinar chat
immediately after the event ends. This message
drives the first post-event action before the
email sequence begins. Include: thank you
(one sentence), the follow-up resource or
recording link [placeholder], and the
primary post-event CTA.

---

### 4B — In-Person: Follow-Up Capture Brief

For in-person event format only.

**Badge scan and notes protocol:**
Guidance for the team on what information
to capture at the event beyond contact
details. Derive from buying_committee.md
if available — the most valuable signals
are: role in the buying process, stated
pain points, current solution in use,
timeline signals, and specific interest
topics from the agenda.

Provide a list of 5 qualifier questions
the team can use in conversation. Each
question is open-ended and does not
mention the company's product by name.
Each question is designed to surface
whether the contact is in an active
evaluation, experiencing a trigger event,
or at a stage of general awareness.

**High-engagement signals to capture:**
List 3–4 behaviours at the event that
indicate high intent — for example:
attended a specific session, requested
a follow-up meeting, asked a specific
question. These signals determine which
post-event track each contact enters.

**Networking conversation guide:**
3–4 conversation starters appropriate
for the target persona's information
diet and professional context. Derived
from persona_depth.md if available.
Each starter is a question or observation
that positions the team member as a
practitioner peer, not a vendor pitching
a product.

---

## Step 5 — POST-EVENT TRACKS

Three tracks run in parallel based on attendee
behaviour. Every email in every track is fully
written — subject line variants, preview text,
full body copy, and CTA.

For each email, include:
- Subject line: 2 options
- Preview text: 1 option (under 90 characters)
- Body copy: fully written
- CTA: copy and destination [placeholder if URL
  not yet known]
- Send timing: exact number of days after event
- HubSpot note: enrollment trigger, branch logic,
  and suppression conditions

---

### TRACK 1 — ATTENDEES

Contacts who attended the event.
Sequence length: 3 emails over 10 days.
Objective: convert attendance into a next step —
content consumption, meeting booking, or handoff
to sales depending on funnel stage.

**Track 1 enrollment trigger:**
Attended webinar (LinkedIn event attendance
data or Zoom/on24 integration) or badge scanned
at in-person event and not flagged as high
engagement (Track 3 criteria not met).

---

**Track 1 — Email 1**
Send timing: Day 1 after event (same day,
send within 2 hours of event end for webinar;
next morning for in-person)
Objective: Thank, deliver the promised follow-up
resource, and set up the next email's angle.

Write:
- Subject line: [2 options — one that references
  the event topic, one that delivers the resource]
- Preview text: [1 option]
- Body copy: 2–3 short paragraphs. Open by
  referencing a specific moment or topic from the
  event — make it feel personal, not automated.
  Deliver the follow-up resource (recording, deck,
  summary — use [resource link placeholder]).
  Close by previewing the next email or the next
  step available to them.
- CTA: [Access the recording / Download the summary
  / View the deck — whichever applies]
- HubSpot note: Enrollment trigger = event
  attendance confirmed. Delay = 2 hours post-
  event end for webinar. If in-person: delay =
  next morning 8am. Check for bounce or unsubscribe
  before sending.

**Track 1 — Email 2**
Send timing: Day 4 after event
Objective: Deepen the value. Give the attendee
something useful they can act on without the
company's involvement — a framework, a checklist,
a benchmark. This earns the right to make a more
direct ask in Email 3.

Write:
- Subject line: [2 options — one resource-led,
  one question-led]
- Preview text: [1 option]
- Body copy: 3–4 paragraphs. Reference one
  key takeaway from the event. Provide the
  actionable resource or framework. Connect
  it to the proof point most relevant to this
  persona's pain — use proof_points.md. Close
  with a soft next step, not a hard CTA.
- CTA: [Resource or tool — keep it low friction]
- HubSpot note: Delay = 3 days after Email 1.
  Suppress if contact has booked a meeting or
  replied to any prior email in this sequence.

**Track 1 — Email 3**
Send timing: Day 10 after event
Objective: Make the direct ask. Based on funnel
stage: consideration stage = offer a relevant
content asset or peer story; decision stage =
offer a meeting or a specific evaluation resource.

Write:
- Subject line: [2 options — one that names the
  next step, one that names the outcome]
- Preview text: [1 option]
- Body copy: 2–3 paragraphs. Brief recap of
  value delivered. Direct ask with clear
  benefit to the persona. CTA.
- CTA: [Book a 30-minute call / View the case
  study / Request the evaluation guide — based
  on funnel stage]
- Closing move logic: Select from the following
  based on funnel stage and prior engagement:
  - Consideration stage, low engagement: One
    Specific Thing ("The one question I'd want
    to answer for you is...")
  - Consideration stage, high engagement:
    Permission to Close ("Happy to leave you
    to it — let me know if useful to connect")
  - Decision stage: Hard CTA (calendar link,
    no ambiguity)
- HubSpot note: Delay = 6 days after Email 2.
  Suppress if meeting booked, replied, or
  unsubscribed at any point. Add meeting
  booking link if available.

---

### TRACK 2 — NO-SHOWS

Contacts who registered but did not attend.
Sequence length: 3 emails over 14 days.
Objective: recover attention and deliver the
event value in a format that does not require
live attendance.

Tone note: Do not make the contact feel bad
for not showing up. Do not use language like
"You missed it" or "Sorry you couldn't make
it." Frame the entire sequence around the
topic and value, not the missed event.

**Track 2 enrollment trigger:**
Registered for event AND did not attend
(no webinar join event or badge scan recorded).

---

**Track 2 — Email 1**
Send timing: Day 1 after event (same timing
as Track 1 Email 1 — no-shows get this email
at the same time as attendees)
Objective: Deliver the recording or recap
without referencing attendance. Make it feel
like a value delivery, not a catch-up email.

Write:
- Subject line: [2 options — both lead with
  the topic and resource, neither reference
  the missed event]
- Preview text: [1 option]
- Body copy: 2 paragraphs. Open with the
  topic and why it matters now (not "you
  missed the webinar"). Deliver the recording
  or summary with a direct link. Let the
  value speak for itself.
- CTA: [Watch the recording / Read the summary]
- HubSpot note: Enrollment trigger = registered
  AND not attended. Delay = same as Track 1
  Email 1. Check suppression list — anyone
  who already unsubscribed from related
  communications should not receive this.

**Track 2 — Email 2**
Send timing: Day 5 after event
Objective: Re-engage around the topic using
a different angle. The contact did not attend
— the event angle has limited leverage. Switch
to a pain or peer proof angle.

Write:
- Subject line: [2 options — one pain-led,
  one proof-led. Neither references the event.]
- Preview text: [1 option]
- Body copy: 2–3 paragraphs. Open with the
  persona's core pain in their vocabulary
  — derived from icp.md and voice_of_customer.md.
  Introduce the most relevant proof point for
  this persona from proof_points.md. Close with
  a relevant resource or a soft next step.
- CTA: [Low-friction resource — not a meeting ask]
- HubSpot note: Delay = 4 days after Email 1.
  Suppress if contact clicked any link in Email 1
  and the CTA destination has a re-enroll trip
  wire configured. Otherwise send regardless of
  Email 1 open status.

**Track 2 — Email 3**
Send timing: Day 14 after event
Objective: Final attempt. Offer a direct
conversation with low pressure.

Write:
- Subject line: [2 options — one question-led,
  one direct]
- Preview text: [1 option]
- Body copy: 2 short paragraphs. Acknowledge
  this is the last email in this series (no
  shame, no pressure). One question: is this
  topic relevant to what they are working on
  right now? Direct CTA.
- CTA: [Book a 20-minute call / Reply to this
  email / Access the resource] — based on
  funnel stage
- Closing move: Permission to Close. Keep this
  email short. If they are not engaging by now,
  a long email will not change that.
- HubSpot note: Delay = 9 days after Email 2.
  After sending, move contact to general nurture
  sequence if no engagement. Do not re-enroll
  in another event sequence for 60 days.

---

### TRACK 3 — HIGHLY ENGAGED

Contacts who showed high-intent signals at
the event. Sequence length: 2 emails over
4 days. Objective: move to a sales conversation
as quickly as possible without feeling pushy.

High-intent signal definition: at least one of:
- Asked a question in Q&A (webinar)
- Clicked a CTA slide link during the event
- Requested a follow-up or specific resource
  during or after the event
- Attended the full event duration (webinar:
  >80% watch time)
- Badge scanned and qualified by the team
  as an active evaluation (in-person)

**Track 3 enrollment trigger:**
Attended event AND met at least one high-intent
signal above. Must be manually reviewed or
triggered by a HubSpot workflow using webinar
integration data. Flag for the human: "Track 3
contacts should be reviewed by a sales or
SDR team member before Email 2 sends — this
track is designed to hand off to a human
conversation, not run fully automated."

---

**Track 3 — Email 1**
Send timing: Day 1 after event (same day,
within 1 hour of event end for webinar if
possible; within 4 hours for in-person)
Objective: Strike while intent is highest.
Reference the specific moment or signal that
identified this contact as high-engagement.
Do not be generic.

Write:
- Subject line: [2 options — both direct and
  specific. No generic "thanks for attending."]
- Preview text: [1 option]
- Body copy: 2 short paragraphs. Reference
  the specific signal if possible (their
  question, the CTA they clicked, the session
  they attended). Deliver the promised follow-up
  resource. Make the next step clear and easy.
- CTA: [Book a 25-minute call / Access the
  evaluation guide / View the case study most
  relevant to their stated interest]
- HubSpot note: Enrollment trigger = high-intent
  signal recorded in HubSpot or manually added
  to Track 3 list. Delay = 0 (send immediately
  or at start of next business day if event ends
  after 4pm). Sales notification: trigger a
  task in HubSpot for the assigned SDR at the
  same time this email sends.

**Track 3 — Email 2**
Send timing: Day 4 after event
Objective: If no reply to Email 1: follow up
once with a direct, low-pressure ask. If
replied: this email is suppressed — hand off
to sales team to continue the conversation
directly.

Write:
- Subject line: [2 options — one direct,
  one question-led]
- Preview text: [1 option]
- Body copy: 1–2 very short paragraphs.
  Reference Email 1 briefly. One direct ask.
  Make it easy to say yes or no.
- CTA: [Book a call — calendar link / Reply
  to this email to connect]
- Closing move: Hard CTA with a specific
  call booking link. This contact has shown
  high intent — do not soften the ask.
- HubSpot note: Delay = 3 days after Email 1.
  Suppress if: replied to Email 1, booked a
  meeting at any point, or has an active
  opportunity in CRM. After Email 2 sends
  with no reply: move to sales queue for
  manual follow-up. Do not enroll in standard
  nurture automatically — this contact
  deserves a direct sales touch first.

---

## Step 6 — HubSpot Workflow Architecture

Produce a summary of the full HubSpot workflow
architecture for all three post-event tracks.
This is a reference for whoever configures
HubSpot — it describes the logic, not the
button clicks.

Structure:

**Workflow name recommendation:**
[Event name] — Post-Event Routing
[Event name] — Track 1: Attendees
[Event name] — Track 2: No-Shows
[Event name] — Track 3: Highly Engaged

**Enrollment triggers for each workflow:**

Track 1: Contact property "Attended [event name]"
= Yes AND Contact property "High Engagement" = No

Track 2: Contact property "Registered [event name]"
= Yes AND Contact property "Attended [event name]"
= No

Track 3: Contact property "Attended [event name]"
= Yes AND Contact property "High Engagement" = Yes
(High Engagement property set manually by sales
team or via webinar integration data)

**Branch logic:**
After each email in each track, check:
- Has the contact replied? → Suppress all
  further automated sends. Notify assigned
  sales rep or SDR.
- Has the contact booked a meeting? → Suppress
  all further automated sends. Enroll in
  meeting confirmation workflow.
- Has the contact unsubscribed? → Suppress
  all sends. Do not re-enroll.

**Suppression conditions (apply across all tracks):**
- Active deal in CRM with stage = Negotiation
  or Proposal Sent → suppress all automated
  sends, notify sales rep
- Contact marked as Do Not Contact → suppress
  all sends
- Competitor company in Company Domain field
  → suppress all sends (review list in
  competitors.md to configure this filter)

**Post-sequence routing:**
Track 1 completers (no reply, no meeting): enroll
in general consideration-stage nurture sequence.
Track 2 completers (no reply, no meeting): pause
for 30 days, then enroll in general awareness
or consideration nurture. Do not re-enroll in
event sequences for 60 days.
Track 3 completers (no reply, no meeting): route
to sales team as a warm lead for manual outreach.
Flag in HubSpot as "Attempted — event sequence
complete, requires human follow-up."

**Integration notes:**
Webinar platform (Zoom Webinar / ON24 / other):
attendance data and engagement data must sync
to HubSpot contact properties before post-event
workflows can enroll contacts correctly. Verify
this integration is live and tested before the
event date.

LinkedIn Lead Gen Forms: if used for registration,
confirm HubSpot sync is live and the correct
list is feeding the pre-event sequence enrollment.

---

## Step 7 — Save Option

After displaying all output, ask:

"All event campaign assets are ready above.

Would you like to save the output?
If yes, I will save as:
webinar_[company]_[YYYY-MM-DD].md

Check outputs/ for a file with the same
base name before saving. If one exists,
ask for a theme descriptor:
webinar_[theme]_[company]_[YYYY-MM-DD].md
Theme = 1-3 words describing the event topic.

Type 'save' to write the file or 'skip'
to finish without saving."

Only save after explicit confirmation.
Never save automatically.

---

## Rules This Skill Must Always Follow

1. No hardcoded company names, product names,
   competitor names, or industry-specific terms
   anywhere in this file. Every reference to the
   company, its buyers, and its market must come
   from context files read at runtime.

2. All copy produced in this skill — registration
   page, email sequences, LinkedIn posts, ad copy,
   chat prompts — must comply with brand_voice.md.
   Check the tone scale for the active segment
   before writing. Do not use words on the avoid
   list.

3. Every email in every post-event track must be
   fully written — not a brief, not a template with
   blanks. The only acceptable placeholders are
   URLs and links that do not yet exist.

4. LinkedIn paid copy must observe funnel stage
   rules. Awareness stage: hold product references
   and hard metrics. Consideration stage: introduce
   named proof points. Decision stage: direct CTA
   with specific outcome claim is permitted.

5. Track 3 must never run fully automated without
   a human review step before Email 2. Always flag
   this to the human in the Track 3 section.

6. Never update context files automatically.
   If any asset produced in this skill suggests
   an update to icp.md, proof_points.md, or any
   other context file — draft the proposed update
   and ask the human to review and apply it
   manually.

7. All output goes to outputs/ only. Never create
   files in context/ unless explicitly instructed.
   Never modify existing context files.
