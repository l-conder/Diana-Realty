# `_cases/` — The Team's Working Memory

Every active lead or deal lives here as its own folder. Each folder has exactly two files:

- **`card.md`** — the facts. Updated when facts change. Read by every specialist before they do anything.
- **`log.md`** — the timeline. Appended to every time something happens. Never rewritten.

## Why this exists

Diana said: *"Everything lives in my head and three different Google Docs."*

This folder is the answer. The case folder is the team's single source of truth for any given lead or deal. If you can't find an answer here, the answer doesn't exist yet — and the first job is to write it down.

## Folder naming convention

```
YYYY-MM-DD_short-descriptor_type
```

Examples:
- `2026-05-15_smith_buyer`
- `2026-05-19_travis-heights_seller`
- `2026-04-02_johnson_seller`

Date is the **case open date** (first contact or first request). It doesn't change.

## Folder lifecycle

- **`_cases/active/`** — work in progress. Every status from `new` through `under_contract`.
- **`_cases/closed/`** — closed deals and dead leads. Move here when `status: closed_won`, `closed_lost`, or `dead_lead`.

Closed cases are still readable. They're how new hires learn the system, and how Diana spots patterns at the end of each quarter.

## Starting a new case

1. Copy `_template/` to `active/YYYY-MM-DD_descriptor_type/`.
2. Fill in what you know in `card.md`. Leave the rest blank. **Don't invent fields.**
3. Add the first log entry. One line. Date, your initials, what happened, what's next.
4. The case is now live. Any specialist can pick it up.

## The two-file rule

Never add other files to a case folder unless a specialist explicitly produces one (e.g., `research_2026-05-21.md` from `02_property_research/`). The card and the log are the heartbeat. Everything else is supplementary and named with a date.
