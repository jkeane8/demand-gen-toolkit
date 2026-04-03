Demand Gen Toolkit
A reusable demand generation system
built on Claude Code. Designed for
B2B SaaS companies. Takes company
intelligence as input and produces
campaign-ready outputs across paid
search, LinkedIn, email, and ABM —
from a single plain-English brief.

The Problem This Solves
Most demand gen work is repetitive,
time-consuming, and disconnected.
Keyword research lives in one tool.
Copy lives in another. Campaign
structure is assembled manually.
Email sequences are written from
scratch each time. None of it is
connected to a shared intelligence
layer about the buyer.
This toolkit connects all of it.

How It Works
Two layers
Engine — a set of skills that
never change. Each skill is a
structured instruction file that
tells Claude Code exactly how to
research, read, produce output
for a specific job. The skills are
company-agnostic.
Fuel — a set of context files
that are specific to the active
company. The context builder skill
researches a company and produces
11 files covering ICP, brand voice,
competitors, market, proof points,
voice of customer, persona depth,
objection depth, competitive
intelligence, buying committee,
trigger events, and market gaps.
Every skill reads from the context
files. Switching companies means
replacing the context files. The
skills never need to change.
One brief, full chain
You describe what you want in plain
English. The orchestrator reads the
brief, determines the channel, and
runs the right skill chain
automatically.
"Bottom funnel paid search for Head 
of Localization, switching objection 
angle, 3 variants"
The orchestrator runs keyword finder,
campaign writer, ad group organiser,
and offers a landing page brief —
all from that one sentence.

Skills
Campaign Orchestrator
Entry point. Reads a plain English
brief and routes to the correct skill
chain. Pre-flight check shows every
decision before execution. Waits for
confirmation before running.
Context Builder (v2)
Deep research skill producing 11 files:
4 core context files and 7 deep-dive
files. Sources: company website,
G2/Capterra reviews, LinkedIn job
postings, competitor sites, and industry
research. Depth prioritization: voice
of customer, persona depth, objection
depth, and competitive intelligence
at maximum depth. Buying committee,
trigger events, and market gaps at
standard depth.
Campaign Writer
Generates individual copy units across
formats. Applies Direct Response craft
frameworks: Schwartz awareness levels,
pain quantification, So What chain,
headline formulas. Every variant is
annotated with formula, awareness
level, lead pain point, angle, and
best-for notes. Reads all 11 context
files. Avoids AI tells.
Keyword Finder
Produces scored keyword lists for paid
search and SEO. Scores each keyword
0-100 across four criteria: ICP
vocabulary match, intent fit,
winnability, and strategic value.
Groups by intent cluster with negative
keyword recommendations. Staleness
Check: reuses files under 6 weeks old.
Landing Page Brief
Complete page specification, including
message match map per ad variant,
above-the-fold spec, proof point
hierarchy with placement rationale,
objection handling map with exact
copy, form field recommendations,
thank you page brief, and AEO
structure notes. Optionally generates
a styled HTML prototype.
Ad Group Organiser
Maps keyword files and copy variants
into Google Ads campaign structure.
Produces a strategy document with
match type recommendations and
reasoning, negative keyword checklists
(required not optional), Quality Score
predictions, A/B testing plan, budget
allocation, and phased launch sequence.
Also produces a Google Ads Editor CSV
ready for import.
Email and Nurture Sequencer
Handles four email types: nurture,
campaign, re-engagement, and ABM.
Produces a sequence map first and
waits for approval before writing.
Every email includes subject line
variants with testing hypotheses,
preview text, full body copy, CTA,
send timing, HubSpot workflow notes,
and persona reasoning. Closing move
logic: Permission to Close, One
Specific Thing, Hard CTA, Sales
Handoff, or Different Angle —
selected based on sequence type,
funnel stage, and prior email
engagement.
LinkedIn Campaign Organiser
Phase-aware campaign structure covering
awareness, retargeting, and ABM phases.
For each phase: audience targeting
spec with job title inclusions and
exclusions, company size, industry,
geographic targeting, and estimated
audience size. Format recommendation
with reasoning (single image, carousel,
video, document, lead gen form). Bid
strategy by phase objective. A/B
testing plan with one variable at a
time. Prerequisite checklist before
launch.
Trigger Monitor
Scans target accounts for buying
signals defined in the trigger events
file. Five searches per account per
run. Signals rated Hot (act within
48 hours), Warm (act within 2 weeks),
or Monitor. For every Hot signal:
verify source, why it matters,
persona to target first, outreach
angle, suggested copy hook, and
a ready-to-use orchestrator brief.
Updates target_accounts.md with
accumulated trigger history after
every run.

Context Files
The context layer is what makes
every skill produce company-specific,
buyer-accurate output rather than
generic content.
Templates showing the structure of
each file — with explanations of
what goes in each field — are in
context/example/.
Core files (4)

icp.md — buyer personas, segments,
pain points, trigger events,
objection summaries, and buyer
vocabulary
brand_voice.md — tone scale by
segment, vocabulary to use and avoid,
example sentences
competitors.md — competitor
analysis, ownable positioning angles,
competitive battlecard summaries
market.md — market category, size
estimates, trends, opportunities, threats

Deep-dive files (7, in context/deep/)

voice_of_customer.md — exact buyer
quotes, competitor criticisms,
copy-ready phrases, job description
intelligence
persona_dep-the-life,
information diet, career anxieties,
buying role for each persona
objection_depth.md — surface
objection, real fear, winning response,
what backfires, copy implications
for each major objection
competitive_intel.md — deep analysis
with G2 evidence, churn signals,
marketing weaknesses, win strategies
buying_committee.md — all roles
involved, 6-stage buying process,
deal stall points
trigger_events.md — 4 trigger types
with search behavior, content needs,
outreach angles, monitoring signals
market_gaps.md — unclaimed
positioning, keyword white space,
underserved segments, emerging
opportunities


Skill Chain by Channel
Paid search:
Brief → Orchestrator → Keyword Finder 
→ Campaign Writer → Ad Group Organiser 
→ Landing Page Brief

LinkedIn:
Brief → Orchestrator → Campaign Writer 
→ LinkedIn Campaign Organiser

Email / Nurture:
Brief → Orchestrator → Email and 
Nurture Sequencer

ABM:
Trigger Monitor → Orchestrator → 
Email Nurture Sequencer (ABM type) 
+ LinkedIn Cate from one 
orchestrator brief.

Architecture Decisions
Why SKILL.md files rather than
Python scripts?
Skills are instruction files, not
code. Claude Code reads them and
reasons about how to apply them to
the current context. This means skills
can handle ambiguity, make judgment
calls, and produce outputs that are
tailored to the specific brief —
something a rigid script cannot do.
Why separate engine and fuel layers?
Portability. The skills are built
once and work for any company. The
context files are the only thing that
changes when switching companies.
This means the system compounds in
value — every improvement to a skill
immediately benefits every company
it's used for.
Why a context builder skill rather
than manual research?
The context builder produces 11
structured files from a single run.
It researches sources that take hours
to cover manually: G2 and Capterra
reviews, LinkedIn job postings,
competitor positioning, industry
research, and analyst reports. The
output is structured in a format that
other skills can read directly. Manual
research produces unstructured notes
that don't feed downstream tools.
Why does the orchestrator show a
pre-flight check before running?
Transparency and control. The pre-
flight check shows every decision the
orchestrator made from the brief —
format, segment, persona, funnel stage,
skills that will run, files that will
be created. You can correct anything
before it runs. Nothing executes
without explicit confirmation.

No external APIs, no databases,
no infrastructure. The entire system
runs locally from a single project
folder.
