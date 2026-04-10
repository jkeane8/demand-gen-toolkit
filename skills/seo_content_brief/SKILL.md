# SEO Content Brief
## Produces a pillar page brief plus 3-5 cluster piece briefs
## for a given topic or keyword cluster
## AEO and GEO optimisation included in every brief
## Connects to keyword file, ICP, competitor intel,
## and competitor ad intelligence outputs

---

## What This Skill Does

Takes a topic or keyword cluster as input. Reads keyword data from
the existing keyword file in outputs/ if one exists — runs fresh
keyword research if not. Reads context files to understand the ICP,
buyer vocabulary, proof points, competitive landscape, and market
gaps. Checks outputs/ for any Competitor Ad Intelligence reports to
identify keywords where competitors are strong in both paid and
organic — and flags these with a compete-or-pivot recommendation.

Produces one run covering:
- One pillar page brief
- Three to five cluster piece briefs
- Each brief is fully specified: target keyword, search intent,
  recommended H1 and title tag, meta description, recommended
  structure with section-by-section guidance, internal linking map,
  AEO question targets with exact question phrasing, GEO citation
  signals, schema markup type, and estimated word count

AEO (Answer Engine Optimisation) and GEO (Generative Engine
Optimisation) are treated as primary optimisation targets alongside
traditional search ranking — not afterthoughts. Every brief
identifies the specific questions AI answer engines are likely to
surface this content for and how to structure the content to be
selected as the answer or cited as a source.

Runs on demand. Triggered by any mention of SEO brief, content
brief, blog brief, pillar page, content cluster, SEO content,
organic content, or any mention of SEO strategy or content planning.

---

## Step 1 — Read Before Building

### Required files

**context/icp.md**
Read for: exact buyer vocabulary and phrases, pain points by
segment, trigger events, and the questions buyers are actually
asking. The ICP vocabulary is the foundation for AEO question
identification — AI answer engines are queried in the buyer's own
language, not vendor language. Map every AEO question target to a
phrase or question pattern documented in the ICP.

**context/competitors.md**
Read for: competitor names, their positioning, and the angles they
already own. Used to identify which topics competitors are likely
ranking for organically and whether competing on those keywords
requires a differentiation angle rather than a direct match.

**context/market.md**
Read for: market category, trends, and the broader topic landscape.
Used to identify cluster piece opportunities beyond the immediate
product category — educational and trend content that attracts
early-stage buyers before they are searching for a specific product.

**context/proof_points.md**
If found: read for named customer results. These are GEO citation
signals — specific attributed outcomes that AI systems can extract
and cite when answering questions about this category. Every
GEO-optimised piece should include at least one named customer
result with a specific metric.

### Optional files

**context/deep/market_gaps.md**
If found: read for unclaimed positioning angles and keyword white
space. These are the highest-priority content opportunities — topics
where competitors have not yet produced authoritative content and
where the active company can establish first-mover authority.

**context/deep/voice_of_customer.md**
If found: read for exact buyer quotes and phrases. These map
directly to AEO question phrasing — the way buyers describe their
problems in their own words is how they query AI answer engines.
VOC phrases should appear verbatim in AEO question targets where
possible.

**outputs/keywords_*.md**
If a keyword file exists: read it before doing any keyword research.
Extract the keyword clusters, scores, and intent classifications.
Map the highest-scoring keywords to pillar and cluster assignments.
Keywords scoring above 80 are the priority targets for the pillar
page brief.

If no keyword file exists: run fresh keyword research for the stated
topic using web search. Search for the topic, competitor sites
ranking for the topic, and common questions asked about the topic.
Note clearly in the output that keyword data came from fresh
research rather than a scored keyword file.

**outputs/competitor_intel_*.md**
If a Competitor Ad Intelligence report exists: read it before
building the brief. For every keyword in the brief, check whether a
competitor was flagged as active in paid advertising for that angle.
If a competitor is strong in both paid search and organic for a
keyword, flag it with a compete-or-pivot recommendation.

### Display before building

