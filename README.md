# Demand Gen Toolkit

A reusable demand generation system built on Claude Code. Designed for B2B SaaS
companies. Takes company intelligence as input and produces campaign-ready outputs
across paid search, LinkedIn, email, and ABM — from a single plain-English brief.

Built by John Keane as a portfolio project demonstrating systems-level thinking
in demand generation.

---

## The Problem This Solves

Most demand gen work is repetitive, time-consuming, and disconnected. Keyword
research lives in one tool. Copy lives in another. Campaign structure is assembled
manually. Email sequences are written from scratch every time. None of it is
connected to a shared intelligence layer about the buyer — so the same research
gets redone, the same context gets lost, and each campaign starts from the same
baseline.

This toolkit connects all of it. Company intelligence is researched once and
stored in structured context files. Every skill reads from those files. Output
compounds — each campaign builds on everything that came before it.

---

## How It Works

### Two layers

**Engine** — a set of skills that never change. Each skill is a structured
instruction file that tells Claude exactly how to research, reason, and produce
output for a specific job. The skills are company-agnostic. They work the same
way regardless of which company's context files are loaded.

**Fuel** — a set of context files specific to the active company. The Context
Builder skill researches a company and produces 11 files covering ICP, brand
voice, competitors, market, proof points, voice of customer, persona depth,
objection depth, competitive intelligence, buying committee, trigger events, and
market gaps. Switching companies means replacing the context files. The skills
never need to change.

### One brief, full chain

You describe what you want in plain English. The Campaign Orchestrator reads the
brief, identifies the channel, segment, persona, and funnel stage, and routes to
the correct skill chain automatically.

Example brief: "Bottom funnel paid search for Head of Localization, switching
objection angle, 3 variants"

The orchestrator runs Keyword Finder, Campaign Writer, Variant Scorer, and Ad
Group Organiser — and offers a Landing Page Brief — all from that one sentence.

---

## Skills

### Campaign Orchestrator

Entry point for the entire system. Reads a plain-English brief and routes to the
correct skill chain. Displays a pre-flight check showing every decision it made
from the brief — format, segment, persona, funnel stage, skills to run, and files
to create — and waits for explicit confirmation before running anything. Handles
Google Ads, LinkedIn, email, ABM, and performance review chains.

### Context Builder (v2)

Deep research skill that produces 11 structured context files from a single run.
Sources covered: company website, G2 and Capterra reviews, LinkedIn job postings,
competitor sites, and industry research. Produces 4 core files and 7 deep-dive
files. Depth prioritisation: voice of customer, persona depth, objection depth,
and competitive intelligence at maximum depth; buying committee, trigger events,
and market gaps at standard depth. Displays a research plan and progress updates
before and during the run.

### Campaign Writer

Generates copy variants across paid search, LinkedIn, email, and landing page
formats. Applies direct response craft frameworks: Schwartz awareness levels,
pain quantification, So What chain, and headline formulas. Every variant is
annotated with formula used, awareness level, lead pain point, angle, and
best-for notes. Reads all 11 context files before writing. Scans explicitly for
AI tells and brand voice violations.

Phase-aware for LinkedIn: automatically detects whether the brief calls for Phase
1 Awareness, Phase 2 Retargeting, or Phase 3 ABM, and applies different copy
rules for each phase. Phase 1 holds product references and hard metrics; Phase 2
introduces named proof points; Phase 3 uses peer story framing matched to the
named account's industry and trigger event.

### Keyword Finder

Produces scored keyword lists for paid search. Scores each keyword 0–100 across
four criteria: ICP vocabulary match, intent and funnel fit, winnability, and
strategic value. Groups keywords by intent cluster with negative keyword
recommendations for each group. Includes a staleness check — reuses existing
keyword files under 6 weeks old rather than re-running unnecessarily.

### Landing Page Brief

Complete page specification that creates message continuity from ad click to
conversion. Covers: message match map per ad variant, above-the-fold spec, proof
point hierarchy with placement rationale, objection handling map with exact copy,
form field recommendations, thank you page brief, and AEO structure notes.
Optionally generates a styled HTML prototype for stakeholder review.

### Ad Group Organiser

Maps keyword files and copy variants into a Google Ads campaign structure ready
for launch. Produces a strategy document covering match type recommendations with
reasoning, negative keyword checklists, Quality Score predictions, A/B testing
plan, budget allocation, and phased launch sequence. Also produces a Google Ads
Editor CSV ready for direct import — no manual data entry required.

### Email and Nurture Sequencer

