# Performance Grader
## Reads campaign performance data and
## grades results against benchmarks
## and predictions
## Flags underperformance, recommends
## next actions, and drafts context
## file updates for review

---

## What This Skill Does

The Performance Grader reads performance data exported from Google Ads,
LinkedIn Campaign Manager, HubSpot, or any other platform and produces
a structured grade for each campaign, ad group, variant, or sequence
in the data.

It grades performance against two standards simultaneously:
1. Industry benchmarks for the channel and audience type
2. Predictions made in the strategy documents produced by the toolkit
   — ad group strategy files, LinkedIn strategy files, email sequence files

It runs in two modes:
- Weekly mode: triggered every Monday with a fresh data export dropped
  into outputs/performance/
- On demand: triggered any time with a data file reference or paste

For every underperforming element it:
- Flags what is wrong and why
- Recommends a specific next action with the exact skill to run
- Drafts proposed context file updates for human review — never updates
  context files automatically

---

## Step 1 — Read Before Grading

Before reading any performance data, read ALL of these files.

### Required files

context/icp.md
Read for: segment definitions, persona titles, pain points, and buyer
vocabulary. Used to interpret whether performance patterns suggest a
message-market fit problem or a targeting problem.

context/brand_voice.md
Read for: tone scale and vocabulary rules. Used to interpret whether
low engagement suggests a brand voice mismatch.

context/competitors.md
Read for: competitor positioning. Used to interpret whether low CTR on
specific angles suggests competitors are winning on those terms.

context/proof_points.md
If found: read for named customer metrics. Used to verify whether proof
points used in campaigns are producing expected engagement lift.

### Strategy documents to check

Scan outputs/ for these file types and read the most recent version
of each that matches the active company:
- ad_group_strategy_*.md — for Google Ads predictions and recommendations
- linkedin_strategy_*.md — for LinkedIn phase recommendations and audience
  targeting predictions
- email_nurture_*.md or copy_cold_email_*.md — for email sequence structure
  and expected engagement patterns

### Display before grading

---
PERFORMANCE GRADER
─────────────────────────────────────────
Data file: [filename or "pasted data"]
Platform detected: [Google Ads / LinkedIn / HubSpot / Multiple / Unknown]
Date range in data: [start — end]
Elements being graded: [number and type — e.g. "4 ad groups, 12 keywords"
  or "3 LinkedIn campaigns, 6 variants"]

Matching strategy files found in outputs/:
[list each — these will be used for prediction accuracy grading]

Strategy documents not found:
[list any channels in the data that have no matching strategy document —
benchmark grading only for these]

Context files loaded:
[✓/✗] context/icp.md
[✓/✗] context/brand_voice.md
[✓/✗] context/competitors.md
[✓/✗] context/proof_points.md

Grading now.
─────────────────────────────────────────
---

---

## Step 2 — Detect Platform and Metrics

Before grading, identify what platform the data is from and what metrics
are present. Do this dynamically — do not assume a fixed set of columns.

### Platform detection rules

- If columns include Quality Score, Search Impression Share, or Ad Group:
  Google Ads
- If columns include Campaign Objective, LinkedIn Relevance Score, or
  Sponsored Content: LinkedIn
- If columns include Open Rate, Click Rate, Unsubscribe Rate, or Workflow:
  HubSpot email
- If multiple platform patterns present: flag as Multiple and grade each
  platform separately
- If platform cannot be determined: flag as Unknown and ask one question
  before proceeding

### Metric detection

Read every column header in the data and note which metrics are present.
Grade only on metrics that are actually in the file. Do not penalize for
missing metrics — note them as not available.

Display detected platform and metrics before grading:

```
Detected platform: [name]
Metrics available for grading:
[list every metric column found]
Metrics not available:
[list any standard metrics for this platform missing from the file]
```

---

## Step 3 — Apply Benchmarks

Use these benchmarks as the standard for grading. These are B2B SaaS
benchmarks for the personas and segments in the ICP. Flag clearly when
actual performance is above, at, or below benchmark.

### Google Ads benchmarks
For VP/Director level B2B SaaS targeting:

CTR:
- Above benchmark: 4%+
- At benchmark: 2–4%
- Below benchmark: 1–2%
- Critical: under 1%

