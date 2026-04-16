# ABM Account Prioritisation Model
## Scores and tiers a target account list across four criteria:
## ICP fit, buying readiness, revenue potential, and relationship warmth
## Produces a prioritised account file and summary report
## Feeds optional tier context to the Trigger Monitor — does not replace it

---

## What This Skill Does

Takes a raw account list as input — pasted directly into Claude Code
or provided as a CSV file — and turns it into a scored, tiered, and
actionable ABM target list.

Before scoring a single account, the skill reads all context files
to understand exactly what the ideal customer looks like, which
trigger events indicate active buying intent, what a high-value deal
looks like, and what proof points exist for comparable companies.
Every score is grounded in the context files — not in general
knowledge about the industry.

Each account is scored 0–100 across four criteria. Each account is
then assigned to one of four tiers — Strategic, Full ABM, Light ABM,
or Programmatic — based on its total score. The tier determines how
much resource is allocated to that account and at what cadence.

The skill displays the full scored and tiered list before saving
anything, and waits for explicit confirmation before writing files.

Two output files are produced:
1. A prioritised account file with scoring rationale and recommended
   next actions for each account
2. A Trigger Monitor feed file containing only the tier assignments —
   the Trigger Monitor reads this file to adjust search depth per
   account when present. The Trigger Monitor runs correctly at full
   depth for all accounts if this file does not exist. Tier data is
   optional context, not a dependency.

---

## Step 1 — Read Before Scoring

Read the following files before scoring any account. These files
are the intelligence layer this skill draws from — every score
is tied to specific content found in these files, not to general
assumptions about the category.

Display the pre-flight block after reading:

```
ABM ACCOUNT PRIORITISATION MODEL
─────────────────────────────────────────────────────────────────
Input format: [Pasted list / CSV file — detected automatically]
Accounts to score: [number]

Context files loaded:
[✓ or ✗] context/icp.md
[✓ or ✗] context/market.md
[✓ or ✗] context/competitors.md
[✓ or ✗] context/proof_points.md
[✓ or –] context/deep/trigger_events.md
[✓ or –] context/deep/buying_committee.md
(– = not found, will proceed without)

Prior intelligence found:
[Yes — list files by name / No]

Active company: [read from first line of context/icp.md]

Scoring now.
─────────────────────────────────────────────────────────────────
```

---

### Required files

**context/icp.md**
This is the primary scoring reference for ICP Fit. Read every
segment definition: the company size ranges, industry verticals,
persona seniority levels, pain points, and trigger events associated
with each segment. An account that matches the primary ICP segment
on all dimensions scores maximum ICP Fit points. An account that
partially matches or matches a secondary segment scores
proportionally. An account whose profile does not appear in any
segment definition scores low regardless of how interesting the
company looks from the outside.

**context/market.md**
Read for market trends, high-growth segments, and the competitive
landscape. Used to calibrate Revenue Potential scores — accounts
in markets the active company has named as growth opportunities,
or in segments where comparable companies have succeeded, score
higher on Revenue Potential than accounts in flat or declining
segments.

**context/competitors.md**
Read for competitor names and their known customer bases. If any
account in the list is known to use a competitor's product, flag
it. Competitor usage is a two-sided signal: it confirms the account
is already spending in this category (buying readiness indicator)
and it identifies a displacement opportunity. Both should be noted
in the account entry.

**context/proof_points.md**
If found: read for named customer results organised by segment and
company type. Accounts that closely resemble named customers in
this file score higher on Revenue Potential — if a comparable
company succeeded, confidence in the outcome for this account
increases. Note which named customer is most comparable when this
factor influences a score.

---

### Optional files

**context/deep/trigger_events.md**
If found: read for the trigger event types, their search behavior,
content needs, and monitoring signals. Used to evaluate Buying
Readiness — accounts showing one or more trigger event signals
score higher on this criterion. An account currently exhibiting
a Hot trigger event signal scores at the top of the Buying
Readiness range.

**context/deep/buying_committee.md**
If found: read for the roles involved in a purchase decision and
the typical buying process stages. Used to evaluate Relationship
Warmth — accounts where known contacts hold buying committee roles
score higher than accounts where known contacts are outside the
decision process. Also used to set realistic expectations on deal
timeline when recommending next actions.

---

### Scan outputs/ for prior intelligence

Before scoring, check outputs/ for:

**outputs/trigger_monitor_*.md or outputs/trigger_briefing_*.md**
If a recent Trigger Monitor briefing exists: read it before scoring.
Any account that appeared in the briefing with a Hot or Warm signal
should have its Buying Readiness score adjusted upward to reflect
that active intelligence. Note the source briefing file in the
account entry.