```
SEO CONTENT BRIEF
─────────────────────────────────────
Topic: [stated topic or keyword cluster]
Active company: [from context/icp.md first line]
Keyword data source: [Existing keyword file — filename /
  Fresh research — web search]
Context files loaded:
[✓/✗] context/icp.md
[✓/✗] context/competitors.md
[✓/✗] context/market.md
[✓/✗] context/proof_points.md
[✓/✗] context/deep/market_gaps.md
[✓/✗] context/deep/voice_of_customer.md
Competitor Ad Intel found: [Yes — filename /
  No — competitor organic strength evaluated from web search]
Keyword file found: [Yes — filename /
  No — running fresh research]
Building now.
─────────────────────────────────────
```

---

## Step 2 — Keyword Assignment and Competitor Flags

Before writing any brief, produce a keyword assignment table showing
how keywords are distributed across the pillar and cluster pieces,
with competitor flags where relevant.

```
─────────────────────────────────────
KEYWORD ASSIGNMENT
─────────────────────────────────────
Content piece        | Target keyword
                     | Est. monthly volume
                     | Difficulty
                     | Competitor flag
─────────────────────────────────────
Pillar page          | [keyword]
                     | [volume or "est. from research"]
                     | [Easy / Medium / Hard]
                     | [Competitor flag or "None"]

Cluster piece 1      | [keyword]
                     | [volume]
                     | [difficulty]
                     | [flag or "None"]

Cluster piece 2      | [keyword]
                     | [volume]
                     | [difficulty]
                     | [flag or "None"]

[repeat for all cluster pieces]
─────────────────────────────────────
```

For each keyword that carries a competitor flag, display a separate
block immediately below the table:

```
─────────────────────────────────────
COMPETITOR FLAG: [keyword]
─────────────────────────────────────
Competitor: [competitor name from competitors.md]
Strength: [Paid only / Organic only / Both paid and organic]
Source: [Competitor Ad Intel report — filename /
  Web search finding]

COMPETE OR PIVOT RECOMMENDATION:

Compete — with differentiation angle:
[Recommend this when the keyword has high strategic value and the
  active company has a genuine differentiator that competitors
  cannot match on this topic. State the specific angle: what the
  content should argue or demonstrate that the competitor's content
  does not. Draw the differentiator from competitors.md positioning
  gaps and market_gaps.md if available.]

Pivot — to adjacent keyword:
[Recommend this when the competitor has such strong authority on
  the exact keyword that ranking against them would require months
  of effort for marginal traffic. Suggest a specific adjacent
  keyword that covers the same buyer intent with less competition
  — draw from market_gaps.md if available.]

Split — target both:
[Recommend this when the pillar page should target the competitive
  keyword for brand authority, but a cluster piece should target
  an adjacent lower-competition keyword for actual traffic. Explain
  the division of purpose between the two pieces.]
─────────────────────────────────────
```

---

## Step 3 — Pillar Page Brief

Produce the full pillar page brief using this exact structure.

