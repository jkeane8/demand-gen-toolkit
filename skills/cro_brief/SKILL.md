# CRO Brief
## Diagnoses landing page conversion problems and produces
## a prioritised test plan with rewritten challengers,
## sample size requirements, and success metrics.

---

## What This Skill Does

Takes landing page content in any format — pasted copy,
pasted HTML, or a plain English description — and evaluates
it against four inputs simultaneously: the ICP buyer
vocabulary and pain points, the brand voice rules, the
proof points available, and the ad copy that sent traffic
to the page.

Identifies where message continuity breaks down between
the ad and the page. Produces a full diagnosis and three
prioritised tests. For each test: a hypothesis, a control,
a challenger, minimum sample size, and success metrics.

Stays close to the existing copy unless the diagnosis
shows the angle is fundamentally wrong. When a full
reframe is chosen, states explicitly why a targeted
improvement was insufficient.

Connects to Performance Grader findings when available —
if a grader report exists, its diagnosis is the starting
hypothesis, not a suggestion to consider.

Accepts HTML or plain text and detects which format was
provided automatically.

---

## Step 1 — Read Before Evaluating

Read all of these files before touching the page content.
Every finding must connect back to something specific in
these files — not general CRO advice.

**Required files:**

context/icp.md
Read for: exact buyer vocabulary, pain points by segment,
what triggers buyers to act, and the language they use
to describe their own problems. Every page element will
be evaluated against whether it speaks the buyer's
language or the vendor's language. These are different.
Vendor language describes the product. Buyer language
describes the pain.

context/brand_voice.md
Read for: tone scale by segment, words and phrases to
avoid, and calibration sentences showing what on-brand
and off-brand copy look like. Flag any page element that
uses a word on the avoid list or sounds like the
anti-examples. Brand voice violations are often invisible
to the people who wrote the page.

**Optional files — check and use if found:**

context/proof_points.md
If found: read for named customer results. Evaluate
whether the landing page is using the most relevant proof
point for the persona and funnel stage. A page targeting
a Head of Localization at decision stage should lead with
Intel 40% — not a generic efficiency claim. A wrong proof
point is as bad as no proof point.

