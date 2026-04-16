# Campaign Orchestrator
## One brief in. Complete campaign package out.
## Chains all demand gen skills in sequence
## automatically.

---

## What This Skill Does
Accepts a plain English campaign brief and
runs the full demand gen toolkit chain
automatically — checking for stale context,
running keyword research, building proof
points if missing, and generating campaign
copy. Returns a complete campaign package
with a run summary first, followed by the
output most relevant to the campaign type.

You never need to run individual skills
manually for a campaign request. Just
describe what you want in plain English
and the orchestrator handles the rest.

---

## Step 1 — Parse The Brief

Accept any plain English description of
what the human wants. Do not require a
specific format. Interpret casually spoken
briefs the same as structured ones. Examples
of briefs the orchestrator accepts:

"I want to run a bottom funnel paid search
campaign targeting Head of Localization
at large enterprise companies"

"paid search, enterprise, decision stage,
3 variants for the vendor management angle"

"can you put together some Google ad copy
for the localization director persona,
we want to push the Intel case study,
mid to bottom funnel"

"LinkedIn ads for the high growth SaaS
segment, awareness stage, something around
the brand voice consistency pain point"

From any brief, extract and confirm:
- Campaign format (paid search, LinkedIn,
  cold email, landing page, webinar, etc.)
- Target segment (read options from
  context/icp.md if unclear)
- Target persona (read from context/icp.md)
- Funnel stage (awareness, consideration,
  decision — infer if not stated)
- Number of variants (default to 3 if
  not specified)
- Specific angle, offer, or constraint
  (optional — use if mentioned)

If anything critical is genuinely ambiguous
and cannot be inferred, ask one clarifying
question only. Do not ask multiple questions.
Make reasonable assumptions on everything
else and state them in the run summary.

---

## Step 2 — Pre-Flight Check

Before running any skill, check the state
of the project. Display a pre-flight status
block showing what was found and what will
run. Wait for me to type 'run' before
proceeding.

Display exactly this format:

---
PRE-FLIGHT CHECK
─────────────────────────────────────────
Campaign brief interpreted as:
Format: [format]
Segment: [segment]
Persona: [persona]
Funnel stage: [stage]
Variants: [number]
Angle/offer: [if specified, otherwise
"not specified — will draw from context"]

Context files:
[✓ or ✗] context/icp.md
[✓ or ✗] context/brand_voice.md
[✓ or ✗] context/competitors.md
[✓ or ✗] context/market.md
[✓ or ✗] context/proof_points.md

Active company: [read from first line
of context/icp.md]

Keyword file status:
[Found / Not found]

