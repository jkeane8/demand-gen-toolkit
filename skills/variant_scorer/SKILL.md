# Variant Scorer
## Evaluates copy variants before launch
## Scores, ranks, flags issues, and
## provides rewrites for every problem found

---

## What This Skill Does

Reads a copy output file from outputs/ and evaluates every variant
against four criteria drawn from the active context files. Produces
an independent score for each variant, ranks them, flags every issue
found, and provides a drop-in rewrite for each flagged problem. Runs
automatically after Campaign Writer completes or manually at any time
by referencing a file or pasting copy directly.

---

## Step 1 — Read Before Scoring Anything

Before evaluating a single variant, read ALL of these files.

### Required files

context/icp.md
Read for:
- Exact buyer vocabulary and phrases — these are the words copy must use
- Pain points by segment — match to the segment the copy targets
- Typical objections — check if copy pre-empts the right ones
- The Language They Actually Use section — primary vocabulary reference
  for scoring pain point accuracy

context/brand_voice.md
Read for:
- Words and Phrases to Avoid — treat as a hard checklist, scan every
  variant for violations
- Tone scale by segment — score formality match against this
- Example sentences that sound like the brand and those that do not —
  calibrate every variant against these before scoring

context/competitors.md
Read for:
- Messaging angles competitors already own — flag if any variant
  competes on claimed competitor ground
- Positioning gaps — note if any variant is exploiting an ownable angle

context/proof_points.md
If found: read for named customer metrics and results — used to verify
proof point accuracy and relevance in scored variants.

### Optional files

context/deep/voice_of_customer.md
If found: read for exact buyer quotes — used to verify vocabulary mirror
accuracy. A variant that uses exact buyer phrases scores higher on pain
point accuracy than one that paraphrases.

context/deep/objection_depth.md
If found: read for objection conversations and winning responses — used
to verify whether copy pre-empts the right objections for the funnel stage.

### Display before scoring

---
VARIANT SCORER
─────────────────────────────────────────
File being scored: [filename or "pasted copy"]
Variants found: [number]
Segment: [from file header or brief]
Persona: [from file header or brief]
Funnel stage: [from file header or brief]
Awareness level: [Schwartz level from file header, or inferred]
LinkedIn phase: [Phase 1 / 2 / 3 — omit if not LinkedIn format]

Context files loaded:
[✓/✗] context/icp.md
[✓/✗] context/brand_voice.md
[✓/✗] context/competitors.md
[✓/✗] context/proof_points.md
[✓/✗] context/deep/voice_of_customer.md
[✓/✗] context/deep/objection_depth.md

Scoring now.
─────────────────────────────────────────
---

---

## Step 2 — Score Each Variant

Score every variant independently across all four criteria before ranking.

---

### CRITERION 1: AWARENESS LEVEL MATCH
Weight: 30 points

What it measures: Does the copy actually operate at the Schwartz
awareness level it claims? A variant that claims Problem-aware but opens
with a product pitch is misaligned. A variant that claims Most-aware but
buries the offer is misaligned.

Scoring rubric:

30/30 — Copy opens, develops, and closes at exactly the claimed awareness
level. Hook matches. Body develops correctly. CTA matches. No level mixing.

20-29 — Mostly correct but one section slips — a brief product mention
before it should appear, or a soft CTA when a hard one is warranted.

10-19 — Claims one level but operates at a different one throughout.
The hook belongs to a different awareness level than stated. The buyer
would feel the mismatch even if they couldn't name it.

0-9 — No discernible awareness level strategy. Generic. Could be sent
to anyone at any stage.

LinkedIn phase check (LinkedIn format only):
Deduct up to 10 points if phase rules are violated:
- Phase 1: no product name, no hard metrics, Learn More CTA only
- Phase 2: named metrics present, higher-intent CTA appropriate
- Phase 3: peer story frame, short copy, comparable account proof point used

---

