# A/B Test Tracker
## Tracks all tests run across copy, audience, landing page,
## email, and channel formats
## Reads from outputs/ files and accepts manual entry
## Produces full test history and pattern summary
## Flags Variant Scorer prediction vs live result discrepancies
## Recommends next tests based on gaps and patterns

---

## What This Skill Does

Scans every relevant file in outputs/ and builds a complete
record of every A/B test that has been run or planned across
the toolkit — copy tests, audience tests, landing page tests,
email tests, channel tests, and format tests.

The scan covers: Performance Grader reports (for live results),
campaign copy files (for Variant Scorer predictions), CRO
briefs (for planned and completed page tests), email sequence
files (for subject line and structure tests), LinkedIn strategy
files (for audience and format tests), paid social audience
files (for targeting tests), and any previously saved tracker
files (to continue accumulated history rather than start fresh).

After scanning, the skill offers manual entry for any test that
ran but has not been recorded in an outputs/ file.

With the full test log assembled, the skill produces three
outputs: a pattern analysis identifying what is consistently
winning or losing across tests for each persona and segment,
a Variant Scorer calibration section flagging every instance
where a pre-launch prediction did not match the live result,
and a prioritised list of recommended next tests based on gaps
in coverage and patterns that need confirmation.

Nothing is updated automatically. Patterns and findings are
surfaced for human review. The user decides what to do with them.

Runs on demand — triggered by any mention of A/B testing, test
history, what has been tested, test patterns, or what to test next.

---

## Step 1 — Read Before Scanning

Before touching any file in outputs/, read the context files
that make the test history interpretable.

---

### Required files

**context/icp.md**
Read for: every persona name, segment definition, company size
range, industry, pain points, and funnel stage vocabulary. All
test results are only meaningful in relation to the audience
they were tested against. A copy angle that consistently wins
with one persona may consistently lose with another — the test
log organises everything by persona and segment precisely
because of this. Never present a finding as universal when it
applies only to one audience.

**context/brand_voice.md**
Read for: tone scale by segment, vocabulary to use and avoid,
and the calibration sentences that define on-brand and off-brand
copy. Used in pattern analysis to flag whether winning test
variants consistently align with or deviate from brand voice
guidelines. If copy that violates the avoid list is winning
tests, that is a finding — surface it, do not suppress it.

---

### Optional files to scan in outputs/

Scan outputs/ for each file type below. Read every file found.
Note what test data it contains. Some files will contain
completed tests with results. Others will contain planned tests
with no results yet. Log both — planned tests are tracked as
awaiting results.

**outputs/performance_\*.md**
Performance Grader reports. Read for any A/B test results
reported against live campaign data — variant comparisons,
element-level performance grades, and diagnostic notes that
identify which variable underperformed and why. These are the
highest-confidence entries in the test log because they contain
real outcome data.

**outputs/copy_\*.md**
Campaign copy files. Read for Variant Scorer annotations on
each copy variant — formula used, awareness level, angle, score
out of 100, and best-for notes. These are pre-launch predictions.
Cross-reference against any Performance Grader data found for
the same campaign. If a Variant Scorer file exists and a
corresponding Performance Grader report exists: log the
prediction alongside the result and flag any discrepancy.

**outputs/cro_brief_\*.md**
CRO test plans. Read for: hypothesis, control, challenger copy,
primary success metric, minimum sample size, and implementation
notes. If a corresponding Performance Grader report exists with
results: log as a completed test. If no results exist yet: log
as a planned test awaiting data.

**outputs/ab_test_tracker_\*.md**
Previously saved tracker files. If found: read the full prior
test history and load all prior test entries before scanning
other files. The tracker accumulates history across runs — do
not rebuild from scratch when prior history exists. Merge prior
entries with new findings from this run. Assign new sequential
Test IDs continuing from the prior tracker's highest ID.

**outputs/email_nurture_\*.md** and **outputs/email_sequence_\*.md**
Email sequence files. Read for: subject line variants with
stated testing hypotheses, preview text options, send timing
recommendations, and any HubSpot A/B test configuration notes.
Log as planned tests if no performance data exists yet in a
corresponding Performance Grader report.

**outputs/linkedin_strategy_\*.md**
LinkedIn campaign strategy files. Read for: A/B testing plans
noted in the strategy — audience tests (job title variants,
company size variations), format tests (Single Image vs
Document Ad), and copy tests (variant rotation plans). Log as
planned tests if no results are recorded.

**outputs/paid_social_audiences_\*.md**
Paid social audience files. Read for: A/B testing recommendations
per channel — audience source tests (lookalike vs interest-based),
format tests (skippable vs non-skippable, in-stream vs in-feed),
creative direction tests noted for Reddit or YouTube. Log as
planned tests.

