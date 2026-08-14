# Design brief — Landing (roster tool)

Source of design rules: **design-taste-frontend** (tasteskill v2 experimental) only, applied *after* this product brief. Domain language: [CONTEXT.md](./CONTEXT.md). Decision record: [ADR 0002](../../docs/adr/0002-home-is-showcase-find-tool.md). Supersedes the marketing-scroll / small-roster reading of [#2](https://github.com/FrancoLedArg/dtm-ones-v2/issues/2) and [#4](https://github.com/FrancoLedArg/dtm-ones-v2/issues/4).

Home is a find UI. Do not apply tasteskill marketing-page defaults (AIDA, cinematic hero, two CTAs, 3-5 card bento, chapter spacing) to Home. Instagram signing-poster craft applies on the detail page only.

## Product

- **Page kind:** roster tool (public Landing), not a small marketing brochure
- **Product:** DTM ONES — basketball talent-representation agency
- **Primary job:** Evaluators **find and inspect** roster entries (**Players** and **Coaches**) among ~**200** entries
- **Audience:** international Evaluators (clubs, coaches, scouts) — serious, time-poor, legitimacy-seeking; athletes seeking representation are secondary
- **Arrival:** ~50/50 deep link to a known entry vs self-serve find on Home
- **Vibe words:** bold, athletic, high-contrast, find-efficient
- **Theme:** one **dark athletic** DTM ONES look on Home, About, and Contact Request. Signing poster: dark field with that entry’s club colors
- **References (split):** Home density = EuroLeague / FIBA player roster lists (many small tiles, many names on one screen). Detail posters = Instagram `@dtm.ones` signing graphics (`apps/landing/assets/image_1.jpeg` … `image_5.jpeg`) and Nike Basketball / EuroLeague athlete posters
- **Avoid:** AI-purple gradients; Inter + slate SaaS look; warm cream + terracotta “premium” default; soft pastels; thin delicate serifs; three equal feature cards; glassmorphism everywhere; fake startup jargon; treating Home as a feed of full signing posters; featuring a single preferred Player in the first viewport; a large title or agency speech above the Showcase grid

## Surfaces

| Surface | Job | Density | Motion | Color |
|---|---|---|---|---|
| Home (Showcase) | Find | Many compact cards per screen | Hover + filter feedback only | One dark DTM ONES look |
| Detail (signing poster) | Inspect | One poster, then profile modules | Layered depth; parallax later | Dark field + that entry’s club colors |
| About / Contact Request / DTM Legends | Trust, talk, legends | Editorial or simple list, not a find grid | Minimal | Same dark DTM ONES look as Home |

Nav: DTM ONES name (Home), DTM Legends, About, Contact Request. No extra Contact block on Home.

## Home = Showcase (find UI)

The **first screen is the Showcase**. Brand is the wordmark, the athletic material of the compact cards, and the License marks. There is no manifesto H1 and no featured Player.

**Find chrome** (stays on screen while the grid scrolls):

1. **Name search** — list shrinks as the Evaluator types; no Search button as the main path
2. **Category** — one choice; default is all Players and Coaches; Dashboard/CMS-owned labels; Landing does not hardcode the set (may include coach buckets)
3. **Match count** — number of matching roster entries (the full matching list, not only cards on screen)

**First screen, then it scrolls away:**

4. **Thin License strip** — FIBA / JBA marks under find chrome, above the grid. Must not enter the sticky bar. About keeps the full credentials

**Grid:**

5. **Compact cards** — photo the agency stores, one crop, DTM ONES field (not club colors). Photo on top; name and Category under the photo. Not a small signing poster. Players and Coaches in one grid; Category distinguishes them. Many compact cards visible per screen (roster-list density)
6. **Order** — name A to Z when there is no search
7. **Long lists** — Search and Category shrink the matching set. If that set is long, show about **32** compact cards, then add more as the Evaluator scrolls. A new search or Category starts the list again from the first group. Do not use page numbers as the main find method
8. **No matches** — say so; keep search and Category

**Not on Home:** marketing hero with a featured Player; Legends teaser as a peer section; sequenced “poster feed” of the whole roster; mini full signing posters in the grid; type or name laid on top of the photo; club colors on compact cards.

## Detail = signing poster

`/players/[slug]` (and the same shape for Coaches): **signing poster** hero adapted for web — massive type, layered cutout, club/local accent, stat chips, lockups — plus modules per [#3](https://github.com/FrancoLedArg/dtm-ones-v2/issues/3). Coach detail matches Player depth. Height, nationality, and last club are profile facts on detail, not Showcase filters and not compact-card fields.

## About, DTM Legends, Contact Request

Short rules only (same dark DTM ONES look as Home). Showcase stays the only find UI.

- **About:** what DTM ONES is, including License credentials (FIBA / JBA)
- **DTM Legends:** `/legends` only; not a Home teaser; not a second Showcase
- **Contact Request:** `/contact` talk-to-us only; reasons include `Looking for a player` (coach needs go in the message). No roster picker. Not a second filter UI

## Motion

- **Home:** a compact card may lift a little on hover. Search and Category may show simple feedback. No parallax on the Showcase grid
- **Signing poster:** layered depth now; parallax later (this is where owner-preferred parallax lives)
- Honor `prefers-reduced-motion` (hover and poster motion collapse)

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
I have loaded tasteskill v2 (experimental) as my only source of design rules. Apply them AFTER this product brief. Home is a roster-tool Showcase, not a marketing landing.

Brief:
- Page kind: roster-tool landing (Home IS the Showcase find UI)
- Product: DTM ONES — basketball talent-representation agency; ~200 Players + Coaches
- Audience: international Evaluators — find-efficiency first; athletes seeking representation use nav only
- Theme: dark athletic on Home, About, Contact Request; signing poster uses club colors on a dark field
- Home first screen: wordmark + name search + Category + match count + thin License strip + compact card grid. No manifesto H1. No featured Player
- Find chrome (search, Category, match count) stays on screen while the grid scrolls. License strip is on the first screen only, under that chrome
- Name search filters as the Evaluator types. Category is one choice; default is all. Count is the full matching list
- Compact card: agency photo on top, name + Category under; one crop; DTM ONES field; not a mini signing poster; not club colors
- Density: many compact cards per screen (EuroLeague / FIBA roster lists). Name A-Z when there is no search
- Long lists: about 32 compact cards, then more as the Evaluator scrolls. Search or Category resets to the first group. No page numbers as the main find method
- Detail: Instagram @dtm.ones signing-poster hero + profile modules. Height / nationality / last club on detail only
- Motion: Home hover + filter feedback only, no parallax. Parallax later on the signing poster. Honor prefers-reduced-motion
- Other routes (if touched): About = agency + Licenses; /legends = DTM Legends, not a second Showcase; /contact = talk-to-us, no roster picker. Same dark look as Home
- Category: Dashboard-owned labels, exactly one per entry (includes coach buckets)
- Avoid: AI-purple; Inter+slate SaaS; cream+terracotta default; equal feature cards; glassmorphism; AIDA / cinematic hero / bento / chapter spacing on Home; featured Player; mini posters in the grid

Step 1. Declare your design read in one sentence and the three dial values with one-line reasoning each. For this brief, Home is high VISUAL_DENSITY and low MOTION_INTENSITY (roster find UI, not agency marketing). Stop.

Step 2 (after my OK). Ship Home as the Showcase (sticky search + Category + count, License on first screen, compact card grid with scroll-load after ~32) and a Player detail with signing-poster hero. Use real images (gen-tool first, then Picsum-seed). Lock the dark athletic theme on Home. Do not invent a marketing hero.

Step 3. Run in writing:
- Em-dash audit (zero em-dashes U+2014 or en-dashes U+2013 anywhere)
- Pre-Flight Check (Section 14, every box marked Pass or Fail with one-line justification)
- Section-Layout-Repetition audit (list each section's layout family)
- Find-efficiency audit: first screen is search + Category + cards (no manifesto)? Filter as-you-type? Chrome still there after scroll? Count visible? Can an Evaluator pick a Category and scan compact cards without a marketing scroll?

Any Fail blocks completion.
```
