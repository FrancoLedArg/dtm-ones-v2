# Landing

Public marketing site for **DTM ONES**, a basketball talent-representation agency. **Evaluators** primarily use the **Showcase** to inspect **Players**; the site also explains the agency (**About**) and accepts **Contact Requests**. Athletes seeking representation are a secondary audience. Public copy is **English-first** (international Evaluators).

**Brand visual direction** stays consistent with Instagram `@dtm.ones` (bold, athletic, high-contrast, player-forward), with **parallax** as a preferred motion signature. See [DESIGN-BRIEF.md](./DESIGN-BRIEF.md).

## Language

**DTM ONES**:
The basketball talent-representation agency this site represents.
_Avoid_: DTM Ones, DTM One's, the agency (when the brand name is meant)

**Evaluator**:
A club, coach, scout, or other visitor assessing Players on the Showcase (often via a link shared by the agency).
_Avoid_: Buyer, customer, user, visitor (when this role is meant)

**Player**:
A basketball athlete currently represented by DTM ONES and presented on the Showcase for Evaluators.
_Avoid_: Athlete, talent, prospect, client

**DTM Legend**:
An iconic athlete who was part of DTM ONES at some point and is featured as a Legend (route `/legends`; Home includes a Legends teaser that links there — see #4). Profile depth is lighter than a Player for now (photo, name, years with DTM, short blurb, optional highlight) unless we explicitly bump it.
_Avoid_: Alumni, hall of fame, former player (as section/brand language — prefer DTM Legend / DTM LEGENDS)

**Showcase**:
The primary use of the landing — browsing and inspecting current Players (Legends are separate).
_Avoid_: Catalog, gallery, portfolio

**Contact Request**:
A visitor’s ask to hear from DTM ONES via the site-wide `/contact` path only. Fields: **reason** (`Seeking representation` | `Looking for a player`), **email**, **phone**, **message** — no name field. *Looking for a player* is intent wording only (recruiting / need a player); the form has no Player picker and must not collect a Player name/slug. The agency owns which Players enter negotiation.
_Avoid_: Lead, inquiry, ticket, form submission, player interest, “I like this player”

**About**:
The separate page for people who want to learn what DTM ONES is, beyond the Showcase — including credentials such as FIBA/JBA licensing.
_Avoid_: Company page, story page (unless used as section labels inside About)

**License**:
An official accreditation DTM ONES holds with a basketball governing body — notably **FIBA** and the **Japan Basketball Association (JBA)** — shown as proof of legitimacy, not a vague “partnership.”
_Avoid_: Partner, partnership, affiliation (when a formal license/accreditation is meant)