**outputs/variant_score_\*.md**
Variant Scorer output files. Read for: scores per variant, the
reasoning behind each score, issue flags with severity ratings,
and launch recommendations. This is the primary source for
Variant Scorer predictions. Cross-reference every variant scored
here against any Performance Grader data for the same campaign.

---

Display before scanning:

```
A/B TEST TRACKER
─────────────────────────────────────────────────────────────────
Mode: [Full scan — no prior tracker found /
  Update — prior tracker loaded with [X] tests]
Files found in outputs/:
  [List every file found, one per line, with a one-word
  description of what test data it may contain]
Prior tracker file: [Yes — [filename], [X] prior tests loaded /
  No — starting fresh]
Manual entry: Offered after scan completes
Context files loaded:
[✓ or ✗] context/icp.md
[✓ or ✗] context/brand_voice.md
Active company: [read from first line of context/icp.md]
Scanning now.
─────────────────────────────────────────────────────────────────
```

---

## Step 2 — Accept Manual Test Entry

After completing the outputs/ scan, display:

> "Scan complete. I found [X] tests across [Y] files.
>
> Would you like to add any tests that ran but are not yet
> recorded in the files above? This is common for tests run
> directly in ad platforms or email tools where the result
> was not fed back through a Performance Grader report.
>
> To add a test manually, provide the following:
>
> **TEST TYPE** — choose one:
> - Copy test (headline, body, CTA)
> - Audience test (targeting variable)
> - Landing page test (page element)
> - Email test (subject line, send time, sequence structure)
> - Channel test (comparing two channels for the same objective)
> - Format test (ad format, content type)
>
> **WHAT WAS TESTED** — control vs challenger
> Describe both — exact copy if you have it, a description
> if not. For copy tests: include the specific element (e.g.,
> "headline only — body copy was identical across both variants").
>
> **PERSONA AND SEGMENT** — who was this tested against?
>
> **CHANNEL** — where did the test run?
>
> **RESULT** — which won and by how much?
> Include the metric used: CTR, conversion rate, open rate,
> click rate, or whatever was measured.
>
> **SAMPLE SIZE** — how many impressions, sends, or visitors
> per variant?
>
> **STATISTICAL SIGNIFICANCE** — was the result statistically
> significant? If unknown, note this — the tracker will flag
> low-confidence results.
>
> **VARIANT SCORER PREDICTION** — did the Variant Scorer score
> these variants before launch? If yes, which variant did it
> predict would win?
>
> You can add as many tests as you have. Type 'done' when
> finished, or press Enter to skip manual entry and proceed
> with scanned data only."

Process each manual entry as it is provided. Assign a
sequential Test ID to each entry before moving to the next.
Confirm each entry is logged before proceeding.

---

## Step 3 — Build the Test Log

After scanning and manual entry, build the complete test log.
Organise by test type. Within each type, organise by persona
and segment — most recent tests first.

For each test log entry:

```
─────────────────────────────────────────────────────────────────
TEST ID: [sequential number — continues from prior tracker if
  one was loaded]
Test type: [Copy / Audience / Landing Page / Email /
  Channel / Format]
Channel: [where the test ran — Google Ads, LinkedIn,
  email, landing page, etc.]
Persona: [target persona from icp.md — or "Unknown" if
  not recorded]
Segment: [target segment from icp.md — or "Unknown"]
Funnel stage: [Awareness / Consideration / Decision /
  Unknown]
Date: [date of test or date file was saved — note if
  estimated from filename]
Status: [Completed — result known / Planned — no results
  yet / In progress — test is live]
─────────────────────────────────────────────────────────────────
WHAT WAS TESTED
Variable: [the specific element tested — be precise, e.g.
  "headline angle: pain-led vs proof-led" or "audience:
  job title exact match vs broad seniority targeting"]
Control: [description or exact copy of the control variant]
Challenger: [description or exact copy of the challenger]

RESULT
Winner: [Control / Challenger / No significant difference /
  Awaiting results]
Margin: [% improvement in primary metric — or "N/A" if
  awaiting results]
Primary metric: [CTR / conversion rate / open rate / CPL /
  whatever was measured]
Sample size: [per variant if known — or "Unknown"]
Confidence: [High — statistically significant result at
  adequate sample size / Medium — trending but not yet
  significant / Low — insufficient sample size or
  significance not assessed / Awaiting results]

VARIANT SCORER CROSS-REFERENCE
Variant Scorer prediction: [which variant was predicted to
  win and its score — or "Not scored" if no Variant Scorer
  file covers this test]
Prediction matched result: [Yes / No / Partial /
  Awaiting results / Not applicable]
Discrepancy flag: [If the prediction did not match the live
  result: describe what the Variant Scorer got wrong and what
  the live result suggests. If prediction matched: "None." If
  not applicable: "N/A."]

SOURCE
[Filename this test was extracted from — or "Manual entry,
  [date entered]"]
─────────────────────────────────────────────────────────────────
```

