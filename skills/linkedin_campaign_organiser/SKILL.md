---

# LinkedIn Campaign Organiser
## Maps copy variants to LinkedIn campaign
## structure with phase-aware targeting,
## format recommendations, and bid strategy
## Produces one structured strategy document

---

## What This Skill Does
Takes copy variants from the Campaign
Writer and maps them into a complete
LinkedIn Ads campaign structure.

Unlike Google Ads which organises by
keyword intent, LinkedIn organises by
audience targeting — job title, company
size, industry, seniority, and interest.
The same copy variant performs differently
depending on which audience sees it and
at what phase of the buyer journey.

This skill determines:
- Which phases to run (awareness,
  retargeting, ABM) based on the brief
- Which audience targeting combinations
  serve each phase
- Which copy variant is assigned to
  each campaign and why
- Which ad form serves each campaign
  objective and why
- How budget should be allocated across
  campaigns
- How to bid for each campaign objective
- What to A/B test and in what order

Output: one structured strategy document
ready to hand to whoever builds the
campaigns in LinkedIn Campaign Manager.

---

## Step 1 — Read Before Doing Anything

Before asking a single question, read
ALL of these files:

### Required context files

context/icp.md
Pay close attention to:
- Primary buyer personas — LinkedIn
  targeting is built around job titles
  and seniority. The ICP file contains
  the exact titles to target and the
  titles that appear adjacent to the
  ICP but should be excluded.
- Segments — company size and industry
  targeting parameters come directly
  from the segment definitions
- What triggers them to start looking —
  trigger events inform which phase
  is most urgent and what the copy
  angle should be for each phase
- The language they actually use —
  LinkedIn interest targeting sometimes
  inclest categories that
  mirror ICP vocabulary. Check for
  alignment.

context/brand_voice.md
Pay close attention to:
- Tone by segment — LinkedIn campaigns
  targeting government buyers need
  different register than campaigns
  targeting growth-stage SaaS
- Words and phrases to avoid — apply
  to every ad copy assignment

context/competitors.md
Pay close attention to:
- Competitor displacement angles —
  LinkedIn retargeting campaigns are
  often the right place to run
  competitive differentiation copy
  because the audience has already
  shown interest
- Messaging angles this company can own —
  use to assign the strongest ownable
  angle to the awareness phase where
  first impressions are formed

context/proof_points.md
If found: use to validate which proof
points are assigned to which phases.
Awareness phase gets conceptual proof.
Consideration and retargeting phases
get specific named metrics.

### Optional deep-dive files

context/deep/persona_depth.md
If found: use for LinkedIn-specific
audielligence — what groups
the persona belongs to, what content
they engage with on LinkedIn, and
what their LinkedIn activity signals
about their buying stage.

context/deep/buying_committee.md
If found: use to identify whether
multiple personas at the same company
need separate campaigns. LinkedIn's
matched audiences and company list
targeting make buying committee
campaigns feasible.

context/deep/market_gaps.md
If found: use to identify positioning
angles that no competitor is running
on LinkedIn — these are the highest
value awareness phase angles because
they own unclaimed territory.

context/deep/trigger_events.md
If found: use to identify which trigger
events can be targeted on LinkedIn
through job change signals, company
news following, or interest categories.

### Required campaign files

Scan outputs/ for the most recent
campaign writer output matching
this campaign:

outputs/copy_*_[company]_*.md
Required — cannot proceed without it.
Read every variant, its headline
formula, its angle, its aws
level, and its best for note.
The LinkedIn campaign structure is
built around these variants — not
generic copy.

outputs/landing_page_brief_*_[company]_*.md
If found: use to confirm the destination
page continues the message each ad
establishes. Flag any message match
gaps between ad copy and landing page.

---

## Step 2 — Show All Questions At Once

After reading all files, display ALL
questions in one message. Wait for
all answers before proceeding.

---
Before I build the campaign structure,
I need a few details. Answer all in
one message:

1. CAMPAIGN GOAL — what is the primary
   objective for this LinkedIn campaign?
   - Brand awareness — maximise
     impressions among the right audience
   - Lead generation — capture leads
     directly via LinkedIn Lead Gen Forms
   - Website conversions — drive traffic
     to a landing page with a form
   - Engagement — drive reactions,
     comments, and shares on content
   - Multiple — describe the mix

2. PHASES TO INCLUDE — based on you recommend phases.
   Confirm or adjust:
   [I will fill this in after reading
   the brief — either recommending
   awareness only, awareness plus
   retargeting, or the full three-phase
   structure including ABM]

