---
name: whitespace
description: >
  Finds whitespace (underserved, unclaimed) business opportunities at the
  intersection of two or more markets or domains. Use when the user runs
  /whitespace or names a few business spaces (e.g. "pets, AI, art") and
  asks where the gaps, unmet needs, or open opportunities are where those
  spaces overlap. Maps what already exists at each intersection, then
  surfaces concrete, scored opportunity ideas with the evidence and the
  risks behind each one.
argument-hint: "<space 1>, <space 2>[, <space 3> ...] [--depth quick|standard|deep]"
---

# Whitespace

Find the gaps where two or more business spaces overlap but nobody (or
nobody good) is serving the customer yet.

Example: `/whitespace pets, ai, art`

## Inputs

- **Spaces**: 2–5 business domains, comma- or space-separated (pets, AI,
  art, fintech, elder care, outdoor, ...). If only one is given, ask for at
  least one more. If more than 5 are given, ask which to focus on, or group
  them.
- **Depth** (optional, default `standard`):
  - `quick` — no web research; reasoning only; 5 opportunities.
  - `standard` — light research per intersection; 8–10 opportunities.
  - `deep` — thorough research, incumbent mapping, demand signals;
    10–15 opportunities plus a one-page brief on the top 3.
- Optional context the user may add: their skills, budget, geography,
  B2B vs B2C preference. Use it to rank, never to filter out silently.

Don't interrogate the user up front. If the spaces are clear, start.

## Method

### 1. Define each space

For each space, write one line covering: who the customers are, what they
pay for today, and what is changing (tech, regulation, demographics,
behavior). Ambiguous terms ("AI", "art") get a sentence on which slice you
mean; pick the most commercially relevant interpretation and say so.

### 2. Enumerate intersections

List every pairwise intersection, plus the full N-way intersection (for
3 spaces: A×B, A×C, B×C, A×B×C). For 4–5 spaces, cover all pairs briefly
and the most promising triples in depth. The richest whitespace is often
where one space's *new capability* meets another space's *old pain*.

### 3. Map what already exists (the "occupied space")

For each intersection, identify existing players and categories:
- Established companies and well-funded startups
- Common product types and business models
- Obvious, already-crowded ideas (call these out explicitly — e.g. "AI pet
  portrait generators" is crowded, not whitespace)

When web search is available and depth is `standard` or `deep`, search for
each intersection (e.g. `"AI" "pet" startup`, `pet art marketplace`,
product directories, recent funding news, app store listings, Reddit/forum
complaints). Note the date sensitivity: markets move fast, so prefer
recent sources and say when something may be out of date. If search isn't
available, say the map is from general knowledge and may be stale.

Never invent company names, funding figures, or market-size numbers. If
you're not sure something exists, say "unverified" or leave it out.

### 4. Find the gaps

Use these lenses to generate candidate opportunities. Run each lens across
each intersection:

| Lens | Question |
|---|---|
| Underserved customer | Who in this overlap is ignored? (niche segments, B2B buyers behind the consumer, professionals, older/younger users, non-US markets) |
| Unmet job | What job are people hacking together with spreadsheets, forums, or 3 different apps? |
| Complaint mining | What do reviews and forums complain about in existing products? |
| New-capability transfer | What can one space now do cheaply that the other hasn't adopted yet? |
| Business-model swap | Does a model that works in one space (subscription, marketplace, insurance, rental, B2B SaaS) not exist yet in the other? |
| Picks and shovels | Who sells tools, data, or infrastructure to the people building in this overlap? |
| Trust / regulation gap | Where is there demand but no trusted, compliant, or credentialed provider? |
| Timing shift | What became possible or necessary in the last 1–2 years (cost drop, new law, cultural shift)? |

Generate more candidates than you'll keep, then cut the ones that are
crowded, vague ("an app for X"), or that only touch one space.

### 5. Score and rank

Score each surviving opportunity 1–5 on:

- **Gap** — how unserved is it really? (5 = nobody credible)
- **Demand** — evidence people want it / pay for adjacent things
- **Fit** — how genuinely it needs *all* the combined spaces (not just one)
- **Feasibility** — can a small team build and reach customers?
- **Defensibility** — data, community, network effects, or expertise moat

Total out of 25. Rank by total; break ties on Demand. If the user gave
context (skills, budget), add a short "fit for you" note but keep the
score objective.

## Output format

Keep it scannable. Use this structure:

```markdown
# Whitespace: <Space A> × <Space B> × <Space C>

## The spaces
- **A** — one line
- **B** — one line
- **C** — one line

## Intersection map
| Intersection | What's already there | Crowded? | Whitespace signal |
|---|---|---|---|
| A × B | ... | High/Med/Low | ... |
| ... | | | |

## Top opportunities
### 1. <Short, concrete name> — <score>/25
- **What**: one or two sentences, specific product/service.
- **Who pays**: the customer and roughly how (subscription, per-use, B2B license...).
- **Why it's open**: the gap, with evidence or reasoning.
- **Why now**: what changed.
- **Spaces used**: which of the input spaces it combines and how.
- **Risks**: the top 1–2 reasons it could fail.
- **Cheapest test**: a validation step doable in under 2 weeks.
- Scores: Gap x · Demand x · Fit x · Feasibility x · Defensibility x

(repeat)

## Crowded — avoid or differentiate hard
- Idea — why it's crowded

## Wildcards
2–3 higher-risk, non-obvious ideas that didn't score top but are worth a look.

## Caveats
What was researched vs. reasoned, and what to verify before acting.
```

For `deep`, add a one-page brief on each of the top 3: target customer
profile, rough competitor list with links, go-to-market first step, and
what would have to be true for it to work.

## Quality bar

- **Specific over generic.** "Subscription AI that turns a vet's notes
  into an owner-friendly illustrated care sheet" beats "AI for pet health".
- **Every opportunity must use at least two of the spaces meaningfully.**
- **Say what's crowded.** Telling the user what *not* to build is half the value.
- **Separate evidence from inference.** Mark claims as sourced, reasoned,
  or unverified. Cite links for sourced claims.
- **No fake numbers.** Use ranges or qualitative terms unless a source backs a figure.
- End by offering next steps: go deeper on one opportunity, run the
  analysis with a different set of spaces, or turn the top pick into a
  one-page pitch or validation plan.