If no tests are found and no manual entries are provided:

> "No test data found in outputs/ and no manual entries provided.
> The tracker is ready to record tests as they are created and
> completed. Run the tracker again after your first campaign,
> CRO brief, or Performance Grader report has been saved to
> outputs/."

---

## Step 4 — Pattern Analysis

After building the full test log, produce a pattern analysis.
A pattern requires evidence from two or more tests — single-test
findings are logged as hypotheses, not patterns. Label the
confidence of every pattern based on the number and quality of
the tests supporting it.

---

```
─────────────────────────────────────────────────────────────────
PATTERN ANALYSIS
─────────────────────────────────────────────────────────────────
Tests with results: [count]
Tests awaiting results: [count]
Patterns identified: [count]
Hypotheses (single-test findings): [count]
─────────────────────────────────────────────────────────────────
```

---

### Patterns by persona

For each persona with two or more completed tests:

```
[Persona name — from icp.md]
─────────────────────────────────────────────────────────────────
Copy patterns:
  Pattern: [description of the consistent finding — e.g.
    "pain-led headlines outperform outcome-led headlines
    in paid search for this persona"]
  Evidence: Test IDs [list]
  Confidence: [High — 3+ supporting tests / Medium — 2
    supporting tests / Low — 1 test, logged as hypothesis]
  Implication: [one sentence on what this means for future
    copy decisions targeting this persona]

Audience patterns:
  [Same format — targeting variables, match types, or
  audience sources that consistently win or lose]

Format patterns:
  [Same format — ad formats, content types, or creative
  approaches that consistently perform above or below
  average for this persona]

Funnel stage patterns:
  [Same format — whether certain angles or formats work
  differently at different funnel stages for this persona]
─────────────────────────────────────────────────────────────────
```

If a persona has only one completed test, note it as a
hypothesis entry under that persona. Do not promote it to
a pattern until a second confirming test exists.

---

### Variant Scorer calibration findings

Only display this section if one or more Variant Scorer
predictions did not match live results. If all predictions
matched or no Variant Scorer data exists: skip this section
or note "No calibration discrepancies found."

```
─────────────────────────────────────────────────────────────────
VARIANT SCORER CALIBRATION
─────────────────────────────────────────────────────────────────
Predictions assessed: [count]
Predictions matched live result: [count]
Discrepancies found: [count]
─────────────────────────────────────────────────────────────────

[For each discrepancy:]

Test ID: [number]
What the Variant Scorer predicted:
  [which variant it scored higher, its score, and the
  primary reason it was favoured — awareness level, pain
  point match, brand voice, or CTA appropriateness]
What actually won: [live result]
Margin of live result: [how much the actual winner beat the
  predicted winner]

Discrepancy type — choose the most accurate description:

  Awareness level mismatch: The Variant Scorer correctly
    evaluated copy quality but the audience was at a different
    Schwartz awareness level than the copy assumed — the
    predicted winner spoke to an audience that was either
    more or less aware than the people who actually saw it.

  Pain point mismatch: The scored pain point was technically
    accurate for the persona but was not the most resonant
    one at this particular time — a different pain was more
    acute when the test ran.

  Brand voice overcorrection: The Variant Scorer penalised
    copy that deviated from brand voice guidelines, but the
    live audience responded better to that deviation —
    the guidelines may need updating for this channel or
    persona.

  Sample size issue: The live result is not statistically
    significant. The Variant Scorer was not necessarily wrong
    — the test was inconclusive.

  Other: [describe]

Implication for future scoring:
  [One sentence on what this discrepancy suggests about how
  Variant Scorer criteria should be weighted for this
  persona, channel, or funnel stage in future runs]
─────────────────────────────────────────────────────────────────
```

---

### Overall patterns

After persona-level patterns, produce an overall summary
covering the following. Only include a finding if evidence
supports it — do not fill in sections with speculation.

```
─────────────────────────────────────────────────────────────────
OVERALL PATTERNS
─────────────────────────────────────────────────────────────────

Strongest performing angle across all tests:
[The single copy angle, format, or targeting variable that
has won most consistently across personas and channels —
cite the Test IDs. If no clear winner exists across
personas, say so rather than forcing a conclusion.]

Most tested variable:
[What has been tested most frequently — and whether the
depth of testing is sufficient to call the pattern
reliable, or whether more tests are needed to confirm it.]

Least tested areas:
[Test types, personas, channels, or funnel stages with
zero or minimal test coverage — these are the highest-
priority gaps. Be specific: "No landing page tests for
the VP Marketing persona" is more useful than "landing
pages are under-tested."]

Biggest surprise:
[The result that most contradicts what the context files
or Variant Scorer would predict — the finding that is
most worth acting on or investigating further.]

Brand voice alignment:
[Whether winning test variants consistently align with or
deviate from brand_voice.md guidelines — one sentence.
Flag any deviation pattern even if it conflicts with
existing guidelines.]
─────────────────────────────────────────────────────────────────
```

