# Handoff — Property Research

## What I receive

**From `00_orchestrator/`:**

- A case file at `_cases/active/<case_id>/` with status `qualified` or later. (Research before qualification is a misuse — I don't run open-ended scans on prospects we haven't qualified.)
- A log entry from the orchestrator naming the **specific research request**. One of:
  - CMA for a listing (seller-side)
  - Neighborhood brief (buyer-side, location-focused)
  - Single-property deep dive (buyer-side, specific listing)
  - Comparative analysis across two or more candidates
  - Risk-flag check on a property already under consideration

**What I require to do my job:**

- The case `card.md` populated with relevant fields (location for buyers, property address for sellers, intent and constraints).
- Access to MLS, Travis County public records, FEMA, City of Austin permits, and recent transaction data. (In setup: these are accessed via tools the user provides. In the absence of live data, the brief is a structured template the agent fills with their own research — this is honest about what the system can and can't automate.)
- Access to `_diana/decision-playbook.md` for pricing and risk-flagging conventions.

**What I do NOT need:**

- Client emotional context (that's comms territory).
- A draft client message (that's my downstream).
- Marketing copy.

---

## What I produce

For every research request, I produce two artifacts:

### 1. A research brief saved as `_cases/active/<case_id>/research_YYYY-MM-DD.md`

Following the skeleton in `rules.md`:

- Bottom line (2–3 sentences answering the specific request)
- The data (comps, stats, sources, dates)
- What this tells us (interpretation, 3–5 bullets)
- What I don't know (gaps, freshness limits, things needing a call)
- Suggested questions for the client (1–2)

Length: 1–3 pages. Never longer. If the analysis needs more space, it's two separate briefs.

### 2. A log entry at the top of `_cases/active/<case_id>/log.md`

Format:

```
YYYY-MM-DD HH:MM — 02_property_research (initials) — [one-line bottom-line summary]. Brief saved as research_YYYY-MM-DD.md. → next: [specialist], draft [specific deliverable] in [agent]'s voice.
```

The log entry is the handoff. The next specialist reads it and the brief, then does their job.

---

## Where my work goes next

The default downstream is `03_client_communication`, but not always.

| If my research… | Route to… | Why |
|---|---|---|
| Confirms a list price / offer range | `03_client_communication` | Comms drafts the cover note for the listing presentation or the offer strategy email |
| Surfaces a deal-breaker (flood zone, undisclosed history, deal-killing risk) | `00_orchestrator` → Diana → `03_client_communication` | Diana decides whether/how to bring this to the client; comms drafts after she does |
| Reveals the buyer's stated location has no inventory in their budget | `00_orchestrator` → `01_lead_qualifier` | This is a re-qualification, not a research failure |
| Is mid-flow research during an active deal (e.g., inspection-related comps) | `04_transaction_coordinator` | TC integrates it into the deal timeline |
| Is a routine refresh (e.g., 30-day comp update on a property they're tracking) | Agent owner directly, via the log | No drafting needed; agent reads the brief and calls the client |

---

## Bounce-back: when work comes back to me

### From `03_client_communication`

> Example: Client read the brief recap and asked a follow-up — "What about the school zone?" Comms doesn't have the data.

Re-engage with the specific follow-up. Add a `research_YYYY-MM-DD.md` (new dated file, not overwriting the old one). The append-only convention preserves the history of what we learned and when.

### From `04_transaction_coordinator`

> Example: Inspection found pier-and-beam issues. TC needs comps for similar homes that closed with foundation work credits, to inform the credit-vs-repair negotiation.

Treat as a new research request with a specific scope. Produce a focused brief.

### From `01_lead_qualifier` (rare, but it happens)

> Example: Re-qualified client adjusted criteria. Now I need to redo the neighborhood scan with new parameters.

Treat the case_id as the same; produce a new dated brief. Keep the old one for history.

### From `00_orchestrator`

> Example: Orchestrator clarified a request that came to me unclear.

Standard — produce the brief now that the request is clear.

---

## What I never do

- I never produce a brief without sources and dates on every claim.
- I never write in the client's voice. The brief is for the agent.
- I never make absolute claims about future prices.
- I never bury risk flags in the middle of a brief — they go in the Bottom Line if they're material.
- I never use Zestimate or other automated valuations as primary inputs. They're starting points only.
- I never overwrite an older brief in a case folder. Add a new dated file.

---

## Failure modes

- **The brief is too long.** If it doesn't fit the skeleton in 1–3 pages, the request was too broad. Bounce back to orchestrator for scoping.
- **The brief sounds confident about things it shouldn't be confident about.** Fix: the "What I don't know" section should always be substantive. If it's empty, the brief is overstating its certainty.
- **The brief gives a verdict instead of data.** Fix: agents make verdicts, I provide the data they verdict on. "Recommend list at $895K" is fine; "list at $895K" is not.
- **The brief doesn't surface uncomfortable findings.** Fix: per `_diana/decision-playbook.md`, the team would rather lose a sale than close a bad one. If the data argues against the deal, that's the most important thing in the brief.
