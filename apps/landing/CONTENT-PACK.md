# Landing content pack (Players + Legends)

**Status:** curated pack for [#5](https://github.com/FrancoLedArg/dtm-ones-v2/issues/5) — 5 Players + same 5 as Legends (asset reuse)  
**Assets root:** `apps/landing/assets/players-assets/<Player Name>/`  
**Facts marked PLACEHOLDER** (height, nationality, last club, position) are invented for UI work until real values replace them.

Aligned to Player page (#3): hero = institutional cutout + name + position/height chips + nationality + last club (logo/color when available); below = action gallery + YouTube highlights.

Agency owns final asset quality; this pack is the curated usable base after local cleanup (~23MB, no zips).

---

## Active Players (5)

| Name | Slug | Position (PLACEHOLDER) | Height (PLACEHOLDER) | Nationality (PLACEHOLDER) | Last club (PLACEHOLDER) | Institutional (hero) | Action gallery | YouTube |
|------|------|------------------------|----------------------|---------------------------|-------------------------|----------------------|----------------|---------|
| Alphonso Anderson | `alphonso-anderson` | Forward | 201 cm | USA | Boca Juniors | `institutional.png` | `FOTO JUEGO7.jpg`, `FOTO JUEGO8.jpg`, `FOTO JUEGO9.jpg`, `522397727_…_n.jpg`, `541890232_…_n.jpg`, `cinthiamute_…_n.jpg` | missing |
| Bryan Carabali | `bryan-carabali` | Guard | 188 cm | Ecuador | Pasto | `institucional.png` | `FOTO JUEGO 1.jpg` … `FOTO JUEGO 5.jpg`, `carabali_22_…_n.jpg` | missing |
| Christian Alaekwe | `christian-alaekwe` | Forward | 200 cm | Nigeria | Ferro | `institutional.png` | `JUEGO 2.jpg` … `JUEGO 6.jpg` (incl. `JUEGO 5 (2).jpg`) | missing |
| Richard Granberry | `richard-granberry` | Center | 205 cm | USA | Ciclista Olímpico | `institucional.png` | `FOTOS JUEGO 3.jpg`, `FOTOS JUEGO 4.jpeg`, `FOTOS JUEGO 5.jpg`, `ciclistaolimpico_…_n.jpg` | missing |
| Stedmon Lemon | `stedmon-lemon` | Forward | 201 cm | USA | Quimsa | `INSTITUCIONAL.png` | `JUEGO 1.jpg`, `shots_byce_…_n.jpg` | missing |

### Per-folder file inventory

**Alphonso Anderson** (7)

- Hero: `institutional.png`
- Action: `FOTO JUEGO7.jpg`, `FOTO JUEGO8.jpg`, `FOTO JUEGO9.jpg`, `522397727_17911857333172813_4375161999891479298_n.jpg`, `541890232_17916886437172813_795229296516635341_n.jpg`, `cinthiamute_528325120_18518063419012020_6192154861422663819_n.jpg`

**Bryan Carabali** (7)

- Hero: `institucional.png`
- Action: `FOTO JUEGO 1.jpg`, `FOTO JUEGO 2.jpg`, `FOTO JUEGO 3.jpg`, `FOTO JUEGO 4.jpg`, `FOTO JUEGO 5.jpg`, `carabali_22_589912555_18093891097922785_8617115379682770053_n.jpg`

**Christian Alaekwe** (6)

- Hero: `institutional.png`
- Action: `JUEGO 2.jpg`, `JUEGO 3.jpg`, `JUEGO 4.jpg`, `JUEGO 5 (2).jpg`, `JUEGO 6.jpg`

**Richard Granberry** (5)

- Hero: `institucional.png`
- Action: `FOTOS JUEGO 3.jpg`, `FOTOS JUEGO 4.jpeg`, `FOTOS JUEGO 5.jpg`, `ciclistaolimpico_557521986_18528774172060227_5385646592908811816_n.jpg`

**Stedmon Lemon** (3)

- Hero: `INSTITUCIONAL.png`
- Action: `JUEGO 1.jpg`, `shots_byce_607906335_18034292906751236_1269026200465513259_n.jpg`

---

## DTM Legends (5 — same athletes, reused assets)

Same five as active Players for UI placeholders. Reuse the institutional (or primary) photo from `players-assets/<Name>/`. Lighter profile per glossary: photo, name, years with DTM, short blurb, optional highlight. Copy below is PLACEHOLDER.

| Name | Photo (reuse) | Years with DTM (PLACEHOLDER) | Blurb (PLACEHOLDER) | Optional highlight |
|------|---------------|------------------------------|---------------------|--------------------|
| Alphonso Anderson | `…/Alphonso Anderson/institutional.png` | 2022–2024 | Power forward who brought scoring punch to the DTM ONES roster. | — |
| Bryan Carabali | `…/Bryan Carabali/institucional.png` | 2021–2023 | Guard known for pace and perimeter pressure during his DTM years. | — |
| Christian Alaekwe | `…/Christian Alaekwe/institutional.png` | 2020–2023 | Athletic forward and a cornerstone of the agency’s early Showcase era. | — |
| Richard Granberry | `…/Richard Granberry/institucional.png` | 2019–2022 | Rim presence and leadership that defined a DTM Legend stretch. | — |
| Stedmon Lemon | `…/Stedmon Lemon/INSTITUCIONAL.png` | 2021–2024 | Skilled wing whose highlight plays still represent the brand. | — |

No separate `legends-assets` folder — intentional reuse of Player media.

---

## Gaps

| Gap | Impact |
|-----|--------|
| Height / nationality / last club / position are PLACEHOLDER | Replace before launch |
| Legend years / blurbs are PLACEHOLDER | Replace when owner has real Legend copy |
| No YouTube highlight URLs | Highlights module empty |
| No club logos | Poster accent = text / default palette |
| Players and Legends are the same five people | Fine for UI; split real roster later if needed |
| Stedmon Lemon thin action set (2) | Still usable; more action stills would help |

---

## Acceptance checklist (#5)

- [x] Active Players list with assets/facts sufficient for detail pages (5 curated; facts PLACEHOLDER)
- [x] DTM Legends list with lighter assets/blurbs (same 5; assets reused; copy PLACEHOLDER)
- [x] Gaps called out above
