# Design brief — Landing (roster tool)

Source of design rules: **design-taste-frontend** (tasteskill v2 experimental) only, applied *after* this product brief. Domain language: [CONTEXT.md](./CONTEXT.md). Decision record: [ADR 0002](../../docs/adr/0002-home-is-showcase-find-tool.md). Supersedes the marketing-scroll / small-roster reading of [#2](https://github.com/FrancoLedArg/dtm-ones-v2/issues/2) and [#4](https://github.com/FrancoLedArg/dtm-ones-v2/issues/4).

## Product

- **Page kind:** roster tool (public Landing), not a small marketing brochure
- **Product:** DTM ONES — basketball talent-representation agency
- **Primary job:** Evaluators **find and inspect** roster entries (**Players** and **Coaches**) among ~**200** entries
- **Audience:** international Evaluators (clubs, coaches, scouts) — serious, time-poor, legitimacy-seeking; athletes seeking representation are secondary
- **Arrival:** ~50/50 deep link to a known entry vs self-serve find on Home
- **Vibe words:** bold, athletic, high-contrast, find-efficient
- **References:** Instagram `@dtm.ones` signing graphics (`apps/landing/assets/image_1.jpeg` … `image_5.jpeg`) for **detail** posters; Nike Basketball / EuroLeague athlete posters as peer anchors
- **Avoid:** AI-purple gradients; Inter + slate SaaS look; warm cream + terracotta “premium” default; soft pastels; thin delicate serifs; three equal feature cards; glassmorphism everywhere; fake startup jargon; treating Home as a feed of full signing posters; featuring a single preferred Player in the first viewport

## Home = Showcase (find UI)

Home **is** the Showcase work surface:

1. **Name search** — when the Evaluator already knows who
2. **Category filter** — when the need is a bucket (owner pattern: “I need a pivot”). **Category** is Dashboard/CMS-owned; exactly one per entry; Landing does not hardcode labels (may include coach buckets)
3. **Compact card grid** — photo/cutout, bold name, Category chip; DTM athletic look; many results visible per viewport
4. **Thin License strip** — FIBA / JBA marks for legitimacy; must not displace find chrome
5. **One grid** — Players and Coaches together; Category distinguishes them
6. **Out of Home** — full Legends roster (`/legends`); About; Contact

**Not on Home:** marketing hero with a featured Player; Legends teaser as a peer section; sequenced “poster feed” of the whole roster; mini full signing posters in the grid.

## Detail = signing poster

`/players/[slug]` (and the same shape for Coaches): **signing poster** hero adapted for web — massive type, layered cutout, club/local accent, stat chips, lockups — plus modules per [#3](https://github.com/FrancoLedArg/dtm-ones-v2/issues/3). Coach detail matches Player depth.

## Contact

Unchanged for now: `/contact` talk-to-us only; reasons include `Looking for a player` (coach needs go in the message). No roster picker. Showcase is the find tool; Contact is not a second filter UI.

## Motion

Parallax remains a preferred brand signature on **detail / layered poster** surfaces. Do **not** prioritize parallax on the Home find grid until find UX is solid. Honor `prefers-reduced-motion`.

## Instagram signals (still true for posters)

Repeatable poster system for **detail** pages:

- Massive bold white sans display with layered depth (type behind cutout)
- Cutout as hero subject; club palette may drive each piece
- Script accent for surname; slanted/black stat chips
- Footer lockup: league/federation marks + DTM ONES logo
- High contrast, athletic impact

Public site copy remains **English-first** per `CONTEXT.md`; Instagram may stay Spanish for social — brand *visuals* sync on detail, find UX owns Home.

## Prompt block (paste into tasteskill)

```text
I have loaded tasteskill v2 (experimental) as my only source of design rules.

Brief:
- Page kind: roster-tool landing (Home IS the Showcase find UI)
- Product: DTM ONES — basketball talent-representation agency; ~200 Players + Coaches
- Audience: international Evaluators — find-efficiency first
- Home: name search + Category filter + compact card grid + thin License strip; no featured-Player hero; no full signing posters in the grid
- Detail: Instagram @dtm.ones signing-poster hero + profile modules
- Category: Dashboard-owned labels, exactly one per entry (includes coach buckets)
- References: Instagram signing graphics for detail only; compact athletic cards on Home
- Motion: parallax on detail/poster layers later; not required on Home find grid yet
- Avoid: AI-purple; Inter+slate SaaS; cream+terracotta default; equal feature cards; glassmorphism; featured Player preference on Home; mini full posters in the Home grid

Step 1. Declare your design read in one sentence and the three dial values with one-line reasoning each. Stop.

Step 2 (after my OK). Ship Home as the find UI (search + Category + compact cards + License strip) and a Player detail with signing-poster hero. Use real images (gen-tool first, then Picsum-seed). Lock one theme for the whole site.

Step 3. Run in writing:
- Em-dash audit (zero em-dashes U+2014 or en-dashes U+2013 anywhere)
- Pre-Flight Check (Section 14, every box marked Pass or Fail with one-line justification)
- Section-Layout-Repetition audit (list each section's layout family)
- Find-efficiency audit (can an Evaluator filter to a Category and scan results without a marketing scroll?)

Any Fail blocks completion.
```