outputs/performance/*.md
If a Performance Grader report exists: read it before
evaluating the page. The grader's diagnosis is the
starting hypothesis. Do not repeat analysis the grader
already did — extend it. If the grader said "landing
page is probably dropping the vendor management tax
framing," verify that hypothesis against the actual
page content and either confirm or refine it.

outputs/copy_*.md
Scan outputs/ for any copy file that matches the
campaign, persona, or angle of the page being evaluated.
This includes paid search copy, LinkedIn ad copy, and
cold email copy. If found, compare the ad's opening hook,
pain point, proof point, and CTA against the landing page.
Message continuity failures — where the ad promises one
thing and the page delivers another — are the most common
and highest-impact conversion problems.

outputs/landing_page_brief_*.md
If a Landing Page Brief exists for this page: read it
and check whether the page was built according to the
spec. If the spec was followed but conversion is still
low, the brief itself may have been wrong — note this
as a finding.

Display this before evaluating:

---
CRO BRIEF
─────────────────────────────────────
Page being evaluated: [URL if provided,
  or "pasted content"]
Input format detected: [HTML / Plain
  text copy / Description]
Persona: [inferred from page content
  or stated in brief]
Funnel stage: [inferred from CTA and
  content, or stated in brief]
Segment: [inferred or stated]
Ad copy file found: [filename if found
  in outputs/, or "None found —
  continuity check skipped"]
Performance Grader finding: [one-line
  summary of relevant finding if a
  report was found, or "No Performance
  Grader report found — evaluating
  from context files only"]
Landing page brief found: [filename
  if found, or "No brief found"]
Context files loaded:
[✓/✗] context/icp.md
[✓/✗] context/brand_voice.md
[✓/✗] context/proof_points.md
Evaluating now.
─────────────────────────────────────
---

---

## Step 2 — Parse the Input

Before diagnosing anything, extract the key page elements
from whatever format was provided and display them. This
gives the human a chance to confirm the extraction is
correct before the diagnosis runs.

**If HTML was pasted:**
Strip all structural tags, scripts, tracking pixels, and
CSS classes. Extract only:
- Page title and meta description
- H1 headline
- H2 subheadline or supporting statement
- Above-the-fold body copy
- Primary proof point or case study referenced
- Form fields and labels
- Primary CTA button text
- Any secondary CTAs
- Trust signals: logos, certifications, review badges
- Below-the-fold body copy summary

Display the extracted elements clearly. Ask one
clarifying question if a critical element is ambiguous
— for example, if it is unclear which of two buttons
is the primary CTA, or if a form field label is
truncated. Do not ask multiple questions.

**If plain text copy was pasted:**
Work from the copy as provided. Identify the structural
elements above as best as possible from the text.
Note any elements that could not be clearly identified.

**If a description was provided:**
Work from the description. Note which elements were not
described and flag them as unknown — these are gaps in
the evaluation that may reduce diagnostic confidence.

---

## Step 3 — Message Continuity Check

Before evaluating individual page elements, check whether
the ad and the landing page are telling the same story.
This check runs only if an ad copy file was found in
outputs/. If none was found, skip this step and note it.

**If an ad copy file was found:**

Compare these five elements between the ad and the page:

1. Opening hook — does the landing page headline continue
   the frame the ad established, or does it open a
   different conversation?

2. Pain point — does the page name the same pain the ad
   addressed, using the same vocabulary?

3. Awareness level — is the page written for the same
   Schwartz awareness level as the ad? An ad written for
   Problem-aware should land on a page written for
   Problem-aware or Solution-aware — not a page that
   assumes Most-aware.

4. Proof point — does the page use the same proof point
   the ad referenced, or does it introduce a different
   one without context?

5. CTA commitment — does the page CTA ask for a similar
   level of commitment as the ad CTA, or does it escalate
   prematurely?

Display the continuity check as a markdown pipe table:

| Element | Ad | Page | Match |
| --- | --- | --- | --- |
| Opening hook | [ad hook] | [page headline] | ✓/✗ |
| Pain point | [ad pain] | [page pain] | ✓/✗ |
| Awareness level | [ad level] | [page level] | ✓/✗ |
| Proof point | [ad proof] | [page proof] | ✓/✗ |
| CTA commitment | [ad CTA] | [page CTA] | ✓/✗ |

Any ✗ in this table is a conversion problem. Continuity
failures are almost always higher-impact fixes than any
individual page element optimisation. A continuity
failure becomes Test 1 unless the diagnosis reveals
something more damaging below the fold.

---

## Step 4 — Full Page Diagnosis

Evaluate every major page element against four criteria.
Apply the Performance Grader finding as the starting
hypothesis where one exists — confirm or refine it,
do not ignore it.

**Four evaluation criteria for every element:**

1. Buyer vocabulary vs. vendor vocabulary
   Does this element use the words buyers use to describe
   their own problem, or the words the company uses to
   describe its own product? Buyer vocabulary is found
   in icp.md. Vendor vocabulary is what the company
   invented. Buyers skim past vendor vocabulary.

2. Brand voice compliance
   Does this element violate the avoid list or sound
   like the anti-examples in brand_voice.md? Scan every
   element explicitly — do not assume compliance.

3. Proof point relevance
   Is the proof point used the most relevant one for
   this persona and funnel stage? Check against
   proof_points.md. A proof point that is wrong for the
   persona (e.g. a consumer example on an enterprise page)
   can actively reduce credibility.

4. Awareness level match
   Is this element written for the awareness level of
   the buyer arriving from the ad? A Most-aware CTA on
   a page receiving Problem-aware traffic will kill
   conversion. Reference the ad copy file if found.

**Elements to evaluate in order:**
1. Headline
2. Subheadline
3. Above-the-fold body copy
4. Primary proof point — placement and content
5. Form — number of fields, labels, friction level
6. Primary CTA — text, placement, specificity
7. Trust signals — relevance and placement
8. Below-the-fold content — supports or distracts

**Rating for each element:**
Strong — working as intended
Adequate — functional but improvable
Weak — likely hurting conversion
Critical — almost certainly causing significant conversion
  loss and should be addressed in the first test

---

## Step 5 — Produce Three Prioritised Tests

After the diagnosis, produce exactly three tests ranked
by expected conversion impact — highest impact first.
Never produce more than three. A focused test roadmap
is more useful than an exhaustive list.

**Prioritisation logic — apply in this order:**
1. Message continuity failures rank above all individual
   element optimisations. A headline mismatch with the
   ad is more important than a subheadline word choice.
2. Above-the-fold elements rank above below-the-fold.
3. Elements rated Critical rank above elements rated Weak.
4. Form friction ranks high — reducing fields from 6 to
   3 typically produces larger lifts than headline
   rewrites.

**Display each test in this format:**

---
─────────────────────────────────────
TEST [N] — [Element name]
Expected impact: [High / Medium / Low]
Why this ranks [N]: [one sentence connecting the ranking
  to the diagnosis]
─────────────────────────────────────

HYPOTHESIS
We believe [element] is causing [problem] because
[evidence from diagnosis]. Changing [element] to
[direction] will improve [metric] because [buyer
behaviour reasoning].

CONTROL — currently on the page
[Exact copy or description of the current element]

CHALLENGER — what to test against it
[The rewritten version — this should be copy-ready,
not a direction. Write the actual words.]

Creative latitude applied:
[Choose one and explain:]
Stay close — the angle is sound, the execution needs
  tightening. The challenger improves word choice,
  specificity, or proof point usage without changing
  the underlying frame.
Moderate reframe — the angle is partially right but
  is missing a key buyer pain or using the wrong proof
  point. The challenger shifts the emphasis without
  rebuilding the page.
Full reframe — the diagnosis shows the entire angle
  is wrong. The page is addressing the wrong pain,
  wrong persona, or wrong awareness level. State clearly
  why a full reframe was chosen over a targeted
  improvement and what the new frame is.

Why this challenger:
[Two to three sentences connecting the challenger to
specific findings from icp.md, the ad copy file, or
the Performance Grader — not generic CRO advice.
Name the source: "Per icp.md, the Head of Localization
describes this pain as..." or "The ad used [hook] —
the challenger continues that frame by..."]

SUCCESS METRIC
Primary metric: [conversion rate / click-through rate
  / form completion rate / scroll depth — whichever
  is most directly affected by this element]
Current baseline: [from Performance Grader if available,
  or "unknown — establish baseline before testing"]
Target: [specific improvement, e.g. "conversion rate
  improves from 3.4% to 5%+" — not "conversion rate
  improves"]
Secondary metric: [what else to watch that might
  indicate unintended effects — e.g. time on page,
  scroll depth, or bounce rate]

MINIMUM SAMPLE SIZE
[Calculate using this formula:
Current conversion rate = X%
Target conversion rate = Y%
Minimum visitors per variant =
  16 × (X × (1-X)) / (Y-X)²
Round up to nearest 100.
Assumption: 80% statistical power, 95% confidence
  interval, two-tailed test.
State: at [X visitors/month if known from Performance
  Grader], this test reaches significance in approximately
  [Y weeks].
If traffic is unknown: "Traffic volume not provided —
  divide minimum sample size by your monthly unique
  visitors to estimate test duration."]

IMPLEMENTATION NOTES
Tool: [VWO / Optimizely / Google Optimize / Manual A/B
  page swap — recommend the simplest tool that handles
  this test type]
Setup: [one to three sentences on how to configure
  the test — what to change, what to keep constant,
  what to watch for in the first week]
Do not change simultaneously: [any other page element
  that must remain constant while this test runs —
  changing two things at once makes results
  uninterpretable]
─────────────────────────────────────
---

[Repeat for all three tests]

---

## Step 6 — Test Sequence Recommendation

After all three tests, display a sequencing recommendation.

---
RECOMMENDED TEST SEQUENCE
─────────────────────────────────────
Run first: Test [N]
Why: [one sentence — highest impact, fastest to
  implement, or its result is needed to inform Test 2]

Run second: Test [N]
Why: [one sentence — depends on or is informed by
  Test 1, or is the next highest independent impact]

Run third: Test [N]
Why: [one sentence]

Parallel testing note:
[If any two tests can run simultaneously without
  interfering, state which ones and why. If all three
  must run sequentially, explain why — typically because
  Test 2 changes an element that Test 1 already changed,
  or because the traffic volume is too low to split three
  ways reliably.]

Expected timeline to complete all three tests:
[Base this on typical B2B SaaS landing page traffic of
  1,000–5,000 unique visitors per month. State the
  assumption. If traffic volume is known from the
  Performance Grader report, use the actual figure and
  note it. Tests at low traffic volumes require longer
  run times — flag if any test requires more than
  8 weeks to reach significance, as this reduces
  the value of the test.]
─────────────────────────────────────
---

---

## Step 7 — Save Option

After all tests and the sequence recommendation, ask:

"Would you like to save this CRO brief?

It will be saved as:
cro_brief_[page or angle description]_[company]_[date].md
in outputs/

This gives you a dated test plan you can share with
your web team or use as a brief for implementation."

Save only on explicit confirmation.
Follow the file naming convention in CLAUDE.md.
Read the active company name from the first line of
context/icp.md before naming the file.

---

## Rules

Always read context files before evaluating — never
diagnose from general CRO knowledge alone. Every
finding must connect to a specific buyer insight from
icp.md, brand_voice.md, or proof_points.md.

Always check outputs/ for a matching ad copy file —
message continuity between ad and page is the most
common high-impact CRO problem and must be checked
before evaluating individual elements.

Always check outputs/performance/ for a Performance
Grader report — if one exists it is the starting
hypothesis, not a suggestion.

Always extract page elements before diagnosing when
HTML is provided — never attempt to diagnose from
raw HTML without parsing it first.

Stay close to existing copy unless the diagnosis shows
the angle is fundamentally wrong. When a full reframe
is chosen, state explicitly why a targeted improvement
was insufficient.

Always rank tests by expected conversion impact —
never rank in page order or arbitrary order.

Always calculate minimum sample size — never recommend
a test without stating how much traffic it requires
and how long it will take to reach significance.

Always specify what not to change while each test runs
— changing multiple elements simultaneously makes
results uninterpretable.

Never recommend more than three tests.

Never save without explicit confirmation.

Read the active company name from context/icp.md for
file naming. Follow the naming convention in CLAUDE.md
for all output files.
