---

# Ad Group Organiser
## Maps keyword research and copy variants
## into a campaign-ready Google Ads structure
## Produces a strategy document and a
## Google Ads Editor-compatible CSV

---

## What This Skill Does
Takes the keyword file and copy variants
from a campaign and maps them together
into a complete Google Ads campaign
structure. Produces two files:

File 1 — Strategy document with full
rationale for every decision. The single
source of truth for how the campaign
should be built and why.

File 2 — Google Ads Editor CSV formatted
for direct import. Every row ready to
paste or upload without manual reformatting.

The strategy document is the brief.
The CSV is the build spec. Together they
eliminate the gap between campaign strategy
and campaign execution.

---

## Step 1 — Read Before Doing Anything

Before asking a single question, read all of these files:

### Required files

context/icp.md
Pay close attention to:
- Buyer segments and personas — ad group
  naming and structure should reflect
  how buyers actually think about their
  problem, not how the product is organized
- What triggers them to start looking —
  these trigger moments map directly to
  keyword intent and should inform which
  groups get highest bid priority
- The language they actually use —
  ad group names should use buyer
  vocabulary, not internal product terms

context/brand_voice.md
Pay close attention to:
- Words and phrases to avoid — these
  inform negative keyword lists. Terms
  on the avoid list often signal the
  wrong audience.
- Tone by segment — the copy variant
  assigned to each group must match
  the tone appropriate for that segment

context/competitors.md
Pay close attention to:
- Competitor displacement keywords —
  these need their own dedicated groups
  with specific copy that addresses
  competitor weaknesses without naming
  the competitor itself
- Topics competitors own strongly —
  these inform bid priority and budget
  allocation recommendations

context/deep/voice_of_customer.md
If found: use phrases that signal buying
intent to validate keyword-to-intent
mapping. If not found, proceed.

context/deep/market_gaps.md
If found: use keyword white space analysis
to identify which groups have lowest
competition and highest strategic value.
If not found, proceed.

### Required campaign files

Scan outputs/ for the most recent files
matching the active company:

outputs/keywords_*_[company]_*.md
The keyword research file this campaign
is based on. Required — cannot proceed
without it. Read every keyword, its
score breakdown, its group assignment,
its competitive context, and its
negative keyword notes.

outputs/copy_*_[company]_*.md
The most recent campaign writer output
matching this campaign. Required —
cannot proceed without it. Read every
variant, its headline formula, its
angle, its awareness level, and its
best for note.

outputs/landing_page_brief_*_[company]_*.md
If found: use to inform landing page
flag recommendations. If not found,
note that landing page briefs should
be produced for priority groups.

---

## Step 2 — Show All Questions At Once

After reading all files, display ALL
questions in one message. Wait for
answers before proceeding.

---
Before I map the campaign, I need
a few details. Answer all in one message:

1. CAMPAIGN NAME — what should this
   campaign be called in Google Ads?
   This becomes the Campaign column
   in the CSV.
   (e.g. "LILT — Enterprise Paid Search
   — Q2 2026" or suggest one based
   on the brief)

2. CAMPAIGN GOAL — what is the primary
   conversion action?
   - Demo booking
   - Case study download
   - Contact sales
   - Free trial signup
   - Other — describe it

3. CAMPAIGN TYPE — confirm this is
   Google Search (not Display or
   Performance Max)

4. DAILY BUDGET — what is the total
   daily budget for this campaign?
   (Used for budget allocation
   recommendations across groups. Say
   "not yet" if unknown — I will provide
   percentage allocations instead of
   dollar amounts)

5. GEOGRAPHIC TARGETING — where should
   these ads run?
   - US only
   - US and Canada
   - English-speaking globally
   - Specific regions — list them
   - Not sure — I will recommend based
     on the ICP

6. EXISTING CAMPAIGNS — are there any
   existing Google Ads campaigns running
   for this company that I should be
   aware of to avoid keyword conflicts?
   Say "none" or "not sure" if unknown.

7. PRIORITY SEGMENTS — are all buyer
   segments from the keyword file in
   scope, or should I focus on specific
   segments for this campaign?
   (e.g. "Commercial Enterprise only"
   or "all segments")
---

---

## Step 3 — Build The Ad Group Structure

After receiving answers, build the
complete ad group map. Follow these
rules precisely:

### Ad group naming convention
Format: [Campaign Theme] — [Intent Signal]