```
─────────────────────────────────────
PILLAR PAGE BRIEF
─────────────────────────────────────

OVERVIEW
Target keyword: [primary keyword]
Secondary keywords: [2-4 supporting keywords to include naturally
  — draw from the keyword file or related terms from icp.md
  buyer vocabulary]
Search intent: [Informational / Navigational / Commercial /
  Transactional — with one sentence on what the searcher wants
  when they type this query]
Estimated word count: [3,000–5,000 for pillar pages — adjust up
  if competing content is longer; never pad to hit a word count,
  only add content that answers a real question]
Funnel stage: [Awareness / Consideration / Decision]
Primary persona: [from icp.md — who is most likely to find and
  read this content; note their seniority and what they are trying
  to accomplish when they search this query]

─────────────────────────────────────

METADATA

Title tag: [Under 60 characters. Include target keyword. Put the
  keyword first or second in the tag. Do not put the company name
  in the title tag unless it is the keyword. Title tag is what
  appears in search results — make it a clear answer to the
  query, not a brand statement.]

Meta description: [Under 160 characters. Include target keyword.
  Write as an answer preview — the meta description should answer
  the search query in one sentence before inviting the click.
  Include a specific metric or named outcome where the keyword
  supports it — this improves CTR because it signals the content
  has evidence, not just explanation.]

H1 headline: [Can differ from title tag. Should be conversational
  and include the target keyword. The H1 is what the reader sees
  first — make it the clearest possible statement of what the
  page delivers. Avoid clever; favour direct.]

URL slug: [Lowercase, hyphenated, keyword-forward. No stop words
  unless they are part of the exact keyword. Under 60 characters.]

─────────────────────────────────────

CONTENT STRUCTURE

Introduction (150–200 words):
Purpose: Frame the problem the keyword represents, name who this
  content is for, and signal what the reader will learn. Include
  the target keyword in the first paragraph. Do not open with a
  generic definition — open with the problem or question.
Key element: One sentence that answers the primary AEO question
  directly. AI answer engines often extract the opening paragraph
  as the answer — make the first paragraph stand alone as a
  useful answer if someone never reads further.

[For each major section — produce 4–6 sections for a pillar page:]

Section [N] — [Section heading, written as an H2, phrased as
  a statement or question that matches how a buyer would
  search for this subtopic. Include a secondary keyword
  where it fits naturally — never force it.]

Purpose: [What this section does for the reader and for the
  search engine — one sentence each]
Key points to cover: [3–5 specific points drawn from icp.md
  pain points, market.md trends, and proof_points.md — not
  generic advice. Every point should connect to something
  a real buyer in the ICP cares about or a proof point that
  validates a claim.]
Word count guidance: [recommended range for this section]
Proof point to include: [Specific named customer result from
  proof_points.md that belongs in this section. State the
  customer name, the metric, and the context. This is also
  a GEO citation signal — it makes this section citeable
  by AI systems because it is specific and attributed.]

Conclusion (100–150 words):
Purpose: Summarise the key argument the content made, connect
  it to the next step for the reader. The CTA must match the
  funnel stage — awareness content links to a consideration-stage
  resource, not a demo request. A pillar page CTA should point
  to a cluster piece or a gated benchmark resource, not a
  product page.

─────────────────────────────────────

INTERNAL LINKING

Link to this page from:
[List 2–3 existing site pages that should link to this pillar
  page with the target keyword as anchor text. If site structure
  is unknown, suggest page types: product page, related case study,
  existing blog post on a related topic. Note the suggested anchor
  text for each.]

Link from this page to:
[List every cluster piece that will be created in this run.
  The pillar page must link to every cluster piece it anchors —
  this is the structural requirement of a pillar-cluster model.
  For each cluster piece note:]
  - Cluster piece title
  - Anchor text to use (should match the cluster piece's target
    keyword exactly or closely)
  - Where in the pillar page the link should appear (which section)

─────────────────────────────────────

AEO OPTIMISATION
Answer Engine Optimisation — structuring content to be selected
as the answer by AI tools including ChatGPT, Perplexity, Google
AI Overview, and Claude.

Target questions for this page:
[List 5–8 specific questions this page should answer. These are
  the exact phrasings a buyer in the ICP would type into an AI
  answer engine. Derive from:]
  - icp.md pain points and trigger events turned into questions
  - voice_of_customer.md phrases turned into questions
  - The search query itself phrased as a direct question
  - Related questions a buyer would ask after the primary query

For each target question:

Question: [exact question phrasing — write it the way a buyer
  would type it, not the way a marketer would write it]
Answer format: [one sentence / numbered list / comparison table /
  definition — the format most likely to be extracted as an answer]
Where in content: [which section should answer this question and
  how — the question should appear as a subheading (H2 or H3) or
  be answered in the opening sentence of a paragraph]
AEO signal strength: [High — direct match to a common AI query
  pattern for this category / Medium — indirect match, still worth
  targeting / Low — informational but unlikely to be the primary
  answer surfaced]

AEO structural requirements for this page:
- Answer the primary keyword as a direct question somewhere in
  the introduction — one clear sentence that functions as a
  standalone answer
- Use H2 and H3 headings that match question phrasing where
  possible — AI systems extract headings as candidate answers
- Include a definitions section if the keyword involves a technical
  term the buyer may not know — definitions are frequently extracted
  as AI answers
- Include a numbered or bulleted summary that can be extracted as
  a list answer — list format is the most commonly extracted AEO
  format after definitions
- Keep answer paragraphs under 100 words per question — longer
  paragraphs are less likely to be extracted as discrete answers

─────────────────────────────────────

GEO OPTIMISATION
Generative Engine Optimisation — structuring content to be cited
as a source by generative AI systems when they answer questions
about this topic.

Citation signals to include in this page:

Named customer evidence:
[List the specific proof points from proof_points.md that should
  appear in this page. For each, note: the customer name, the
  metric, the context, and which section of the content it belongs
  in. Named attributed outcomes are the highest-value GEO signal
  — AI systems strongly prefer specific, verifiable claims over
  generic assertions. An unattributed claim ("companies see 40%
  cost reduction") has low GEO value. A named claim ("Company X
  reduced costs by 40% — case study published at [URL]") has high
  GEO value because an AI system can verify and cite the source.]

Original data or research:
[If the active company has proprietary data — benchmark reports,
  survey results, internal research — note where it should be
  referenced in this page. Original data is the strongest GEO
  signal because it cannot be found elsewhere. AI systems prefer
  sources that have data no other source has. Even a small
  internal dataset cited with methodology has high citation value.]

Expert attribution:
[Note where named expert or customer quotes should appear. AI
  systems weight attributed quotes from named individuals over
  unattributed claims. A quote from a named practitioner at a
  named company is a strong GEO signal. Draw from
  voice_of_customer.md if direct quotes are available.]

Specific statistics with sources:
[List any industry statistics from market.md that should be cited
  in this page. Include the source. Unsourced statistics have low
  GEO value — an AI system cannot verify them. Sourced statistics
  have high GEO value because the AI can trace the claim.]

Entity coverage:
[List the named entities — companies, people, technologies,
  organisations, regulatory bodies — that should be mentioned in
  this page to establish topical authority with AI systems. Entities
  signal to AI that the content is knowledgeable about the real
  landscape of this topic. Draw from competitors.md, market.md,
  and icp.md trigger events for relevant entities.]

─────────────────────────────────────

SCHEMA MARKUP

Recommended schema type: [Article / HowTo / FAQ / BreadcrumbList
  — choose the type most appropriate for this content's structure
  and primary purpose. FAQ schema is the default recommendation
  when AEO is a primary objective, because FAQ schema feeds
  directly into the structured data that AI systems extract for
  answer generation.]

Why this schema: [One sentence on why this schema type improves
  search appearance and AI citation likelihood for this specific
  page — connect to the content's structure, not a generic
  explanation of schema.]

Required fields to complete:
[List the specific fields from the recommended schema type that
  must be filled before implementation. Examples:]
  Article schema: headline, author (name, url), datePublished,
    dateModified, description, image
  FAQ schema: list each question and its answer as they should
    appear in the markup — these must match the AEO target
    questions above
  HowTo schema: name, description, each step with name and text

FAQ schema question-answer pairs:
[If FAQ schema is recommended — and it should be for most AEO-
  focused briefs — list the 3–5 question-answer pairs to mark up.
  These must match the AEO target questions. Keep each answer
  under 100 words for extraction quality.]

Q: [exact question]
A: [concise answer — under 100 words, direct, specific]

[repeat for each pair]

─────────────────────────────────────
```