Conversion rate (click to lead):
- Above benchmark: 8%+
- At benchmark: 4–8%
- Below benchmark: 2–4%
- Critical: under 2%

Cost per click:
- Above benchmark: under $8
- At benchmark: $8–$15
- Below benchmark: $15–$25
- Critical: over $25

Quality Score:
- Above benchmark: 8–10
- At benchmark: 6–7
- Below benchmark: 4–5
- Critical: under 4

Search impression share:
- Above benchmark: 50%+
- At benchmark: 30–50%
- Below benchmark: 15–30%
- Critical: under 15%

### LinkedIn benchmarks
For VP/C-Suite B2B SaaS targeting in North America:

CTR (awareness phase):
- Above benchmark: 0.6%+
- At benchmark: 0.3–0.6%
- Below benchmark: 0.1–0.3%
- Critical: under 0.1%

CTR (retargeting phase):
- Above benchmark: 0.8%+
- At benchmark: 0.4–0.8%
- Below benchmark: 0.2–0.4%
- Critical: under 0.2%

Engagement rate:
- Above benchmark: 2%+
- At benchmark: 1–2%
- Below benchmark: 0.5–1%
- Critical: under 0.5%

CPM:
- Above benchmark: under $15
- At benchmark: $15–$28
- Below benchmark: $28–$40
- Critical: over $40

Lead gen form completion rate:
- Above benchmark: 13%+
- At benchmark: 8–13%
- Below benchmark: 4–8%
- Critical: under 4%

### HubSpot email benchmarks
For VP/Director level B2B sequences:

Open rate:
- Above benchmark: 35%+
- At benchmark: 20–35%
- Below benchmark: 10–20%
- Critical: under 10%

Click rate:
- Above benchmark: 5%+
- At benchmark: 2–5%
- Below benchmark: 1–2%
- Critical: under 1%

Reply rate (for ABM sequences):
- Above benchmark: 8%+
- At benchmark: 3–8%
- Below benchmark: 1–3%
- Critical: under 1%

Unsubscribe rate:
- Acceptable: under 0.5%
- Watch: 0.5–1%
- Critical: over 1%

Meeting book rate (from sequence):
- Above benchmark: 3%+
- At benchmark: 1–3%
- Below benchmark: 0.5–1%
- Critical: under 0.5%

---

## Step 4 — Grade Each Element

Grade every campaign, ad group, variant, email, or sequence element
in the data.

For each element display:

---
[ELEMENT TYPE]: [Element name]
[Platform] | [Date range if available]
─────────────────────────────────────────
METRICS

[For each metric in the data:]
[Metric name]: [actual value]
Benchmark: [benchmark range for this metric and audience type]
Grade: [Above benchmark / At benchmark / Below benchmark / Critical]
Implication: [one sentence on what this means]

─────────────────────────────────────────
BENCHMARK GRADE: [A / B / C / D / F]
A = 80%+ of metrics at or above benchmark
B = 60–79% of metrics at or above benchmark
C = 40–59% of metrics at or above benchmark
D = 20–39% of metrics at or above benchmark
F = under 20% of metrics at or above benchmark

[If strategy document found for this element:]

PREDICTION ACCURACY

[For each metric where a prediction was made in the strategy document:]
Predicted: [what the strategy document said]
Actual: [what the data shows]
Accuracy: [Accurate / Over-estimated / Under-estimated — with % difference]
[One sentence on what this tells you about the prediction model]

PREDICTION GRADE: [Accurate / Optimistic / Conservative — with one
  sentence summary]

─────────────────────────────────────────
DIAGNOSIS

What is working:
[One paragraph on the strongest performing elements and why — connect
to ICP fit, copy angle, or targeting. Be specific.]