### CRITERION 2: PAIN POINT ACCURACY
Weight: 25 points

What it measures: Does the copy use the vocabulary buyers use to describe
their pain — from icp.md and voice_of_customer.md — or does it paraphrase
into generic language that loses the mirror effect?

Scoring rubric:

25/25 — Uses exact phrases from icp.md vocabulary section and/or
voice_of_customer.md quotes. Buyer would read it and think that is exactly
how I would describe it. Pain named specifically, not categorically.

18-24 — Captures the right pain but uses slightly softened or paraphrased
language. Meaning is correct but the mirror effect is weakened.

10-17 — Identifies general pain category but describes it in generic terms.
Could apply to any company in any category. No specific vocabulary mirror.

0-9 — Does not accurately represent buyer pain. Uses vendor language to
describe a buyer problem. Or addresses the wrong pain point for this
segment entirely.

---

### CRITERION 3: BRAND VOICE COMPLIANCE
Weight: 25 points

What it measures: Does the copy follow the brand voice rules in
brand_voice.md? This includes avoid list compliance, tone scale match,
and calibration against the example sentences.

Scoring rubric:

25/25 — Zero words from the avoid list. Tone matches the segment scale.
Reads like the brand example sentences, not the anti-examples. No AI tells.

18-24 — One minor violation. Single word from the avoid list or tone
slightly off-register for the segment but not jarring.

10-17 — Multiple avoid list violations or tone clearly wrong for segment.
Reads like a generic SaaS ad, not the specific brand voice.

0-9 — Pervasive avoid list violations, AI tells throughout, or tone
completely mismatched to segment. Would not pass a brand review.

Avoid list — scan every variant explicitly for these words and flag any found:
leverage, utilize, robust, comprehensive, cutting-edge, streamline,
game-changing, revolutionary, disruptive, world-class, best-in-class,
leading, unlock, unleash, supercharge, delve, dive into, crucial, vital,
ensure, innovative, dynamic, synergy

Also check for structural AI tells:
- Every paragraph the same length
- Every bullet starting the same way
- Excessive bold formatting
- Passive voice throughout
- No contractions

---

### CRITERION 4: CTA APPROPRIATENESS
Weight: 20 points

What it measures: Does the CTA match the funnel stage, the format, and
the offer? Does it ask for the right level of commitment given where the
buyer is in their journey?

Scoring rubric:

20/20 — CTA is specific, names what the buyer gets, matches the funnel
stage exactly, and is appropriate for the format. A buyer can read the
CTA alone and know what they will get and why it is worth their time.

14-19 — Mostly right but slightly generic or slightly mismatched to funnel
stage. Learn More at consideration when a case study CTA would be more
specific.

7-13 — Clearly wrong for the funnel stage. Awareness copy with a demo ask.
Decision copy with a passive Learn More. Would hurt conversion rate.

0-6 — Absent, completely passive, or so generic it adds no value.
Click here. Find out more. Get started.

---

## Step 3 — Display Individual Scores

Display each variant's score using this exact format:

---
VARIANT [N] — [Angle name from file]
─────────────────────────────────────────
SCORES

Awareness Level Match:    [X]/30
Pain Point Accuracy:      [X]/25
Brand Voice Compliance:   [X]/25
CTA Appropriateness:      [X]/20
─────────────────────────────────────────
TOTAL:                    [X]/100
Rating: [Strong (85-100) / Good (70-84) / Needs Work (50-69) / Rewrite (0-49)]
─────────────────────────────────────────

ISSUES FOUND

[If no issues:]
No issues found — variant is ready to launch.

[For each issue:]
Issue [N]: [criterion name]
Severity: [Critical / Moderate / Minor]
What is wrong: [one sentence describing the problem]
Where it appears: [quote the exact phrase or sentence with the problem]
Why it matters: [one sentence on what this costs in conversion or brand terms]

