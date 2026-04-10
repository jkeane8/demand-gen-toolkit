# Budget Allocation Model
## Takes a campaign objective and total budget and produces
## three allocation scenarios across channels and funnel
## stages with projected outcomes.
## Projections use benchmark data unless historical
## performance data is available in outputs/performance/.

---

## What This Skill Does

Takes a campaign objective and total budget as input and
produces three allocation scenarios — Conservative,
Recommended, and Aggressive — each showing how to split
budget across channels and funnel stages with reasoning
for every decision.

For each scenario it produces:
- Channel split: paid search, LinkedIn, email, ABM —
  with percentage and dollar amount
- Funnel stage split within each channel: awareness,
  retargeting, conversion
- Projected outcomes per channel: impressions, clicks,
  leads, and CPL based on benchmark data
- If historical performance data exists in
  outputs/performance/: uses real CPMs, CPCs, and
  conversion rates instead of benchmarks and flags
  this clearly

Produces both a monthly view and a quarterly view.

Runs on demand — triggered by any mention of budget,
allocation, spend planning, or channel mix.

---

## Step 1 — Read Before Modeling

Before building any allocation, read ALL of these files:

**Required files:**

context/icp.md
Read for: segment definitions, persona seniority levels,
and buying process length. Used to determine which
channels reach this audience most efficiently and what
funnel stage balance is appropriate for the buying
cycle length.

context/market.md
Read for: market trends and competitive intensity. Used
to adjust channel recommendations — a highly competitive
paid search market warrants a different allocation than
an uncrowded one.

context/competitors.md
Read for: competitor channel presence. If competitors
dominate paid search, LinkedIn may warrant a higher
allocation. If competitors are absent from a channel,
that channel may offer lower CPCs and higher impression
share.

**Optional files — check and use if found:**