**outputs/competitor_intel_*.md**
If a recent Competitor Ad Intelligence report exists: read it for
any account-level intelligence that may affect scoring. An account
flagged as actively evaluating alternatives should be scored as
higher Buying Readiness.

If prior intelligence is found, note this in the pre-flight block
and reference it in the specific account scores it affects.

---

## Step 2 — Accept Input

Accept account lists in two formats. Detect the format automatically
and note which format was used in the pre-flight block.

---

**Format 1 — Pasted list**

The user pastes account names directly into Claude Code. One account
per line or comma-separated. The only required field is the company
name. Extract all additional fields if provided.

Optional fields that improve scoring confidence when present:
- Industry
- Company size (employee count or revenue range)
- Known contact name and title
- Current vendor or technology in use
- Notes (reason for inclusion, prior engagement, etc.)

**Format 2 — CSV file**

The user drops a CSV file into inputs/accounts_to_score.csv.
The required column is Company Name. All other columns are optional.

If the CSV does not exist and no pasted list is provided, ask:

> "Please provide the account list in one of two ways:
> 1. Paste the account names directly here — one per line is fine
> 2. Drop a CSV file into inputs/accounts_to_score.csv and let me
>    know when it is ready"

For either format: extract all fields provided. Note which fields
are missing per account — missing fields reduce scoring confidence
but do not prevent scoring. A company with no additional information
beyond its name will receive a Confidence: Low rating on its score.

---

## Step 3 — Score Each Account

Score every account across four criteria. Each criterion is scored
0–25, for a maximum total of 100.

Before scoring, display the scoring rubric so the user understands
what each score means:

```
─────────────────────────────────────────────────────────────────
SCORING RUBRIC
─────────────────────────────────────────────────────────────────

CRITERION 1 — ICP Fit (0–25)
Measures how closely this account matches the ideal customer
profile defined in context/icp.md.

25 points: Perfect match — company size, industry, segment, and
  likely persona all align with the primary ICP segment defined
  in icp.md
20 points: Strong match — matches the primary segment on 3 of
  4 dimensions (size, industry, segment, persona)
15 points: Moderate match — matches a secondary ICP segment or
  partially matches the primary segment on 2 dimensions
10 points: Weak match — tangential fit, not a named segment in
  icp.md but plausible given the category
0–5 points: Poor fit — company profile does not match any ICP
  segment defined in icp.md

CRITERION 2 — Buying Readiness (0–25)
Measures how likely this account is to be in an active buying
cycle now or within the next 90 days.

25 points: Strong active signal — a Hot trigger event was
  detected in prior intelligence, a known evaluation is underway,
  or direct interest has been expressed
20 points: Warm signal — a trigger event signal exists but is
  not confirmed active, or known dissatisfaction with a current
  vendor has been noted
15 points: Moderate signal — one trigger event indicator is
  present but unconfirmed
10 points: Latent potential — no known trigger event but the
  company profile and segment suggest a likely near-term need
0–5 points: No signal — no evidence of buying readiness;
  cold outreach only

CRITERION 3 — Revenue Potential (0–25)
Measures the expected deal value and strategic importance of
this account if it converts.

25 points: High-value account — company size and profile suggest
  a top-tier deal; closely resembles named customers in
  proof_points.md; in a high-growth segment per market.md
20 points: Strong potential — above-average deal size expected;
  good alignment with a proven segment
15 points: Moderate potential — average expected deal size for
  the ICP; standard segment fit
10 points: Below average — smaller company or segment with lower
  typical deal value based on ICP definitions
0–5 points: Low potential — company profile suggests a deal size
  below the threshold worth pursuing with ABM-level resources

CRITERION 4 — Relationship Warmth (0–25)
Measures the strength of existing relationships and engagement
history with this account.

25 points: Warm relationship — a named contact in a buying
  committee role, prior engagement, or a direct referral from
  a known connection
20 points: Known contact — someone at the company is known but
  the relationship has not been developed
15 points: Indirect connection — a mutual contact, event
  attendance in common, or documented content engagement
10 points: Weak signal — the company has engaged with content
  or visited relevant pages but no direct contact is known
0–5 points: Cold — no known relationship or engagement history
─────────────────────────────────────────────────────────────────
```

For each account, produce this entry:

```
Account: [name]
ICP Fit: [score]/25 — [one sentence connecting the score to the
  specific icp.md criteria that determined it — name the segment
  or dimension that drove the score]
Buying Readiness: [score]/25 — [one sentence — name the specific
  signal if one exists; if no signal exists, name the absence]
Revenue Potential: [score]/25 — [one sentence — reference a named
  customer from proof_points.md if comparability influenced the
  score]
Relationship Warmth: [score]/25 — [one sentence — name the
  specific contact or engagement type if known]
Total Score: [sum]/100
Confidence: [High — strong data on all four criteria /
  Medium — partial data, some criteria estimated /
  Low — minimal information provided, score is an estimate]
Competitor flag: [Yes — [competitor name] and what is known /
  No]
```

