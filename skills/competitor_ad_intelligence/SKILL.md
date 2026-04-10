# Competitor Ad Intelligence
## Monitors competitor advertising across LinkedIn,
## Google Ads, and Meta using publicly available
## ad libraries and transparency tools.
## Produces a weekly competitive brief covering
## active ads, historical patterns, spend signals,
## gap analysis, and counter-angle recommendations.

---

## What This Skill Does

Reads all competitors from context/competitors.md
and context/deep/competitive_intel.md. Searches
the LinkedIn Ad Library, Google Ads Transparency
Center, and Meta Ad Library for each competitor.
Produces a structured brief covering:

- Active ads currently running across all three
  platforms
- Historical patterns showing what competitors
  run consistently across multiple periods
- Spend signals indicating where each competitor
  is investing most heavily
- Gaps showing angles no competitor is covering
- Counter-angle drafts connecting each gap to
  Lilt's ICP and named proof points

Runs weekly on Mondays alongside the Trigger
Monitor. Drafts proposed updates to
competitive_intel.md for human review — never
updates context files automatically.

This is a Tier 1 skill — data retrieval uses
web search only. When upgrading to Tier 2,
replace the search queries in Step 2 with direct
MCP web fetching of the ad library URLs. All
other sections remain identical.

---

## Step 1 — Read Before Searching

Read all of these files before running any search.
What you find in the search phase is only meaningful
when compared against what you already know about
each competitor's stated positioning and Lilt's
own strengths.

**Required files:**

context/competitors.md
Read for: the full list of competitors to monitor,
their stated positioning, their claimed
differentiators, and the messaging angles they
already own. This is the baseline. Every search
finding is compared against this file to identify
what is new, what has changed, and what gaps exist.

context/icp.md
Read for: buyer personas, segments, pain points,
and the exact vocabulary buyers use to describe
their problems. Used to evaluate whether competitor
ads are targeting the same personas as Lilt and
whether their copy is speaking to the same pain
points.

**Optional files — check and use if found:**

context/deep/competitive_intel.md
If found: read for deep prior analysis of each
competitor including G2 review evidence, churn
signals, and any ad intelligence gathered on
previous runs. Use as the historical baseline.
Flag anything found in this run that contradicts
or updates prior findings.

context/proof_points.md
If found: read for Lilt's named customer results.
Used when drafting counter-angles — every
counter-angle must be anchored to a specific
named proof point from this file. Do not draft
counter-angles without proof point support.

context/deep/market_gaps.md
If found: read for positioning gaps and keyword
white space already identified. Cross-reference
against this run's findings — if a gap from
market_gaps.md is now being filled by a competitor,
flag it as URGENT.

Display this before searching:

---
COMPETITOR AD INTELLIGENCE
─────────────────────────────────────
Run date: [today's date]
Mode: [Weekly / On demand]
Platforms searched: LinkedIn Ad Library,
  Google Ads Transparency Center,
  Meta Ad Library
Context files loaded:
[✓/✗] context/competitors.md
[✓/✗] context/deep/competitive_intel.md
[✓/✗] context/icp.md
[✓/✗] context/proof_points.md
[✓/✗] context/deep/market_gaps.md
Prior competitive intel found:
[Yes — competitive_intel.md loaded as
  baseline / No — first run]
Competitors to monitor: [list names
  from competitors.md]
Searching now.
─────────────────────────────────────
---

---

## Step 2 — Search Each Competitor

For each competitor in context/competitors.md run
all five searches below in order. Complete all
five searches for one competitor before moving
to the next.

**Search 1 — LinkedIn Ad Library:**
Primary query: "[competitor name] LinkedIn ad library"
Also search:
- "[competitor name] LinkedIn sponsored content 2026"
- "[competitor name] LinkedIn ads localization 2026"
Purpose: Find active LinkedIn sponsored content.
Identify target personas from copy language, job
titles mentioned, and pain points referenced.

**Search 2 — Google Ads Transparency Center:**
Primary query: "[competitor name] Google ads transparency center"
Also search:
- "[competitor name] paid search ads translation management 2026"
- "[competitor name] TMS Google ads copy"
Purpose: Find active search ads. Identify keywords
being targeted, headline formulas in use, and
copy angles running in paid search.

**Search 3 — Meta Ad Library:**
Primary query: "[competitor name] Meta ad library active ads"
Also search:
- "[competitor name] Facebook ads localization 2026"
Purpose: Find active Meta ads. Identify audience
targeting signals and creative angles being tested
on social.

**Search 4 — Spend and activity signals:**
Queries:
- "[competitor name] advertising spend 2025 2026"
- "[competitor name] marketing investment localization"
- "[competitor name] new campaign launch 2026"
Purpose: Surface public signals about advertising
investment levels, new campaign launches, or
marketing strategy shifts.

**Search 5 — Recent messaging changes:**
Queries:
- "[competitor name] new positioning 2026"
- "[competitor name] rebrand campaign 2026"
- "[competitor name] product launch marketing 2026"
Purpose: Identify any recent messaging pivots,
new product marketing angles, or positioning
changes not yet reflected in competitive_intel.md.

After completing all five searches for a competitor,
display a search log before moving to the next:

---
[Competitor name] — Search complete
  LinkedIn: [Signal found / No signal]
  Google Ads: [Signal found / No signal]
  Meta: [Signal found / No signal]
  Spend signals: [Signal found / No signal]
  Messaging changes: [Signal found / No signal]
---

---

## Step 3 — Produce Competitor Brief

After completing all searches, produce a
structured brief for each competitor. Display
each brief in full before moving to the gap
analysis.

Display this format for each competitor:

---
─────────────────────────────────────
COMPETITOR: [Name]
Brief date: [today's date]
─────────────────────────────────────

ACTIVE ADS FOUND

[For each ad or ad pattern found — repeat
this block once per platform:]

Platform: [LinkedIn / Google Ads / Meta]
Ad copy or description: [exact copy if
  found, or a description of the pattern
  if exact copy is not available]
Angle: [one sentence on the strategic
  framing — what problem or outcome they
  are leading with]
Persona signal: [who this ad appears to
  target based on copy language, job titles
  mentioned, or pain points referenced]
Proof point used: [any named customer,
  specific metric, or case study referenced
  in the ad — or "none found"]
CTA: [the action they are asking the
  viewer to take]
Source: [URL or search result description
  — always cite a source, even if indirect]
Confidence: [High — exact ad copy found /
  Medium — ad pattern inferred from multiple
  signals / Low — single indirect signal only]

If no active ads are found for a platform:
"No active [platform] ads found in this
search. This may indicate no current spend
on this channel, ads not yet publicly
indexed, or search terms need refinement.
Flag for manual check if this competitor
is known to advertise on [platform]."

─────────────────────────────────────

HISTORICAL PATTERNS

Consistent angles — running across
multiple periods:
[List angles that appear in both prior
competitive_intel.md findings and current
search results — these are core positioning
claims this competitor owns and defends
consistently]

New angles — not in prior intel:
[List anything found in this run that was
not captured in competitive_intel.md —
these represent new investments, tests,
or strategic pivots]

Dropped angles — in prior intel but not
found this run:
[List anything previously recorded in
competitive_intel.md that did not appear
in this run's searches — these may signal
a strategic retreat, a paused test, or a
seasonal pattern]

If no prior intel exists for this
competitor:
"No baseline available — this is the
first run for this competitor. All
findings are logged as current state.
Patterns will begin to emerge from
Week 2 onward."

─────────────────────────────────────

SPEND SIGNALS

Channel investment signals:
[Which channels show the most active
ad presence — more ads running across
a platform indicates higher investment.
Note which platform appears to be the
primary channel for this competitor.]

Recent changes:
[Any new campaigns, budget increases,
or creative refreshes detected — cite
source for each]

Competitive pressure level:
[High — actively advertising in Lilt's
  primary channels and targeting the same
  personas /
Medium — advertising present but not
  directly competing with Lilt's primary
  angles or personas /
Low — minimal advertising activity found
  in this run]

─────────────────────────────────────
---

[Repeat for all competitors in competitors.md]

---

## Step 4 — Gap Analysis and Counter-Angles

After all competitor briefs are complete, produce
a single gap analysis that looks across all
competitors combined.

---
─────────────────────────────────────
COMPETITIVE GAP ANALYSIS
─────────────────────────────────────

ANGLES NO COMPETITOR IS USING

[For each gap identified across all competitors:]

Gap: [name the unclaimed angle in plain language]
Evidence: [which competitors were checked and
  what they are covering instead — be specific]
Why it matters: [one sentence connecting this
  gap to a real buyer pain from icp.md — why
  would this angle resonate with Lilt's ICP]
Urgency: [Standard — gap confirmed available /
  URGENT — this gap was previously identified
  in market_gaps.md and is now at risk of being
  claimed by a competitor who is moving toward it]

─────────────────────────────────────

COUNTER-ANGLE RECOMMENDATIONS

[For each significant competitor angle found —
especially new angles not in prior intel —
draft a specific counter-angle for Lilt.
Do not draft counter-angles for angles Lilt
is already running.]

Competitor angle: [what they are running and
  on which platform]
Why it is working or likely to work: [one sentence
  connecting their angle to a real buyer pain from
  icp.md — if it is not connected to a real pain,
  say so]
Lilt counter-angle: [the specific reframe or
  alternative angle Lilt should use — must be
  genuinely different from the competitor's
  framing, not a slight variation of it]
Proof point to anchor it: [the specific named
  customer result from proof_points.md that makes
  this counter-angle credible — do not suggest a
  counter-angle without a named proof point]
Suggested next action: [which skill to run —
  Campaign Writer for ad copy, Email and Nurture
  Sequencer for competitive displacement sequences,
  Landing Page Brief for conversion page]
Ready-to-use orchestrator brief:
"[exact brief the human can paste into the
  orchestrator to act on this counter-angle
  immediately — include format, persona, segment,
  funnel stage, and angle]"

─────────────────────────────────────
---

---

## Step 5 — Overall Competitive Summary

After all competitor briefs and the gap analysis,
display a summary of the full run.

---
─────────────────────────────────────
COMPETITIVE ADVERTISING SUMMARY
Week of: [date]
─────────────────────────────────────
Competitors monitored: [number]
Active ad signals found: [number]
New angles identified: [number]
Gaps confirmed available: [number]
Urgent flags: [number — gaps from
  market_gaps.md now being claimed]

Most active competitor this week:
[Competitor name — one sentence on why,
referencing which platforms they are most
active on and what angle is dominant]

Biggest threat:
[Competitor name and the single most
dangerous angle found this week — one
sentence on why this specific angle is
the most threatening to Lilt's pipeline,
connecting it to a buyer pain from icp.md]

Immediate recommended action:
[One specific action — which skill to run,
which competitor to respond to, which gap
to claim first — with the exact orchestrator
brief to paste and execute]
─────────────────────────────────────
---

---

## Step 6 — Proposed Context File Updates

After the summary, draft proposed updates to
competitive_intel.md based on this run's findings.

Never update context files automatically.
Always present as drafts for human review.
Make clear that no changes have been made yet.

---
─────────────────────────────────────
PROPOSED COMPETITIVE INTEL UPDATES

These are drafts based on this week's findings.
Review each before approving. No changes have
been made to any context file yet.

[For each proposed update — one block per change:]

File: context/deep/competitive_intel.md
Section: [competitor name]
Change type: [New finding / Updated finding /
  Contradicts prior finding]
Reason: [one sentence on what this week's
  search found that triggered this update]
Confidence: [High — exact ad copy sourced /
  Medium — pattern inferred / Low — indirect signal]

Current content:
"[paste the relevant existing text from
competitive_intel.md, or "No prior entry"
if this section does not exist yet]"

Proposed addition or replacement:
"Ad Intelligence note ([date]): [the new
finding written in the same style as the
existing competitive_intel.md entries —
factual, specific, sourced]"

