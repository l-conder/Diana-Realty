# Examples — Property Research

## Example 1: Single-property deep dive (the Smith / Springdale case)

**Request from orchestrator:**
> Marcus is touring 2308 Springdale Rd with James and Priya Smith. Priya is worried about road noise. Pull 30-day comps and noise data for this property specifically.

**Brief produced (`research_2026-05-16.md` in the case folder):**

```markdown
# Research Brief — 2308 Springdale Rd, Austin TX
case_id: 2026-05-15_smith_buyer
prepared: 2026-05-16
prepared_by: 02_property_research
specific_request: 30-day comps for 2308 Springdale + noise assessment for Priya's concern

## Bottom line
Property is priced reasonably given recent comps ($685K asking vs. $672K median for comparable 3/2s within 0.3 mi over last 60 days). The noise concern is real and measurable — Springdale Rd carries ~62 dB peak afternoon traffic per TxDOT 2024 data. Whether that's a deal-breaker depends on Priya's work-from-home situation; the back of the house is meaningfully quieter than the front.

## The data

**Comps (closed, within 0.3 mi, last 60 days, 3/2 or 3/2.5):**

| Address | Beds/Baths | Sqft | Closed | Price | $/sqft | Notes |
|---|---|---|---|---|---|---|
| 2412 Tillery St | 3/2 | 1,520 | 2026-04-22 | $649K | $427 | Renovated kitchen, similar lot |
| 1907 Cedar Ave | 3/2.5 | 1,640 | 2026-04-08 | $672K | $410 | New construction infill |
| 2104 Springdale Rd | 3/2 | 1,480 | 2026-03-30 | $645K | $436 | Same street, 4 doors down — same noise profile |
| 2515 E 14th St | 3/2 | 1,580 | 2026-04-15 | $698K | $442 | One block off Springdale, quieter |

Subject (2308 Springdale): 3/2, 1,580 sqft, listed $685K, $434/sqft. Mid-pack.

**Noise data:**
- TxDOT 2024 traffic count, Springdale @ 7th: 14,200 ADT (avg daily traffic).
- Modeled noise levels at front-of-house setback (~30 ft from curb): 62 dB peak weekday afternoon, 51 dB overnight.
- Back-of-house setback (~80 ft from curb): 53 dB peak, 44 dB overnight.
- For reference: normal conversation is ~60 dB. A dishwasher across the room is ~55 dB.

## What this tells us
- Pricing is fair. Not a deal at $685K, not overpriced either.
- The closest direct comp (2104 Springdale, 4 doors down) closed at $645K. That's the strongest single data point. Suggests there's some room to negotiate, though probably not a lot.
- Days on market for the subject: 14. In this submarket that's neither hot nor cold.
- The noise concern is real but **scoped to the front of the house**. The back yard, the primary bedroom (back-corner per floorplan), and the kitchen are meaningfully quieter.

## What I don't know
- Whether the listing agent has any pending offers (would need a call).
- The exact sound levels inside the house (depends heavily on windows — the listing notes "newer windows" but doesn't specify rating).
- Whether Springdale is on the 2027 mobility plan for any changes (Austin Mobility portal not yet showing 2027 projects).

## Suggested questions for James and Priya
1. Where does Priya work on her Tuesday/Thursday WFH days — front of house, back of house, or flexible? The answer changes the noise question entirely.
2. How important is the front yard vs. the back yard? The back yard here is the strength of the property.
```

**Log entry produced:**
```
2026-05-16 14:30 — 02_property_research (MJ) — Springdale priced fair vs comps ($685K ask vs $672K median). Noise real at front but scoped — back of house meaningfully quieter. Brief saved as research_2026-05-16.md. → next: 03_client_communication, draft recap for James and Priya in Marcus's voice. Surface noise honestly, lead with the back-of-house framing.
```

---

## Example 2: Seller-side CMA

**Request from orchestrator:**
> Sara has a listing meeting Tuesday with the Hendersons for 1922 Garner Ave (Bouldin Creek). Pull a full CMA.

**Brief produced (`research_2026-05-20.md`):**

