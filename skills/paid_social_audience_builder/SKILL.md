# Paid Social Audience Builder
## Produces full channel setup for Meta, Reddit, and YouTube —
## cold and retargeting audiences, campaign objectives, bidding
## strategy, and budget guidance for each channel.

---

## What This Skill Does

Reads the ICP, brand voice, competitors, and market context files.
Takes a campaign objective and persona as input. Produces three
separate briefs — one for Meta, one for Reddit, one for YouTube —
each with platform-native targeting logic.

For each channel produces:
- Cold audience specifications
- Retargeting audience specifications
- Campaign objective recommendation
- Bidding strategy
- Estimated reach and CPM benchmarks
- Budget guidance
- A/B testing recommendations
- Prerequisite checklist

Connects to existing Campaign Writer outputs — if Meta, Reddit, or
YouTube copy exists in outputs/ it maps that copy to the correct
audience and channel in the cross-channel summary.

Runs on demand. Triggered by any mention of paid social, Meta,
Facebook, Instagram, Reddit, YouTube, or social advertising.

---

## Step 1 — Read Before Building

### Required files

**context/icp.md**
Read for: all buyer personas with seniority levels, segments, pain
points, trigger events, and the exact vocabulary buyers use. Used to
build interest stacks, subreddit lists, and YouTube topic targeting
that reflects where real buyers spend time online — not where
marketers assume they spend time. Pay particular attention to the
information diet section for each persona if present — publications
they read, communities they participate in, and content they consume
are direct inputs to targeting on all three channels.

**context/competitors.md**
Read for: competitor names and positioning. Used to build competitor
interest targeting on Meta and YouTube and to identify competitor
subreddits on Reddit where buyers discuss alternatives.

**context/market.md**
Read for: market category, industry trends, and the broader topic
landscape. Used to identify YouTube topic categories and Reddit
communities beyond the immediate product category.

**context/brand_voice.md**
Read for: tone scale by segment. Used to note which audiences require
formal versus conversational creative direction — important for Reddit
where overly corporate tone is actively rejected by the community.

### Optional files

**context/deep/persona_depth.md**
If found: read the information diet and online community sections for
each persona. These are the highest-value inputs for paid social
targeting — a persona who reads specific publications, participates
in specific communities, or watches specific YouTube channels maps
directly to targetable interests and placements.

**context/deep/buying_committee.md**
If found: read for all roles involved in a purchase decision. Paid
social reaches broader audiences than paid search — the full buying
committee may be reachable on Meta and YouTube even if they are not
actively searching.

**outputs/copy_*.md**
Scan for any Meta ad, Reddit post, or YouTube copy files. If found:
note the copy angle, persona, and funnel stage and map each copy
variant to the correct audience spec in the cross-channel summary.
This connects the Campaign Writer's copy outputs to the audience
builder's targeting outputs.

### Display before building

```
PAID SOCIAL AUDIENCE BUILDER
─────────────────────────────────────
Campaign objective: [stated objective]
Persona: [stated or inferred from brief]
Channels: Meta, Reddit, YouTube
Audience types: Cold + Retargeting
Context files loaded:
[✓/✗] context/icp.md
[✓/✗] context/competitors.md
[✓/✗] context/market.md
[✓/✗] context/brand_voice.md
[✓/✗] context/deep/persona_depth.md
[✓/✗] context/deep/buying_committee.md
Copy files found:
[list any Meta, Reddit, or YouTube copy
files found in outputs/ or "None found —
audience specs will be produced without
copy mapping"]
Building now.
─────────────────────────────────────
```

---

## Step 2 — Ask for Inputs

After reading context files, display these questions if not already
clear from the brief:

```
Before I build, I need a few details.
Answer all in one message:

OBJECTIVE — which of these?
- Brand awareness — reach as many ICP members as possible
- Lead generation — drive form completions or demo requests
- Content engagement — drive clicks to a specific piece of content
- Retargeting — re-engage people who have already seen the brand

PERSONA — which persona from the ICP?
[list personas from icp.md]

FUNNEL STAGE
- Awareness
- Consideration
- Decision

BUDGET — monthly budget for paid social?
(If not provided, percentage allocations will be used instead of
dollar amounts)

CONSTRAINTS — any channel restrictions?
(e.g. no Meta spend approved, Reddit only, etc.)
Press Enter to skip.
```

Skip this step if all inputs are clear from the brief.

---

## Step 3 — Meta Channel Brief

Produce the Meta brief using Facebook and Instagram targeting logic.
Meta uses behavioral, interest, demographic, and custom audience
targeting — not keyword or community targeting.

