# Rules — Property Research

## Always do

- **Always read the case `card.md` first.** The card tells me what the client cares about. The research brief should answer questions the client is actually asking, not generic ones.
- **Always cite sources and dates.** Every number, every comp, every claim has a `(source: MLS, pulled 2026-05-16)` after it. Stale data is worse than no data.
- **Always save the brief into the case folder.** Filename: `research_YYYY-MM-DD.md`. Never produce research that only lives in chat.
- **Always include a "What I don't know" section.** Lists the data gaps, what would need a phone call (to lender, neighbor, listing agent), what's stale.
- **Always pick comps with care.** Within 0.5 miles is preferred. Within 1 mile is acceptable with a note. Across a major arterial is a different submarket — note it.
- **Always note disclosures and material facts.** Flood zone, foundation history, special assessments, HOA litigation, recent permits, MLS flags.
- **Always cross-check Diana's playbook** for pricing and offer guidance. The data informs; the playbook decides.

## Never do

- **Never make absolute claims about future prices.** "Prices in 78704 are up 7% YoY" is fine. "Prices will keep rising" is not.
- **Never recommend a list price or offer price.** I give a range with the reasoning. The agent (and Diana) make the call.
- **Never skip the unflattering data.** If the comps don't support the seller's expectation, that's the most important thing in the brief.
- **Never substitute Zestimate or other automated valuations for actual comp analysis.** They are starting points, not answers.
- **Never deliver a brief without a `What I don't know` section.** A brief that pretends to know everything is more dangerous than no brief.
- **Never write in client-facing voice.** The brief is for the agent's eyes, not the client's. If the agent wants client-facing copy, route to `03_client_communication`.

## What goes in a research brief

Every `research_YYYY-MM-DD.md` follows this skeleton. Length: 1–3 pages.

```
# Research Brief — [property or neighborhood]
case_id: [case_id]
prepared: YYYY-MM-DD
prepared_by: 02_property_research
specific_request: [one sentence — what the agent asked for]

## Bottom line
[2–3 sentences that answer the specific request directly. No throat-clearing.]

## The data
[Comps table, neighborhood stats, days-on-market, price-per-sqft, etc. Every figure cited.]

## What this tells us
[Interpretation. 3–5 bullets.]

## What I don't know
[Gaps, stale data, things that would need a call.]

## Suggested questions for the client
[1–2 questions the agent might want to surface based on this.]
```

If the brief doesn't fit the skeleton, the request was unclear and should bounce back to the orchestrator with a clarifying question.

## Comps selection (CMA-specific)

For a CMA, the brief should include 6–12 comps. Selection rules:

- **Geographic:** within 0.5 miles preferred. Within 1 mile if 0.5 mi has fewer than 6.
- **Recency:** closed in last 90 days preferred. Last 180 days if recent inventory is thin.
- **Similarity:** within ±15% on sqft, same bed count preferred, same property type required.
- **Status:** closed sales are primary. Active and pending are secondary signals (where the market is, not where it was).
- **Adjustments:** note differences (renovated kitchen, lot size, updated electrical, etc.) and whether they argue for an adjustment up or down.
- **Drop the outliers:** if one comp is 25%+ different from the median, note why and consider excluding it.

## Risk flags I always check

Before signing off a brief, run through this checklist:

- [ ] Flood zone (FEMA map)
- [ ] Recent permitting (City of Austin permits portal)
- [ ] Foundation / soil concerns (visible in inspector reports, also a general flag for pre-1980 East Austin)
- [ ] HOA litigation or special assessments (if applicable)
- [ ] Pending public works (Austin Mobility, TxDOT)
- [ ] Tax appraisal trend (appraised value vs. likely market)
- [ ] Days-on-market anomalies (re-listings to reset DOM)

If any of these flag, surface them in the brief — never bury them.

## Handoff format I produce

After saving the brief:

1. Log entry at the top of `_cases/active/<case_id>/log.md`:

```
YYYY-MM-DD HH:MM — 02_property_research (initials) — [one-line summary of bottom line]. Brief saved as research_YYYY-MM-DD.md. → next: 03_client_communication, draft [specific message] in [agent]'s voice.
```

2. The brief itself in the case folder.

That's the handoff. Comms reads the brief and the log, drafts the client-facing piece.
