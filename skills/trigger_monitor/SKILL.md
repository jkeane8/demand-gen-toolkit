---

# Trigger Monitor
## Scans target accounts for buying signals
## Produces a prioritized weekly briefing
## with outreach briefs ready to execute

---

## What This Skill Does
Reads the target account list from
context/target_accounts.md, searches
for evidence that any of the trigger
events defined in context/deep/
trigger_events.md have fired at any
account in the past 7 days, and
produces a prioritized briefing with
actionable outreach briefs for every
Hot signal found.

Runs in two modes:
- Scheduled: every Monday morning,
  produces a dated briefing saved
  to outputs/
- On demand: run any time with an
  optional account override to check
  specific accounts immediately

Updates context/target_accounts.md
with new trigger history after every
run so patterns accumulate over time.

---

## Step 1 — Read Before Doing Anything

Before searching anytng, read ALL
of these files:

### Required files

context/deep/trigger_events.md
This is the primary reference for
what to search for. Read every trigger
event definition including:
- What the trigger is
- What signals indicate it has fired
- What search terms it creates
- What content the buyer needs
- What outreach angle resonates
- How to monitor for it
- How to identify it without being
  intrusive

Do not search for anything that is
not defined as a signal in this file.
The trigger events file is the source
of truth for what counts as a signal.

context/target_accounts.md
The target account list with trigger
history. Read the full file before
running any searches. Note:
- Which accounts are already flagged
  as Hot or Warm from prior runs
- Which accounts have fired multiple
  triggers — these are higher priority
  than single-trigger accounts
- When each account was last checked
- Any notes added from prior outreach

If this file does not exist, create
it using the template in Step 6 before
proceedi with searches.

context/icp.md
Read for:
- Which personas to target first at
  each account based on the trigger
  type — different triggers surface
  different buying roles
- What the buying process looks like
  so outreach brief recommendations
  are realistic about who to contact
  and in what order
- Segment definitions — company size
  and industry help identify which
  ICP segment a flagged account falls
  into

context/deep/persona_depth.md
If found: read for persona-specific
outreach intelligence — what each
persona reads, where they spend time
online, what opening lines resonate.
Use to sharpen the suggested copy
hook for each flagged account.

context/deep/buying_committee.md
If found: read for buying process
intelligence — who gets involved
when a trigger fires and in what
order. Use to recommend the right
first contact at each account.

context/proof_points.md
If found: read to identify which
proof point is most relevant for
each trigger type. Market expansion
triggers get different pros
than compliance triggers.

### Scan outputs/ for recent files

outputs/trigger_briefing_*.md
Read the most recent briefing file
to understand what was flagged last
week. Accounts that were Hot last
week and have not been actioned
should be re-flagged this week with
an escalation note.

---

## Step 2 — Determine Run Mode

Check the prompt for run mode signals:

SCHEDULED MODE (default):
Triggered by: "run trigger monitor,"
"weekly briefing," "Monday briefing,"
or no specific account mentioned
Action: check all accounts in
context/target_accounts.md

ON DEMAND MODE:
Triggered by: a specific company name
mentioned in the prompt, or "check
[company name]" phrasing
Action: check the named account(s)
immediately, plus any accounts
flagged as Hot in the last briefing
that have not been actioned

In either mode, display this before
searching:

---
TRIGGER MONITOR — [date]
Mode: [Scheduled / On Demand]
Accounts to check: [number or list]
Trigger events scanning for:
[list trigger event names from
trigger_evend]
Reading prior briefing: [filename
or "none found"]

Starting search now.
---

---

## Step 3 — Search For Signals

For each account in the list, run
searches based on the signal indicators
defined in trigger_events.md.

### Search approach

Search efficiently — do not run
redundant searches. For each account:

Search 1: "[company name] localization
OR translation OR international
expansion 2026"
Purpose: catches market expansion
and localization-specific signals

Search 2: "[company name] AI
transformation OR AI initiative
OR AI governance 2026"
Purpose: catches AI mandate signals

Search 3: "[company name] hiring
Head of Localization OR Localization
Manager OR i18n"
Purpose: catches new localization
function signals — one of the
strongest early buying signals

Search 4: "[company name] CISO OR
security OR compliance AI 2026"
Purpose: catches compliance and
security audit trigger signals

Search 5: "[company name] funding
OR Series OR raised 2026"
Purpose: catches funding rounds
with international ion as
stated use of funds

Run all 5 searches per account.
Do not skip searches to save time —
the signal might only appear in
one of the five.

### Signal qualification rules

A signal qualifies if it meets ALL
of these criteria:
- Published or posted within the
  last 7 days for scheduled mode
  (last 30 days for on demand mode
  on a new account being checked
  for the first time)
- Directly connected to one of the
  four trigger event types in
  trigger_events.md
