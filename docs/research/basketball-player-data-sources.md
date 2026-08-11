# Basketball player / match data sources for a talent-agency showcase

**Date:** 2026-08-11  
**Project:** DTM ONES basketball talent agency landing site  
**Audience:** product / engineering evaluating licensed feeds for always-current European & international club player profiles

---

## 1. Question / scope

**Question:** What licensed (or officially documented) basketball data sources can power rich, up-to-date **player profiles** on a small talent-agency landing showcase focused on **European / international club basketball** (not NBA-only)? How does **eurobasket.com** (the news/database site) fit, and does it sit on another provider’s feed?

**In scope**

- Programmatic or licensed access to player bio + season/career stats, preferably with match/live data as a bonus
- European club competitions (EuroLeague, EuroCup, national leagues such as ACB, BBL, ABA, etc.) and broader international club coverage
- Fitness for a **small roster of represented players** (agency showcase), not full league operations or betting books
- Pricing transparency where public; flag “contact sales” when that is all that is published

**Out of scope**

- Scraping eurobasket.com or any Cloudflare-protected site (ToS + bot protection; not a viable path)
- Conflating **FIBA EuroBasket** (the continental national-team tournament) with **eurobasket.com** (independent commercial news/database site)

**Naming note:** In this doc, “eurobasket.com” always means the website. “EuroBasket” / “FIBA EuroBasket” means the FIBA tournament.

---

## 2. Does eurobasket.com use an underlying third-party feed?

### Short answer

**No strong primary-source evidence that eurobasket.com’s core player-profile database is a reskin of Sportradar, STATSCORE, Opta, or similar.** Public first-party copy presents the database as **correspondent-built and proprietary**. Sportradar / STATSCORE appear in eurobasket.com *editorial* about live tournament coverage (often referring to the FIBA **EuroBasket** event), which is not the same as proving the site’s 940k+ profile DB is those vendors’ APIs.

### Evidence