3. BUDGET — what is the total monthly
   LinkedIn budget for this campaign?
   Say "not set yet" — I will provide
   percentage allocations instead of
   dollar amounts.
   Note: LinkedIn minimum effective
   budget is typically $3,000-5,000
   per month per campaign to generate
   meaningful data. Below that,
   impression volume is too low to
   optimise.

4. TARGET SEGMENTS — which segments
   from the ICP are in scope?
   - Commercial Enterprise only
   - High-Growth Tech only
   - US Federal / Defense only
   - All segments
   - Specific mix — describe it

5. EXISTING LINKEDIN CAMPAIGNS —
   are any LinkedIn campaigns already
   running for this company that I
   should avoid duplicating audiences
   or angles with?
   Say "none" or "not sure."

6. ABM CONTEXT — if including e, do you have a target
   account list available?
   - Yes — I will structure the ABM
     campaign around matched audiences
   - No — I will structure it around
     lookalike audiences from existing
     customer list instead
   - Not including ABM phase
---

---

## Step 3 — Determine Phase Structure

After receiving answers, determine
which phases to include and display
the phase recommendation before
building the full structure.

### Phase selection rules

AWARENESS PHASE only — recommend when:
- No retargeting pixel data exists yet
  (new campaigns, no website history)
- Budget is under $5,000/month
  (retargeting requires minimum volume
  to function effectively)
- The brief specifies brand awareness
  as the primary goal
- The company is entering a new market
  or segment with no existing presence

AWARENESS + RETARGETING — recommend when:
- Website traffic exists and LinkedIn
  Insight Tag is installed
- Budget is $5,000-15,000/month
- The brief specifies lead generation
  or website cons goals
- Campaign writer output includes
  both awareness-level and
  consideration/decision-level variants

FULL THREE PHASES (including ABM) —
recommend when:
- A target account list exists with
  minimum 300 matched companies
- Budget is $10,000+/month
- The brief specifies account-based
  or named account objectives
- buying_committee.md identifies
  multiple personas at target accounts
  worth addressing separately

Display the phase recommendation with
reasoning before proceeding:

---
PHASE RECOMMENDATION

Recommended phases for this campaign:
[List phases]

Reasoning: [2-3 sentences on why
these phases, based on the brief,
the budget, and the available assets]

Confirm or adjust before I build
the full structure.
---

---

## Step 4 — Build The Campaign Structure

After phase confirmation, build the
complete LinkedIn campaign map.

### LinkedIn campaign naming convention
Format:
[Company] | [Phase] | [Segment] |
[Angle] | [Quarter]

Examples:
"Lilt | Awareness | Enterprise |
Vendor Tax | Q2 202"Lilt | Retargeting | Enterprise |
Switching Objection | Q2 2026"

"Lilt | ABM | Enterprise |
Intel Story | Q2 2026"

---

## Step 5 — Produce The Strategy Document

Structure the strategy document
exactly as follows:

---
LINKEDIN CAMPAIGN STRATEGY
─────────────────────────────────────────
Company: [from context/icp.md]
Campaign theme: [from brief]
Phases included: [list]
Total campaigns: [number]
Source copy file: [filename]
Strategy created: [today's date]
─────────────────────────────────────────

CAMPAIGN-LEVEL SETTINGS

LinkedIn Insight Tag:
[Confirm whether retargeting and
conversion tracking require the
Insight Tag to be installed. If
retargeting phase is included,
flag this as a prerequisite.]

Conversion tracking setup:
[What conversion events to track —
demo booking, form fill, content
download. Specific enough that
whoever sets up
contact lists, account lists,
lookalike audiences. Flag build time:
matched audiences require 300+
members and 24-48 hours to populate.]

─────────────────────────────────────────

[For each phase, use this structure:]

─────────────────────────────────────────
PHASE [N]: [Phase Name]
Objective: [LinkedIn campaign objective]
─────────────────────────────────────────

AUDIENCE TARGETING

Primary audience:
Job titles to include:
[List exact LinkedIn job title
targeting options that match the
ICP persona. LinkedIn job title
targeting is imprecise — include
variations and note which are
exact matches vs. approximations.]

Job titles to exclude:
[List job titles that appear in
the same seniority level but are
not ICP buyers — preventing budget
waste on adjacent but ic LinkedIn industry
categories that match the segment —
LinkedIn industry categories do not
always map cleanly to ICP definitions;
flag any gaps]

Geographic targeting:
[Country and region targeting]

Estimated audience size:
[Rough LinkedIn audience estimate
based on targeting parameters —
note that LinkedIn shows this in
Campaign Manager before launch.
Flag if audience is likely under
50,000 members — too small for
meaningful delivery at most budgets]

Secondary audience (if applicable):
[Interest-based or group-based
targeting as a broader reach option —
lower CPM but weaker ICP match.
Specify when to use this vs. the
primary job title audience.]

─────────────────────────────────────────
ASSIGNED COPY VARIANT

Primary: Variant [N] — [variant name]
  Intro text: [the LinkedIn body copy
  — adapted from campaign writer output
  for LinkedIn format. LinkedIn intro
  text performs best at 150 characters
  or underer 100 chars]
  CTA button: [LinkedIn CTA options:
  Learn More, Download, Sign Up,
  Register, Apply Now, Get Quote,
  Contact Us — specify which and why]

  Why this variant for this phase:
  [one sentence on why this variant's
  awareness level and angle match
  the audience's likely buying stage
  in this phase]

  Message match check: [one sentence
  confirming the ad copy and the
  destination page are continuing
  the same conversation. Flag any
  mismatch.]

Backup: Variant [N] — [variant name]
  Why backup: [one sentence on what
  scenario makes this the better
  choice and what metric triggers
  the swap]

─────────────────────────────────────────
AD FORMAT RECOMMENDATION

Primary format: [Single Image /
Carousel / Video / Document /
Conversation Ad / Lead Gen Form]

Why this format:
[2-3 sentences on why this specific
format serves this phase's objective
and this audience's likely behavior.
Reference LinkedIn fo for all objectives.
Best for awareness and retargeting
with a strong visual hook.

Carousel: higher engagement rate than
single image when the story benefits
from multiple frames — e.g. a
step-by-step process, multiple proof
points, a before/after contrast.
Higher production cost; recommend
only when the narrative requires it.

Video: highest engagement rate for
awareness phase when production
quality is sufficient. Under 30
seconds outperforms longer formats.
Requires video asset — flag if asset
doesn't exist.

Document Ad: uniquely strong for
B2B content distribution — case
studies, reports, frameworks.
LinkedIn members can read the first
few pages in-feed, which drives
higher qualified clicks than a
blind "download" CTA. Recommend
when a relevant document asset exists.

Conversation Ad: message-based format
sent to LinkedIn inboxes. Higher
cost per send but more personal.
Recommend for retargeting only —
sending to cold audiences feels
intrusive and damages brand perception.

Lead Gen Form: elimhe landing
page step by collecting form data
inside LinkedIn. Reduces friction
but loses the message match and
conversion context of a dedicated
landing page. Recommend when landing
page experience is weak or when
mobile conversion is a priority.

Secondary format to test:
[Alternative format with one sentence
on what learning it would produce
compared to the primary format]

Creative direction notes:
[Specific guidance on the visual
approach for this format — what
the image or video should show,
what text overlay if any, what
the visual hierarchy should be.
Specific enough that a designer
can brief from this without asking
questions. Not art direction —
strategic creative guidance.]

─────────────────────────────────────────
BID STRATEGY

Bid type: [Maximum Delivery /
Manual CPC / Manual CPM /
Target Cost]

Why this bid type:
Maximum Delivery: LinkedIn's automated
bidding. Use for awareness phase
where reach is the goal aes for impressions.

Manual CPC: use for conversion-focused
campaigns where controlling cost
per click is more important than
reach. Start 20-30% above LinkedIn's
suggested bid — too low and the
campaign won't deliver.

Target Cost: use when you have
historical conversion data and
a known target CPL. Requires
minimum 50 conversions to function.
Do not use on new campaigns.

Suggested starting bid:
[Specific recommendation — e.g.
"start at $8-12 CPC for Director/VP
level targeting in North America"
or "Maximum Delivery for awareness
phase with daily budget cap"]

Daily budget recommendation:
[Dollar amount if budget was provided,
percentage of monthly budget if not]

─────────────────────────────────────────
A/B TESTING RECOMMENDATION

Test 1 (launch with):
[Primary variant and format as above]
Run until: [minimum impressions and
clicks before drawing conclusions —
LinkedIn requires more volume than
Google Ads. Minimum 5,est — copy variant swap,
format swap, or audience expansion.
Test one variable at a time.]
What to measure: [specific metric —
CTR for awareness, conversion rate
for lead gen, cost per lead for
retargeting]

Test 3 (after Test 1 vs Test 2
produces a winner):
[Next hypothesis — what to test
once the baseline is established]

─────────────────────────────────────────
QUALITY AND RELEVANCE SCORE NOTES

LinkedIn Relevance Score equivalent:
[LinkedIn uses an internal relevance
score that affects delivery and CPM.
Flag the factors that will most
affect this campaign's score:]

Audience match: [how well the
copy angle matches what this
audience cares about — the stronger
the match, the higher the relevance
score and the lower the CPM]

Engagement rate impact: [LinkedIn
rewards ads that earn reactions,
comments, and shares with lower
CPMs. Note whether this format
and copy angle is likely to earn
organic engagement beyond clic immediately from
the landing page, relevance score
suffers. Flag any landing page
gaps that would cause this.]

─────────────────────────────────────────
LANDING PAGE FLAG

[One of three options — same logic
as Ad Group Organiser:]

EXISTING PAGE SUFFICIENT:
[Confirm which page serves this
campaign and why it continues the
ad's message adequately]

DEDICATED PAGE RECOMMENDED:
[Flag the message match gap and
recommend running Landing Page
Brief skill before scaling budget]

DEDICATED PAGE REQUIRED:
[Flag the specific promise the ad
makes that the current destination
does not fulfill. Do not scale
budget to this campaign until
the page exists.]

─────────────────────────────────────────

[Repeat for each phase]

─────────────────────────────────────────

BUDGET ALL;
  retargeting gets more budget
  once the pool is large enough
  to deliver meaningfully]

[If budget not provided:]
Recommended percentage allocation:

Awareness: [X]% of budget
Why: [reasoning]

Retargeting: [X]% of budget
Why: [reasoning]

ABM: [X]% of budget
Why: [reasoning]

Budget principle applied:
[One paragraph on the logic behind
the allocation — LinkedIn CPMs are
significantly higher than Google Ads
for the same audience. Director/VP
level targeting in North America
typically runs $12-25 CPM. Budget
allocation must account for this
or the campaign will underdeliver.]

─────────────────────────────────────────

LAUNCH SEQUENCE

Week 1 — Launch: [phase(s)]
Why: [reasoning — awareness first
to build retargeting pool before
launching retargeting campaigns]

Week 3-4 — Add: [phase(s)]
Why: [reasoning — retargeting
requires minimum audience size
before it can deliver]

Week 6+ — Add: [phase(s) if ABM]
Why: [ied
☐ Conversion events configured
  in Campaign Manager
☐ Matched audiences built and
  populated (300+ members)
☐ Landing page reviewed for
  message match
☐ Creative assets approved
☐ Campaign naming convention
  confirmed with team

─────────────────────────────────────────

SKILLS THAT WOULD IMPROVE THIS CAMPAIGN

Files that were missing:
[List optional files not found]

Creative assets that don't exist yet:
[List specific assets flagged during
format recommendation — video,
document, case study PDF — that
would improve campaign performance
if they existed]

Skills worth running next:
[2-3 skills from the toolkit that
connect to this campaign — Landing
Page Brief for flagged pages, Email
and Nurture Sequencer for leads
captured via Lead Gen Forms,
Trigger Monitor for ABM phase
account intelligence]

Data that would sharpen these
recommendations:
[LinkedIn Campaign Manager historical
data — CPM benchmarks───────────────────────────────────────

SAVE CONFIRMATION

After the full strategy document,
ask:

"Would you like to adjust anything
before saving?

You can ask me to:
- Reassign a copy variant to a phase
- Change the format recommendation
- Adjust the audience targeting
- Change the bid strategy
- Add or remove a phase
- Adjust budget allocation

Or type 'save' to write the output file."

Save as:
linkedin_strategy_[angle]_[company]
_[date].md

Save to outputs/.

Only save after explicit confirmation.
Never save without confirmation.

---

## Rules This Skill Must Always Follow

Never assign the same copy variant
to awareness and retargeting phases
without explanation — these audiences
are at different stages and need
different messages.

Never recommend Maximum Delivery
for conversion-focused campaigns —
LinkedIn's algorithm optimises for
impressions, not conversions, on
Maximum Delivery.

Never recommend Conversation Ads
ntrusive.

Never recommend broad match audience
targeting without exclusions — job
title targeting on LinkedIn captures
adjacent roles that are not ICP
buyers. Exclusions are required.

Always flag the LinkedIn Insight Tag
as a prerequisite if retargeting
phase is included — retargeting
cannot run without it.

Always flag audience size — if
targeting parameters produce an
audience under 50,000, note that
delivery will be limited and CPMs
will be high.

Always recommend testing one variable
at a time — copy variant OR format
OR audience, never multiple variables
simultaneously.

Always include the prerequisite
checklist — LinkedIn campaigns
frequently launch with missing
conversion tracking or unverified
Insight Tags, which makes
optimisation impossible.

Never save without explicit
confirmation.

Always read the active company name
from the first line of context/icp.md
before naming output files.

Follow the file naming convention
in CLAUDE.md for all output files.

If the campaign writer output f be found in outputs/, stop
and say so before proceeding —
this skill cannot map copy variants
that don't exist.

---