Handles four email sequence types: nurture, campaign, re-engagement, and ABM.
Produces a sequence map for approval before writing any copy. Every email includes
subject line variants with testing hypotheses, preview text, full body copy, CTA,
send timing, HubSpot workflow configuration notes, and persona reasoning.

Closing move logic selects from five options — Permission to Close, One Specific
Thing, Hard CTA, Sales Handoff, or Different Angle — based on sequence type,
funnel stage, and prior email engagement pattern.

### LinkedIn Campaign Organiser

Phase-aware campaign structure for LinkedIn Sponsored Content. Covers awareness,
retargeting, and ABM phases. For each phase: audience targeting spec with job
title inclusions and exclusions, company size, industry, geographic targeting, and
estimated audience size. Format recommendation with reasoning. Bid strategy by
phase objective. A/B testing plan with one variable at a time. Prerequisite
checklist before launch to confirm creative assets, URLs, and tracking are in place.

### Trigger Monitor

Scans named target accounts for buying signals defined in the trigger events
context file. Runs five searches per account per run. Signals are rated Hot (act
within 48 hours), Warm (act within 2 weeks), or Monitor. For every Hot signal:
verified source, why it matters, which persona to target first, outreach angle,
suggested copy hook, and a ready-to-use orchestrator brief. Updates
target_accounts.md with accumulated trigger history after every run.

### Variant Scorer

Quality gate between Campaign Writer and paid media launch. Evaluates every copy
variant independently across four criteria: Awareness Level Match (30 points),
Pain Point Accuracy (25 points), Brand Voice Compliance (25 points), and CTA
Appropriateness (20 points). Ranks variants and provides a launch recommendation.

For every issue found — whether Critical, Moderate, or Minor — provides a drop-in
rewrite of the specific phrase or sentence, not a full variant rewrite. Catches
unverified statistics, LinkedIn phase rule violations, and brand voice errors
before they reach paid media spend. Runs automatically after Campaign Writer or
on demand against any copy file in outputs/.

### Performance Grader

Reads campaign performance data exported from Google Ads, LinkedIn Campaign
Manager, or HubSpot and grades results against two standards simultaneously:
industry benchmarks for the channel and audience type, and predictions made in
strategy documents produced by the toolkit.

Detects platform and available metrics dynamically — works with any CSV export.
For every underperforming element: provides a specific diagnosis that connects
performance to a hypothesis about message-market fit, targeting, or copy angle
— not just a report of the numbers. Recommends a next action with an exact skill
brief to run. Drafts proposed context file updates for human review. Never updates
context files automatically.

Runs in weekly mode (reads the most recently modified file in outputs/performance/)
or on demand against any file or pasted data.

### Budget Allocation Model

Takes a campaign objective and total budget and produces three allocation
scenarios — Conservative, Recommended, and Aggressive — each showing how to
split budget across channels and funnel stages with projected outcomes. Produces
both monthly and quarterly views.

Projections use benchmark CPMs, CPCs, and conversion rates unless historical
performance data exists in outputs/performance/ — in which case real numbers
replace benchmarks and are flagged as such. Includes a scenario comparison table
and a recommendation connecting the allocation to the specific ICP, objective,
and competitive context loaded in the context files.

### Competitor Ad Intelligence

Monitors competitor advertising activity across LinkedIn, Google Ads, and Meta using
publicly available ad libraries and transparency tools. Runs weekly on Mondays
alongside the Trigger Monitor, or on demand against specific competitors.

Produces a brief covering active ads found across all three platforms, historical
patterns showing what competitors run consistently across multiple weeks, spend signals
indicating where each competitor is investing most, a gap analysis identifying angles
no competitor is covering, and counter-angle recommendations anchored to the active
company's named proof points. Drafts proposed updates to competitive_intel.md for
human review — never updates context files automatically.

### Paid Social Audience Builder

Produces full channel setup specifications for Meta, Reddit, and
YouTube from a single brief. For each channel: cold audience specs,
retargeting audience specs, campaign objective, bidding strategy,
estimated reach and CPM benchmarks, budget guidance, A/B testing
recommendations, and a prerequisite checklist. Each channel uses
platform-native targeting logic.

Meta uses interest stacks, lookalike audiences, and behavioral
targeting. Interest stacks are derived from the persona's actual
information diet in icp.md and persona_depth.md — not from generic
assumptions. Lookalike audiences are built from customer lists,
Pixel visitors, or lead form completions in priority order.
Competitor interest targeting is included where available.

Reddit uses subreddit targeting, interest categories, and keyword
targeting with practitioner-voice creative direction. Subreddits
are selected based on where the persona actually spends time online.
Includes detailed creative direction — Reddit is the channel most
sensitive to tone mismatch and the brief covers what works, what
kills Reddit ads, and the required formality level per segment.