Examples:
"Vendor Pain — LSP Consolidation"
"Migration — TM Data Protection"
"Competitor Displacement — [Vendor]"
"ROI — Business Case Builder"
"Trend — Agentic AI"

Rules:
- Use buyer vocabulary from icp.md —
  never internal product names
- Intent signal describes what the
  buyer is trying to do, not what
  the product does
- Keep names under 50 characters for
  readability in Google Ads interface
- Each group should be distinct enough
  that a person building the campaign
  could not confuse two groups

### Ad group logic rules
- Maximum 10-15 keywords per group —
  tighter groups produce higher Quality
  Scores because ad relevance is stronger
- Keywords within a group must share
  the same core intent — a buyer
  searching "vendor management tax"
  and a buyer searching "TMS migration
  support" have different intents and
  should never be in the same group
- Competitor displacement keywords
  always get their own dedicated group —
  never mix branded competitor terms
  with non-branded terms
- Unexpected vocabulary keywords from
  the keyword file get their own group —
  their near-zero competition and high
  ICP match score make them the highest
  priority group and they should not
  be diluted with generic category terms

### Match type assignment rules
For each keyword, assign a primary
match type with reasoning, then flag
one alternative match type option:

Exact match [keyword]
Use when: keyword is specific enough
that only the right buyer would search
it (e.g. "vendor management tax
localization" — only a localization
practitioner searches this exact phrase)
Default for: unexpected vocabulary group,
high ICP vocabulary match score (20+/25)

