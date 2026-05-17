# Handoff — Client Communication

## What I receive

**From any other specialist** (this is the most-handed-to specialist in the system):

- A case file with `card.md`, `log.md`, and any specialist briefs (research, TC checklists) in the folder.
- A log entry naming the specific communication needed. The log entry should specify:
  - **Situation** (recap of tour, response to inspection, listing presentation cover, etc.)
  - **Audience** (which client; if a referral source, who)
  - **Voice** (which agent's voice to draft in)
  - **Constraints** (anything sensitive Diana flagged, anything the playbook overrides)
  - **Channel** (email, text, call-prep notes)

**What I require:**

- The agent owner's name must be set in `card.md`.
- Access to `_diana/voice-profiles.md` and `_diana/decision-playbook.md`.
- For research-based drafts: the relevant `research_YYYY-MM-DD.md` brief must exist in the case folder.
- For deal-stage drafts: the relevant `card.md` "Deal" section must be populated.

**What I do NOT need:**

- The decision itself. If the message contains a recommendation, that recommendation came from somewhere else (Diana, research, TC). I draft what the team has decided.
- Permission to invent voice. If the agent's voice profile is missing, default to Diana's voice and flag.

---

## What I produce

For every communication request, I produce:

### 1. A draft (or set of drafts) in the assigned agent's voice

- For short messages (texts, brief emails): in a code block in the log entry.
- For long messages (listing presentation covers, year-end batches, multi-paragraph emails): saved as `draft_YYYY-MM-DD_subject.md` in the case folder, referenced from the log.
- For situations requiring a call (per playbook): call-prep notes + a post-call recap draft. Two artifacts, not one.

### 2. A log entry

Format:

```
YYYY-MM-DD HH:MM — 03_client_communication (initials) — drafted [situation] in [agent]'s voice. → next: [agent] to review and send.
```

If the draft requires Diana's review before send (Jamie's drafts, or anything sensitive), the log entry says so explicitly:

```
→ next: Diana to review, then [agent] to send.
```

---

## Where my work goes next

Most often: **back to the human agent**, who reads, edits if needed, and sends.

But sometimes the case keeps moving:

| If my draft is for… | What happens next |
|---|---|
| A first-contact reply (from qualifier handoff) | Agent sends, then `01_lead_qualifier` re-engages with reply |
| A research recap (from research handoff) | Agent sends, then waits for client decision |
| A listing presentation cover (from research handoff, seller) | Agent presents, then if listing wins → `00_orchestrator` flips status, → MLS prep |
| An offer-strategy email (buyer) | Agent sends, then offer drafted and submitted (TC takes over once accepted) |
| A response to an inspection finding (from TC handoff) | Agent sends, then `04_transaction_coordinator` tracks the counter |
| A nurture-cadence touch (from qualifier soft-lead handoff) | Agent sends, then schedule next touch in the log |
| A year-end check-in (from closed-case batch) | Agent sends, then move on |

---

## Bounce-back: when work comes back to me

### From the agent (revision request)

> Example: Sara reads the draft, says "too long, also I'd lead with the data point about Travis Heights." I rewrite. The original draft stays in the log; the revision is a new entry. We don't overwrite history — we learn from it.

The revision is also a teaching signal: every time an agent has to edit a draft significantly, that edit becomes a note in `_diana/voice-profiles.md` (for voice issues) or in the relevant rules.md (for situation-handling issues). The system gets better over time.

### From `04_transaction_coordinator`

> Example: TC flagged that the lender hasn't responded and the financing contingency is in 48 hours. Comms drafts the catch-up email to the buyer + a draft message to the lender.

Two drafts in one log entry — one for each audience.

### From `00_orchestrator`

> Example: Diana resolved an escalation and decided on a position. Orchestrator routes to comms to put the position into a client-facing message.

Standard situation. Draft, log, done.

### From `01_lead_qualifier`

> Example: A "qualified" lead's reply made it clear they actually aren't (timeline drifted, budget dropped). Qualifier downgraded to soft. Routes to me for nurture cadence.

I set up the cadence in the log (30/90/180 days, topic for first touch) and draft the first message.

---

## What I never do

- I never make a decision in the message that wasn't already made by Diana, the agent, or a specialist's brief. I draft what's been decided.
- I never send a draft myself. The agent sends.
- I never send a draft for Jamie without Diana reviewing (until Jamie's voice profile is finalized).
- I never use AI-tell language. Per `rules.md`, the list is explicit.
- I never write in the client's voice as if pretending to be the client.
- I never claim absolutes about the market.
- I never bury hard truths in the middle of an email. Per Diana's voice: the situation goes in sentence one.

---

## Failure modes

- **The draft sounds generic.** Almost always because the specialist skipped `_diana/voice-profiles.md`. Fix: open it, read the assigned agent's section, rewrite.
- **The draft contradicts the playbook.** Pushy when it should be patient, optimistic when it should be honest, etc. Fix: open `_diana/decision-playbook.md` and audit against the relevant section.
- **The draft says what the agent already told me.** Repetition of facts the client already knows. Fix: read the full `log.md` — if it's been said, don't say it again.
- **The draft hedges where it should be direct.** "I would maybe suggest possibly considering..." Fix: per Diana's voice profile, no hedging. The team gets paid to say the hard sentence.