```markdown
# Research Brief — 1922 Garner Ave, Austin TX (CMA)
case_id: 2026-05-18_henderson_seller
prepared: 2026-05-20
prepared_by: 02_property_research
specific_request: Full CMA ahead of Tuesday listing presentation

## Bottom line
Recommended list range: **$885K – $925K**. The market is showing strength in Bouldin Creek but the subject has two factors arguing for the conservative end of that range: a partially unpermitted addition (per City of Austin records) and a lot that backs to the alley (vs. interior-block comps that closed higher). A $895K list is defensible, drives multiples, and gives room for a price reset in week 3 if needed.

## The data
[12 comps table — omitted here for brevity, would be fully populated]

Median $/sqft for Bouldin Creek closes (last 90 days, 3/2 single-story): $548/sqft.
Subject (1,712 sqft) at median = $939K. Adjusted for unpermitted addition (-$25K, conservative) and alley-backing (-$15K): $899K.

## What this tells us
- Bouldin is currently a 9-day-median-DOM market. A correctly priced listing here will have multiples.
- The unpermitted addition is the biggest risk. Buyers (and their inspectors) will find it. Better to address upfront than during option period.
- The alley-backing isn't a deal-killer but it's a noticeable factor — most buyers will discount mentally for it.

## What I don't know
- Whether the Hendersons want to address the unpermitted addition before listing (permitting retroactively can be done but takes 4–8 weeks).
- Recent updates inside the house — I haven't seen photos beyond the prior 2018 listing photos.
- Whether the comps reflect any rate-driven softness (rates moved in March; some of the older 90-day comps may be from a stronger period).

## Suggested questions for the Hendersons
1. Are they open to a 6–8 week pre-list timeline if it means resolving the addition permit cleanly? It could be worth $25–40K in offer strength.
2. What's their walk-away number? (Per Diana's playbook: if their expectation is >7% above our number, walk politely.)
```

**Log entry produced:**
```
2026-05-20 11:00 — 02_property_research (JL) — CMA done. Range $885K–$925K, recommend $895K list. Unpermitted addition is biggest risk; flagged in brief. → next: 03_client_communication, draft listing-presentation cover in Sara's voice. Include the permit conversation up front (per playbook: honest > hopeful).
```

---

## Example 3: Killing a deal early

**Request from orchestrator:**
> Jamie's buyer is excited about 4118 Bluebonnet Ridge. Pull a deep dive. They're planning to offer this weekend.

**Brief produced (`research_2026-05-21.md`):**

```markdown
# Research Brief — 4118 Bluebonnet Ridge, Austin TX
case_id: 2026-05-20_chen_buyer
prepared: 2026-05-21
prepared_by: 02_property_research
specific_request: Deep dive ahead of offer this weekend

## Bottom line
**Stop and call the client before any offer goes out.** This property is in FEMA flood zone AE (1% annual chance), which means mandatory flood insurance for any financed purchase, currently quoting $3,200–$5,800/year in this area. The seller's disclosure does not mention flooding, but Travis County records show two flood claims at this address (2015, 2018). Three of the four most-recent listings on this street had price reductions after the flood zone surfaced in inspection. This isn't necessarily a no — but the client needs to know before writing.

## The data
- FEMA flood map (current effective): Zone AE.
- Flood insurance quote (NFIP estimate for this zone, 1,600 sqft SFH, replacement cost ~$280K): $3,400/year.
- Public flood claim history (Travis County): 2015 ($14K paid), 2018 ($31K paid). Source: county clerk records, accessed 2026-05-21.
- Three of the four comparable Bluebonnet Ridge listings since 2024 had price reductions of $20K–$45K after flood disclosure surfaced in option period.

## What this tells us
- The seller's silence in disclosure is not necessarily intentional but it's a serious gap. This needs to be raised before the offer, not after.
- The property may still be the right one for the client at a *different price* — comps that flooded historically still close, they just close ~5–8% below dry equivalents.

## What I don't know
- Whether the seller has done any mitigation work (elevation, drainage). Would need to see permits or ask.
- The current insurer's willingness to renew vs. drop after two claims.

## Suggested questions for the client (urgent — before offer)
1. Were they aware of the flood zone? (Probably not — most buyers learn during option period.)
2. Does the flood risk change their interest, or just their price?
```

**Log entry produced:**
```
2026-05-21 09:30 — 02_property_research (MJ) — Flood zone AE with two prior claims, NOT in seller disclosure. Recommend STOPPING the offer until Jamie has the conversation with the buyer. → next: Diana flagged. 03_client_communication to draft Jamie's call-prep notes (NOT an email — this is a phone-call situation per playbook).
```

**What this example demonstrates:** the research specialist's job is sometimes to slow the team down. The deal might still happen — but it shouldn't happen blind.