Phrase match "keyword"
Use when: keyword has high intent but
buyers may search variations (e.g.
"enterprise TMS migration" could be
searched as "enterprise TMS migration
support" or "enterprise TMS migration
guide")
Default for: evaluation keywords,
outcome and ROI keywords

Broad match modifier
Use when: budget allows exploration
and the keyword has strong negative
keyword coverage to filter waste
Default for: category-level terms only
when exact and phrase are already
covered

Never assign broad match without
a minimum of 10 negative keywords
in that group — uncontrolled broad
match without negatives wastes budget.

### Copy variant assignment rules
For each ad group, assign the single
best matching copy variant from the
campaign writer output file. Then
flag one backup variant.

The primary variant assignment must:
- Mirror the search intent of the
  keywords in that group as closely
  as possible. A buyer who searched
  "vendor management tax localization"
  should see a headline that contains
  or references that exact phrase.
- Match the awareness level of the
  keyword intent. High-intent decision
  stage keywords need product-aware
  copy. Lower-intent keywords need
  solution-aware or problem-aware copy.
- Comply with all brand voice rules
  from brand_voice.md — particularly
  the avoid list.

If no existing variant is a strong
match for a group, flag the gap:
"No strong variant match — recommend
running Campaign Writer for [specific
angle] before launching this group."

### Negative keyword rules
For each group, negative keywords
are REQUIRED — not optional.

Pull from three sources in order:
1. The negative keyword notes in
   the keyword file for each term
   in this group
2. Cross-group negatives — terms
   from other groups that would
   cannibalize this group's traffic
   if a searcher's query matches both
3. Universal negatives that apply
   to all groups — flag these as
   campaign-level negatives to add
   once, not per-group

Present negative keywords as a
required checklist with match type:
[Exact] "translator jobs"
[Exact] "freelance linguist"
[Phrase] "translation certification"
[Broad] free

Label clearly: "These are required.
Launching without these will waste
budget on irrelevant clicks."

---

## Step 4 — Produce The Strategy Document

Structure the strategy document exactly
as follows:

---
AD GROUP STRATEGY
─────────────────────────────────────────
Campaign: [campaign name]
Source keyword file: [filename]
Source copy file: [filename]
Total ad groups: [number]
Total keywords: [number]
Strategy document created: [today's date]
─────────────────────────────────────────

### CAMPAIGN-LEVEL SETTINGS

Geographic targeting: [recommendation
with one sentence reasoning]

Campaign-level negative keywords:
[List terms that should be excluded
across the entire campaign — not just
one group. These are added once at
campaign level in Google Ads.]
[Exact] "[term]" — [one line on why]
[Phrase] "[term]" — [one line on why]

Bid strategy recommendation:
[Specific recommendation — Manual CPC
for new campaigns with no conversion
data, Target CPA once 30+ conversions
exist, Target ROAS once revenue data
is available. Include reasoning.]

─────────────────────────────────────────

### AD GROUPS

[For each ad group, use exactly this format:]

AD GROUP [N]: [Ad Group Name]
Priority: [1-5, where 1 is highest]
─────────────────────────────────────────

KEYWORDS
Primary match type recommendation and
reasoning for each keyword, plus one
alternative option:

[Exact] "keyword phrase" — Score: [X]/100
  Why exact: [one sentence]
  Alternative: [Phrase] — use if volume
  is too low for exact to serve reliably

[continue for each keyword in group]

─────────────────────────────────────────
ASSIGNED COPY VARIANT

Primary: Variant [N] — [variant name]
  Headline 1: [exact copy]
  Headline 2: [exact copy]
  Description: [exact copy]
  Why this variant: [one sentence on
  why this variant's angle matches
  the search intent of this group]
  Message match check: [one sentence
  confirming the headline mirrors or
  directly references the keyword
  intent — this is the most important
  Quality Score factor]

Backup: Variant [N] — [variant name]
Gap flag: [only include if no variant
is a strong match — describe exactly
what angle is missing and why it matters]

─────────────────────────────────────────
NEGATIVE KEYWORDS — REQUIRED CHECKLIST
☐ [Exact] "term" — [why]
☐ [Exact] "term" — [why]
☐ [Phrase] "term" — [why]
☐ [Broad] term — [why]

Do not launch this group without
adding all of the above.

─────────────────────────────────────────
QUALITY SCORE PREDICTION

Predicted Quality Score: [High/Medium/Low]
Primary driver: [the single biggest
factor affecting QS for this group]

Expected Ad Relevance: [Above Average/
Average/Below Average]
Why: [one sentence — does the headline
directly mirror keyword intent?]

Expected Landing Page Experience:
[Above Average/Average/Below Average]
Why: [one sentence — does a landing
page exist that continues the message
of the ad, or will the buyer land on
the wrong one?]

─────────────────────────────────────────
A/B TESTING RECOMMENDATION

Test 1 (launch with this):
Primary variant as specified above.
Run until: 500 impressions minimum,
100 clicks preferred before drawing
conclusions.

Test 2 (run simultaneously if budget
allows):
[Backup variant or a specific element
to test — headline formula, CTA wording,
or awareness level shift]
What to measure: [CTR, conversion rate,
or both — specify which metric determines
the winner for this group]

Test 3 (run after Test 1 vs Test 2
produces a winner):
[Next hypothesis to test once baseline
is established — e.g. "test a pain
question headline against the current
specificity formula"]

─────────────────────────────────────────
LANDING PAGE FLAG

[One of three options:]

EXISTING PAGE SUFFICIENT:
The current destination URL continues
the message of the ad adequately.
No dedicated page required at launch.

NEW PAGE RECOMMENDED:
A dedicated landing page would
meaningfully improve conversion rate.
Reason: [one sentence on the specific
message match gap]
Recommended action: Run Landing Page
Brief skill for this group before
launch or within first 30 days.

DEDICATED PAGE REQUIRED:
This group's copy makes a specific
promise that the current destination
does not fulfill. Launching without a
dedicated page will produce a poor
landing page experience score and
waste budget.
Reason: [one sentence]
Recommended action: Do not launch
this group until a dedicated page
exists.

─────────────────────────────────────────

[Repeat for each ad group]

─────────────────────────────────────────

### BUDGET ALLOCATION

[If daily budget was provided:]
Total daily budget: $[amount]
Recommended allocation:

Ad Group [N] — [Name]: $[amount]/day
  ([X]% of budget)
  Why: [one sentence — highest priority
  signal, lowest competition, etc.]

[If daily budget was not provided:]
Recommended percentage allocation:

Ad Group [N] — [Name]: [X]% of budget
  Why: [one sentence]

Budget principle applied:
Unexpected vocabulary groups get
disproportionate budget because their
near-zero competition means low CPC
and high buyer intent. Generic category
terms get minimum budget because high
competition means high CPC and lower
ICP specificity.

─────────────────────────────────────────

### LAUNCH SEQUENCE

Recommended order to launch ad groups:

Week 1 — Launch these groups first:
[List highest priority groups]
Why: [one sentence — these have the
clearest intent signal, lowest
competition, and strongest copy match.
Start here to build conversion data
before expanding.]

Week 2-3 — Add these groups:
[List medium priority groups]
Why: [one sentence]

Week 4+ — Add these groups when ready:
[List lower priority groups and any
groups flagged as needing dedicated
landing pages first]
Why: [one sentence]

─────────────────────────────────────────

### GAPS AND NEXT STEPS FOR THIS CAMPAIGN

Files that were missing:
[List any optional files checked but
not found, with one sentence on what
each would have contributed]

Landing page gaps:
[Summarize all groups flagged as needing
dedicated pages, with priority order]

Skills worth running next:
[List 2-3 skills not yet run that would
meaningfully improve this campaign's
performance — base on what was actually
missing from this run]

Data that would sharpen these recommendations:
[List 2-3 specific data points — actual
search volume, historical CPC data,
conversion rate from existing campaigns —
that would make recommendations more
precise. Note these require live campaign
data or a connected keyword tool.]

─────────────────────────────────────────

### SAVE CONFIRMATION

After displaying the full strategy
document ask:

"Would you like to adjust anything
before saving?

You can ask me to:
- Reassign a keyword to a different group
- Change a copy variant assignment
- Add or remove negative keywords
- Adjust the budget allocation
- Change the launch sequence order

Or type 'save' to write both output
files."

---

## Step 5 — Produce The Google Ads
## Editor CSV

After the strategy document is confirmed,
produce a CSV file formatted for direct
import into Google Ads Editor.

Use exactly these column headers in
exactly this order:

Campaign, Ad Group, Keyword, Match Type,
Max CPC, Final URL, Headline 1,
Headline 2, Description, Status

Rules for each column:

Campaign: Use the campaign name from
the intake questions exactly as provided.
Same value for every row.

Ad Group: Use the ad group name exactly
as specified in the strategy document.

Keyword: The keyword phrase only —
no match type symbols in this column.
Match type symbols go in the Match Type
column only.

Match Type: Use Google Ads Editor's
exact accepted values:
- Exact
- Phrase
- Broad

Max CPC: Leave blank — bid strategy
is set at campaign level. Google Ads
Editor will import without a CPC value
and use the campaign-level bid strategy.

Final URL: Leave blank — placeholder
for the human to fill in before import.
Add a note at the top of the CSV:
"REQUIRED: Add Final URL for each
ad group before importing"

Headline 1: Use the primary variant's
Headline 1 exactly as written.
30 character maximum — flag any
headline that exceeds this with
"[OVER LIMIT — EDIT BEFORE IMPORT]"

Headline 2: Use the primary variant's
Headline 2 exactly as written.
30 character maximum — same flag rule.

Description: Use the primary variant's
description exactly as written.
90 character maximum — same flag rule.

Status: "Paused" for all rows.
Never "Enabled" — campaigns should
always be reviewed before going live.

### One row per keyword
Each keyword gets its own row.
The copy columns repeat for every
keyword in the same ad group — this
is correct Google Ads Editor behavior.

### Negative keywords in CSV
Add negative keywords as separate rows
with a minus sign before the keyword
in the Keyword column and "Negative"
in the Match Type column:

Campaign, Ad Group, -translator jobs,
Negative Exact, , , , , , Paused

### CSV header note
Add this as a comment row at the very
top before the column headers:
"# [Company] Demand Gen Toolkit — Ad Group
Organiser Output — [today's date]
# REQUIRED: Fill in Final URL column
before importing
# All ads set to Paused — review before
enabling
# Character limit flags marked
[OVER LIMIT — EDIT BEFORE IMPORT]"

---

## Step 6 — Save Both Files

Save with these exact naming conventions:

Strategy document:
ad_group_strategy_[campaign_theme]_[company]_[date].md

Google Ads Editor CSV:
ad_group_import_[campaign_theme]_[company]_[date].csv

Both files save to outputs/.

Confirm both files are saved and show
the file paths.

---

## Rules This Skill Must Always Follow

Never mix keywords with different core
intents in the same ad group — this
is the single most important quality
signal in Google Ads and the most
common campaign build error.

Never launch a group without negative
keywords — present them as a required
checklist, not a suggestion.

Never assign broad match without a
minimum of 10 negative keywords for
that group.

Always assign copy variants based on
message match to keyword intent —
not based on which variant is the
strongest overall but which variant
most closely mirrors what the buyer
searched.

Always set CSV status to Paused —
never Enabled.

Always flag the Final URL column as
required before import.

Always flag character limit violations
clearly — Google Ads Editor will reject
ads that exceed limits and the error
is not always obvious.

Always produce both files — never
just one.

Never save without explicit confirmation.

Always read the active company name
from the first line of context/icp.md
before naming output files.

Follow the file naming convention
in CLAUDE.md for all output files.

If keyword file or copy file cannot
be found in outputs/, stop and tell
the human before proceeding — this
skill cannot run without both files.
