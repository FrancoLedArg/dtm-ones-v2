# Context Map

## Contexts

- [Landing](./apps/landing/CONTEXT.md) — public roster tool for DTM ONES: find/inspect Players and Coaches (Showcase), agency story, contact requests
- **Dashboard** *(planned, `@dtm-ones/dashboard`)* — internal agency tool for day-to-day representation work. No `apps/dashboard` or `CONTEXT.md` until that app is scaffolded.

## Relationships

- **Landing** is the only active context. **Dashboard** will be mapped here when it exists.
- **Dashboard → Landing (planned):** Dashboard/CMS owns Player content and **Category** labels; Landing reads them for Showcase find/filter. No shared code yet.
