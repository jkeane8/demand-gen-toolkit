---

# Budget Reallocation Model

## What this skill does

Takes pasted campaign performance data or an uploaded CSV
and produces a structured reallocation decision — which
campaigns to cut, scale, or hold — with dollar amounts
and written rationale for each decision.

Primary logic weights pipeline quality (opportunity rate,
SAL rate, influenced pipeline) over efficiency metrics
(CPL, CPA). Efficiency informs but does not drive decisions.
A campaign with low CPL and zero pipeline contribution is
a cut candidate. A campaign with high CPL and strong
opportunity rate is a hold or scale candidate.

---

## When to use this skill

Use when:
- Reviewing performance at end of month, quarter, or sprint
- Rebalancing a budget after a campaign underperforms
- Building a reallocation recommendation for leadership
- Preparing a budget defence or reforecast

Do not use when:
- You have fewer than 3 weeksdata per campaign
  (too early to distinguish signal from noise)
- You have no pipeline attribution data at all
  (efficiency-only decisions are flagged as limited confidence)

---

## Input formats accepted

### Option A — Pasted data

Paste campaign performance directly into the chat.
Minimum required fields:

  Campaign name
  Channel (Google Search / LinkedIn / Retargeting / Other)
  Spend (period)
  Leads or form fills
  MQLs
  SALs or Sales Accepted Leads
  Opportunities created
  Pipeline influenced ($)
  CPL

Optional but improves output:
  CPC, CTR, conversion rate by stage
  Impression share (Search)
  Frequency (LinkedIn / Paid Social)
  Notes on audience, offer, or match type

If pipeline data is unavailable, note that explicitly.
The skill will flag decisions as lower confidence and
weight efficiency metrics more heavily as a fallback.

### Option B — Uploaded CSV

Upload a CSV export from Google Ads, LinkedIn Campaign
Manager, or a custom reporting export.

Column headers do not need to maexactly.
Describe what each column represents when you upload
if the headers are non-standard.

The skill will map columns to the required fields and
flag any that are missing before producing output.

---

## What to tell the skill before running

Provide the following context:

1. Total budget for the period (or remaining budget if
   mid-period reallocation)
2. Budget period (monthly / quarterly / sprint)
3. Primary goal: pipeline volume, pipeline quality,
   or pipeline efficiency
4. Any campaigns that are protected (cannot be cut
   regardless of performance — e.g. brand terms,
   always-on retargeting)
5. Any hard constraints: minimum spend floors per
   channel, committed contract spend, exec preferences

If you do not provide these, the skill will ask
before producing output.

---

## Output structure

### Section 1 — Executive summary
3–5 sentences. Total spend reviewed, overall pipeline
performance, headline reallocation recommendation,
and confidence level.

### Section 2 — Campaign score row per campaign:

  Campaign name | Channel | Spend | Pipeline contribution
  | Opp rate | Decision | Confidence

Decision options: CUT / SCALE / HOLD / HOLD-WATCH

HOLD-WATCH = keep at current spend but flag for
review next cycle. Used when data is thin or a
campaign is too new to cut with confidence.

Confidence levels: HIGH / MEDIUM / LOW
Driven by data completeness and volume of conversions.
Low confidence decisions are flagged explicitly.

### Section 3 — Reallocation table
Dollar-level reallocation plan.

  Freed budget (from cuts and reductions)
  Reallocation targets (which campaigns receive freed budget)
  Rationale for each reallocation move
  New budget per campaign
  Total check (must equal original total)

### Section 4 — Rationale log
One paragraph per campaign that received a CUT or
SCALE decision. Written in plain language suitable
for sharing with a VP or CMO. No jargon. Explains
the decision, the data behind it, and what would
need to be true to reverse it.

### Section 5 — Data quflags
Any fields that were missing, estimated, or low-volume.
Calls out which decisions should be held with lower
confidence and what data would improve them.

---

## Scoring logic

### Pipeline quality score (weighted 60%)

  Opportunity rate (opps / leads): 30%
  SAL rate (SALs / MQLs): 20%
  Pipeline influenced per dollar spent: 10%

### Efficiency score (weighted 40%)

  CPL relative to benchmark: 20%
  MQL rate (MQLs / leads): 10%
  Stage progression rate (MQL → SAL → Opp): 10%

### Benchmarks

Benchmarks are pulled from context/benchmarks.md
if that file exists in the project.

If no benchmarks file exists, the following
defaults are used. These are calibrated for B2B
companies with multi-touch sales cycles. They
should be replaced with company-specific data
after 60 days of baseline is available.

  Google Search CPL: $150–$400
  LinkedIn CPL: $200–$600
  Retargeting CPL: $80–$200
  MQL rate: 15–30% of raw leads
  SAL rate: 40–60% of MQLs
  Opp rate: 25–40% of SALs

When defaults aremark comparisons
are flagged in the data quality section so the
reader knows they are indicative, not definitive.

### Cut triggers (any one is sufficient)

  Opp rate below 5% with 30+ leads
  Zero pipeline influenced after 4+ weeks of spend
  CPL more than 3x benchmark with no offsetting
  pipeline quality signal
  Impression share collapse on branded terms
  with no competitive explanation

### Scale triggers (all three required)

  Opp rate above benchmark
  Pipeline influenced trending up week-over-week
  CPL within 1.5x benchmark OR pipeline quality
  justifies the higher CPL explicitly

---

## Portability note

This skill works for any B2B company with a
multi-touch sales cycle and some form of pipeline
attribution, even if imperfect.

When running against a new company context, check
context/benchmarks.md for company-specific CPL
targets, MQL definitions, and pipeline stage names.

If the company uses different funnel stage names
(e.g. SQL instead of SAL, Demo instead of Opp),
note the mapping when you run the skill and it
will adjust output labels accordingly.

---