```
─────────────────────────────────────
META CHANNEL BRIEF
Platform: Facebook and Instagram
Objective: [Meta campaign objective — map stated objective to Meta's
  campaign objective options: Awareness, Traffic, Engagement,
  Leads, or Sales]
─────────────────────────────────────

COLD AUDIENCE SPECS

Audience 1 — Interest and Behavior Targeting

Age range: [infer from typical seniority of target persona from
  icp.md]
Job titles: [list specific job titles from icp.md persona — Meta
  job title targeting is less precise than LinkedIn but useful as
  a secondary filter]
Note: Meta job title targeting is imprecise — use it as a secondary
  filter alongside interests, not as the primary targeting mechanism.

Interest stack:
[List 8–12 specific interests that map to where this persona actually
  spends time online. Derive these from icp.md information diet,
  persona_depth.md if available, and the market category.
  Group by relevance tier:]

Tier 1 — Direct category interests:
[Interests directly related to the product category]

Tier 2 — Adjacent professional interests:
[Interests related to the persona's broader professional world]

Tier 3 — Publication and media interests:
[Specific publications, podcasts, or media the persona consumes]

Why these interests:
[One paragraph connecting the interest stack to specific findings
  from icp.md or persona_depth.md — not generic rationale]

Behavior targeting to add:
[Meta-specific behaviors relevant to this persona — select only
  those that map to the actual persona seniority and role]

Exclusions:
[Who to exclude — existing customers via custom audience,
  competitors via employer targeting, junior roles via job title]

Estimated audience size: [range based on interest stack — note this
  is approximate until the audience is built in Meta Ads Manager]
Recommended minimum: 500,000 members for meaningful delivery on Meta

---

Audience 2 — Lookalike Audience
(activate once source data exists)

Lookalike source: [best available source in priority order]
  1. Customer list — email addresses of existing customers uploaded
     to Meta. Produces the highest-quality lookalike.
  2. Website visitors — Meta Pixel visitors from the last 90 days.
     Requires Pixel installation.
  3. Lead form completions — people who completed a Meta lead form.

Lookalike percentage: 1–2% for highest similarity, 3–5% for broader
  reach
Geographic scope: [US only / US + Canada / broader based on ICP
  geography from icp.md]
Prerequisite: Source audience must have minimum 100 people for Meta
  to generate a lookalike. 1,000+ people recommended for quality.

---

Audience 3 — Competitor Interest Targeting

Competitors to target:
[List competitor names from competitors.md that have a Meta
  presence — targeting people interested in competitor brands
  reaches buyers already in the category]
Interest targeting: [competitor brand names as interests where
  available in Meta]
Note: Meta does not always carry specific competitors as targetable
  interests. Check availability in Meta Ads Manager before relying
  on this audience.

---

RETARGETING AUDIENCE SPECS

Retargeting Audience 1 — Website Visitors

Source: Meta Pixel — all website visitors last 90 days
Refinement: Apply seniority filter via job title if available, or
  use engagement signals (visitors who spent 30+ seconds on key pages)
Exclusion: Current customers and anyone who has already completed a
  lead form
Minimum size: 1,000 visitors before retargeting delivers reliably

Retargeting Audience 2 — Engagement Retargeting

Source: People who engaged with Meta ads or Instagram posts in the
  last 180 days — watched 25%+ of a video, clicked a link, or saved
  a post
Why: Engagement retargeting often produces lower CPL than website
  visitor retargeting because the audience has demonstrated content
  interest without necessarily visiting the site

Retargeting Audience 3 — CRM Retargeting

Source: Upload contact list from CRM — leads who have not yet
  converted to customers
Objective: Accelerate consideration-stage contacts toward demo request
Match rate expectation: 40–60% of B2B email addresses match to Meta
  profiles

---

CAMPAIGN OBJECTIVE AND BIDDING

Campaign objective: [Meta objective]
Why this objective: [one sentence connecting to the stated goal and
  persona funnel stage]

Bidding strategy:
Cold audiences: Highest Volume (formerly Lowest Cost) — let Meta's
  algorithm optimise for the most conversions within budget
Retargeting: Cost Cap — set a maximum CPL and let Meta optimise
  within that ceiling. Use for retargeting where expected conversion
  rate is higher and CPL should be lower.

Expected benchmarks for B2B SaaS VP/Director targeting on Meta:
CPM: $8–15 (significantly lower than LinkedIn — broader audience,
  less precise targeting)
CTR: 0.5–1.5% (lower intent than LinkedIn or paid search)
CPL: $50–150 (lower than LinkedIn but leads are typically earlier
  funnel)
Note: Meta CPL appears lower than LinkedIn but conversion-to-pipeline
  rate is typically lower — track lead quality alongside CPL.

---

BUDGET GUIDANCE

Minimum viable monthly budget: $2,000
Below this level impression frequency is too low to build brand
  familiarity.

Recommended allocation if budget is confirmed:
Cold audiences: 70%
Retargeting: 30%
Rationale: Build the retargeting pool in months 1–2, then shift
  toward 50/50 as the pool grows.

---

PREREQUISITE CHECKLIST
☐ Meta Pixel installed on website and firing correctly
☐ Conversion events configured (demo request, content download)
☐ Customer email list prepared for lookalike source upload
☐ Creative assets sized for Meta:
    Feed: 1080x1080px (1:1)
    Stories: 1080x1920px (9:16)
    Both required — do not run Meta without the 9:16 version
☐ Copy variants ready from Campaign Writer — Meta format

---

A/B TESTING RECOMMENDATION
Test 1: Interest stack vs Lookalike audience — same creative,
  different audience source
Test 2: Feed placement vs Stories placement — same audience,
  different format
Test 3: Awareness objective vs Traffic objective — which drives
  lower CPL for this specific persona

─────────────────────────────────────
```

