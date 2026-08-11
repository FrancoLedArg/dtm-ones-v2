# Design brief — Landing (tasteskill v2)

Source of design rules: **design-taste-frontend** (tasteskill v2 experimental) only.

Locked decision: Landing brand must **stay consistent with Instagram** (`@dtm.ones`). Visual language follows the existing signing/graphics system, not a quieter SaaS/agency default. Feeds [#2](https://github.com/FrancoLedArg/dtm-ones-v2/issues/2) and unblocks Home IA ([#4](https://github.com/FrancoLedArg/dtm-ones-v2/issues/4)).

## Brief

- **Page kind:** landing
- **Product:** DTM ONES — basketball talent-representation agency; public Landing is Showcase-first for Evaluators
- **Audience:** international Evaluators (clubs, coaches, scouts) — serious, time-poor, legitimacy-seeking; athletes seeking representation are secondary
- **Vibe words:** bold, athletic, high-contrast, player-forward
- **References:** Instagram `@dtm.ones` signing graphics (local captures in `apps/landing/assets/image_1.jpeg` … `image_5.jpeg`); peer anchors Nike Basketball / EuroLeague-style athlete posters
- **Motion:** agency owner wants **parallax** as a real brand motion signature (layered scroll depth on heroes / player cutouts / section backgrounds). Prefer intentional parallax over generic micro-bounce; respect `prefers-reduced-motion`
- **Avoid:** AI-purple gradients; Inter + slate SaaS look; warm cream + terracotta “premium” default; soft pastels; thin delicate serifs; three equal feature cards; glassmorphism everywhere; fake startup jargon (“unlock talent platform”); motion for its own sake without parallax depth

## Instagram signals (captured)

Repeatable poster system observed across assets:

- Massive bold white sans display (“FIRMADO”) with layered depth (type behind cutout player)
- Player cutout as hero subject; club palette drives each piece (maroon/green, red, black/yellow, forest green)
- Script accent for surname; slanted/black stat chips (position + height)
- Footer lockup: league/federation marks + DTM ONES logo
- High contrast, athletic impact, mobile-first composition

Public site copy remains **English-first** per `CONTEXT.md`; Instagram may stay Spanish for social — brand *visuals* sync, language follows glossary.

## Structure implications (for Home IA / #4)

What Instagram rhythm suggests for Landing Home (still to settle on #4):

1. **Player-forward first viewport** — cutout/athlete hero, not agency prose; brand name as hero-level signal beside or over the player plane.
2. **Showcase as the spine** — Home should emphasize browsing/inspecting Players the way the feed emphasizes signed athletes; Legends can teaser later but should not outrank active roster.
3. **Poster-like section rhythm** — high-impact type + layered depth + stat chips; sections should feel like sequenced posters, not equal SaaS feature cards.
4. **Parallax depth between layers** — background wash / oversized type / player cutout / foreground UI should move at different rates on scroll.
5. **Club/league color as local accent** — per-Player pieces may borrow jersey/club color; global chrome stays DTM-consistent (dark, high-contrast, bold sans).
6. **Proof strip without softening** — FIBA/JBA License marks can sit like the Instagram footer lockups (small, official), not as soft partner logos.

## Prompt block (paste into tasteskill)

```text
I have loaded tasteskill v2 (experimental) as my only source of design rules.

Brief:
- Page kind: landing
- Product: DTM ONES — basketball talent-representation agency; public Landing is Showcase-first for Evaluators
- Audience: international Evaluators (clubs, coaches, scouts) — serious, time-poor, legitimacy-seeking; athletes seeking representation are secondary
- Vibe words: bold, athletic, high-contrast, player-forward
- References: Instagram @dtm.ones signing graphics (apps/landing/assets/image_1–5.jpeg); Nike Basketball / EuroLeague-style athlete posters
- Motion: parallax as brand signature (layered scroll depth on heroes / player cutouts / section backgrounds); honor prefers-reduced-motion
- Avoid: AI-purple gradients; Inter + slate SaaS look; warm cream + terracotta “premium” default; soft pastels; thin delicate serifs; three equal feature cards; glassmorphism everywhere; fake startup jargon (“unlock talent platform”); motion without parallax depth

Step 1. Declare your design read in one sentence and the three dial values with one-line reasoning each. Stop.

Step 2 (after my OK). Ship a single Next.js page with at least 8 sections. Pick the sections that actually fit the product. At least 4 different layout families across the page. Use real images (gen-tool first, then Picsum-seed). Lock one theme for the whole page.

Step 3. Run in writing:
- Em-dash audit (zero em-dashes U+2014 or en-dashes U+2013 anywhere)
- Pre-Flight Check (Section 14, every box marked Pass or Fail with one-line justification)
- Section-Layout-Repetition audit (list each section's layout family)
- Hero discipline audit (headline lines, subtext words, CTA visibility)

Any Fail blocks completion.
```