---

## Step 4 — Assign Tiers

After scoring all accounts, assign each to a tier using these
thresholds.

**Default thresholds:**
- Tier 1 — Strategic: 80–100
- Tier 2 — Full ABM: 60–79
- Tier 3 — Light ABM: 40–59
- Tier 4 — Programmatic: 0–39

**Relative tiering rule:**
If the absolute thresholds produce fewer than 3 Strategic accounts
or more than 40% of the list in Strategic, apply relative tiering
instead: top 10–15% of scores → Strategic, next 25% → Full ABM,
next 40% → Light ABM, remainder → Programmatic. Flag clearly when
relative tiering has been applied and note the score ranges it
produced.

---

**Tier 1 — Strategic (score 80–100)**

Treatment: Maximum resource allocation. A fully personalised ABM
program built around this account specifically.

What this tier warrants:
- Executive dinner, roundtable invitation, or high-value direct
  event designed around this account's profile
- Direct mail or gifting campaign tied to a specific pain point
  or trigger event
- Personalised LinkedIn outreach sequence referencing this
  account's specific situation
- Dedicated email sequence with named-account personalisation —
  not segment-level copy applied to the account
- Weekly Trigger Monitor coverage — every run checks this account
  at full depth
- A joint sales and marketing account plan before any outreach
  begins — marketing and sales aligned on message, timing, and
  ownership of each step

Typical account count: 5–15% of the total list. If the list
produces more than 15% Strategic, review whether the input list
was pre-filtered or whether relative tiering should be applied.

---

**Tier 2 — Full ABM (score 60–79)**

Treatment: Full multichannel ABM program without high-touch or
one-to-one tactics.

What this tier warrants:
- LinkedIn Sponsored Content with account-level targeting applied
- Personalised email sequence — segment-level personalisation
  is acceptable at this tier; account-specific is preferred but
  not required
- Bi-weekly Trigger Monitor coverage — checked on alternate weeks
  at full search depth
- Content personalised to the account's segment and persona if
  not to the individual account

Typical account count: 20–30% of the total list.

---

**Tier 3 — Light ABM (score 40–59)**

Treatment: Segment-level personalisation. Not account-specific.
ABM resources are not justified at this tier without a trigger
event.

What this tier warrants:
- Standard paid media targeting the account's segment — not
  account-specific targeting
- Standard nurture sequence for the relevant persona from the
  active context files
- Monthly Trigger Monitor coverage — checked once per month at
  reduced search depth
- No direct personalised outreach unless a trigger event is
  detected that justifies upgrading the account to Tier 2

Typical account count: 30–40% of the total list.

---

**Tier 4 — Programmatic (score 0–39)**

Treatment: Standard demand generation. No ABM resources allocated.

What this tier warrants:
- Standard paid media only — the account may be in the targeting
  audience but receives no account-specific treatment
- Generic nurture sequence for the relevant segment
- Trigger Monitor coverage only if a signal is actively detected —
  not proactive monitoring; the account is not on the search list
- Revisit scoring in 90 days if no signal has been detected

Typical account count: 20–30% of the total list.

---

## Step 5 — Display Results

Display the full scored and tiered list before saving. Do not
save any file before displaying results and receiving explicit
confirmation.

```
─────────────────────────────────────────────────────────────────
ABM ACCOUNT PRIORITISATION RESULTS
─────────────────────────────────────────────────────────────────
Total accounts scored: [number]
Tiering method: [Absolute thresholds / Relative tiering — note
  if relative tiering was applied and why]

Strategic (Tier 1): [count] accounts
Full ABM (Tier 2): [count] accounts
Light ABM (Tier 3): [count] accounts
Programmatic (Tier 4): [count] accounts
─────────────────────────────────────────────────────────────────
```

---

**TIER 1 — STRATEGIC**

For each Strategic account:

```
[Account name] — [total score]/100
  ICP Fit: [score]/25
  Buying Readiness: [score]/25
  Revenue Potential: [score]/25
  Relationship Warmth: [score]/25
  Confidence: [High / Medium / Low]
  Competitor flag: [Yes — detail / No]

  Why Strategic: [Two sentences connecting the score to specific
    findings — what makes this the highest-priority account and
    what the combination of scores signals about timing and approach]

  Recommended next action:
    [One of the following — display the recommendation, do not
    auto-run anything:]

    "Run Trigger Monitor for fresh signals before outreach —
    this account warrants real-time intelligence before the first
    message is sent."

    "Run Email Nurture Sequencer — ABM type — for this account.
    Trigger event context available."

    "Run Campaign Writer — ABM phase — for this account's persona.
    Personalised copy needed before outreach begins."

    "Escalate to Sales for a joint account plan before any
    marketing outreach — relationship warmth score and deal
    potential justify a sales-led approach."

  Ready-to-use brief:
    "[Paste this directly into the orchestrator to act on this
    account — exact brief text, filled in for this account's
    specific situation, persona, segment, and recommended angle
    based on context files]"
```