Skills that will run:
[List each skill in order with one
sentence on why it is or isn't running]

Files that will be created:
[List expected output file names using
the naming convention from CLAUDE.md]

Type 'run' to start. Or correct anything
above before proceeding.
─────────────────────────────────────────
---

---

## Step 3 — Run The Chain

After receiving 'run', execute each skill
in this sequence. Show a one-line progress
update before each step. Do not show full
intermediate output between steps — only
the progress line.

Progress line format:
▶ Running [Skill Name] — [one sentence
on what it is doing right now]
✓ [Skill Name] complete — [one sentence
on what it produced]

### Skill 1 — Context Builder
Run this skill if ANY of these are true:
- context/icp.md is missing
- context/brand_voice.md is missing
- context/competitors.md is missing
- context/market.md is missing

Skip this skill if all four context files
exist. Do not run the context builder on
a timer — only when files are missing or
the company changes.

If run: use skills/context_builder/SKILL.md
to populate all four context files before
any other skill runs.

### Skill 2 — Proof Point Library
Run this skill if EITHER of these are true:
- context/proof_points.md does not exist
- context/proof_points.md exists but is
  empty or has only placeholder content

Skip this skill if proof_points.md exists
and has real content.

If run: read all four context files and
any existing output files in outputs/ and
extract every named customer result,
specific metric, case study outcome, and
proof statistic into context/proof_points.md
organized by company name, segment, and
metric type. This is not a full skill build
yet — use best judgment from available
context to produce a structured file.

Save as: context/proof_points.md
(not in outputs/ — this is a context file)

### Skill 3 — Keyword Finder
For paid search and landing page formats:
always run or reuse.

For all other formats (LinkedIn, email,
Reddit): skip this skill entirely.

Staleness check for paid search and
landing page:
- Search outputs/ for keyword files
  matching the active company name:
  keywords_*_[company]_*.md
- If found: check the date in the filename
- If the file is less than 6 weeks old
  from today's date: reuse it, skip
  running the keyword finder again
- If the file is older than 6 weeks or
  no matching file exists: run the keyword
  finder fresh

If running fresh: use
skills/keyword_finder/SKILL.md
Pass the campaign format, segment, and
funnel stage from the brief automatically.
Do not ask the human the intake questions
again — use what was already captured in
Step 1.

Save as: keywords_[format]_[company]
_[YYYY-MM-DD].md

### Skill 4 — Campaign Writer
Always run this skill last.

Pass all of the following automatically:
- The brief details from Step 1
- The keyword file (if one exists or
  was just created)
- The proof_points.md file (if it exists)
- Any other relevant files found in
  outputs/ matching the active company

Do not ask the campaign writer's intake
questions again — use what was already
captured in Step 1 and confirmed in the
pre-flight check.

The campaign writer should produce the
requested number of variants in the
annotated format with the skills
suggestion section at the end.

Save as: copy_[format]_[company]
_[YYYY-MM-DD].md

After Campaign Writer saves its output,
check the campaign format. If the format
is paid search, Google ads, or landing
page, offer to run the Landing Page Brief
skill before closing the run:

"Campaign Writer complete. Would you
also like a landing page brief for this
campaign? It will map directly to the
ad variants just produced and produce
HubSpot-ready copy for the page that
receives these clicks. Type 'yes' to
run it or 'skip' to finish here."

If 'yes': run skills/landing_page_brief/
SKILL.md passing the campaign output
file automatically.
If 'skip': proceed to the run summary.

After the landing page brief offer is
resolved (whether 'yes' or 'skip'),
check the campaign format again. If
the format is paid search or Google ads,
offer to run the Ad Group Organiser:

"Campaign Writer complete. Would you
also like me to run the Ad Group
Organiser to map keywords to copy
variants and produce a Google Ads
Editor import file? Type 'yes' to
run it or 'skip' to finish here."

If 'yes': run skills/ad_group_organiser/
SKILL.md passing the campaign output
file and keyword file automatically.
If 'skip': proceed to run summary.

### LINKEDIN CHAIN

Triggered by: "LinkedIn," "social,"
"sponsored content," "LinkedIn ads,"
"sponsored post"

When triggered, do NOT run the
standard paid search chain (Skills
1-4 above). Instead:

Step 1 — Check for existing LinkedIn
copy variants in outputs/:
- Search for copy_linkedin_ad_[company]_*.md
- If found and dated within 6 weeks:
  skip Campaign Writer, pass directly
  to LinkedIn Campaign Organiser
- If not found or older than 6 weeks:
  run Campaign Writer first for
  LinkedIn format

Step 2 — After Campaign Writer
completes for LinkedIn format, offer
to run the LinkedIn Campaign Organiser:

"Campaign Writer complete. Would you
also like me to run the LinkedIn
Campaign Organiser to map these
variants to a full LinkedIn campaign
structure with audience targeting,
format recommendations, and bid
strategy? Type 'yes' to run it
or 'skip' to finish here."

If 'yes': run skills/linkedin_campaign_
organiser/SKILL.md passing the
campaign output file automatically.
If 'skip': proceed to run summary.

### COMPETITOR AD INTELLIGENCE CHAIN

Triggered by: "competitor ads," "what are
competitors running," "ad intelligence,"
"competitive advertising," "competitor brief,"
or any request to see what a specific competitor
is advertising.

When triggered, route directly to Competitor
Ad Intelligence:
skills/competitor_ad_intelligence/SKILL.md

Skills that run:
1. Competitor Ad Intelligence — reads all
   competitors from context/competitors.md
   and context/deep/competitive_intel.md,
   searches LinkedIn Ad Library, Google Ads
   Transparency Center, and Meta Ad Library,
   produces a brief covering active ads,
   historical patterns, spend signals, gap
   analysis, and counter-angle recommendations
   anchored to proof_points.md, and drafts
   proposed updates to competitive_intel.md
   for human review

Note: Competitor Ad Intelligence runs
standalone. It produces counter-angle
recommendations with ready-to-use orchestrator
briefs that the human pastes back in as
separate runs when ready to act. It does not
automatically trigger Campaign Writer or
any other skill.

### TRIGGER MONITOR CHAIN

Triggered by: "trigger monitor," "weekly briefing,"
"account signals," "check accounts," "target accounts,"
or a specific company name followed by "trigger"
or "signal"

When triggered, route directly to the Trigger Monitor.
Do not run any other skill first.

Skills that run:
1. Trigger Monitor — reads context/target_accounts.md,
   searches for buying signals at each account,
   produces a prioritized briefing with outreach
   briefs ready to execute

Note: The Trigger Monitor runs standalone. It does
not chain to other skills automatically. It produces
outreach briefs that the human pastes into the
orchestrator as separate runs when ready to act
on a signal.

### SEO CONTENT BRIEF CHAIN

Triggered by: "SEO brief," "content brief," "blog brief,"
"pillar page," "content cluster," "SEO content," "organic
content," or any mention of SEO strategy or content planning.

When triggered, do NOT run the standard paid search chain
(Skills 1-4 above). Instead:

Route directly to the SEO Content Brief:
skills/seo_content_brief/SKILL.md

Pass the full brief directly, including the stated topic or
keyword cluster. The skill reads context files and keyword
files internally. It produces one pillar page brief plus
3-5 cluster piece briefs with AEO and GEO optimisation
included in every brief.

The skill checks outputs/ for:
- An existing keyword file to use as the keyword data source
  (avoids re-running keyword research if a scored file exists)
- A Competitor Ad Intelligence report to identify keywords
  where competitors are strong in both paid and organic

Skills that run:
1. SEO Content Brief — reads icp.md, competitors.md, market.md,
   proof_points.md, market_gaps.md, and voice_of_customer.md
   if available; reads existing keyword file from outputs/ or
   runs fresh research; checks for competitor ad intelligence
   reports; produces keyword assignment table with competitor
   flags, one fully specified pillar page brief, 3-5 cluster
   piece briefs, and a content calendar recommendation

Note: SEO Content Brief runs standalone. It does not
automatically trigger Keyword Finder or Campaign Writer.
If no keyword file exists in outputs/, the skill runs fresh
research and notes this clearly in the output. If the brief
covers a topic where paid search is also planned, run the
Keyword Finder separately first and the SEO Content Brief
will pick up that file automatically.

### ABM ACCOUNT PRIORITISATION MODEL CHAIN

Triggered by: "prioritise accounts," "score accounts," "tier my
account list," "ABM prioritisation," "rank accounts," or any
mention of scoring or tiering a target account list.

When triggered, do NOT run the standard paid search chain (Skills
1-4 above). Instead:

Route directly to the ABM Account Prioritisation Model:
skills/abm_account_prioritisation/SKILL.md

Pass the full brief directly, including the account list if pasted
or the note that a CSV file has been dropped into
inputs/accounts_to_score.csv. The skill reads all context files
internally and detects the input format automatically.

The skill accepts pasted account lists or CSV files — either format
works. It reads icp.md, market.md, competitors.md, proof_points.md,
trigger_events.md, and buying_committee.md before scoring, and scans
outputs/ for prior Trigger Monitor and Competitor Ad Intelligence
reports to incorporate live intelligence into scores.

Skills that run:
1. ABM Account Prioritisation Model — reads context files and
   prior intelligence, scores each account across four criteria
   (ICP fit, buying readiness, revenue potential, relationship
   warmth), assigns tiers, displays full results before saving,
   and produces two output files: a prioritised account list with
   rationale and recommended next actions, and a Trigger Monitor
   feed file with tier assignments

Note: ABM Account Prioritisation Model runs standalone. It produces
tier assignments and ready-to-use orchestrator briefs for each
account. The Trigger Monitor reads the tier feed file to adjust
search depth per account — but runs correctly at full depth for
all accounts if no tier file is present. Tier data is optional
upstream context, not a dependency.

### A/B TEST TRACKER CHAIN

Triggered by: "A/B test," "test tracker," "what have we tested,"
"test history," "test patterns," "what should we test next,"
"testing log," or any mention of reviewing, logging, or
analysing test results.

When triggered, do NOT run the standard paid search chain (Skills
1-4 above). Instead:

Route directly to the A/B Test Tracker:
skills/ab_test_tracker/SKILL.md

Pass the full brief directly, including any manual test data the
user provides. The skill scans all outputs/ files automatically —
no files need to be specified. It detects whether a prior tracker
file exists and continues from accumulated history if one is found.

Skills that run:
1. A/B Test Tracker — reads context/icp.md and context/brand_voice.md,
   scans all relevant files in outputs/ (performance reports, copy files,
   variant score files, CRO briefs, email sequence files, LinkedIn strategy
   files, paid social audience files, and prior tracker files), accepts
   manual test entry, builds a complete test log organised by persona and
   segment, produces a pattern analysis, flags Variant Scorer calibration
   discrepancies, and produces a prioritised list of recommended next tests

Note: A/B Test Tracker runs standalone. It reads from outputs/ files
produced by other skills — it does not trigger any skill automatically.
Recommended next test briefs are provided in ready-to-use format that
the user can paste into the orchestrator as separate runs.

### WEBINAR AND EVENT CAMPAIGN BUILDER CHAIN

Triggered by: "webinar," "event campaign," "event promotion,"
"conference," "virtual event," "in-person event," or any mention
of a webinar or event alongside a campaign objective.

When triggered, do NOT run the standard paid search chain (Skills
1-4 above). Instead:

Route directly to the Webinar and Event Campaign Builder:
skills/webinar_event_campaign_builder/SKILL.md

Pass the full brief directly. The skill reads all context files
internally. It produces three phases of assets in one run:
pre-event promotion (registration page brief, email sequence,
LinkedIn organic posts, LinkedIn paid promotion brief), during-event
assets (chat prompts and poll questions for webinars; follow-up
capture brief for in-person events), and three post-event email
tracks routing contacts based on their behaviour.

Skills that run:
1. Webinar and Event Campaign Builder — reads icp.md, brand_voice.md,
   proof_points.md, market.md, and deep-dive files if available;
   produces all pre-event, during-event, and post-event assets plus
   a HubSpot workflow architecture summary for all three post-event tracks

Note: Webinar and Event Campaign Builder runs standalone. It produces
a complete event campaign package. Individual sections (registration
page brief, email sequences, LinkedIn posts, paid promotion brief)
can be extracted and used independently. It does not automatically
chain to Campaign Writer — if new paid social copy is needed for
promotion beyond the ad copy produced within this skill, run the
Paid Social Audience Builder separately.

### PAID SOCIAL AUDIENCE BUILDER CHAIN

Triggered by: "paid social," "Meta," "Facebook," "Instagram,"
"Reddit," "YouTube," "social audiences," "social advertising,"
or any mention of these channels alongside a campaign objective.

When triggered, do NOT run the standard paid search chain (Skills
1-4 above). Instead:

Route directly to the Paid Social Audience Builder:
skills/paid_social_audience_builder/SKILL.md

Pass the full brief directly. The skill reads all context files
internally. It produces three separate channel briefs in one run —
Meta, Reddit, and YouTube — each with platform-native targeting
logic.

If Campaign Writer copy files for Meta, Reddit, or YouTube formats
exist in outputs/, the skill maps those copy variants to the correct
audience and channel automatically. No additional step required.

Skills that run:
1. Paid Social Audience Builder — reads icp.md, brand_voice.md,
   competitors.md, market.md, and deep-dive files if available;
   produces cold and retargeting audience specs, campaign objective
   recommendations, bidding strategy, benchmarks, budget guidance,
   A/B testing recommendations, and a prerequisite checklist for
   each of Meta, Reddit, and YouTube; produces a cross-channel
   summary with launch sequence and copy mapping

Note: Paid Social Audience Builder runs standalone. It does not
automatically trigger Campaign Writer. If no copy exists in outputs/
for these channels, it flags this in the copy mapping section and
instructs the human to run Campaign Writer for the relevant formats
before launching.

### CRO BRIEF CHAIN

Triggered by: "CRO," "conversion rate,"
"landing page test," "A/B test the
landing page," "page is underperforming,"
"fix the landing page," or any reference
to conversion optimisation, landing page
performance, or A/B testing.

When triggered, route directly to the
CRO Brief:
skills/cro_brief/SKILL.md

Pass the full brief directly, including
any pasted copy, pasted HTML, or
description of the page. The CRO Brief
reads all context files and scans
outputs/ for matching ad copy and
Performance Grader reports internally.

Skills that run:
1. CRO Brief — reads context files,
   checks for matching ad copy and
   Performance Grader report in outputs/,
   evaluates page elements against ICP
   vocabulary and brand voice, runs
   message continuity check between ad
   and page, produces three prioritised
   tests with hypothesis, control,
   challenger copy, sample size
   calculation, and implementation notes

Note: CRO Brief runs standalone. It
produces a test plan the human shares
with their web team for implementation.
It does not automatically trigger other
skills, but its findings may point to
Campaign Writer (to fix ad copy that
is mismatched to the page) or Landing
Page Brief (to rebuild the page spec
from scratch if a full reframe is
warranted).

### EMAIL AND NURTURE CHAIN

Triggered when the brief contains any
of these signals: "email," "nurture,"
"sequence," "drip," "follow-up,"
"re-engagement," "ABM," "account-
based," or a specific company name
given as a target account.

When triggered, do NOT run the
standard paid search chain (Skills
1-4 above). Instead:

Route directly to the Email and
Nurture Sequencer:
skills/email_nurture_sequencer/SKILL.md

Pass the full brief directly. The
sequencer reads all context files
internally and determines what it
needs. The orchestrator does not
need to run Context Builder, Proof
Point Library, Keyword Finder, or
Campaign Writer first — the sequencer
handles all of this itself.

Note: If context files are missing
entirely, run the Context Builder
first (Skill 1 above), then pass
the brief to the sequencer. This
is the only pre-step required.

### BUDGET ALLOCATION MODEL CHAIN

Triggered by: "budget," "allocation,"
"how should I spend," "channel mix,"
"spend planning," "budget model," or
any mention of a dollar amount alongside
a campaign objective

When triggered, do NOT run the standard
paid search chain (Skills 1-4 above).
Instead:

Route directly to the Budget Allocation
Model:
skills/budget_allocation_model/SKILL.md

Skills that run:
1. Budget Allocation Model — reads
   context files and any available
   performance data, produces three
   scenarios with projections and a
   recommendation

Note: Budget Allocation Model runs
standalone. It produces a planning
document the human uses for stakeholder
conversations and campaign setup — it
does not automatically trigger other
skills.

### PERFORMANCE GRADER CHAIN

Triggered by: "performance report,"
"grade my campaign," "how is the
campaign performing," "review results,"
"weekly performance," or any reference
to performance data or campaign metrics

When triggered, do NOT run the
standard paid search chain (Skills
1-4 above). Instead:

Route directly to the Performance
Grader:
skills/performance_grader/SKILL.md

Skills that run:
1. Performance Grader — reads data
   file from outputs/performance/ or
   a pasted export, grades against
   benchmarks and strategy document
   predictions, flags underperforming
   elements, recommends next actions,
   and drafts proposed context file
   updates for human review

Note: Performance Grader runs
standalone. It produces recommended
next actions with specific skill briefs
that the human pastes into the
orchestrator as separate runs when
ready to act on the findings.

---

## Step 4 — Handle Failures

If any skill fails or produces an error
during the chain:

Do not stop the entire run if other skills
can still complete. Continue running
remaining skills where possible.

When the full chain has finished (or all
remaining skills have been attempted),
display a diagnostic block:

---
DIAGNOSTIC REPORT
─────────────────────────────────────────
Skills that completed successfully:
[list with one line each]

Skills that failed or were skipped
due to an error:
[list each with:]
- What it was trying to do
- What error or problem occurred
- Exact error message if available
- What to do next to resolve it

What to do next:
[Plain English instructions on how to
resolve each failure. Written so the
human can copy this diagnostic and
bring it to Claude.ai to get a fix
that can be pasted back into Claude Code.]
─────────────────────────────────────────
---

---

## Step 5 — Display The Run Summary

After all skills complete, display the
run summary first before showing any copy.

Format exactly like this:

---
CAMPAIGN ORCHESTRATOR — RUN COMPLETE
─────────────────────────────────────────
Brief: [the original plain English brief]

Interpreted as:
Format: [format]
Segment: [segment]
Persona: [persona]
Funnel stage: [stage]
Variants: [number]
Active company: [company name]

Skills that ran:
[✓ or ↩ or ✗] Context Builder
  [✓ = ran successfully]
  [↩ = skipped, reason in one line]
  [✗ = failed, see diagnostic]

[✓ or ↩ or ✗] Proof Point Library
  [filename created or "skipped"]

[✓ or ↩ or ✗] Keyword Finder
  [filename created or "skipped"]

[✓ or ↩ or ✗] Campaign Writer
  [filename created]

Files accessed this run:
[List every file read or created with
its full path]

Files created this run:
[List only new files written to disk]

Assumptions made:
[List any inferences made from an
ambiguous brief — what was assumed
and why]

[If any failures: "See diagnostic report
below for errors and recommended fixes"]
─────────────────────────────────────────
---

Display the run summary block first. Then
display the campaign writer output. Never
show copy variants before the run summary.

After the run summary, display the
campaign writer output in full —
all variants with annotations, best
for notes, and the skills suggestion
section.

Do not display the full keyword finder
output inline — it is saved to the file.
Instead show this after the run summary:

"Keyword file: [filename]
Top 5 keywords used in copy:
1. [keyword] — [score]/100
2. [keyword] — [score]/100
3. [keyword] — [score]/100
4. [keyword] — [score]/100
5. [keyword] — [score]/100
Full keyword research: [filename]"

---

## Step 6 — Confirm Before Saving

After displaying the run summary and copy
output, ask:

"Would you like to adjust anything before
saving the output files?

You can ask me to:
- Adjust tone up or down on any variant
- Swap a headline formula
- Rewrite a variant with a different angle
- Add a specific proof point
- Change the CTA
- Try a format I haven't written yet

Or type 'save all' and I will write all
output files using the naming convention
in CLAUDE.md."

Before saving any file, check outputs/ for
a file with the same base name. If one
exists, ask:
"A file with this name already exists. What
is the campaign theme for this run? I will
add it to the filename as:
[skill_type]_[format]_[theme]_[company]_[date].md
Theme should be 1-3 words describing the
angle — for example: switching_objection,
intel_case_study, vendor_tax."
Wait for the theme before writing any file.

Only save files after explicit confirmation.
Never save mid-chain without confirmation.

---

## Future Skills In This Chain

The following skills are not yet built but
will slot into this chain when ready.
Add them here when built:

Variant Scorer — runs after Campaign Writer,
before display. Scores each variant against
awareness level, pain point match, and brand
voice. Only variants scoring 70+ are shown
by default. Add between Skill 4 and Step 5
when built.

Landing Page Brief — runs after Campaign
Writer for paid search, LinkedIn, and
landing page format campaigns. Takes the
top keyword cluster and the ad copy
variants and produces a complete page
brief including message match map, above
the fold specification, proof point
hierarchy, objection handling map, form
field recommendations, thank you page
brief, and AEO notes. Also produces a
copy-ready content block with every word
on the page written out ready to paste
into HubSpot. Optionally generates a
styled HTML prototype on request.

To activate: add as Skill 5 in the chain
for paid search and landing page format
runs. After Campaign Writer completes,
ask: "Would you like me to also produce
a landing page brief for this campaign?
The brief will connect directly to the
ad variants just produced." Wait for
confirmation before running.

Ad Group Organiser — ACTIVE. Runs after
Campaign Writer for paid search campaigns.
Maps keywords to copy variants with match
types and negative keywords. Produces a
strategy document and a Google Ads Editor
CSV ready for direct import. Skill lives
at skills/ad_group_organiser/SKILL.md.
Offer is made automatically after Campaign
Writer completes for paid search format.

Email and Nurture Sequencer — ACTIVE.
Triggered by any email, nurture, sequence,
drip, follow-up, re-engagement, ABM, or
account-based brief. Handles four sequence
types (Nurture, Campaign, Re-engagement,
ABM) and produces fully written HubSpot-
ready emails with subject line variants,
preview text, persona reasoning, and
HubSpot workflow setup notes. Skill lives
at skills/email_nurture_sequencer/SKILL.md.
Routed directly from the orchestrator —
no prior skills required before it runs.

LinkedIn Campaign Organiser — ACTIVE.
Triggered by any LinkedIn, social,
sponsored content, LinkedIn ads, or
sponsored post brief. Maps copy variants
to a complete LinkedIn campaign structure
with phase-aware audience targeting,
format recommendations, bid strategy,
A/B testing plan, and budget allocation.
Produces one structured strategy document.
Skill lives at skills/linkedin_campaign_
organiser/SKILL.md. Offered automatically
after Campaign Writer completes for
LinkedIn format.

Trigger Monitor — ACTIVE. Triggered by any
reference to "trigger monitor," "weekly briefing,"
"account signals," "check accounts," "target
accounts," or a specific company name followed
by "trigger" or "signal." Reads context/target_
accounts.md, searches for buying signals at each
account using the trigger event definitions in
context/deep/trigger_events.md, and produces a
prioritized briefing with outreach briefs ready
to paste into the orchestrator. Runs standalone —
does not chain to other skills automatically.
Skill lives at skills/trigger_monitor/SKILL.md.

SEO Content Brief — ACTIVE. Triggered by any mention of SEO
brief, content brief, blog brief, pillar page, content cluster,
SEO content, organic content, or SEO strategy. Takes a topic
or keyword cluster and produces one pillar page brief plus
3-5 cluster piece briefs, each with target keyword, search
intent, title tag, meta description, H1, URL slug, section-
by-section content structure, internal linking map, AEO
question targets with exact phrasing, GEO citation signals,
and schema markup recommendations. Reads the existing keyword
file from outputs/ if available — runs fresh research if not.
Checks Competitor Ad Intelligence reports for keywords where
competitors are strong in both paid and organic — flags these
with a compete-or-pivot recommendation. Produces a content
calendar sequencing cluster pieces before the pillar. Runs
standalone — does not chain to other skills automatically.
Skill lives at skills/seo_content_brief/SKILL.md.

A/B Test Tracker — ACTIVE. Triggered by any mention of A/B test,
test tracker, what has been tested, test history, test patterns,
what to test next, or testing log. Scans all relevant files in
outputs/ automatically — performance reports, copy files, variant
score files, CRO briefs, email sequence files, LinkedIn strategy
files, and paid social audience files — and loads any prior tracker
file found to continue accumulated history. Accepts manual entry
for tests run but not recorded in outputs/ files. Produces a full
test log organised by persona and segment, a pattern analysis with
confidence ratings, a Variant Scorer calibration section flagging
prediction vs live result discrepancies, and a prioritised list of
up to five recommended next tests with ready-to-use orchestrator
briefs. Never updates context files automatically — surfaces findings
for human review only. Skill lives at
skills/ab_test_tracker/SKILL.md.

ABM Account Prioritisation Model — ACTIVE. Triggered by any mention
of prioritising accounts, scoring accounts, tiering an account list,
ABM prioritisation, or ranking target accounts. Accepts a pasted
account list or a CSV file dropped into inputs/accounts_to_score.csv
— detects format automatically. Scores each account 0–100 across
four criteria (ICP Fit, Buying Readiness, Revenue Potential,
Relationship Warmth), assigns each account to one of four tiers
(Strategic, Full ABM, Light ABM, Programmatic), and applies
relative tiering automatically if the absolute thresholds produce
a skewed distribution. Incorporates prior Trigger Monitor and
Competitor Ad Intelligence reports into Buying Readiness scores
when found in outputs/. Produces a prioritised account file with
scoring rationale and ready-to-use orchestrator briefs, and a
separate Trigger Monitor feed file that adjusts search depth per
account when present. The Trigger Monitor runs at full depth for
all accounts when no tier file exists — tier data is optional
context, not a dependency. Runs standalone — does not auto-chain
to other skills. Skill lives at
skills/abm_account_prioritisation/SKILL.md.

Webinar and Event Campaign Builder — ACTIVE. Triggered by any
mention of webinar, event campaign, event promotion, conference,
virtual event, in-person event, or a webinar or event alongside
a campaign objective. Produces all pre-event promotion assets
(registration page brief, 3-email pre-event sequence, 3 LinkedIn
organic posts, LinkedIn paid promotion brief), during-event assets
(chat prompts and poll questions for webinar; follow-up capture
brief and networking guide for in-person), and three post-event
email tracks (Track 1 Attendees — 3 emails over 10 days; Track 2
No-shows — 3 emails over 14 days; Track 3 Highly Engaged — 2
emails over 4 days accelerated to sales). Includes a HubSpot
workflow architecture summary for all three tracks with enrollment
triggers, branch logic, and suppression conditions. Runs standalone.
Skill lives at skills/webinar_event_campaign_builder/SKILL.md.

Paid Social Audience Builder — ACTIVE. Triggered by any mention
of paid social, Meta, Facebook, Instagram, Reddit, YouTube, social
audiences, or social advertising alongside a campaign objective.
Produces three separate channel briefs in one run — Meta, Reddit,
and YouTube — each with cold and retargeting audience specs,
campaign objective recommendation, bidding strategy, estimated
reach and CPM benchmarks, budget guidance, A/B testing
recommendations, and a prerequisite checklist. Connects to Campaign
Writer copy outputs automatically — maps existing copy variants to
the correct audience and channel if found in outputs/. Runs
standalone — does not chain to Campaign Writer automatically, but
flags missing copy and instructs the human to run it before launch.
Skill lives at skills/paid_social_audience_builder/SKILL.md.

CRO Brief — ACTIVE. Triggered by any mention
of CRO, conversion rate, landing page test, A/B
test, page underperforming, or fix the landing
page. Accepts pasted copy, pasted HTML, or a
plain English description of the page. Reads
context files, checks for matching ad copy in
outputs/ to run a message continuity check, and
connects to Performance Grader findings when
available. Produces three prioritised tests with
hypothesis, control, challenger copy, sample size
calculation, success metrics, and implementation
notes. Runs standalone — does not chain to other
skills automatically, but may point to Campaign
Writer or Landing Page Brief if the diagnosis
warrants it. Skill lives at
skills/cro_brief/SKILL.md.

Competitor Ad Intelligence — ACTIVE. Triggered
by any mention of competitor ads, ad intelligence,
competitive advertising, competitor brief, or a
request to see what a specific competitor is
running. Reads all competitors from
context/competitors.md and competitive_intel.md,
searches LinkedIn Ad Library, Google Ads
Transparency Center, and Meta Ad Library,
produces a competitive brief with gap analysis
and counter-angle recommendations anchored to
proof_points.md, and drafts proposed updates to
competitive_intel.md for human review. Runs
standalone weekly on Mondays alongside the
Trigger Monitor, or on demand. Skill lives at
skills/competitor_ad_intelligence/SKILL.md.

Budget Allocation Model — ACTIVE. Triggered
by any mention of budget, allocation, spend
planning, channel mix, or a dollar amount
alongside a campaign objective. Reads all
three core context files and any available
performance data in outputs/performance/.
Produces three scenarios — Conservative,
Recommended, and Aggressive — each with
channel split, funnel stage split, monthly
and quarterly projections, and a scenario
comparison table with a recommendation.
Projections use benchmarks unless real
performance data is found, in which case
actual CPMs, CPCs, and conversion rates
are used and flagged as such. Runs
standalone — does not chain to other
skills automatically. Skill lives at
skills/budget_allocation_model/SKILL.md.

Performance Grader — ACTIVE. Triggered by
any reference to performance data, campaign
results, grading, or weekly performance
review. Reads data exports from Google Ads,
LinkedIn Campaign Manager, or HubSpot.
Grades against B2B SaaS benchmarks and
against predictions in strategy documents.
Flags underperforming elements with
diagnoses and specific skill briefs for
next actions. Drafts proposed context file
updates for human review — never updates
automatically. Skill lives at
skills/performance_grader/SKILL.md.
Drop performance data exports into
outputs/performance/ for weekly mode.

Note: Skills that only produce output files
(proof points, persona intelligence, trigger
events) are handled automatically by the
general outputs scan in the Campaign Writer.
They do not need to be added to this chain
explicitly — the Campaign Writer finds their
output files automatically.

---

## Rules This Skill Must Always Follow

Never run a skill without showing the
pre-flight check first and receiving 'run'.

Never save any file without explicit
confirmation after the run completes.

Never ask the intake questions of individual
skills during a chain run — all brief
details are captured in Step 1 and passed
automatically.

Always show the run summary before any
copy output.

Always use the file naming convention
from CLAUDE.md for all files created.

Always read the active company name from
the first line of context/icp.md before
naming any output file.

If context files are missing entirely,
run the Context Builder before any other
skill regardless of the campaign format.

For paid search and landing page formats,
always check for a keyword file before
running the Campaign Writer — never skip
this check.

If the Keyword Finder needs to run fresh,
pass all brief details automatically —
do not interrupt the chain to ask questions.

Display progress updates between each step
but never show full intermediate output
until the chain is complete.

Write the diagnostic report in plain English
that can be copied and brought to Claude.ai
for a fix — never use technical jargon in
error messages.