---

## Step 4 — Cluster Piece Briefs

Produce a full brief for each cluster piece using the same structure
as the pillar page brief, adapted for a narrower topic. Produce
between 3 and 5 cluster briefs depending on how many keyword
opportunities exist in the keyword file or fresh research. Do not
pad to hit 5 if there are only 3 strong opportunities.

Cluster pieces should:
- Target a longer-tail keyword that is a specific subtopic of the
  pillar keyword
- Serve a more advanced or specific buyer — someone who has already
  read the pillar page or is searching for a particular aspect
  of the topic rather than an overview
- Link back to the pillar page in the introduction and conclusion
  with the pillar's target keyword as anchor text
- Have an estimated word count of 1,000–2,000 words (shorter than
  the pillar page — cluster pieces answer one specific question
  deeply, not the full topic broadly)

Label each clearly before the brief:

```
─────────────────────────────────────
CLUSTER PIECE [N] BRIEF
─────────────────────────────────────
```

Use the same sections as the pillar brief for each cluster piece:
Overview, Metadata (title tag, meta description, H1, URL slug),
Content Structure, Internal Linking, AEO Optimisation, GEO
Optimisation, and Schema Markup.

In the internal linking section for every cluster piece, include:

Must link back to:
[Pillar page title] — use the pillar's target keyword as anchor
  text. Link should appear in the introduction (first 200 words)
  and the conclusion.