---

## Step 5 — Recommended Next Tests

After the pattern analysis, produce a prioritised list of
up to five recommended next tests. Base every recommendation
on one of four reasons: a gap in test coverage, a pattern
that needs a confirming third test, a high-impact variable
that was recommended by the CRO Brief or Campaign Writer
but has not yet been tested, or a Variant Scorer discrepancy
that needs a follow-up test to understand whether the scoring
criteria need adjustment.

Do not recommend tests just because they seem interesting.
Every recommendation must connect to a specific gap, finding,
or calibration need.

```
─────────────────────────────────────────────────────────────────
RECOMMENDED NEXT TESTS
─────────────────────────────────────────────────────────────────

PRIORITY 1
Test type: [Copy / Audience / Landing Page / Email /
  Channel / Format]
Variable to test: [exactly what should be held constant and
  exactly what should change between control and challenger]
Control: [description — what to use as the baseline]
Challenger: [description — what to test against it]
Reason for priority: [Gap / Pattern confirmation /
  High-impact untested variable / Variant Scorer discrepancy
  resolution]
Why this matters: [one sentence connecting this test to a
  specific finding or gap from the analysis above]
Persona: [who to test this against]
Channel: [where to run it]
Expected learning: [what this test will tell you regardless
  of which variant wins — a test that only produces useful
  learning if the challenger wins is a weak test]
Ready-to-use brief:
  "[Exact brief to paste into the orchestrator if the user
  wants to generate copy or a campaign brief for this test
  — filled in with specifics from the context files]"

[Repeat for Priority 2 through Priority 5]
─────────────────────────────────────────────────────────────────
```

---

## Step 6 — Save Option

After all sections display:

> "Would you like to save the test tracker?
>
> It will be saved as:
> ab_test_tracker_[company]_[YYYY-MM-DD].md
> in outputs/
>
> This file will be read automatically on the next run — your
> test history accumulates over time and patterns become more
> reliable as more tests are added. The more tests you log,
> the more useful the pattern analysis becomes.
>
> Every Performance Grader report, CRO brief, campaign copy
> file, and manual entry adds to this record. Running the
> tracker after each campaign cycle keeps the pattern analysis
> current.
>
> Type 'save' to write the file or 'skip' to finish without
> saving."

Save only on explicit confirmation. Never save automatically.

On save: note in the file header how many tests are recorded
and the date range they cover, so future runs can identify
the file quickly and assess how current the history is.

---

## Rules This Skill Must Always Follow

1. Always organise test history by persona and segment —
   patterns are only meaningful when grouped by audience.
   Never present a finding as universal when it applies only
   to one persona or one channel.

2. Always flag low-confidence results — tests with insufficient
   sample size or unknown statistical significance must be
   marked Confidence: Low or Confidence: Medium clearly.
   Never present a low-confidence result as a confirmed pattern.

3. Always cross-reference Variant Scorer predictions when copy
   files or variant score files exist in outputs/ — the
   calibration finding is one of the most valuable outputs
   of this skill. Never skip this step if relevant files
   are present.

4. Always surface brand voice deviations that win tests —
   if copy that violates the avoid list in brand_voice.md
   consistently outperforms compliant copy, that is a finding
   worth noting. Do not filter out results that contradict
   existing guidelines.

5. Always base next test recommendations on evidence — gaps
   in coverage, patterns needing confirmation, high-impact
   untested variables, or Variant Scorer discrepancies.
   Never recommend a test without connecting it to a specific
   finding.

6. Never update context files — surface patterns for human
   review only. The user decides what, if anything, to change
   in the context layer based on test findings.

7. Never present a single-test result as a pattern — a pattern
   requires evidence from two or more tests. Label single-test
   findings as hypotheses explicitly.

8. Always load prior tracker files if they exist in outputs/ —
   never start from scratch when accumulated history is
   available. Merge prior test entries with new findings and
   assign continuing sequential Test IDs.

9. Never save without explicit confirmation.

10. Read the active company name from the first line of
    context/icp.md for output file naming.

11. Follow the file naming convention in CLAUDE.md for all
    output files.

12. No company names, product names, competitor names, or
    industry-specific terms are hardcoded in this skill.
    Every reference to the company, its buyers, and its
    market comes from context files read at runtime.