outputs/performance/*.csv or outputs/performance/*.md
If any performance data files exist in
outputs/performance/ — read them before modeling.
Extract actual CPMs, CPCs, conversion rates, and CPLs
by channel. Use these real numbers instead of benchmarks
for projections. Flag clearly in the output which
projections are based on real data vs benchmarks.

outputs/keywords_*.md
If found: read for keyword competitiveness signals.
High average CPC estimates in the keyword file suggest
paid search will be more expensive than benchmark —
adjust projections accordingly.

outputs/linkedin_strategy_*.md
If found: read for LinkedIn audience size estimates and
CPM predictions from the LinkedIn Campaign Organiser.
Use these instead of benchmark CPMs if available.

Display this before modeling:

---
BUDGET ALLOCATION MODEL
─────────────────────────────────────
Objective: [stated objective]
Total budget: [amount]
Monthly budget: [total divided by 3 if quarterly,
  or stated amount if monthly]
Quarterly budget: [total if quarterly, or monthly x 3]
Budget period: Monthly + Quarterly view
Scenarios: Conservative, Recommended, Aggressive
Active company: [from context/icp.md]
Context files loaded:
[✓/✗] context/icp.md
[✓/✗] context/market.md
[✓/✗] context/competitors.md
Historical performance data found:
[Yes — list files / No — using benchmarks]
Keyword file found: [Yes/No]
LinkedIn strategy file found: [Yes/No]
Modeling now.
---

---

## Step 2 — Gather Inputs

After reading context files, display these questions
if any are not already clear from the brief:

---
Before I model, I need a few details.
Answer all of these in one message:

TOTAL BUDGET — what is the total budget?
State whether this is monthly or quarterly — I will
produce both views either way.

OBJECTIVE — what is the primary campaign objective?
- Pipeline generation — maximise leads, opportunities
  created
- Brand awareness — maximise reach among the ICP
- Account expansion — penetrate a specific named
  account list
- Mixed — awareness and pipeline in parallel

CHANNELS AVAILABLE — which channels are active
or available to use?
- Paid search (Google Ads)
- LinkedIn Sponsored Content
- Email and nurture (HubSpot)
- ABM (named account outreach)
- All of the above

CONSTRAINTS — any budget floors or ceilings
per channel?
(e.g. minimum $X on LinkedIn, no paid search budget)
Press Enter to skip.
---

Wait for answers before modeling.
If all inputs are clear from the brief, skip this
step and proceed directly to Step 3.

---

## Step 3 — Apply Benchmarks

Use these benchmarks for projections unless historical
data is available in outputs/performance/.

Always flag which data source is being used for each
channel projection:
[Benchmark] or [Historical — filename]

**PAID SEARCH BENCHMARKS**
B2B SaaS, VP/Director level targeting:

Average CPC: $12
Click-to-lead conversion rate: 4%
CPL: $300

Monthly budget to meaningful data threshold: $3,000
minimum. Below this threshold impression volume is
too low to optimise.

**LINKEDIN BENCHMARKS**
B2B SaaS, VP/C-Suite, North America:

Awareness phase CPM: $22
Retargeting phase CPM: $18
Average CTR: 0.4%
Lead gen form completion rate: 10%
CPL (awareness to lead): $180
CPL (retargeting to lead): $120

Monthly budget to meaningful data threshold: $5,000
minimum. Below this threshold A/B test results are
not statistically reliable.

**EMAIL AND NURTURE BENCHMARKS**
VP/Director level B2B sequences:

Cost per sequence: $0 media spend
(Internal channel — cost is time and tooling,
not media budget)
Open rate: 25%
Click rate: 3%
Meeting book rate from sequence: 2%

Note: Email has no media cost so it does not consume
budget allocation — but it should always be included
in the channel mix recommendation as the zero-cost
conversion layer.

**ABM BENCHMARKS**
Named account outreach:

LinkedIn ABM CPM: $28
(Higher than standard LinkedIn due to matched
audience targeting)
Email ABM reply rate: 5%
Meeting book rate from ABM: 3%
Average accounts needed to reach 1 meeting: 10-15

Minimum viable ABM list: 20 accounts. Below 20
accounts the program is too narrow to generate
reliable data.

---

## Step 4 — Build Three Scenarios

Build all three scenarios using this logic:

**CONSERVATIVE SCENARIO**
Philosophy: Protect budget. Minimise risk. Prove one
channel works before expanding. Prioritise the channel
with the lowest CPL and most reliable conversion data.

Allocation principles:
- Concentrate 70-80% of budget in one primary channel
- Secondary channel gets 20-30%
- No budget spread across more than two paid channels
- Paid search primary if keyword intent signals exist
  in the ICP
- LinkedIn primary if no strong keyword intent or if
  persona is VP/C-Suite with low search volume
- ABM only if named account list exists and list is
  above 20 accounts
- Always include email as zero-cost parallel channel
  regardless of budget

Funnel stage split (conservative):
- 20% awareness
- 30% retargeting
- 50% conversion
Why: Protect CPL by concentrating spend where intent
is highest. Awareness is minimal — just enough to
feed the retargeting pool.

**RECOMMENDED SCENARIO**
Philosophy: Balance reach and efficiency. Build the
retargeting pool while converting existing intent.
Sustainable CPL with improving returns over time.

Allocation principles:
- Split across two or three channels
- No single channel above 60% of budget
- Paid search captures existing intent
- LinkedIn builds brand and retargeting pool
- ABM runs in parallel if account list exists
- Email runs as zero-cost conversion layer for
  all channels

Funnel stage split (recommended):
- 35% awareness
- 35% retargeting
- 30% conversion
Why: Build the retargeting audience while converting
high-intent traffic. More sustainable than pure
bottom-funnel concentration and produces compounding
returns as the retargeting pool grows.

**AGGRESSIVE SCENARIO**
Philosophy: Maximise reach and pipeline velocity.
Accept higher CPL in exchange for faster market
penetration. Appropriate for product launches,
competitive displacement campaigns, or when
time-to-pipeline is the primary constraint.

Allocation principles:
- Spread across all available channels
- LinkedIn gets largest share due to audience reach
  potential
- Paid search captures all available intent
- ABM targets the highest-priority accounts
  simultaneously
- Email sequences run for all converted awareness
  leads

Funnel stage split (aggressive):
- 50% awareness
- 30% retargeting
- 20% conversion
Why: Front-load brand building to create a large
retargeting pool quickly. Short-term CPL will be
higher but pipeline velocity increases in months 2
and 3 as the retargeting pool becomes large enough
to convert.

---

## Step 5 — Display Each Scenario

Display all three scenarios using this exact format:

---
SCENARIO: [Conservative / Recommended / Aggressive]
Philosophy: [one sentence]
Best for: [one sentence on when this scenario is
the right choice]
─────────────────────────────────────

MONTHLY ALLOCATION
Total monthly budget: $[amount]

[For each channel:]
[Channel name]
Monthly budget: $[amount] ([%] of total)
Funnel stage split:
  Awareness: $[amount] ([%])
  Retargeting: $[amount] ([%])
  Conversion: $[amount] ([%])

PROJECTED MONTHLY OUTCOMES
[Data source: Benchmark / Historical — filename]

[For each paid channel:]
[Channel name]:
  Impressions: [estimated number]
  Clicks: [estimated number]
  Leads: [estimated number]
  Estimated CPL: $[amount]
  Confidence: [High if historical data /
    Medium if benchmark / Low if below minimum
    data threshold]

[For email:]
Email and Nurture:
  Media cost: $0
  Sequences active: [number based on leads from
    paid channels]
  Estimated meetings from sequences: [number based
    on 2% meeting rate]
  Note: Email amplifies paid channel leads at zero
    additional media cost.

Blended CPL: $[total budget divided by total leads]
Estimated meetings booked: [total]
─────────────────────────────────────

QUARTERLY ALLOCATION
Total quarterly budget: $[monthly x 3]

[Repeat channel breakdown for quarterly amounts]

PROJECTED QUARTERLY OUTCOMES
[Same structure as monthly but multiplied — note
that retargeting performance improves in months 2-3
as the awareness pool builds, so quarterly CPL
should be lower than 3x monthly CPL for scenarios
with significant awareness investment]

Month 1 projected CPL: $[amount]
Month 2 projected CPL: $[amount]
  (retargeting pool building)
Month 3 projected CPL: $[amount]
  (retargeting pool established)
Quarterly blended CPL: $[amount]

TOTAL PROJECTED QUARTERLY OUTCOMES
Total leads: [sum]
Blended CPL: $[amount]
Estimated meetings booked: [total]
Pipeline value estimate: [total meetings x average
  deal size if known, otherwise note "deal size not
  provided — multiply meetings by your ACV to
  estimate pipeline"]
─────────────────────────────────────

REASONING

Why this channel split:
[Two to three sentences connecting the allocation
to the ICP, competitive landscape, and objective
— reference specific findings from context files]

Why this funnel stage split:
[One to two sentences on the awareness vs
retargeting vs conversion balance and what it
optimises for]

Trade-offs:
What this scenario optimises for: [one phrase]
What it sacrifices: [one phrase]
When to choose this scenario: [one sentence]
---

[Repeat for all three scenarios]

---

## Step 6 — Scenario Comparison

After all three scenarios, display a comparison
summary:

---
SCENARIO COMPARISON

Always display the comparison table using markdown
pipe character format with | column separators and
--- for the header divider row. This ensures correct
rendering on GitHub and in markdown viewers. Do not
use space-aligned columns.

| Metric | Conservative | Recommended | Aggressive |
| --- | --- | --- | --- |
| Monthly budget | $[X] | $[X] | $[X] |
| Monthly leads | [X] | [X] | [X] |
| Blended CPL | $[X] | $[X] | $[X] |
| Meetings/month | [X] | [X] | [X] |

RECOMMENDATION

Based on the objective stated and the context files
loaded, the [scenario name] scenario is the most
appropriate starting point because [two sentences
connecting the recommendation to the specific
objective, ICP, and competitive context].

If [condition] — switch to the [other scenario]
instead. [One sentence on what would trigger a
scenario change — e.g. "If the retargeting pool
reaches 1,000 members within 6 weeks, shift budget
toward the Recommended scenario."]
---

---

## Step 7 — Save Option

After displaying all scenarios and the comparison,
ask:

"Would you like to save the budget allocation model?

It will be saved as:
budget_allocation_[objective]_[company]_[date].md
in outputs/

This gives you a dated record of the allocation
rationale, projected outcomes, and scenario
comparison to share with stakeholders or use as
a planning baseline."

Save only on explicit confirmation.
Follow the file naming convention in CLAUDE.md.
Read the active company name from the first line
of context/icp.md before naming the file.

---

## Rules

Always read context/icp.md, context/market.md, and
context/competitors.md before modeling — never
allocate from general knowledge alone.

Always flag whether projections are based on
benchmarks or historical data — never mix them
without noting the source per channel.

Always include email as a zero-cost parallel channel
regardless of budget — never exclude it from the
channel mix recommendation.

Always note when a budget is below the minimum
threshold for a channel — do not project outcomes
for budgets that cannot generate statistically
meaningful data.

Always produce all three scenarios — never show
only one even if the brief seems to imply a
preference.

Always produce both monthly and quarterly views —
never show only one.

Always connect allocation reasoning to specific
context file findings — never give generic channel
advice.

Never update context files from this skill — Budget
Allocation Model is a planning tool, not an
intelligence update tool.

Never save without explicit confirmation.

Read the active company name from context/icp.md
for file naming. Follow the naming convention in
CLAUDE.md for all output files.
