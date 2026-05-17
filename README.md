# Diana's Team Operating System

> A five-specialist AI workspace for a 4-person boutique real-estate team in Austin.
> Built so a new hire is operational in a day, not a quarter.

**🌐 Live walkthrough: [Visit the landing page](https://l-conder.github.io/dyana-realty/)** — visual architecture, hour-by-hour onboarding plan, and the design decisions, designed for someone who has never opened the repo.

---

## What this is

This is a **folder system**, not software. Each top-level folder is one specialist on Diana's team — orchestrator, lead qualifier, property researcher, client communications, transaction coordinator. Every active lead or deal lives as its own folder under `_cases/` with two files: `card.md` (facts) and `log.md` (timeline). Specialists read the case folder, do their work, and update the case folder. The **case folder is the handoff** — nothing gets passed between specialists in memory. If you can find the file, you can pick up the work. That is the entire system.

---

## The architecture in one picture

```
┌─────────────────────────────────────────────────────────────────┐
│                       INCOMING REQUEST                          │
│              (email, text, Slack, walk-in, referral)            │
└─────────────────────────────┬───────────────────────────────────┘
                              │
                              ▼
                ┌─────────────────────────┐
                │   00_orchestrator       │
                │   "Is there a case?"    │
                │   "Who handles this?"   │
                └────────┬────────────────┘
                         │  reads/creates a case folder
                         │  under _cases/active/
                         ▼
        ┌────────────────────────────────────────────┐
        │                                            │
        ▼                                            ▼
┌──────────────────┐                       ┌──────────────────────┐
│ 01_lead_qualifier│                       │ 04_transaction_coord │
│  new prospects   │                       │  live deals          │
└────────┬─────────┘                       └────────▲─────────────┘
         │                                          │
         ▼                                          │
┌──────────────────┐    ┌────────────────────┐     │
│ 02_property_     │───▶│ 03_client_         │─────┘
│   research       │    │   communication    │
└──────────────────┘    └────────────────────┘
         ▲                       │
         └───────────────────────┘
            (bounce-back: new criteria)

         All five read & write the same case file.
         The case folder is the handoff.
```

**Forward flow:** new lead → qualified → researched → communicated → under contract → closed.
**Bounce-back is a first-class operation.** Transaction coord finds an inspection issue → it hands the case back to client comms. Client wants different homes → comms hands back to research. Cases can move in any direction. The case folder always tells you where you are.

---

## How a request actually flows (worked example)

> Tuesday 9:14 AM. Sara gets an email: "Hi, found you through my coworker. We're thinking about selling our place in Travis Heights this summer. When could we chat?"

1. **Sara opens this repo, goes to `00_orchestrator/`.** Reads `rules.md`. It tells her: new contact, no existing case → create case folder, route to `01_lead_qualifier`.
2. **Sara creates `_cases/active/2026-05-19_travis-heights_seller/`** by copying `_cases/_template/`. Fills in `card.md` with what she knows (name, source, neighborhood, type=seller).
3. **Sara loads `01_lead_qualifier/`** into Claude (or reads it herself) and uses it to draft a qualifier call/email. The qualifier appends a log entry: "2026-05-19 09:20 — qualifier draft sent (Sara). Awaiting reply with timeline + price expectation."
4. **Thursday: client replies.** Sara updates `card.md` with budget, timeline, motivation. Status flips to `qualified`. Log entry added.
5. **Sara hands off to `02_property_research/`** by writing one line in the log: "→ research: pull Travis Heights CMA + recent comps 78704." Research specialist drops a brief into the case folder as `research_2026-05-21.md`.
6. **Sara hands off to `03_client_communication/`** to draft the listing presentation cover email — in Sara's voice (see `_diana/voice-profiles.md`).
7. **Listing signed.** Sara moves the case to `04_transaction_coordinator/`'s lane by flipping `status: under_contract` in `card.md`. Coordinator now owns the deadlines.

**Notice what didn't happen:** nobody passed a JSON envelope. Nobody wrote a "briefing." The work moved because the case file moved.

---

## Your first day on this system (literal hour-by-hour)

If you've just been hired and someone handed you this repo, do this in order. You should be productive by lunch.

**Hour 1 — Meet Diana (30 min reading, 30 min talking)**
- Read `_diana/about-diana.md`. This is the team philosophy.
- Read `_diana/voice-profiles.md`. Find your own profile. If you're new, ask Diana to draft one with you this week.
- Read `_diana/decision-playbook.md`. This is Diana's brain on paper. When in doubt, this is what she'd say.

**Hour 2 — Walk one real case end-to-end**
- Open `_cases/closed/2026-04-02_johnson_seller/`. Read `card.md` then `log.md`.
- That's a complete deal. Notice how every specialist left footprints.

**Hour 3 — Meet the five specialists**
- Open each numbered folder and read just the `identity.md` (each is < 150 words).
- You don't need to memorize the rules. You'll learn by use.

**Hour 4 — Do your first task with the system**
- Pick any open case from `_cases/active/`. Read it. Decide which specialist would handle the next step. Open that specialist's folder. Use it.
- Update the case log when you're done. One line. Date, your initials, what you did, what's next.

**By end of day 1 you should be able to:**
- Open a new case file from the template.
- Decide which specialist handles a given request.
- Update a case log so the next person knows what happened.
- Ask Diana for a voice profile of your own.

---

## Setup (one-time, ~10 minutes)

1. **Clone or fork this repo.** Keep it in a place every agent can edit (private GitHub repo, or a synced Drive folder if your team is not Git-comfortable).
2. **Personalize `_diana/`.** Replace the example agent names with your real team. Have Diana spend 30 minutes filling in `decision-playbook.md` with her actual rules — this is where the system gets its quality ceiling.
3. **Drop the repo into a Claude Project.** Project knowledge = the whole repo. Custom instructions = "Read README.md first. When the user asks for work, open `00_orchestrator/` and follow its rules. Never invent a case file — always check `_cases/active/` first."
4. **Optionally** publish this README as a GitHub Pages site (the `docs/` folder is ready for that). Diana's team can read it on their phones at 11pm without cloning anything.
5. **Run the first week as a pilot.** One agent uses the system for every new lead. Compare with the agents not using it. Adjust.

---

## What each folder is

| Folder | What lives there | Read it when |
|---|---|---|
| `_diana/` | Diana's philosophy, team voice profiles, decision playbook | Always loaded — sets the quality bar for every specialist |
| `_cases/` | One folder per lead/deal. `card.md` + `log.md`. | Always — this is the working memory of the team |
| `00_orchestrator/` | The dispatcher. Routes requests, opens case files. | First, on every new request |
| `01_lead_qualifier/` | First contact specialist. Captures intent + 5 fields. | New prospects |
| `02_property_research/` | Deep research on properties, neighborhoods, CMAs | Before a tour, before a listing meeting, before an offer |
| `03_client_communication/` | Drafts in each agent's voice | Any client-facing message |
| `04_transaction_coordinator/` | Deadlines, docs, contingencies, risk flags | Once a deal is live |

---

## The four files every specialist folder has

- `identity.md` — Who this specialist is. What they own. What they don't.
- `rules.md` — How they operate. Always-do. Never-do.
- `examples.md` — 2–3 worked examples showing the specialist in action.
- `handoff.md` — **The whole game.** What this folder needs to receive, what it produces, where work flows next, and how work bounces back.

---

## Design decisions, called out

These are the choices that make this system different from a generic template.

1. **The case folder is the handoff.** No JSON envelopes. No typed schemas. No briefings flying between specialists in memory. Persistent state on disk that any human or any Claude session can pick up. This is the answer to Diana's "everything lives in my head" problem.
2. **`_diana/` is loaded by every specialist on every run.** Voice profiles + decision playbook = the system sounds like Diana's team, not a generic AI. Quality ceiling = whatever Diana is willing to write down.
3. **Bounce-back is first-class.** Real deals don't flow linearly. Every `handoff.md` documents the return path, not just the forward one. Transaction coord → client comms → research → back to comms is a normal operation.
4. **The orchestrator's first question is always "does a case file exist?"** This single rule is what keeps the system coherent. Without it you get four agents acting on stale context.
5. **Voice profiles exist for every human agent, not just the principal.** Jamie (6 months in) gets her own profile. She's allowed to sound like herself. Diana sets the floor, not the ceiling.

---

## What I would add with another week

- **Weekly digest specialist.** A sixth folder that reads all active case logs every Friday and produces Diana's Monday-morning brief.
- **Real Gmail integration** so `03_client_communication/` actually pulls thread context instead of being given it.
- **A learning loop:** when Diana corrects a specialist's output, that correction goes into `_diana/decision-playbook.md` as a new rule. The system gets smarter each month.
- **Case state validator.** A tiny pre-commit hook that checks every `card.md` has the required fields before letting it move statuses.

---

## License & use

Built for Diana. Take it, fork it, change it, sell better houses.