---

## Step 4 — Reddit Channel Brief

Reddit targeting is fundamentally different from Meta. Reddit uses
community membership (subreddits) and interest categories — not
demographic or behavioral graphs. The creative approach also differs
significantly — Reddit actively rejects corporate advertising tone
and rewards content that provides genuine value to the community.

```
─────────────────────────────────────
REDDIT CHANNEL BRIEF
Platform: Reddit Ads
Objective: [map to Reddit campaign objectives: Brand Awareness,
  Traffic, or Conversions]
─────────────────────────────────────

COLD AUDIENCE SPECS

Audience 1 — Subreddit Targeting

Target subreddits:
[List 8–15 subreddits where this persona actually spends time.
  Derive from:]
  - icp.md information diet and community participation
  - persona_depth.md if available
  - The product category and adjacent professional topics
  - Competitor communities where buyers discuss alternatives

Group by relevance:

Direct category subreddits:
[Subreddits directly about the product category or buyer's daily
  job function]

Professional and industry subreddits:
[Subreddits about the broader profession — marketing, operations,
  technology, etc.]

Adjacent interest subreddits:
[Subreddits where the persona spends time for reasons related to
  their professional identity — startup culture, SaaS, B2B, etc.]

For each subreddit note:
- Approximate subscriber count if known
- Why this community contains the target persona
- Tone guidance — is this community receptive to promotional content
  or should ads blend into organic discussion style

Minimum subreddit size: 10,000 subscribers for Reddit to deliver
  reliably. Smaller subreddits can be combined into a community
  audience group.

---

Audience 2 — Reddit Interest Targeting

Interest categories:
[Reddit's interest categories are broader than subreddit targeting.
  List the most relevant categories from Reddit's available targeting
  options — Technology, Business, Marketing, etc. Use as a secondary
  audience alongside subreddit targeting, not a replacement.]

---

Audience 3 — Keyword Targeting

Target keywords:
[Reddit allows keyword targeting — ads shown to users who have
  recently searched or engaged with content containing specific
  keywords. List 10–20 keywords drawn from icp.md buyer vocabulary
  and the keyword file if one exists in outputs/]

---

RETARGETING AUDIENCE SPECS

Reddit Pixel retargeting:
[Requires Reddit Pixel installation. Website visitors, video viewers,
  and lead form completers can be retargeted. Note minimum audience
  size requirements — Reddit recommends at least 1,000 matched users
  before retargeting delivers reliably.]

---

CAMPAIGN OBJECTIVE AND BIDDING

Campaign objective: [Reddit objective]
Bidding: CPM bidding for brand awareness, CPC for traffic and
  conversion campaigns. Reddit CPCs are typically lower than
  LinkedIn but higher than Meta.

Expected benchmarks for B2B targeting on Reddit:
CPM: $3–8 (Reddit is significantly cheaper than LinkedIn or Meta
  for B2B audiences)
CTR: 0.3–0.8%
CPL: $30–100 (highly variable by subreddit and creative approach)
Note: Reddit lead quality varies significantly by subreddit.
  Professional subreddits produce higher-quality leads than general
  interest subreddits at similar CPL.

---

CREATIVE DIRECTION FOR REDDIT
This section is critical — Reddit is the channel most sensitive to
  tone mismatch.

What works on Reddit:
- Practitioner voice — write like someone who does this job, not
  like a company marketing to people who do this job
- Data and insight — Redditors respond to "we analysed X and
  found Y" framing
- Honest acknowledgment of limitations — Reddit communities are
  skeptical of perfection claims
- Value-first — lead with something genuinely useful before any
  product reference

What kills Reddit ads:
- Corporate tone — anything that sounds like a press release
- Superlatives without evidence — "world-class," "best-in-class"
- Generic CTAs — "learn more," "find out how"
- Obvious promotional intent without providing value first

Per brand_voice.md tone scale: Reddit requires the most casual
  register in the toolkit — 2/5 formality regardless of which
  segment is being targeted.

---

BUDGET GUIDANCE

Minimum viable monthly budget: $1,000
Reddit has lower CPMs than other channels — meaningful reach is
  achievable at lower spend.

Recommended as a test channel alongside Meta rather than a primary
  channel. Reddit excels at reaching technically sophisticated buyers
  (CTOs, engineers, product managers) who are underrepresented on
  LinkedIn and Meta.

---

PREREQUISITE CHECKLIST
☐ Reddit Pixel installed if retargeting is planned
☐ Subreddit list verified — confirm each subreddit is available as
    a targetable community in Reddit Ads Manager (not all subreddits
    are available for targeting)
☐ Creative written in practitioner voice — not corporate tone
☐ Campaign Writer Reddit format copy ready if available

---

A/B TESTING RECOMMENDATION
Test 1: Subreddit targeting vs Interest category targeting — which
  produces higher-quality leads
Test 2: Practitioner post format vs display ad format — Reddit
  native content often outperforms display
Test 3: Direct category subreddits vs adjacent professional
  subreddits

─────────────────────────────────────
```

