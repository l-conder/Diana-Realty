# Examples — Lead Qualifier

## Example 1: Warm referral, qualified on first reply

**Incoming (forwarded to Sara):**
> "Hi! Kavi Patel told us to reach out. We're a married couple living in Mueller, expecting our second kid in October, and we're starting to think about a bigger place. Probably East Austin or Mueller. Budget around $700K. Would love to chat."

**Qualifier output (drafted for Sara to send):**

> Hi James — great to hear from you, and Kavi's a favorite of ours so the bar is high. Congrats on the second one on the way.
>
> Real quick before we set up time: East Austin and Mueller have moved in pretty different directions over the last six months. Mueller is tight (5–7 days on market for anything under $850K), East Austin has more selection but more variance by block. So our first call would be more useful if I know two things ahead of time:
>
> 1. When are you hoping to be moved in? (helps me know if we're searching now or planning for Q4)
> 2. Any deal-breakers you already know about? (commute, schools, yard, etc.)
>
> 20 minutes Thursday at 4pm? Or earlier if it's helpful.

**What the qualifier captured from this exchange:**
- Source: referral from Kavi
- Side: buyer
- Budget: $700K (stated)
- Location: East Austin or Mueller
- Motivation: growing family (second kid October)
- Intent: real, not browsing

**What's still missing:**
- Exact budget range (high end)
- Timeline (asked)
- Constraints (asked)
- Pre-approval status

**Status set to:** `qualifying` (not yet `qualified` until Thursday's call closes the six). Card updated. Log:
```
2026-05-19 10:45 — 01_lead_qualifier (SM) — referral from Kavi, growing family, budget ~$700K East Austin/Mueller. Reply drafted in Sara's voice, sent. Call Thursday 4pm to close remaining six. → next: re-route after call.
```

---

## Example 2: Cold Zillow inquiry, soft lead

**Incoming (Zillow lead form, routed to whoever's on call — Jamie today):**
> "Interested in 1247 Maple Run, Austin TX. Please call me." (Phone provided.)

**Qualifier action:**
- No source signal, no budget, no timeline, no motivation. This is the thinnest possible lead.
- Property is at $549K, listed by another agent. We're not the listing agent.
- Diana's playbook: cold inquiries get a 24-hour reply window, treated as qualifying.

**Drafted for Jamie to send (text, since they didn't say email):**

> Hi! It's Jamie with the Diana Cooper team. Saw your inquiry on 1247 Maple Run — happy to set up a showing if you'd like to see it.
>
> Quick thing: that one's been on market 19 days at $549K, which usually means there's a story (price drop incoming or something the photos don't show). Want me to pull the listing history and call you with what I find before we book a tour? Free anytime this afternoon.

**What this draft does right:**
- Names a specific data point (19 days, story-shaped). Earns trust without selling.
- Doesn't ask six questions. Asks one decision.
- Sets up a call (where the qualifier work actually happens).

**Status set to:** `qualifying`. Card minimal. Log:
```
2026-05-19 11:30 — 01_lead_qualifier (JL) — cold Zillow lead, 1247 Maple Run. Reply sent in Jamie's voice (Diana reviewed). Awaiting reply or call. If no response in 48hr, send one more, then dead_lead. → next: standby.
```

---

## Example 3: Qualifying out a poor fit

**Incoming (phone call from referral, Marcus took it):**
> Caller wants help finding "the cheapest house in West Lake Hills under $400K." West Lake Hills median is over $2M. Caller is unwilling to consider any other neighborhood. Was previously working with another agent who "didn't get back to me fast enough."

**Qualifier action:**
- Budget vs. location is impossible (off by an order of magnitude in a hot zip).
- Prior agent friction suggests this won't be a happy client even if we found a unicorn.
- Per `decision-playbook.md`: we don't take listings (or buyer engagements) we can't honestly serve. Better to refer.

**Drafted for Marcus (call follow-up email, since the conversation already happened):**

> Hey Tomás —
>
> Thanks for the call earlier. I want to be straight with you about West Lake Hills under $400K — that's not a market that exists. The lowest closing in West Lake last year was $980K, and the median is closer to $2.1M.
>
> If West Lake is the priority, the realistic options are at $900K+ — and I'd be happy to talk you through that if your budget can stretch. If $400K is the priority, the closest neighborhoods with the same feel are Lost Creek (Eanes ISD, similar vibe) or parts of Davenport Ranch. Those have homes in the $500K–$700K range. Still not $400K, but closer.
>
> If neither works, I can refer you to a colleague who specializes in tighter-budget searches across central Austin. No hard feelings — I'd rather point you somewhere useful than waste your time.
>
> Let me know which direction.

**What this draft does:**
- Tells the truth.
- Offers three real options including a referral.
- Doesn't pretend this is a deal we can do.

**Status set to:** `dead_lead` (pending response). Log:
```
2026-05-19 14:00 — 01_lead_qualifier (MJ) — West Lake at $400K is impossible. Honest reply drafted offering three paths including referral. Per playbook: we don't take engagements we can't serve. → next: 30-day follow-up if no reply; otherwise close.
```