Should also link to:
[Any other cluster piece in this set whose topic is directly
  related — note the anchor text for that link too]

Link to this cluster piece from:
[Suggest 1–2 existing site pages from which this cluster piece
  should receive a link — product pages, case studies, or related
  existing blog posts that cover adjacent topics]

---

## Step 5 — Content Calendar Recommendation

After all briefs display a production sequence recommendation.

```
─────────────────────────────────────
CONTENT CALENDAR RECOMMENDATION
─────────────────────────────────────
Production sequence:

Week 1–2: [Cluster piece name]
Target keyword: [keyword]
Why first: [One sentence — either lowest competition and fastest
  to rank, or highest AEO potential for an immediate answer engine
  placement, or most directly connected to an active buyer trigger
  from icp.md]

Week 3–4: [Cluster piece name]
Target keyword: [keyword]
Why second: [One sentence]

Week 5–6: [Cluster piece name]
Target keyword: [keyword]
Why third: [One sentence]

[Add remaining cluster pieces in sequence before the pillar]

Week [N]–[N+1]: Pillar page
Target keyword: [pillar keyword]
Why last: The pillar page should publish after at least 2–3
  cluster pieces are live so its internal links point to
  existing published content from day one. A pillar page that
  launches with no cluster pieces live has no internal linking
  structure and weaker authority signal. Publish the clusters
  first, then the pillar with all links active.

─────────────────────────────────────
Total estimated writing time:
[Sum the word counts across all pieces and estimate at 1 hour
  per 500 words for a writer working from a detailed brief.
  Show the calculation: X total words ÷ 500 × 1 hour = Y hours]

Note on pillar page timing:
Publishing the pillar page last — after cluster pieces are live —
ensures the internal linking structure is active at launch. A
pillar page that goes live with broken or missing cluster links
signals incomplete topical coverage to search engines. Publish
clusters first, then the pillar with all links confirmed working.
─────────────────────────────────────
```

---

## Step 6 — Save Option

After all briefs and the content calendar, ask:

"Would you like to save this brief package?

It will be saved as:
seo_brief_[topic]_[company]_[YYYY-MM-DD].md

This gives you a complete brief package to hand to a content
writer or use as your own writing guide for the full cluster."

Save only on explicit confirmation.

---

## Rules

Always read context/icp.md before building any brief — buyer
vocabulary from the ICP is the foundation for AEO question
identification. Never write AEO questions from general knowledge
about the topic.

Always check outputs/ for a keyword file before doing fresh
research — the Keyword Finder's scored keyword data is more
reliable than a fresh web search. If a keyword file exists use
it. Note clearly in the output if fresh research was used instead.

Always check outputs/ for a Competitor Ad Intelligence report —
if a competitor is strong in both paid and organic for the same
keyword, the content strategy must account for this. Never ignore
a competitor flag.

Always include named proof points from proof_points.md as GEO
citation signals. Generic claims have low GEO value. Named,
attributed outcomes with specific metrics are the highest-value
GEO signal.

Always derive AEO questions from ICP vocabulary and VOC phrases
— not from what a marketer thinks buyers ask, but from what the
context files document they actually say and search for.

Always recommend FAQ schema when AEO is a primary objective —
FAQ schema is the most direct path from structured content to
AI answer engine selection.

Always sequence cluster pieces before the pillar page in the
content calendar — the pillar should launch with internal links
already live.

Never hardcode company names, competitor names, product names,
or industry-specific terms into this skill file — all
company-specific content must come from context files at runtime.

Never produce a brief without AEO question targets — AEO
optimisation is a required output for every piece in every run,
not an optional section.

Never save without explicit confirmation from the human.

Read active company name from the first line of context/icp.md
for file naming.

Follow the file naming convention in CLAUDE.md for all output
files.