YouTube uses custom intent keywords, topic targeting, and in-market
audiences. Custom intent keywords reflect the persona's research and
learning behavior on YouTube — not their transactional search
queries. Placement targeting against specific YouTube channels is
included when persona_depth.md identifies channels the persona
watches.

Connects to Campaign Writer copy outputs — maps existing copy
variants to the correct audience and channel in the cross-channel
summary. Produces a launch sequence recommendation identifying which
channel to start with, when to expand, and how retargeting pools
should build across channels over time.

### SEO Content Brief

Produces a complete SEO content brief covering a pillar page plus
3-5 cluster pieces from a single topic input. Each brief includes
target keyword, search intent, recommended structure, title tag,
meta description, H1, URL slug, internal linking map, AEO question
targets with exact phrasing, GEO citation signals, and schema
markup recommendations.

AEO (Answer Engine Optimisation) and GEO (Generative Engine
Optimisation) are first-class outputs in every brief — not
afterthoughts. AEO question targets are derived from ICP vocabulary
and voice-of-customer phrases, not generic topic assumptions. GEO
citation signals identify the named customer evidence, original
data, expert attribution, and specific statistics that make content
citeable by AI systems.

Reads the existing keyword file from outputs/ if available — runs
fresh keyword research if not, and notes clearly which source was
used. Checks Competitor Ad Intelligence reports for keywords where
competitors are strong in both paid and organic — flags these with
a compete-or-pivot recommendation covering three options: compete
with a differentiation angle, pivot to an adjacent keyword, or
split the strategy across the pillar and a cluster piece.

Content calendar sequencing is included — cluster pieces are always
scheduled before the pillar page so the internal linking structure
is live at launch. Total estimated writing time is calculated from
the word counts across all pieces.

### Webinar and Event Campaign Builder

Produces every asset needed to promote, run, and follow up on a
webinar or in-person event from a single brief. Detects event type
automatically — webinar or in-person — and adjusts during-event
assets accordingly.

Pre-event assets: a full registration page brief (three headline
options, what-you-will-learn bullets, speaker framing, social proof
element, form field recommendations, thank you page brief), a 3-email
pre-event sequence (confirmation, anticipation, day-before reminder),
three LinkedIn organic posts (problem framing, peer proof, day-before
urgency), and a LinkedIn paid promotion brief with audience targeting,
estimated audience size warning, two ad copy options, bid strategy,
and budget guidance.

During-event assets for webinar: opening poll question, mid-event
chat prompt, closing CTA slide brief, and post-event chat message.
During-event assets for in-person: a follow-up capture brief with
qualifier questions, high-engagement signal definitions, and a
networking conversation guide derived from persona_depth.md.

Three post-event email tracks, fully written:
Track 1 — Attendees (3 emails over 10 days): thank and deliver the
resource, deepen value with an actionable takeaway, then make a
direct ask matched to funnel stage.
Track 2 — No-shows (3 emails over 14 days): deliver the recording
without referencing the missed event, re-engage on a pain or proof
angle, then a low-pressure final email.
Track 3 — Highly Engaged (2 emails over 4 days): same-day high-
urgency follow-up referencing the specific signal that flagged this
contact, then a direct ask — suppressed if the contact replies.
Track 3 always includes a human review flag before Email 2 sends.

HubSpot workflow architecture for all three tracks: enrollment
triggers, branch logic (reply detection, meeting booking,
unsubscribe suppression), competitor domain suppression, and
post-sequence routing instructions.

### CRO Brief

Takes a landing page — provided as pasted copy, pasted HTML, or a description —
and produces a prioritised test plan with three tests ranked by expected conversion
impact. Checks message continuity between the ad that sent traffic and the landing
page before evaluating any individual element. Connects to Performance Grader
findings when available, using the grader's diagnosis as the starting hypothesis.

For each test: hypothesis, control, challenger copy written in full, minimum sample
size calculation, success metrics, and implementation notes specifying which tool
to use and what not to change while the test runs. Stays close to existing copy
unless the diagnosis shows a full reframe is needed — and states explicitly why
when it does.

---

## Context Files

The context layer is what makes every skill produce company-specific,
buyer-accurate output rather than generic content. All 11 files are read by the
skills that need them. Templates showing the required structure for each file are
in context/example/.

### Core files (4)

- **icp.md** — buyer personas, segments, pain points, trigger events, objection
  summaries, and the exact vocabulary buyers use to describe their problems
- **brand_voice.md** — tone scale by segment, vocabulary to use and avoid, and
  calibration sentences showing what on-brand and off-brand copy look like