---

**TIER 2 — FULL ABM**

Same format as Tier 1, including recommended next action and
ready-to-use brief.

---

**TIER 3 — LIGHT ABM**

Abbreviated format — score breakdown and confidence only. No
recommended next action or ready-to-use brief unless a trigger
event signal is noted.

```
[Account name] — [total score]/100
  ICP Fit: [score]/25 | Buying Readiness: [score]/25 |
  Revenue Potential: [score]/25 | Relationship Warmth: [score]/25
  Confidence: [High / Medium / Low]
  Competitor flag: [Yes — detail / No]
  Treatment: Standard paid media and nurture. Monthly Trigger
  Monitor coverage. No direct outreach until a trigger event is detected.
```

---

**TIER 4 — PROGRAMMATIC**

Abbreviated format — score and treatment note only.

```
[Account name] — [total score]/100
  Treatment: Standard demand gen only. Revisit in 90 days.
  Competitor flag: [Yes — detail / No]
```

---

```
─────────────────────────────────────────────────────────────────
SUMMARY OBSERVATIONS
─────────────────────────────────────────────────────────────────
[3–5 sentences covering: which segments dominate the list, where
buying readiness is concentrated, which competitor displacement
opportunities are present, whether the list is skewed toward
any particular tier, and any patterns that suggest how the ABM
programme should be sequenced — which tier to activate first,
whether a trigger event is creating urgency across multiple
accounts in the same segment, or whether relationship warmth is
the primary differentiator between Tier 1 and Tier 2 accounts
on this list]
─────────────────────────────────────────────────────────────────
```

---

## Step 6 — Save Output

After displaying results, ask:

> "Full results are above. Would you like to save the output?
>
> If yes, I will save two files:
>
> File 1 — Full prioritised account list:
> abm_prioritised_accounts_[company]_[YYYY-MM-DD].md
> Saved to outputs/ — includes all scored accounts with tier,
> score breakdown, rationale, and recommended next actions.
>
> File 2 — Trigger Monitor feed file:
> abm_tiers_[company]_[YYYY-MM-DD].md
> Saved to outputs/ — contains only tier assignments. The Trigger
> Monitor reads this file to adjust search depth per account when
> it is present. It runs at full depth for all accounts if this
> file does not exist.
>
> Type 'save' to write both files or 'skip' to finish without saving."

Only save after explicit confirmation. Never save automatically.

---

After saving, display:

> "Files saved. When you next run the Trigger Monitor, it will
> detect the tier file and adjust search depth per account:
> Strategic and Full ABM accounts at full depth, Light ABM at
> reduced depth, Programmatic at signal-only coverage.
>
> The Trigger Monitor runs correctly without the tier file if you
> prefer not to use it."

---

## Rules This Skill Must Always Follow

1. Always read context/icp.md before scoring — never score accounts
   from general knowledge about the category. Every ICP Fit score
   must be tied to a specific segment or dimension defined in icp.md.

2. Always display the scoring rubric before producing scores —
   the user should understand what each criterion measures before
   seeing the results.

3. Always display the full scored list before saving — never save
   without the user seeing the results first.

4. Always flag competitor-using accounts — these are displacement
   opportunities and should be noted regardless of tier assignment.

5. Always note Confidence level per account — low-information
   accounts should be clearly flagged so the user knows which
   scores are estimates and which are grounded in real data.

6. Always apply relative tiering if the absolute threshold
   distribution produces fewer than 3 Strategic accounts or more
   than 40% Strategic accounts. Always flag when relative tiering
   was applied and note the score ranges it produced.

7. Never update context/target_accounts.md — this skill produces
   separate output files only. Account history is managed by the
   Trigger Monitor.

8. Never auto-run the recommended next action — display the
   recommendation and the ready-to-use brief, and wait for the
   user to decide.

9. Never save without explicit confirmation.

10. Always read the active company name from the first line of
    context/icp.md for output file naming.

11. Follow the file naming convention in CLAUDE.md for all
    output files.

12. Accept both pasted lists and CSV files — detect format
    automatically and note which format was used in the pre-flight
    block.

13. No company names, product names, competitor names, or
    industry-specific terms are hardcoded in this skill. Every
    reference to the company, its buyers, its market, and its
    competitors comes from context files read at runtime.