What is underperforming:
[One paragraph on the weakest elements with a specific hypothesis for
why — connect to ICP fit, message-market fit, targeting, landing page,
or copy angle. Be specific. "CTR is low" is not a diagnosis. "CTR is
low on the primary copy angle for the target persona, which suggests
this persona may be more Solution-aware than the strategy assumed —
they are already in evaluation mode and the awareness-level hook is
not resonating" is a diagnosis.]

─────────────────────────────────────────
RECOMMENDED NEXT ACTIONS

[For each underperforming element:]

Action [N]: [one sentence on what to do]
Skill to run: [exact skill name and a one-sentence brief to paste
  into the orchestrator]
Expected outcome: [one sentence on what running this skill should produce]
Priority: [This week / Next week / Next planning cycle]
---

---

## Step 5 — Overall Campaign Grade

After grading all elements, display an overall summary across the full
data set:

---
OVERALL CAMPAIGN GRADE
─────────────────────────────────────────
Elements graded: [number]
Above benchmark: [number and %]
At benchmark: [number and %]
Below benchmark: [number and %]
Critical: [number and %]

Overall grade: [A / B / C / D / F]
One sentence summary: [the single most important thing this data tells
  you about the campaign]

Top performer: [element name and why it is leading]
Biggest opportunity: [element name and what one change would most
  improve overall performance]
Biggest risk: [element name and what needs immediate attention]
─────────────────────────────────────────

CHANNEL BREAKDOWN
[If multiple channels in data:]
[Channel]: [average grade] — [one sentence on channel-level pattern]
---

---

## Step 6 — Context File Update Recommendations

After grading, identify any findings that suggest the context files
warrant updates. Flag only findings that are supported by real
performance data — not inferences from a single data point.

---
PROPOSED CONTEXT FILE UPDATES

These are drafts based on performance data. Review each before approving.
None of these changes have been made yet.

[For each proposed update:]

File: [context/filename.md]
Section: [which section to update]
Reason: [one sentence on what performance data triggered this — cite
  the specific metric and element]
Confidence: [High / Medium / Low — based on how much data supports this]

Current content:
"[quote the relevant existing text]"

Proposed update:
"[the rewritten version]"

To apply this update paste into Claude Code:
"Update [filename] — replace [section] with the proposed content above."
---

### Types of updates to flag

Keyword score updates:
If a keyword scored high in the keyword file but has low real CTR or
low conversion rate — flag the score as potentially overstated and draft
a score revision with the real data appended as a performance note.

ICP segment updates:
If a segment is consistently outperforming or underperforming
expectations — flag whether the segment definition, pain point language,
or persona assumptions may need revision.

Proof point updates:
If a campaign angle anchored to a specific proof point from
proof_points.md is outperforming or underperforming other angles — flag
that proof point as more or less effective than assumed and draft an
update to the proof_points.md ranking with the real performance data
appended.

Copy angle updates:
If one copy angle consistently outperforms others across multiple
elements — draft an update to voice_of_customer.md or icp.md noting
which vocabulary or framing is resonating most with real buyers.

---

## Step 7 — Save Option

After displaying all grades and proposed updates ask:

"Would you like to save the performance report?

It will be saved as:
performance_grade_[channel]_[company]_[YYYY-MM-DD].md
in outputs/

This gives you a dated record of campaign performance, what was graded,
what the diagnosis was, and which context file updates were proposed."

Save only on explicit confirmation.

---

## Rules This Skill Must Always Follow

Always read all four required context files before grading — never grade
from memory or general knowledge.

Always detect platform and metrics dynamically — never assume fixed columns.

Always grade against both benchmarks and predictions where a strategy
document exists.

Never update context files automatically — always draft proposed changes
for human review first.

Always provide a specific next action with an exact skill name for every
underperforming element.

Always provide a diagnosis that connects performance to a specific
hypothesis about message-market fit, targeting, copy angle, or ICP
assumptions — never just report the numbers.

Always flag Critical elements prominently — these need immediate attention
before more budget is spent.

For Google Ads data: always check Quality Score if present — it is the
strongest leading indicator of future performance and should be flagged
before CPL or CTR issues compound.

For LinkedIn data: always check CPM alongside CTR — a high CPM with low
CTR indicates audience targeting may be too narrow or the creative is not
resonating with the audience being reached.

For email data: always check unsubscribe rate first — an unsubscribe rate
over 1% signals a fundamental message-audience mismatch that will damage
the sending domain if not corrected immediately.

Never save without explicit confirmation.

Read active company name from context/icp.md for file naming.

Follow file naming convention in CLAUDE.md for all output files.

When running in weekly mode: check outputs/performance/ for the most
recently modified file and grade that automatically without asking which
file to use.

When running on demand: if no file is specified ask one question —
"Which performance file should I grade? You can paste the data directly
or give me the filename."