- **competitors.md** — competitor analysis, ownable positioning angles, and
  competitive battlecard summaries by competitor
- **market.md** — market category, size estimates, trends, opportunities, and
  threats relevant to the active company

### Deep-dive files (7, in context/deep/)

- **voice_of_customer.md** — exact buyer quotes, competitor criticisms sourced
  from review sites, copy-ready phrases, and job description intelligence
- **persona_depth.md** — day-in-the-life, information diet, career anxieties,
  and buying role for each priority persona
- **objection_depth.md** — surface objection, real underlying fear, winning
  response, what backfires, and copy implications for each major objection
- **competitive_intel.md** — deep competitor analysis with G2 review evidence,
  churn signals, marketing weaknesses, and win strategies
- **buying_committee.md** — all roles involved in a purchase decision, the
  full buying process with stage durations, and deal stall points
- **trigger_events.md** — four trigger event types with search behaviour,
  content needs, outreach angles, and monitoring signals for each
- **market_gaps.md** — unclaimed positioning angles, keyword white space,
  underserved segments, and emerging opportunities

---

## Skill Chain by Channel

**Paid search:**
Brief → Orchestrator → Keyword Finder → Campaign Writer → Variant Scorer
→ Ad Group Organiser → Landing Page Brief

**LinkedIn:**
Brief → Orchestrator → Campaign Writer → Variant Scorer
→ LinkedIn Campaign Organiser

**Email / Nurture:**
Brief → Orchestrator → Email and Nurture Sequencer

**ABM:**
Trigger Monitor → Orchestrator → Email and Nurture Sequencer (ABM type)
+ LinkedIn Campaign Organiser (Phase 3)

**Paid social:**
Brief → Orchestrator → Paid Social Audience Builder (Meta + Reddit + YouTube)
→ [Campaign Writer for channel-specific copy if not already in outputs/]

**SEO / organic content:**
Brief → Orchestrator → SEO Content Brief (pillar + cluster briefs with AEO and GEO)
→ [Keyword Finder if no keyword file exists in outputs/]

**Webinar / event:**
Brief → Orchestrator → Webinar and Event Campaign Builder (pre-event + during-event
+ three post-event tracks + HubSpot workflow architecture)

**Performance loop:**
Performance Grader → diagnoses results → recommends exact skill to run
→ drafts context file updates for review → next campaign starts with
updated intelligence

All channels route from a single orchestrator brief.

---

## Architecture Decisions

**Why SKILL.md files rather than Python scripts?**
Skills are instruction files, not code. Claude Code reads them and reasons about
how to apply them to the current context. This means skills can handle ambiguity,
make judgment calls, and produce outputs that are tailored to the specific brief
— something a rigid script cannot do. Skills can also be read, understood, and
modified by anyone without a development background.

**Why separate engine and fuel layers?**
Portability. The skills are built once and work for any company. The context
files are the only thing that changes when switching companies. Every improvement
made to a skill immediately benefits every future company it is used for. The
system compounds in value rather than requiring rebuilds for each client.

**Why a Context Builder rather than manual research?**
The Context Builder produces 11 structured files from a single run, covering
sources that take hours to work through manually — G2 and Capterra reviews,
LinkedIn job postings, competitor positioning, and industry research. The output
is in a format every downstream skill can read directly. Manual research produces
unstructured notes that do not feed into any tool consistently.

**Why does the Orchestrator show a pre-flight check before running?**
Transparency and control. The pre-flight check displays every decision the
orchestrator made from the brief — format, segment, persona, funnel stage, skills
that will run, and files that will be created. You can correct any of these before
execution. Nothing runs without explicit confirmation, which means any
misinterpretation of the brief is caught before work begins rather than after.

**Why a Variant Scorer before launch?**
Quality gate. Copy that looks strong in isolation can violate LinkedIn phase
rules, use statistics not present in any context file, or mismatch the funnel
stage of the audience. The Variant Scorer catches these issues before paid media
spend — not after. Every flagged issue comes with a drop-in rewrite, so fixing
it does not require a full rewrite cycle.

**Why a Performance Grader rather than reviewing data manually?**
The system gets smarter over time. The Performance Grader connects real campaign
results back to the context files that every future campaign reads. A proof point
that underperforms in paid media gets noted. A persona that converts at a higher
rate than expected gets flagged. Each campaign makes the next one more accurate
— the intelligence layer compounds rather than resetting with each new campaign.

---

## Built With

- Claude Code (Anthropic)
- Cursor (file viewing and terminal)

No external APIs, no databases, no infrastructure. The entire system runs locally
from a single project folder.

---

## Contact

John Keane
https://www.linkedin.com/in/john-d-keane/