Rewrite:
[The specific phrase or sentence rewritten to fix the issue. Drop-in
replacement only — same length and position as the original. Do not
rewrite the whole variant.]
---

Severity definitions:
Critical — will measurably hurt conversion rate or brand perception.
  Must fix before launch.
Moderate — weakens copy but will not kill performance. Fix if time allows.
Minor — small improvement available. Fix in next iteration.

---

## Step 4 — Rank All Variants

After scoring all variants individually, display the ranking:

---
VARIANT RANKING
─────────────────────────────────────────
#1 [Variant name] — [score]/100 — [Rating]
   Why it leads: [one sentence on its strongest quality]
   Recommended for: [which A/B test position — primary, challenger, or hold]

#2 [Variant name] — [score]/100 — [Rating]
   Why it ranks here: [one sentence]
   Recommended for: [A/B test position]

#[N] [Variant name] — [score]/100 — [Rating]
   Why it ranks here: [one sentence]
   Recommended for: [A/B test position or "rewrite before launching"]
─────────────────────────────────────────

LAUNCH RECOMMENDATION

Primary variant to launch: [name]
A/B test against: [name]
Hold or rewrite before using: [name if any — with one sentence on what
  needs to change]

If all variants score above 70:
"All variants are launch-ready. Run primary vs A/B test as recommended."

If any variant scores below 50:
"[Variant name] needs a rewrite before launch. [One sentence on what
needs to change.] Use the rewrites provided or run Campaign Writer again
with the specific angle adjusted."
---

---

## Step 5 — Summary and Next Steps

After the ranking, display:

---
SCORING SUMMARY
─────────────────────────────────────────
Variants scored: [number]
Average score: [X]/100
Highest score: [variant name] — [X]/100
Lowest score: [variant name] — [X]/100
Total issues found: [number]
  Critical: [number]
  Moderate: [number]
  Minor: [number]

FILES READY TO LAUNCH
[List variants rated Strong or Good with no Critical issues]

FILES NEEDING ATTENTION
[List variants with Critical issues — one line summary of what to fix]
─────────────────────────────────────────

RECOMMENDED NEXT SKILL

[If paid search format:]
→ Ad Group Organiser — map the launch-ready variants to Google Ads
  campaign structure with match types, negative keywords, and bid strategy.

[If LinkedIn format:]
→ LinkedIn Campaign Organiser — map the launch-ready variants to LinkedIn
  campaign structure with phase-aware audience targeting and bid strategy.

[If email format:]
→ Variants are ready for HubSpot sequence setup. Use the HubSpot workflow
  notes in the copy file for enrollment trigger and delay configuration.

[If any variant was rewritten during this session:]
→ Consider running Variant Scorer again on the rewritten variant to confirm
  the fixes resolved all flagged issues before launch.
---

---

## Step 6 — Save Option

After displaying all scores, rankings, and next steps, ask:

"Would you like to save the scoring report?

It will be saved as:
variant_score_[theme]_[company]_[YYYY-MM-DD].md
in outputs/

This gives you a record of which variants were approved for launch,
what issues were found, and what was changed before going live."

Save only on explicit confirmation.

---

## Rules This Skill Must Always Follow

Always read all four required context files before scoring — never score
from memory or assumptions about the brand.

Always provide a drop-in rewrite for every issue flagged — never flag
without fixing.

Never rewrite the entire variant when a targeted fix resolves the issue —
surgical rewrites only.

Always score awareness level against the level claimed in the copy file
header. If no level is stated, infer it from the copy and state the
inference before scoring.

Always scan explicitly for every word on the avoid list — do not rely on
a general impression.

Always provide a launch recommendation — do not leave without a clear action.

For LinkedIn format: always verify phase rule compliance as part of
Criterion 1. The phase annotation in the copy file tells you which rules
to check against.

Never save without explicit confirmation.

Read the active company name from context/icp.md for file naming.

Follow the file naming convention in CLAUDE.md for all output files.
