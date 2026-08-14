# Landing

Public **roster tool** for **DTM ONES**, a basketball talent-representation agency. **Evaluators** primarily use the **Showcase** to **find and inspect** roster entries (**Players** and **Coaches**) among a full roster (~200); the site also explains the agency (**About**) and accepts **Contact Requests**. Athletes seeking representation are a secondary audience. Public copy is **English-first** (international Evaluators). Arrival is roughly split: deep link to a known roster entry vs self-serve roster find.

**Home is the Showcase** — find UI (name search + **Category** filter + match count + **compact** result cards for **Players** and **Coaches** in one grid), plus a thin legitimacy strip (**License** marks). Detail pages use the **signing poster**. **Contact Request** stays talk-to-us only; reason label `Looking for a player` unchanged for now. **Category** labels are Dashboard/CMS-owned (exactly one per entry).

## Language

**DTM ONES**:
The basketball talent-representation agency this site represents.
_Avoid_: DTM Ones, DTM One's, the agency (when the brand name is meant)

**Evaluator**:
A club staffer, visiting coach, scout, or other visitor assessing roster entries on the Showcase (often via a link shared by the agency).
_Avoid_: Buyer, customer, user, visitor (when this role is meant); do not confuse with **Coach** (a represented roster entry)

**Player**:
A basketball athlete currently represented by DTM ONES and presented on the Showcase for Evaluators.
_Avoid_: Athlete, talent, prospect, client

**Coach**:
A basketball coach currently represented by DTM ONES and shown in the **same Showcase grid** as Players. Distinguished by **Category** (e.g. a “Coaches” label the agency defines in Dashboard), not by a separate Landing section. Detail page uses the same shape as **Player** (signing-poster hero + comparable modules).
_Avoid_: Evaluator, staff, trainer (when a represented Coach is meant)

**DTM Legend**:
An iconic athlete who was part of DTM ONES at some point and is featured as a Legend (route `/legends`). Profile depth is lighter than a Player for now (photo, name, years with DTM, short blurb, optional highlight) unless we explicitly bump it. Not part of the Home find grid.
_Avoid_: Alumni, hall of fame, former player (as section/brand language — prefer DTM Legend / DTM LEGENDS)

**Showcase**:
The primary work surface of the landing, and **what Home is**: name search, one **Category** filter, a count of matching roster entries, **compact cards** for **Players** and **Coaches** in one grid, and a thin **License** strip. The **signing poster** belongs on the detail page; **DTM Legends** are on `/legends`.
_Avoid_: Catalog, gallery, portfolio, browse-only feed, marketing strip of featured entries, mini full posters in the Home grid

**Compact card**:
A small Showcase result tile: the photo the agency stores on top, name and **Category** under the photo, on the DTM ONES field (not club colors). Not a **signing poster**. Sized so many roster entries fit on screen.
_Avoid_: Poster, signing graphic (when the Home tile is meant)

**Signing poster**:
The full Instagram-style composition for one roster entry (massive type, layered cutout, that entry’s club colors, stat bar, lockups) on the detail page. Club colors live here, not on the **compact card**.
_Avoid_: Card, tile (when the full detail hero is meant)

**Category**:
A Dashboard/CMS-owned label; each Showcase roster entry has **exactly one**. Used as the v1 filter facet (alongside name search). May name on-court roles (e.g. pivot) or other agency buckets (e.g. coaches) — Landing does not hardcode the set. Height, nationality, and last club remain profile facts in v1, not find facets.
_Avoid_: Position (as a Landing-owned enum), tag, role, spot (when this filter facet is meant)

**Contact Request**:
A visitor’s ask to hear from DTM ONES via the site-wide `/contact` path only. Fields: **reason** (`Seeking representation` | `Looking for a player`), **email**, **phone**, **message** — no name field. *Looking for a player* stays as-is for now even though Coaches exist on Showcase; coach needs go in the message. The form has no roster picker and must not collect a Player/Coach name/slug. The agency owns who enters negotiation.
_Avoid_: Lead, inquiry, ticket, form submission, player interest, “I like this player”

**About**:
The separate page for people who want to learn what DTM ONES is, beyond the Showcase — including credentials such as FIBA/JBA licensing.
_Avoid_: Company page, story page (unless used as section labels inside About)

**License**:
An official accreditation DTM ONES holds with a basketball governing body — notably **FIBA** and the **Japan Basketball Association (JBA)** — shown as proof of legitimacy, not a vague “partnership.”
_Avoid_: Partner, partnership, affiliation (when a formal license/accreditation is meant)
