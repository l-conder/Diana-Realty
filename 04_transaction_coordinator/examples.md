# Examples — Transaction Coordinator

Three scenarios. Each one shows the case folder state, the TC's read, and the artifact the TC produces.

---

## Example 1: First day on a new under-contract deal

**Case:** `_cases/active/2026-04-22_henderson_seller`. Status just flipped to `under_contract` by Sara at 4:47pm yesterday.

**Trigger:** Orchestrator routes the case to TC at 8:30am Monday morning with the message: "Henderson went under contract Friday. Sara's on the listing. Your case."

**What the TC reads first:**

1. The full contract (Sara linked it in `log.md`)
2. The latest `card.md` — to see what's already populated and what's missing
3. `_diana/decision-playbook.md` § Under-contract section — the daily checklist, the day-by-day windows
4. Last week's `log.md` entries — to understand any context (was there a bidding war? a difficult buyer agent? anything unusual?)

**What the TC produces — three things, in order:**

### 1. Updated `card.md` deal-stage section

```markdown
## Deal stage

- **status:** `under_contract`
- **contract_date:** 2026-04-19
- **option_period_end:** 2026-04-29 (10 days)
- **financing_contingency_end:** 2026-05-12 (21 days)
- **appraisal_due_by:** 2026-05-10
- **close_date:** 2026-05-22 (33 days from contract)
- **buyer_agent:** Tom Reyes, Compass — (512) 555-0118 — tom@example.com
- **buyer_lender:** Sarah Choi, Guaranteed Rate — (512) 555-0173 — schoi@example.com
- **title:** Independence Title, Westlake office — file opened, escrow# pending
- **inspector:** scheduled 2026-04-24, 9am — ATX Home Inspections, Mike Bauer
- **other_side_contacts_confirmed:** 2026-04-22 by MJ
```

### 2. Log entry — day-1 sweep

```markdown
### 2026-04-22 08:55 — TC day-1 sweep

Took ownership of case for under-contract phase.

**Confirmed:**
- All deadlines extracted from contract and entered on card.
- Buyer agent, lender, and title contacts confirmed (called all three this morning).
- Inspection on day 5 of option — buffer is healthy.

**Flags:**
- ⚠️ Seller disclosures still in Sara's drafts folder, not signed by sellers. Need to be in buyer's hands by 2026-04-25 (day 6) per contract. Action: brief to Sara below.
- ⚠️ HOA docs not yet requested. Henderson is in Circle C — they're slow. Need to request today.

**Next checkpoints:**
- 2026-04-23: Confirm HOA doc request submitted, title file opened.
- 2026-04-24: Confirm inspection complete + brief inspector findings to Sara.
- 2026-04-25: Disclosures delivered to buyer agent.
- 2026-04-26: Lender check-in #1 (confirm file active, no surprises).
```

### 3. Brief to Sara via orchestrator → comms

```markdown
**Brief for Sara:**

Two action items before EOD today:

1. **Disclosures:** Hendersons need to sign and return the seller disclosures. They're sitting in your drafts. Suggest texting them now — short, friendly, "we need these by tomorrow morning to stay ahead of the buyer-side deadline."

2. **HOA docs:** Need to be requested today. Circle C HOA takes 5–7 business days. If we order tomorrow we're cutting it close. Recommend ordering today, $375 fee (per current Circle C rate), paid by seller per contract.

I'll handle title and lender check-ins. You handle the Hendersons.
```

**Note what the TC didn't do:** didn't text Sara directly, didn't draft the message to the Hendersons, didn't call the HOA. The TC produced the work-product. The agent acts.

---

## Example 2: Lender goes silent (the routine catch)

**Case:** `_cases/active/2026-05-02_alvarez_buyer`. Day 11 of under-contract. Financing contingency in 10 days.

**Trigger:** TC's daily 7am sweep across all active cases finds: lender hasn't replied to anyone since Friday afternoon. It's Wednesday morning. That's 4 business days of silence.

**What the TC does:**

### Log entry — flag

```markdown
### 2026-05-13 07:14 — Flag: lender silence on Alvarez

**Status:** ⚠️ flag — financing in 10 days, lender (Brian Holt, Movement Mortgage) has not responded to any contact since Friday 2026-05-08, 4:12pm.

**What we know:**
- Loan submitted 2026-05-04
- Last contact: Brian confirmed receipt of docs, said "appraisal ordered, should hear by mid-next week"
- No reply to my Tuesday email
- No reply to Marcus's Monday voicemail

**What I'm asking for:**
- Marcus calls Brian's direct line at 9am today. Not email.
- If Brian doesn't pick up, Marcus calls Movement's branch manager. Number on card.
- If we don't get a substantive answer by EOD, we escalate to Diana for a position call: do we ask the buyer to start a parallel application with Texas Capital? That's a 3-day setup. Earlier is better.

**Briefs queued:**
- Comms: short message to client warning that financing is taking longer than expected, no panic language, holding-pattern tone.
- Comms (held): outreach to Texas Capital backup loan officer if Diana approves parallel app.
```

### Brief to comms (queued, not sent yet)

```markdown
**Brief for client message (Marcus's voice, to Hugo & Sofia Alvarez):**

**Audience tone:** holding pattern, transparent but not alarming. They're first-time buyers, sensitive to "something's wrong" framing.

**Must say:**
- Loan is progressing but our lender has been slow to respond this week.
- We're checking in with them today.
- We're also preparing a backup plan as a precaution — this is standard process, not a sign of trouble.
- If they hear from anyone other than Marcus or the TC about their loan, please tell them first.

**Must not say:**
- Anything specific about what could go wrong.
- "Don't worry" (always reads as a reason to worry).
- A timeline we can't keep.

Wait for Diana's call before sending if the parallel-app path becomes real.
```

**Note what makes this an example worth following:** the flag has a recommended next action *and* a contingency plan already drafted. The TC doesn't deliver problems. The TC delivers problems plus suggested moves. Diana decides; the team executes.

---

## Example 3: The weekly status block

Every Friday at 4pm, the TC produces a one-screen status block per active case, dropped into the case's `log.md`. Diana reads them with coffee Saturday morning. It's how she stays in the loop without being in the loop.

### Sample weekly status block

```markdown
### 2026-05-15 16:00 — Weekly status (Friday digest)

**Case:** 2026-04-22_henderson_seller
**Phase:** Under contract, day 26 of 33. Close date: 2026-05-22.

**On track:**
- ✅ Option period closed clean — buyer asked for $1,800 in repair credits, we settled at $1,200. Per playbook.
- ✅ Appraisal came back at $665K, $5K over contract. No issue.
- ✅ Buyer financing — clear to close issued 2026-05-14.
- ✅ Title commitment received, no exceptions of concern.
- ✅ HOA docs delivered.

**Open:**
- ⏳ Walkthrough scheduled 2026-05-21, 5pm.
- ⏳ Wire instructions to buyer side: I will send via DocuSign, separately from email, on 2026-05-20. Buyer agent has confirmed they will phone-verify before client wires.

**No flags. On track to close 2026-05-22.**

— MJ
```

**Why this artifact matters:** Diana spent 8 years building a team where she didn't have to be in every conversation. The weekly status block is what makes that real. She reads 6–8 of these Saturday morning over coffee and knows everything that matters.