- From a verifiable source — LinkedIn
  post, press release, job board,
  news article. Not speculation
  or rumor.
- Specific to the named account —
  not a general industry trend

A signal does NOT qualify if:
- It is more than 7 days old
  (scheduled mode) or 30 days old
  (first-time on demand check)
- It is a generic industry article
  that mentions the company in passing
- It cannot be verified with a
  specific source URL or post

### Urgency rating rules

HOT — act within 48 hours:
- New job posting for Head of
  Localization ozation Manager
  at a company with no prior
  localization function
- Funding announcement with
  international expansion explicitly
  stated as use of funds
- Press release announcing specific
  new market entry with a named
  quarter deadline
- Public compliance finding or
  AI governance mandate with a
  named deadline
- C-suite LinkedIn post announcing
  an AI transformation initiative
  with a specific timeline

WARM — act within 2 weeks:
- Job posting for i18n engineer or
  localization coordinator (signals
  scaling, not building from scratch)
- Funding announcement without
  explicit international expansion
  mention but company profile matches
  ICP expansion pattern
- New CISO hire (watch for governance
  announcement — typically 60-90 days
  later)
- Industry regulation news affecting
  this company's sector
- LinkedIn post from localization
  team member expressing frustration
  with current tools

MONITOR — watch but brief only:
Any signal that is real but not
yet urgent. Add to account h
in target_accounts.md but do not
include in the main briefing.
Flag for next week's check.

---

## Step 4 — Produce The Briefing

Format the briefing exactly as follows.
Only include Hot signals in the main
briefing. Warm signals get a summary
section. Monitor signals are logged
to the account file only.

---
TRIGGER MONITOR BRIEFING
─────────────────────────────────────────
Date: [today's date]
Mode: [Scheduled / On Demand]
Accounts checked: [number]
Hot signals found: [number]
Warm signals found: [number]
Monitor signals logged: [number]
Prior Hot signals not yet actioned: [number]
─────────────────────────────────────────

[If no Hot signals:]
No Hot signals this week.
[List Warm signals summary]
[Note any prior Hot signals that
remain unactioned from last week]

[If Hot signals found:]

─────────────────────────────────────────
HOT SIGNAL: [Company Name]
Trigger type: [trigger event name]
Signal date: [when it was published]
─────────────────────────────────────────

SIGNAL
What happened: [specific, factual
description of the signal — what
was published, posted, or announced.
Include the source: LinkedIn post
from [name/title], press release
from [date], job posting on [platform].]

Why it matters: [one paragraph connecting
this specific signal to the buying
urgency it creates — reference the
trigger_events.md reasoning for why
this trigger creates urgency now,
not in 6 months]

Prior trigger history at this account:
[Pull from target_accounts.md —
has this account fired any triggers
before? If yes, list them with dates.
Multiple triggers from the same account
in a short window significantly increases
buying intent.]

─────────────────────────────────────────

OUTREACH INTELLIGENCE

Persona to target firstketing as the likely budget
owner for a first localization investment.
For AI mandate triggers: CTO or VP
Engineering as the initiative owner.
For compliance triggers: CISO first,
then Head of Localization as the
operational solution owner.]

Why this persona first:
[One sentence from buying_committee.md
on why this role is the right first
contact for this specific trigger —
not a generic explanation]

ICP segment this account falls into:
[Commercial Enterprise / High-Growth
Tech / US Federal / AI-ML — with
one sentence on why this matters for
the outreach approach]

─────────────────────────────────────────

OUTREACH ANGLE

Primary angle: [which campaign angle
from the context files fits this
trigger best — vendor management tax,
switching objection, AI transformation,
security and compliance, market expansion
speed. One sentence on why this angle
fits this specific trigger.]

