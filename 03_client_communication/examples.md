# Examples — Client Communication

## Example 1: Recap email after a property tour (Marcus's voice)

**Inputs the specialist loaded:**
- Case `card.md`: Smith case, buyer, agent_owner Marcus.
- Log entry: research brief just landed, noise concern is real but scoped to front of house.
- `_diana/voice-profiles.md`: Marcus's voice — thorough, structured, footnotes his reasoning, lists.

**Draft produced:**

```
---DRAFT---
Subject: Springdale — comps + the noise question

James and Priya —

A few things from the research after yesterday's tour. I'll be specific so you can think on it before we talk tomorrow.

1. Pricing. Asking is $685K. Median for comparable 3/2s within 0.3 mi over the last 60 days is $672K. The closest direct comp — 2104 Springdale, four doors down — closed at $645K in late March. So this property is reasonable but not a bargain. Probably some room to negotiate, not a lot.

2. The noise. Priya, I want to be straight with you. TxDOT shows ~62 dB peak weekday afternoon at the front-of-house setback. That's about the volume of a normal conversation. At the back of the house, the modeled level drops to ~53 dB — meaningfully quieter. The primary bedroom is at the back corner per the floorplan, and the back yard is the strongest part of the property. The kitchen, where you'd actually be most of the time, is also at the back.

3. What I don't know yet. Whether the listing agent has any pending offers (I'll find out Monday). And the exact indoor sound levels — depends on the windows, which the listing calls "newer" without specifying rating.

The question I want to ask before tomorrow: Priya, on your Tuesday/Thursday WFH days, where would you actually be working? If it's the back of the house or the back yard, the noise question changes a lot. If it's the front, that's a real factor.

Call tomorrow at 5:30 to talk through it?

Marcus
---END DRAFT---
```

**Why this draft works for Marcus:**
- Numbered list (his signature move).
- Footnotes his reasoning ("$645K in late March," "the floorplan shows...").
- Tells them what he doesn't know.
- Closes with a single question to drive the reply.
- Reads like a long thoughtful email from a friend who happens to be a real estate expert.

**Log entry produced:**
```
2026-05-16 15:45 — 03_client_communication (MJ) — drafted Springdale tour recap in Marcus's voice. References research_2026-05-16.md. → next: Marcus to send today, then await reply or call tomorrow 5:30.
```

---

## Example 2: Competing offers (Sara's voice, seller side)

**Inputs:**
- Case: 1922 Garner, Henderson seller.
- Log entry: three offers received over the weekend. Sara reviewed with Diana. Recommendation is to accept the cleanest offer ($910K, no escalation, 21-day close), not the highest ($925K with a financing escalation clause).
- Voice profile: Sara — warm, direct, fragments, comfortable with "real quick."

**Draft produced:**

```
---DRAFT---
Subject: three offers in. my read.

Rob and Mary —

Real quick recap from this weekend.

Three offers. Highest is $925K but it's got a financing escalation that I don't trust — it's basically a soft offer with a number that looks better than it is. Middle one is $920K but with a 30-day close and a list of inspection demands already baked in. Third is $910K, cash-friendly mortgage, 21-day close, clean inspection contingency.

I'd take the $910K. Yes, it's $15K under the top number on paper. But the top number has two ways it can go sideways and this one has none. Cleaner closes 9 times out of 10.

I want to talk through this on the phone tonight before we commit. Free at 7pm?

Sara
---END DRAFT---
```

**Why this draft works for Sara:**
- Lowercase subject line (her thing).
- Opens with "real quick."
- Short paragraphs, some fragments.
- Tells them where she'd land.
- Wants to talk on the phone — per playbook, decisions like this aren't emailed.

**Log entry produced:**
```
2026-05-21 08:30 — 03_client_communication (SM) — drafted competing-offers email in Sara's voice. Recommendation embedded: $910K clean over $925K with risk. Per playbook, this is a phone call situation; email is the pre-call. → next: Sara to send, then call at 7pm.
```

---

## Example 3: Cold-feet call prep (Jamie owns, Diana reviewed)

**Inputs:**
- Case: 2026-05-09_boulder-creek_buyer. Under contract. HVAC inspection finding ($9K), buyer panicking.
- Log entry from orchestrator: Diana will call the buyer. Jamie needs the post-call recap drafted, plus call-prep notes for Diana.
- Voice: Jamie's profile not yet finalized; default to Diana's voice for the recap, flag for review.

**Draft produced (two parts):**

**Part A — Call-prep notes for Diana (NOT an email — these are notes she takes into the call):**

```markdown
# Call prep — Boulder Creek buyer, HVAC issue
Case: 2026-05-09_boulder-creek_buyer
For: Diana, calling buyer at 11:30 today

## What the buyer is feeling
- Panicked. Inspection findings landed last night.
- HVAC is $9K. They're framing this as "everything is wrong."
- Likely overestimating the size of the problem relative to the deal.

## What's true
- HVAC at $9K is real but routine. It's not on the "go to war" list (foundation, roof, panel, major plumbing, water).
- Option period ends in 2 days. Plenty of time to negotiate credit vs. repair.
- The rest of the inspection was clean (per Jamie's notes).

## Diana's framing (suggested, not scripted)
- This is a credit-vs-repair conversation, not a deal-breaker.
- Three real options: full repair credit ($9K), partial credit ($4-5K + we eat the rest), or seller does the work pre-close.
- If they still want out, the option period covers them — but the question to ask is, "would you be looking at the same kind of house in a month? Or a different price point?"

## What to surface
- Per playbook: emotional decisions made in panic are usually wrong decisions.
- Per playbook: this is the kind of moment we get paid for.
- The buyer's *original* reasons for wanting this house are still true. The HVAC doesn't change those.

## After the call
- If buyer wants to proceed: route to 04_transaction_coordinator to draft the credit-vs-repair counter.
- If buyer wants out: route to me (Jamie) for the option-termination paperwork and the closing-loop message.
- Either way, recap email follows.
```

**Part B — Recap email draft for Jamie to send AFTER Diana's call:**

```
---DRAFT (for Jamie, flagged for Diana review)---
Subject: where we landed on the HVAC

[Client name] —

Quick recap of the conversation with Diana this morning, so you both have it in writing.

The HVAC finding is real but it's a normal inspection item, not a deal-breaker. You have three paths:

1. Ask the seller for a full $9K credit at close.
2. Ask for partial credit and absorb the rest.
3. Ask the seller to do the work themselves pre-close.

Diana's recommendation is the credit path, not the repair path — gives you control over the contractor and the timing. We'd ask for $7,500 as the opening number (per the inspector's estimate plus a small buffer), expecting to land around $5K–$6K.

The option period ends [date]. We have time. Next step: confirm by tomorrow afternoon which path you want, and I'll draft the counter to the listing agent.

Jamie
---END DRAFT---
```

**Log entry produced:**
```
2026-05-10 10:00 — 03_client_communication (JL, Diana reviewed) — drafted (a) call-prep notes for Diana's 11:30 call, (b) post-call recap for Jamie to send after. Recap reflects Diana's three-options framing. → next: Diana to call. Then route per call outcome (TC if proceeding, qualifier-style closing-loop if terminating).
```

**What this example demonstrates:**
- The specialist produced TWO outputs because the situation called for it (notes + email).
- The call-prep notes are not client-facing — they're for Diana's use.
- The recap email follows the call, doesn't replace it (per playbook).
- Jamie's draft was reviewed by Diana before send (per the team norms).