---

## Step 5 — YouTube Channel Brief

YouTube targeting combines search intent signals with viewing
behavior — it is closer to paid search than to Meta or Reddit.
Targeting uses keywords, topics, placements, and audience segments
based on viewing history and search behavior.

```
─────────────────────────────────────
YOUTUBE CHANNEL BRIEF
Platform: YouTube (via Google Ads)
Objective: [map to Google Ads video campaign objectives: Brand
  Awareness and Reach, Product and Brand Consideration, or
  Website Traffic]
─────────────────────────────────────

COLD AUDIENCE SPECS

Audience 1 — Custom Intent Audience (keyword-based)

Custom intent keywords:
[List 15–25 keywords that reflect what the target persona searches
  for on Google and YouTube. These are not the same as paid search
  keywords — they should reflect the research and learning behavior
  of the persona, not their transactional intent. Derive from:]
  - icp.md buyer vocabulary and trigger event search terms
  - The keyword file in outputs/ if available — cross-reference
    paid search keywords against likely YouTube research queries
  - Topics the persona would search to learn about their industry,
    not just their immediate problem

Group by intent type:
Educational queries: [how to, what is, guide to — research phase]
Comparison queries: [vs, alternative, review — evaluating solutions]
Problem-aware queries: [challenges, difficulty with, pain point terms
  — recognising a problem but not yet naming a solution]

Why these keywords:
[One paragraph connecting keyword selection to specific persona
  behaviors from icp.md]

---

Audience 2 — Topic Targeting

YouTube topic categories:
[List 5–8 YouTube topic categories that the persona watches. These
  are Google's predefined topic categories — select those that map
  to the persona's professional interests and information diet]

Placement targeting:
[If specific YouTube channels are known to be watched by this persona
  — from persona_depth.md information diet — list them as placement
  targets. Placement targeting shows ads on specific channels rather
  than topic categories.]

---

Audience 3 — In-Market Audience

Google's in-market audiences:
[List relevant in-market audience segments from Google's predefined
  options — these are people Google has identified as actively
  researching a purchase in a specific category. Select the
  categories most relevant to the ICP buying behavior.]

---

RETARGETING AUDIENCE SPECS

YouTube retargeting sources:
- Google Ads remarketing list — website visitors who have been
  cookied via the Google tag
- YouTube channel viewers — people who have watched the company's
  YouTube content (if a channel exists)
- Customer Match — email list upload via Google Ads for CRM
  retargeting

---

CAMPAIGN OBJECTIVE AND BIDDING

Campaign objective: [Google Ads video campaign type]

Ad format recommendations:
Skippable in-stream ads: Best for awareness — viewer can skip after
  5 seconds. Hook must land in first 5 seconds. Charged only when
  viewer watches 30 seconds or completes the ad.
Non-skippable in-stream (15 seconds): Best for short, high-impact
  messages where the full message needs to land. Higher CPM.
Bumper ads (6 seconds): Best for retargeting — reinforce a message
  the viewer has already seen. Not suitable for cold audiences.
In-feed video ads: Appear in YouTube search results and homepage.
  Best for consideration stage — viewer chooses to watch.

Bidding by objective:
Awareness: CPM bidding — Target CPM
Consideration: CPV bidding — Target Cost Per View
Conversion: Target CPA if conversion tracking is set up

Expected benchmarks for B2B VP/Director targeting on YouTube:
CPM: $5–12
CPV: $0.03–0.08
View rate: 25–40% (skippable)
CTR from video: 0.3–0.8%

---

BUDGET GUIDANCE

Minimum viable monthly budget: $2,000
YouTube requires consistent frequency to build brand recognition —
  below $2,000/month impression frequency is too low for B2B audiences.

YouTube is most effective as a retargeting channel for B2B — showing
  video ads to people who have already engaged with paid search or
  LinkedIn. As a cold channel it works best for personas who consume
  professional video content regularly (CTOs, developers, product
  leaders).

---

PREREQUISITE CHECKLIST
☐ Google tag installed for remarketing list building
☐ Conversion tracking configured in Google Ads
☐ Video creative produced — minimum 15 seconds, 30 seconds preferred
    for skippable in-stream
☐ Captions added to all video creative — 85% of YouTube is watched
    without sound in professional contexts
☐ YouTube channel exists if in-feed placement is planned

---

A/B TESTING RECOMMENDATION
Test 1: Custom intent audience vs In-market audience — which produces
  higher view-through rate and CTR
Test 2: Skippable in-stream vs In-feed placement for cold audiences
Test 3: 15-second vs 30-second creative — does additional context
  improve CTR for this persona

─────────────────────────────────────
```