Proof point to lead with:
[The single most 
One sentence on why this proof point
fits this account's specific situation.]

─────────────────────────────────────────

SUGGESTED COPY HOOK

LinkedIn opening line:
[One sentence — specific to this
account's trigger signal, not generic.
References the signal without feeling
like surveillance. Follows the rule
from trigger_events.md: reference
the outcome another company achieved
in the same situation, not the trigger
event itself directly.

Good: "We helped [comparable company]
launch in [N] markets in [timeframe]
after a similar expansion announcement —
happy to share what made the difference."

Never: "I saw you just raised a
Series C" or "I noticed you posted
a job for..." — this feels intrusive.]

Email subject line (3 options):
A: [direct — specific outcome for
   this trigger type]
B: [curiosity — something they
   haven't calculated yet]
C: [peer story — a comparable
   company in the same situation]

─────────────────────────────────────────

READY-TO-USE ORCHESTRATOR BRIEF
Paste this directly into the orchestrator
to generate the full outreach campaign:

"Run the orchestrator. ABM sequence
for [company name]. Trigger event:
[trigger type]. Persona: [persona
title]. Segment: [ICP segment].
Angle: [primary angle]. Lead with
[proof point]. 3-4 emails."

Skills the orchestrator will run:
[List the chain — Email and Nurture
Sequencer for ABM type, LinkedIn
Campaign Organiser if LinkedIn
targeting is relevant for this account]

─────────────────────────────────────────

[Repeat for each Hot signal]

─────────────────────────────────────────
WARM SIGNALS — Act Within 2 Weeks
─────────────────────────────────────────

[For each Warm signal — abbreviated
format, no full outreach brief:]

ACCOUNT: [Company Name]
Signal: [one sentence description]
Source: [URL or description]
Recommended action: [one sentence]

─────────────────────────────────────────
SEARCH LOG
─────────────────────────────────────────

[Full transparency — list what was
searched and what was found for
each account. This allows the human
to verify signals and catch anything
the searches missed.]

[Company Name]:
  Searches run: [list the 5 searches]
  Signal found: [yes/no — what source]
  Signal not found: [searches that
  returned nothing relevant]

[Repeat for each account]

─────────────────────────────────────────
PRIOR HOT SIGNALS NOT YET ACTIONED

[Pull from last briefing file —
any accounts that were Hot last week
with no indication of outreach:]

[Company Name] — flagged [date]
Signal: [original signal summary]
Status: No outreach recorded
Recommendation: Escalate — signal
is now [X] days old. If no outreach
in the next 48 hours, downgrade to
Warm and note reason in account file.

─────────────────────────────────────────

---

## Step 5 — Update Target Accounts File

After producing the briefing, append
trigger history to context/target_
accounts.md. Never overwrite prior entries.
The history must accumulate.

For each account with a signal add:
[Date]: [Trigger type] — [one sentence
summary of signal]. Urgency: [Hot/Warm/
Monitor]. Source: [URL or description].
Outreach brief generated: [yes/no].

If an account had no signal this week,
add:
[Date]: Checked — no signal found.

This creates a complete audit trail
of every check, every signal, and
every action taken at every account.

---

## Step 6 — Target Accounts File Template

If context/target_accounts.md does
not exist, create it with this structure
before the first run:
Target Accounts
Last updated: [date]
Active accounts: [number]

How To Use This File
Add target accounts below using the
template. The Trigger Monitor reads
this file every run and appends
trigger history automatically.
To add a new account: copy the
template and fill in what you know.
Unknown fields can be left blank —
the monitor will fill in intelligence
as it finds signals.
To remove an account: move it to
the Archived Accounts section at
the bottom. Do not delete — the
history may be useful later.

Account Template
[Company Name]
ICP segment: [Commercial Enterprise /
High-Growth Tech / US Federal / AI-ML]
Company size: [employee range if known]
Industry: [industry]
Primary persona to target: [title]
Known contacts: [names and titles
if any — from LinkedIn or CRM]
Current TMS or localization vendor:
[if known]
Reason this account is on the list:
[why they are a target — ICP fit,
existing relationship, competitive
displacement opportunity, etc.]
Date added: [date]
Added by: [your name]
Trigger history:
[The Trigger Monitor appends entries
here automatically after each run]

Active Accounts
[Accounts go here]

Archived Accounts
[Accounts that are no longer active
targets — moved here with a note
on why]

---

## Step 7 — Save The Briefing

Save the briefing as:
trigger_briefing_[date].md
in outputs/

Confirm the file path after saving.

Also confirm that context/target_
accounts.md has been updated with
new trigger history.

---

## Rules This Skill Must Always Follow

Never fabricate signals — if a search
returns nothing, log "no signal found"
and move on. Do not infer a signal
from weak evidence.

Never reference the trigger event
directly in the suggested copy hook —
"I saw you posted a job for Head of
Localization" feels like surveillance.
Always reference the outcome another
company achieved in the same situation.

Always cite the source for every
signal — a LinkedIn post from a
named person, a press release with
a date, a job posting on a named
platform. Anonymous or unverifiable
signals do not count.

Always append to trigger history —
never overwrite. The historical
record is the most valuable part
of the target accounts file over time.

Always check prior briefings for
unactioned Hot signals — an account
that was Hot last week and received
no outreach is still Hot this week.

Always produce the ready-to-use
orchestrator brief for every Hot
signal — do not make the human
figure out what to do next.

Always update context/target_accounts.md
after every run — even if no signals
were found. The "no signal" entries
are part of the historical record.

Never include Monitor signals in the
main briefing — log them to the
account file only. The briefing
should be actionable, not exhaustive.

Always read trigger_events.md before
searching — do not rely on general
knowledge about what a buying signal
looks like. The file is the source
of truth.

Never save without confirming both
the briefing file and the account
file have been updated.

Follow the file naming convention
in CLAUDE.md for all output files.

Read the active company name from
the first line of context/icp.md
for any company-specific references
in the briefing.

---
