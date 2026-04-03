Demand Gen Toolkit
Built by John Keane
Claude Code project configuration

About This Project
A reusademand generation system
built on Claude Code. Takes company
intelligence as input and produces
campaign-ready outputs across paid
search, LinkedIn, email, and ABM.
Designed to be company-agnostic.
Swap the context files for a new
company and every skill runs without
modification.

How Claude Should Behave
Skill level: Intermediate Claude Code
user. Explain what you are doing and
why, but do not over-explain basics.
When running skills: always show a
pre-flight check before executing.
Always confirm before saving files.
Never save without explicit confirmation.
When building new skills: follow the
existing SKILL.md structure and naming
conventions exactly.

Project Structure
skills/          — permanent, portable
                   one folder per skill
                   each contains SKILL.md

context/         — active company
                   replace when switching
                   companies

context/deep/    — deep-dive research
                   produced by context
                   builder 
context/example/ — templates showing
                   what goes in each file
                   company-agnostic

contexts/        — archived company
                   context folders

outputs/         — campaign outputs
                   one file per run
                   named by convention

engine/          — utility scripts
                   (future)

File Naming Convention
Format:
[skill_type][format][theme]_
[company]_[YYYY-MM-DD].md
Skill type prefixes:

keywords_
copy_
landing_page_
ad_group_strategy_
ad_group_import_
email_
linkedin_strategy_
trigger_briefing_
performance_

Theme: optional 1-3 word descriptor
when multiple same-day runs would
produce identical filenames.

Skills in This Toolkit
Campaign Orchestrator
Entry point for all campaigns. Reads
a plain English brief and routes to
the correct skill chain automatically.
Context Builder (v2)
Deep research skill. Produces 11 files:
4 core context files and 7 deep-dive
files in context/deep/. Researches
company website, G2/Capterrs,
LinkedIn job postings, competitor sites,
and industry sources.
Campaign Writer
Generates individual copy units across
formats: Google ads, LinkedIn ads, cold
email, landing page headlines, webinar
promo, Meta ads, Reddit posts. Applies
Direct Response craft frameworks. Reads
all context and deep-dive files. Produces
annotated output with formula, awareness
level, angle, and best-for notes per
variant.
Keyword Finder
Produces scored keyword lists for paid
search. Scores each keyword 0-100 across
4 criteria: ICP vocabulary match, intent
fit, winnability, strategic value. Groups
by intent cluster. Includes negative
keyword recommendations.
Landing Page Brief
Strategic landing page specification.
Produces message match map, above-the-
fold spec, proof point hierarchy,
objection handling map, form field
recommendations, thank you page brief,
and AEO structure notes. Optionally
generates HTML prototype.
Ad Group Organiser
Maps keyword file and copy variants
into Google Ads campaign structure.
Produces strategy document and Google
Ads Editor CSV. Assigns match types,
negative keywords, bid priority,
Quality Score predictions, and A/B
testing recommendations per group.
Email and Nurture Sequencer
Designs and writes complete email
sequences across four types: nurture,
campaign, re-engagement, and ABM.
Produces sequence map first, waits
for approval, then writes all emails
in full. Includes subject line variants,
preview text, HubSpot workflow notes,
and persona reasoning per email.
LinkedIn Campaign Organiser
Maps copy variants to LinkedIn campaign
structure with phase-aware targeting.
Covers awareness, retargeting, and ABM
phases. Produces audience targeting
specs with job title inclusions and
exclusions, format recommendations with
reasoning, bid strategy by phase, A/B
testing plan, and prerequisite checklist.
Trigger Monitor
Scans target accounts for buying signals
defined in trigger_events.md. Runs
scheduled or on demand. Produces
prioritized briefing with Hot/Warm
signal tiers, signal descriptions with
verified sources, outreach intelligence,
and ready-to-use orchestrator briefs
for every Hot signal. Updates
target_accounts.md with accumulated
trigger history after every run.

Two-Layer Architecture
Engine layer (skills/) — permanent
and portable. Skills never reference
specific companies. They read from
context files.
Fuel layer (context/) — company-
specific. Replace when switching
companies. Skills automatically use
whatever is in context/.
Switching companies:

Archive context/ to contexts/[company]/
Clear outputs/
Run context builder for new company
Everything else runs automatically


Skill Chain by Channel
Paid search:
Context Builder → Keyword Finder →
Campaign Writer → Ad Group Organiser →
Landing Page Brief
LinkedIn:
Context Builder → Campaign Writer →
LinkedIn Campaign Organiser
Email / Nurture:
Context Builder → Email and Nurture
Sequencer
ABM:
Trigger Monitor → Email and Nurture
Sequencer (ABM type) → LinkedIn
Campaign Organiser (parallel)
All channels:
Campaign Orchestrator rees automatically.