---

## Step 6 — Cross-Channel Summary and Sequencing

After all three channel briefs, produce a cross-channel summary:

```
─────────────────────────────────────
CROSS-CHANNEL SUMMARY
─────────────────────────────────────

CHANNEL COMPARISON

Channel   | Cold CPM  | Cold CPL est. | Targeting strength
----------|-----------|---------------|--------------------
Meta      | $8–15     | $50–150       | Interest + behavior
Reddit    | $3–8      | $30–100       | Community + keyword
YouTube   | $5–12     | CPV $0.03–0.08| Intent + topic

CHANNEL RECOMMENDATION FOR THIS PERSONA
[Which channel is most likely to produce the best results and why —
  connect to specific findings from icp.md about where this persona
  spends time online]

---

RECOMMENDED LAUNCH SEQUENCE

Phase 1 — Launch (Month 1):
[Which channel to start with and why]

Phase 2 — Expand (Month 2–3):
[Which channel to add once Phase 1 is producing data]

Phase 3 — Retargeting (Month 2+):
[How to use retargeting across channels as pools build]

---

COPY MAPPING
[If Campaign Writer copy files were found in outputs/ — map each
  copy variant to the correct audience and channel here. Format:]

[Copy file] → [Channel] → [Audience]

[If no copy files found: "No matching copy found in outputs/. Run
  Campaign Writer for Meta, Reddit, and YouTube formats before
  launching."]

─────────────────────────────────────
```

---

## Step 7 — Save Option

After the cross-channel summary, ask:

"Would you like to save this audience brief?

It will be saved as:
paid_social_[company]_[YYYY-MM-DD].md

This is a complete three-channel setup document to hand to a media
buyer or use as a self-serve campaign setup guide."

Save only on explicit confirmation.

---

## Rules

Always read context/icp.md before building any audience — never
build targeting from general knowledge about B2B audiences.

Always derive subreddits and YouTube topics from the persona's actual
information diet in icp.md and persona_depth.md — not from generic
assumptions about what marketers watch or read.

Always flag when a targeting option may not be available in the
platform — Meta job title targeting is imprecise, not all subreddits
are targetable, not all competitors are available as Meta interests.

Always note minimum audience sizes for each platform — targeting too
narrow an audience prevents delivery.

Always include creative direction notes for Reddit — tone mismatch
on Reddit wastes budget more completely than any other channel.

Always produce cold and retargeting audiences separately — they
require different objectives, bidding strategies, and creative
approaches.

Always flag prerequisites before the channel is launched — a Pixel
not installed before launch means no retargeting pool builds.

Never recommend a channel without noting its limitations for this
specific persona and segment.

Never save without explicit confirmation.

Read active company name from context/icp.md for file naming.

Follow the file naming convention in CLAUDE.md for all output files.