| Claim | Source | Notes |
| --- | --- | --- |
| Site maintains ~940k+ player/coach profiles across 435 leagues / 196 countries; pages updated daily | [eurobasket.com About Us](https://www.eurobasket.com/aboutus.aspx); [Wikipedia: Eurobasket.com](https://en.wikipedia.org/wiki/Eurobasket.com) | Wikipedia attributes content to staff + correspondents and paid-gated database depth |
| Database described as result of **248 correspondents** worldwide | [About Us](https://www.eurobasket.com/aboutus.aspx); [Database Access subscription page](https://www.eurobasket.com/subscribe.aspx?service=db_access) (search-index / payment mirror also at [payment.eurobasket.com](https://payment.eurobasket.com/subscribe.aspx)) | First-party framing: editorial contribution network, not a named third-party feed |
| Paid **Database Access** is a **website subscription** (human browse), not a published developer API | Same subscribe pages; site homepage warns against copying/redistributing downloaded information | No official OpenAPI / XML bulk export found in primary docs for third-party apps |
| Agent-oriented product is **“Agent’s Page”** add-on (+ USD 755 / 12 months on the package list), not a data API | [Database Access packages](https://www.eurobasket.com/subscribe.aspx?service=db_access) | Agency *presence* on eurobasket.com, not licensed feed for your own site |
| Editorial article on eurobasket.com discusses STATSCORE / Sportradar for **EuroBasket** coverage and mentions news portals (e.g. eurobasket.com) embedding Sportradar-enriched data | [“From Courtside to Code…”](https://www.eurobasket.com/European-Championships/news/974908/From-Courtside-to-Code-The-Tech-Behind-EuroBasket%E2%80%99s-Smarter-Coverage) | Topic is FIBA **EuroBasket** tech/coverage. Language is illustrative (“can help”); **not** a technical disclosure that the profile DB is Sportradar-backed |
| Site is behind Cloudflare bot protection | Observed when fetching subscribe pages programmatically | Aligns with “scraping is a no-go” |

### Working conclusion for DTM ONES

- Treat eurobasket.com as a **human research / scouting UI** (and optionally Agent’s Page marketing), **not** as a licensed API for the landing site.
- For always-up-to-date profiles **on DTM ONES**, plan on a **separate licensed feed** (or curated CMS + licensed stats), not eurobasket.com as the system of record.

---

## 3. Candidate sources

### Comparison table (agency-showcase lens)

| Source | Coverage (EU / intl club) | Player profile depth | Match / live? | Licensing / pricing (public) | Fitness for small agency showcase | Official docs |
| --- | --- | --- | --- | --- | --- | --- |
| **Sportradar Global Basketball API** | Explicitly includes EuroLeague, Liga ACB, BBL, ABA, Pro A, etc. (200+ competitions in package; see Coverage Matrix) | Bio + team membership; seasonal / game stats via related feeds | Yes (summaries, timelines, push for RT customers) | **Contact sales** for production; **30-day trial** (1,000 req / 30 days, 1 QPS) via Marketplace | Strong fit if budget allows; overkill if you only need ~10–30 players | [Overview](https://developer.sportradar.com/basketball/reference/global-basketball-overview), [Player Profile](https://developer.sportradar.com/basketball/reference/global-basketball-player-profile), [FAQ / leagues](https://developer.sportradar.com/basketball/reference/global-basketball-faq), [Coverage Matrix](https://coverage-matrix.sportradar.com/), [Account / trial](https://developer.sportradar.com/getting-started/docs/your-account) |
| **Stats Perform / Opta** | Multi-sport; basketball includes NBA / NCAA / European competitions (product pages); 3,900+ competitions claimed across sports | Deep Opta-style metrics / AI products for media | Live feeds + APIs marketed for media/apps | **Enterprise / contact sales only**; custom by competition & data level; FAQ says org-focused, works with startups via sales | Excellent quality; likely **expensive** vs showcase needs | [Pricing FAQ](https://www.statsperform.com/faqs/stats-perform-faqs-pricing-licensing/), [Media APIs page](https://www.statsperform.com/resource/apis-and-ai-tools-for-media-broadcasters-and-sports-apps/), [Opta APIs article](https://www.statsperform.com/insights/crafting-next-gen-sports-apps-and-media-experiences-with-stats-performs-opta-apis/) |
| **STATSCORE SportsAPI** | Basketball listed among 40+ sports; 14k+ competitions / 1M+ athletes claimed | Fixtures → advanced (xG-style / ratings / missing players at higher tiers—sport-dependent) | Separate live products (ScoutsFeed, DeepFeed) | Bespoke; **starts from ~€1,000** (published floor) | Mid-market candidate; still sales-led | [SportsAPI](https://www.statscore.com/products/sportsapi/), [API docs (Confluence)](https://statscore.atlassian.net/wiki/spaces/API/overview), [docs-v3](https://docs-v3.api.statscore.com/) |
| **API-Sports / API-Basketball** | Broad league list incl. Euroleague, Eurocup, FIBA Europe Cup, many national / regional EU leagues | Games, teams, players, stats, standings, odds (plan-gated seasons on Free) | Livescore / games endpoints | **Public self-serve:** Free 100 req/day; Pro $15; Ultra $25; Mega $35 / mo (all comps on paid) | **Best DIY fit** for a small showcase if profile depth is “good enough” | [api-basketball.com](https://www.api-basketball.com/), [Coverage](https://www.api-basketball.com/coverage), [Docs](https://api-sports.io/documentation/basketball/v1), also via RapidAPI |
| **EuroLeague official digital / stats surfaces** | EuroLeague + EuroCup only | Rich people / career / advanced stats via public `api-live.euroleague.net` swagger (V1–V3 + Live) | Live PBP / shots endpoints exist in ecosystem | **Not a commercial data license by default.** Platform terms: private non-commercial use of content; Statistics section restricts commercial / gambling / fantasy / comprehensive regularly updated DB without prior consent | Technically rich for EL/EC players; **legal risk** for agency marketing site without written consent | [Swagger](https://api-live.euroleague.net/swagger/index.html), [hub.euroleague.tech Terms (Statistics)](https://hub.euroleague.tech/terms), Bylaws assert exclusive **Data Rights** ([2025/26 Bylaws PDF](https://ftpserver.euroleague.net/general/2025_26_EuroLeague_Bylaws.pdf)) |
| **FIBA LiveStats / GDAP** | FIBA official competitions + many federations/leagues using LiveStats | Competition / accumulated player & team stats via GDAP (subscription products) | Live via Livestats Integrator (pull-only on GDAP) | LiveStats app **free to federations/leagues**; **GDAP APIs require authenticated subscription** | Poor fit as primary showcase DB (FIBA comps ≠ random club careers); useful if players are in FIBA windows | [FIBA LiveStats](https://about.fiba.basketball/en/services/data-and-video-solutions/fiba-live-stats), [GDAP portal](https://gdap-portal.fiba.basketball/), [GDAP docs](https://gdap-portal.fiba.basketball/documentation) |
| **Genius Sports** | Official / exclusive data partner for many basketball leagues (e.g. historical ACB partnership; ABA; FIBA LiveStats co-dev) | Warehouse REST + streaming for matches, players, stats | Yes (streaming + LiveStats in-venue TV feed) | **Contact / partnership**; pricing not public | Enterprise / rights-holder path; not DIY | [Developer Centre](https://developer.geniussports.com/), [Basketball Warehouse REST](https://developer.geniussports.com/warehouse/rest/index_basketball.html), [ACB partnership (Genius)](https://www.geniussports.com/newsroom/genius-sports-group-extends-long-term-exclusive-betting-data-partnership-with-spanish-acb-league/) |
| **balldontlie** | NBA (primary docs); other US / top sports on all-access—**not** a European club basketball database | Strong NBA player/game/advanced stats | Live NBA-oriented | Self-serve from $0 / $9.99 / $39.99; All-Access $299.99/mo | **Limited for this use case** (NBA-centric) | [docs.balldontlie.io](https://docs.balldontlie.io/), [balldontlie.io](https://www.balldontlie.io/) |
| **eurobasket.com Database Access** | Extremely wide club/amateur coverage (site’s differentiator) | Deep bio / career / evaluations (human UI) | Media guides / game pages; not a documented live API | Website sub from ~$0.58/day (1-year framing); Agent’s Page +$755/yr | Great for **researchers**; **not** for embedding on DTM ONES without a separate license (none published as API) | [About Us](https://www.eurobasket.com/aboutus.aspx), [Subscribe](https://www.eurobasket.com/subscribe.aspx?service=db_access) |
| **League / federation side APIs** (e.g. German basketball-bund.net REST used by community tools) | Single-country / federation | Schedules, tables, boxscores vary | Varies | Often undocumented for commercial reuse; treat as **fragile / ToS-grey** | DIY experiments only; not recommended as sole licensed source | Community docs exist for DBB REST; prefer rights-holder or redistributor |

### Source notes (detail)

#### Sportradar Global Basketball

- Product overview: real-time scores + stats when available; standings; **player profiles**; team profiles; historical results; rosters; seasonal stats; optional probabilities / push. Data via on-venue scouts and in-house operators; **200+ competitions** in one package. Coverage depth varies by competition—use the [Coverage Matrix](https://coverage-matrix.sportradar.com/).
- FAQ lists select leagues including **Euroleague, Eurocup, Pro A, Liga ACB, BBL, Liga ABA**, etc.
- Trial is real and documented; **production pricing is not published** (sales / custom quote). Media page describes Real-time vs Standard packages with request caps for “core” US sports—use as packaging pattern, not a Global Basketball price list.

#### Stats Perform / Opta

- Sold as **enterprise** sports data/AI; FAQ: pricing tailored; **contact sales**; can license **single competition / country**; claims to work with startups via sales.
- Opta APIs article note: *“Stats Perform only sell data at an enterprise level.”*
- Strong for broadcast/media depth; likely poor cost/fit for a landing page of represented players unless the agency already has a media partnership.

#### STATSCORE

- SportsAPI: REST JSON/XML; tiers STARTER → LEGEND; basketball included; public pricing floor **from €1,000** (bespoke by sports/comps/level).
- Positions against “automated scrapes”; human editors/scouts.
- ScoutsFeed offers a **media-oriented** lower-latency variant (still sales).

#### API-Sports / API-Basketball

- Self-serve developer API with **transparent monthly pricing** and large European competition lists (Euroleague, Eurocup, national leagues, FIBA Europe Cup, youth EuroBasket divisions, etc.).
- Available on provider dashboard and historically via **RapidAPI**.
- Profile depth is typically season/game stats oriented—not eurobasket.com-style long-form evaluations. Adequate for “current club + season averages + recent games” on a showcase.
- Free tier exists but is request- and season-limited; paid plans unlock players endpoints more usefully.

#### EuroLeague official

- Public swagger at `api-live.euroleague.net` exposes clubs, people, advanced player stats, game reports, live-oriented surfaces.
- **Terms (Statistics):** attribution required; **legitimate news reporting or private, non-commercial** use; bans sponsorship/commercial identification, gambling, fantasy, real-time PBP products, and **comprehensive regularly updated stats databases** without **express prior consent**.
- Bylaws define exclusive **Data Rights** for Events. For a commercial talent-agency site, assume you need **written Euroleague consent** or a redistributor license—not “the swagger is open so ship it.”

#### FIBA LiveStats & GDAP

- LiveStats: Genius Sports + FIBA; free to federations/leagues for collection; APIs/XML exports as product features.
- GDAP: authenticated, subscription product APIs for FIBA competition systems; pull-only; live via Livestats Integrator. Not a general world-club career DB.

#### Genius Sports

- Infrastructure behind much “official” basketball data (LiveStats, league partnerships such as ACB exclusive betting rights / media distribution rights historically).
- Developer docs are customer-facing (Warehouse REST, streaming). Access is commercial partnership—not a public self-serve price card.

#### balldontlie

- Excellent **NBA** (and multi-sport all-access) developer UX and pricing.
- **Flag as limited** for European club showcase unless represented players are NBA / WNBA / NCAAB only.

#### RapidAPI basketball listings

- Marketplace hosts API-Sports Basketball and third-party aggregators (e.g. BasketAPI claiming 70+ leagues including Euroleague / ACB). Prefer **API-Sports** for clearer vendor + coverage pages; treat anonymous RapidAPI wrappers as higher vendor-risk.

---

## 4. Rough recommendation tiers

### Enterprise

**Sportradar Global Basketball**, **Stats Perform/Opta**, **Genius Sports** (or league-official via Genius).

- Use when: multi-league roster, need contractual SLAs, official/near-official data, live match centres, imagery/editorial add-ons.
- Expect: sales cycle, custom quote, MSA/ToS review; trial first on Sportradar Marketplace.
- Agency tip: ask sales for a **media / digital showcase** package limited to **named player IDs** or a small competition set—enterprise vendors sometimes scope by competition; public “agent media kit” SKUs were **not** found.

### Mid

**STATSCORE SportsAPI** (and related media feeds); possibly **Sportradar** if a discounted media package lands near mid-market.

- Use when: need broader than DIY APIs, willing to pay ~€1k+ and integrate REST, still don’t need Opta-depth AI.
- Agency tip: request **basketball-only**, **selected competitions**, **post-game + player profile** (skip ultra-low-latency betting feed).

### DIY-friendly (best starting point for DTM ONES)

1. **CMS-owned player cards** for represented athletes (bio, agency copy, photos under your license).
2. **API-Basketball (API-Sports)** to refresh current team, season stats, recent games for those players (cache aggressively; small roster ⇒ low request volume).
3. Optional human research on **eurobasket.com Database Access** for scouting—not as site backend.
4. If many clients are EuroLeague/EuroCup only: open a conversation with **Euroleague** (ID Pro / data rights) **before** wiring the public swagger into production.

**Avoid as primary:** scraping eurobasket.com; balldontlie alone; assuming EuroLeague swagger = commercial license; NBA-only packages for an international club agency.

### Agent-friendly / lower price points — what exists?

| Option | What it is | Verdict |
| --- | --- | --- |
| eurobasket.com **Agent’s Page** | Paid marketing presence on their network | Agency marketing on *their* site; **does not** feed DTM ONES |
| eurobasket.com **Database Access** | Cheap human DB access | Research tool, not embeddable API |
| API-Sports tiers ($15–35/mo) | Self-serve multi-league basketball API | Closest thing to **agent-friendly licensed stats** |
| Sportradar 30-day trial | Evaluate Global Basketball profile endpoints | Use to validate coverage for *your* players before sales |
| Stats Perform / Genius / Opta | “Startups welcome” but sales-led | Ask for media/startup quote; no published agent SKU found |
| FIBA LiveStats free download | League/federation tooling | Not an agency data license |

No primary source found for a dedicated **“talent agent media kit”** data product from Sportradar, Opta, or Genius at a published low price. Budget path = **DIY API + own CMS**; premium path = **sales quote** scoped to few competitions / players.

---

## Decision (Landing — 2026-08-11)

Recorded on [Evaluate Eurobasket (or alternatives) as Player data source](https://github.com/FrancoLedArg/dtm-ones-v2/issues/1).

- **Landing now:** no third-party basketball stats/match feed. Showcase Players are CMS-owned (bio, photos, agency narrative).
- **Later, if stats are added:** re-evaluate licensed options then. Prefer a provider with a **documented commercial API** (or written data license). Treat **eurobasket.com** as a candidate **only if** they confirm a machine-readable commercial feed; otherwise default to a mid-market sports API (e.g. API-Basketball) or an enterprise quote (Sportradar / STATSCORE / Opta). Do not scrape.
- **eurobasket.com Database Access** remains fine as optional **human** research while editing CMS content.

---

## 5. Sources cited

### eurobasket.com / naming

- https://www.eurobasket.com/aboutus.aspx  
- https://www.eurobasket.com/subscribe.aspx?service=db_access  
- https://payment.eurobasket.com/subscribe.aspx  
- https://en.wikipedia.org/wiki/Eurobasket.com  
- https://www.eurobasket.com/European-Championships/news/974908/From-Courtside-to-Code-The-Tech-Behind-EuroBasket%E2%80%99s-Smarter-Coverage  

### Sportradar

- https://developer.sportradar.com/basketball/reference/overview  
- https://developer.sportradar.com/basketball/reference/global-basketball-overview  
- https://developer.sportradar.com/basketball/reference/global-basketball-player-profile  
- https://developer.sportradar.com/basketball/reference/global-basketball-faq  
- https://coverage-matrix.sportradar.com/  
- https://developer.sportradar.com/getting-started/docs/your-account  
- https://sportradar.com/media-tech/data-content/sports-data-api/  
- https://marketplace.sportradar.com/media-tech  

### Stats Perform / Opta

- https://www.statsperform.com/faqs/stats-perform-faqs-pricing-licensing/  
- https://www.statsperform.com/resource/apis-and-ai-tools-for-media-broadcasters-and-sports-apps/  
- https://www.statsperform.com/insights/crafting-next-gen-sports-apps-and-media-experiences-with-stats-performs-opta-apis/  
- https://www.statsperform.com/insights/opta-by-stats-perform-global-leader-ai-sports-data-analytics/  

### STATSCORE

- https://www.statscore.com/products/sportsapi/  
- https://www.statscore.com/products/scoutsfeed/  
- https://statscore.atlassian.net/wiki/spaces/API/overview  
- https://statscore.atlassian.net/wiki/spaces/APS/pages/7110733/API+service  
- https://docs-v3.api.statscore.com/  

### API-Sports / RapidAPI

- https://www.api-basketball.com/  
- https://www.api-basketball.com/coverage  
- https://www.api-basketball.com/sports  
- https://api-sports.io/documentation/basketball/v1  
- https://rapidapi.com/fluis.lacasse/api/basketapi1 (third-party RapidAPI listing; vendor ≠ API-Sports)

### EuroLeague

- https://api-live.euroleague.net/swagger/index.html  
- https://hub.euroleague.tech/terms  
- https://ftpserver.euroleague.net/general/2025_26_EuroLeague_Bylaws.pdf  

### FIBA / Genius Sports

- https://about.fiba.basketball/en/services/data-and-video-solutions/fiba-live-stats  
- https://gdap-portal.fiba.basketball/  
- https://gdap-portal.fiba.basketball/documentation  
- https://developer.geniussports.com/  
- https://developer.geniussports.com/warehouse/rest/index_basketball.html  
- https://developer.geniussports.com/livestats/tvfeed/index_basketball.html  
- https://www.geniussports.com/newsroom/genius-sports-group-extends-long-term-exclusive-betting-data-partnership-with-spanish-acb-league/  
- https://investors.geniussports.com/news/news-details/2016/ACB-selects-Genius-Sports-to-unlock-the-value-of-its-data/default.aspx  
- https://www.aba-liga.com/news/38440  

### balldontlie (NBA-limited for this brief)

- https://docs.balldontlie.io/  
- https://www.balldontlie.io/  
- https://www.balldontlie.io/openapi/nba.yml  

---

## Appendix: suggested next actions for DTM ONES

1. List represented (or target) players and their current competitions.  
2. Start **API-Basketball** free/Pro trial; confirm those competitions and player IDs exist and update cadence is acceptable.  
3. In parallel, start **Sportradar Global Basketball** 30-day trial; compare profile richness for the same players.  
4. If EuroLeague-heavy: email Euroleague commercial / digital rights for **written** reuse terms before production use of public endpoints.  
5. Keep eurobasket.com as optional **human** research / Agent’s Page—not the site’s data backend.
