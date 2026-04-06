[README.md](https://github.com/user-attachments/files/26522600/README.md)
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
- Claude Pro subscription
- Cursor (file viewing and terminal)

No external APIs, no databases, no infrastructure. The entire system runs locally
from a single project folder.

---

## Contact

John Keane
https://www.linkedin.com/in/john-d-keane/
