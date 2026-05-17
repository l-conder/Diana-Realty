# Handoff — Orchestrator

> The orchestrator is the **only specialist that doesn't receive from another specialist**. It receives from the outside world (email, text, Slack, walk-in, referral, agent question). Its job is to convert that incoming request into a clean handoff to one of the four downstream specialists.

---

## What I receive

**Anything from the outside world:**
- A forwarded email from a prospect
- A text screenshot from a client
- A Slack message from an agent asking what to do
- A voice memo transcript from Diana after a phone call
- An MLS listing the team is considering
- A reminder that a deadline is approaching

**Required from the requester:**
- Enough context to identify whether this concerns an existing case or starts a new one. If unclear, the orchestrator asks the requester one clarifying question before routing.

**Not required but useful:**
- The agent's intuition about who should handle it (the orchestrator will validate and override if needed)
- The urgency level (same-day, 24-hour, this-week)

---

## What I produce

For **every** routed request, exactly two artifacts:

### 1. An updated or new `_cases/active/<case_id>/card.md`

- If new: opened from template, with all known fields filled and unknown fields left blank.
- If existing: status updated if the incoming request changes status; `last_touched` updated; otherwise unchanged.

### 2. A log entry at the top of `_cases/active/<case_id>/log.md`

Format:

```
YYYY-MM-DD HH:MM — 00_orchestrator (initials) — [one-sentence reason this is being routed to specialist X]. → next: NN_specialist_name.
```

**That log entry IS the handoff.** The next specialist reads the log entry, reads the rest of the case file, and starts work.

---

## How downstream specialists pick up my work

Each downstream specialist's `handoff.md` defines what they need from me. I should produce all of it before logging the handoff.

| Routing to | What that specialist needs from me |
|---|---|
| `01_lead_qualifier` | Open case file with `source`, `side`, `agent_owner`, and any contact info available |
| `02_property_research` | Case must be `qualified` or later. Card must have `location` and `intent`. Log must name the specific research request (e.g., "CMA for 1814 Newning"). |
| `03_client_communication` | Card must have `agent_owner` set. Log must name the specific message to draft (situation, audience, voice). |
| `04_transaction_coordinator` | Status must be `under_contract`. Card must have `contract_date` and `close_date` at minimum. |

If any of those preconditions are missing, the orchestrator fills them in or asks the requester before routing.

---

## Bounce-back handling (when work comes back to me)

Sometimes a specialist finishes their work and needs to re-route. In that case, they log their result and write `→ next: 00_orchestrator` in their log entry. I then:

1. Read the new log entry.
2. Decide the next specialist based on what changed.
3. Write my own log entry under theirs with the next routing.

**Common bounce-back patterns:**

- **`01_lead_qualifier` → orchestrator:** lead is soft, not qualified. I route to nurture (a periodic check-in scheduled by `03_client_communication`).
- **`02_property_research` → orchestrator:** research surfaced a deal-breaker (e.g., property in a flood zone). I route to `03_client_communication` to draft the honest "this isn't the one" message in the agent's voice.
- **`04_transaction_coordinator` → orchestrator:** deadline slip. I route to `03_client_communication` to draft the catch-up, then back to TC.
- **Any specialist → orchestrator → Diana:** judgment call needed. I do not try to make the call.

---

## What I never do

- I never produce client-facing content. Not even one sentence.
- I never modify a specialist's previous log entry.
- I never close a case (that's TC or Diana).
- I never route to two specialists in parallel without writing two log entries explaining why.
- I never make the routing decision before reading both `card.md` and `log.md` for an existing case.

---

## Failure modes to watch for

If the team is using the orchestrator and the system feels slow or wrong, the cause is almost always one of three things:

1. **Stale case files.** Someone updated facts in their head and didn't update the card. Fix: enforce the "card before log before next step" sequence on every routing.
2. **Skipped routing.** Someone went directly to a specialist using a `/command` without an active case file. Fix: commands fail silently if there's no case; require the orchestrator path for anything new.
3. **Diana's playbook is too thin.** Routing defaults to "escalate to Diana" for too many cases. Fix: every time Diana resolves an escalation, the resolution gets written into `_diana/decision-playbook.md`. The playbook should grow weekly.
