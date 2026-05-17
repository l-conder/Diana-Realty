# Handoff — Lead Qualifier

## What I receive

**From `00_orchestrator/`:**

- An open case file at `_cases/active/<case_id>/` with:
  - `card.md` containing at minimum: `source`, `side`, and any contact info available from the inbound request.
  - `agent_owner` field set (the orchestrator assigns based on geography or asks Diana).
  - A log entry naming this routing.
- An indication of urgency (referral = same-day, cold = 24-hour).

**What I require to do my job:**

- The original inbound message (forwarded email, screenshot, call notes). This is loaded into the conversation when the qualifier is invoked. If it's missing, the qualifier asks for it before drafting anything.
- Access to `_diana/voice-profiles.md` and `_diana/about-diana.md`. Always loaded.

**What I do NOT need:**

- Property research (that's later).
- A draft reply (that's my output).
- Diana's approval for routine qualification (only for edge cases — see below).

---

## What I produce

For every qualified or partially-qualified lead, I produce:

### 1. An updated `card.md`

Filled with everything I learned from the inbound message and any qualifier conversation. Specifically:

- All six fields (intent, budget, timeline, location, motivation, constraints) — filled or explicitly left blank.
- Pre-approval status if buyer-side.
- Property details if seller-side.
- `status` field updated to one of: `qualified` | `soft_lead` | `dead_lead`.
- `last_touched` updated.

### 2. A drafted first-contact reply

Saved as a code block in the log entry, or as a separate `draft_2026-05-19.md` in the case folder if the message is long enough to deserve its own file. Always in the agent owner's voice (per `_diana/voice-profiles.md`).

### 3. A log entry naming the next routing

Format:

```
YYYY-MM-DD HH:MM — 01_lead_qualifier (initials) — [one-sentence summary of what was qualified]. Status → [qualified | soft_lead | dead_lead]. → next: [00_orchestrator | 02_property_research | 03_client_communication].
```

---

## Where my work goes next

| If I marked the lead… | Route to… | What I include in the handoff log entry |
|---|---|---|
| `qualified`, buyer | `02_property_research` | Specific research request: neighborhood scan, recent comps, or specific property research |
| `qualified`, seller | `02_property_research` (CMA), then `03_client_communication` (listing presentation) | Property address and any seller-stated price expectation |
| `soft_lead` | `03_client_communication` (nurture cadence) | Suggested cadence: 30/90/180 days, with topic for first touch |
| `dead_lead` | `03_client_communication` (closing-loop message) | Then move case to `_cases/closed/` |
| Edge case requiring Diana | `00_orchestrator` → Diana | Reason for escalation |

---

## Bounce-back: when work comes back to me

A lead can come back to the qualifier in several ways. All are normal.

### Bounce-back from `02_property_research`

> Example: Research surfaces that the buyer's stated location doesn't have inventory in their budget.

The qualifier re-engages: "Based on what's actually available, your options are X or Y — which matters more, the neighborhood or the budget?" This is a re-qualification, not a failure. The card gets updated. Status may move from `qualified` back to `qualifying`.

### Bounce-back from `03_client_communication`

> Example: Comms drafts a follow-up and learns the client's timeline shifted dramatically.

Update the timeline field. If shift is large enough (e.g., "we're not moving until next summer"), status may move to `soft_lead` and route to nurture.

### Bounce-back from `04_transaction_coordinator`

> Example: Deal falls through (financing, inspection, cold feet). Buyer wants to restart the search.

Treat as a re-qualification, not a new case. Same `case_id`. Update card with what changed. Move status back to `qualifying`. Re-route to research with the updated criteria.

### Bounce-back from `00_orchestrator`

> Example: Orchestrator received new info on an existing case and the qualifier needs to incorporate it before the next step.

Update card. Log entry explaining what changed. Re-route forward.

---

## What I never do

- I never produce a draft that doesn't match the agent owner's voice. If I can't tell which agent owns, I ask the orchestrator before drafting.
- I never mark a lead `qualified` with missing fields. Missing fields = `qualifying` or `soft_lead`.
- I never recommend a specific property. That's research's job.
- I never push past a "not now." Re-route to nurture instead.
- I never let a soft lead drop without setting up a cadence.

---

## Failure modes

- **The qualifier sounds like the qualifier, not like Sara/Marcus/Diana.** Fix: open `_diana/voice-profiles.md` and rewrite. The qualifier's draft is the team's first audition.
- **Status moves too fast.** Marking a thin lead `qualified` puts research and comms to work on bad input. When in doubt, `qualifying` is fine.
- **Status moves too slow.** Holding a clearly soft lead in `qualifying` forever clutters the active list. Make the call: nurture or close.