To apply this update, say:
"Update competitive_intel.md — add ad
intelligence note to [competitor] section
with the content above."
─────────────────────────────────────
---

---

## Step 7 — Save Option

After all sections have displayed, ask:

"Would you like to save this competitive
intelligence brief?

It will be saved as:
competitor_intel_[company]_[date].md
in outputs/

Saving creates a dated record of competitor
advertising activity. Patterns become visible
when you compare briefs across multiple weeks —
a competitor who adds a new angle in Week 2 and
scales it in Week 4 is signalling a strategic
commitment, not a test."

Save only on explicit confirmation.
Follow the file naming convention in CLAUDE.md.
Read the active company name from the first line
of context/icp.md before naming the file.

---

## Rules

Always read context/competitors.md before
searching — never search from memory about
who the competitors are or what they claim.

Always cite a source for every ad finding —
URL, search result reference, or platform name.
Never report an ad angle without a source.

Always flag confidence level for every finding —
High for exact ad copy found, Medium for patterns
inferred from multiple signals, Low for single
indirect signals. Never present a Low confidence
finding as confirmed fact.

Always compare findings against competitive_intel.md
as the historical baseline — the change from prior
state is what makes the brief valuable, not just
the current snapshot.

Always draft counter-angles anchored to a named
proof point from proof_points.md. Never suggest
a counter-angle that cannot be supported by a
specific customer result.

Always flag urgently if a gap from market_gaps.md
is now being filled by a competitor — this is the
highest-priority finding in any run.

Never update context files automatically — always
draft proposed changes for human review.

Never report a competitor angle without connecting
it to a specific buyer pain from icp.md. If a
competitor angle is not connected to a real pain,
say so explicitly.

Never save without explicit confirmation.

When running in weekly mode: search all competitors
from competitors.md without asking which ones to
include.

When running on demand: if specific competitors
are named in the brief, check only those. If no
competitors are named, check all.
