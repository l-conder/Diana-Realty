# Examples — Orchestrator

## Example 1: New referral via email

**Incoming request:**
> Email to Sara from Kavi Patel (closed buyer 2024): "Hey Sara — my coworker Aisha and her husband are thinking about selling their place in Travis Heights and moving out to Dripping. Mind if I send them your way?"

**Orchestrator action:**
1. Search `_cases/active/` — no match for "Aisha" or the Travis Heights address (not provided yet).
2. **Open new case:** copy template to `_cases/active/2026-05-19_patel-referral_seller/` (use referral source until names confirmed).
3. Fill in card: `source: referral from Kavi Patel (2024 buyer)`, `side: seller`, `location: Travis Heights → Dripping`. Leave everything else blank.
4. Set `agent_owner: Sara` (Travis Heights specialist).
5. **Log entry:**
   ```
   2026-05-19 10:30 — 00_orchestrator (SM) — referral from Kavi Patel for Aisha + husband, Travis Heights seller. Sara owns. → next: 03_client_communication to draft Sara's reply to Kavi (warm, fast). Then 01_lead_qualifier once we have direct contact.
   ```
6. Route to `03_client_communication` first (need to reply to Kavi same-day, per playbook). Then `01_lead_qualifier` once we have direct contact.

**Why two specialists in sequence:** speed matters more than completeness. Kavi gets a reply today. The qualifier runs as soon as Aisha is in direct contact.

---

## Example 2: Mid-deal panic from Jamie at 11pm

**Incoming request (Slack to Diana, but routed here):**
> "Diana — the Boulder Creek inspection came back and there's a $9K HVAC item. Buyer is freaking out and asking if they can back out. What do I say??"

**Orchestrator action:**
1. Search `_cases/active/` — find `2026-05-09_boulder-creek_buyer`. Read `card.md` and `log.md`.
2. Confirm status is `under_contract`, agent owner is Jamie, option period ends in 2 days.
3. **This is a `decision-playbook.md` flag.** Cross-reference: HVAC is not on the "go to war" list (foundation, roof, electrical panel, major plumbing, water damage). It's a "conversation about credit vs. repair" item.
4. **This is also an escalation trigger** because Jamie is 6 months in and the buyer is emotional.
5. **Log entry:**
   ```
   2026-05-09 23:14 — 00_orchestrator (JL) — HVAC issue, $9K, buyer panicking. Per playbook: not a war item, is a credit/repair conversation. Per playbook: emotional buyer = phone call, not email. Routing to 03_client_communication for the recap email AFTER Diana calls the buyer. Diana flagged.
   ```
6. Route in this order:
   - **First:** ping Diana now (this is the 11pm-Slack-to-Diana case the system was built for).
   - **Second:** `03_client_communication` to draft the *recap* email Jamie sends after Diana's call. Voice: Jamie's, but reviewed by Diana before send.
   - **Third:** `04_transaction_coordinator` to draft the credit-vs-repair counter for the listing agent.

**Why this works:** the system didn't pretend to handle a judgment call that belongs to Diana. It just made sure Diana got the right context, in the right order, with a documented trail.

---

## Example 3: Active case, agent asks a quick question

**Incoming request (Marcus to the system):**
> "Pull the Springdale comps again — Priya wants to see how the prices have moved in the last 30 days."

**Orchestrator action:**
1. Search `_cases/active/` — find `2026-05-15_smith_buyer`. Read `card.md` and `log.md`.
2. Status is `researching`. Last research brief was 2026-05-16. Marcus is asking for a refresh, not a new analysis.
3. **Log entry:**
   ```
   2026-05-19 16:00 — 00_orchestrator (MJ) — Marcus requested 30-day comp refresh for 2308 Springdale. → next: 02_property_research, refresh research_2026-05-16.md or write research_2026-05-19.md.
   ```
4. Route to `02_property_research` with the case_id and the specific request (30-day, single property).

**What the orchestrator did NOT do:** it didn't try to do the research itself, didn't draft the reply to Priya, didn't change the status. One job, done cleanly, with a clean handoff log entry.

---

## What these three examples share

- The orchestrator did not produce client-facing content.
- The orchestrator wrote exactly one log entry per request.
- The orchestrator made the next step obvious to the next specialist.
- The orchestrator deferred to Diana when the request required judgment beyond the playbook.

If the orchestrator ever feels like it's drafting an email or making a pricing call, it's stepped outside its lane.
