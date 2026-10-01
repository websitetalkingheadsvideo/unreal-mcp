# PART XIII — QUEST IMAGES SYSTEM  
## (Full, Exhaustive Version)

## 1. Overview  
The vbn-game Quest Images System defines rules, locked style/technical blocks, subject grammar, aspect handling, and deploy paths for **quest card / quest still** art. These images appear in quest-agent UI surfaces (e.g. `view_quest_api` image resolution), hub dossiers, tracking, and marketing-adjacent quest lists.

Quest images must visually align with the gothic–noir, Phoenix 1994 aesthetic of the entire project. They sit between **Part II (Cinematic)** shot grammar and **Part III (Location)** environment truth, and may include **Part I** character likeness when the still is cast-forward.

Quest stills are **not** square portraits (Part I), not full cutscene sequences (Part II), and not location exterior/blueprint/moodboard triples (Part III / VIII). They are **single coherent film stills** keyed to a `quests.slug`.

### Quest image cinematic charter (prepend subject; lock style + technical)

Every positive quest-image prompt **MUST** use this structure. Only **`[SUBJECT]`** (and, when needed, the short “seen at…” camera clause) may change. **STYLE BLOCK** and **TECHNICAL BLOCK** are **do not modify** unless Storyteller explicitly overrides the Art Bible for a one-off.

---

## 2. Resolution & Aspect Ratio  

| Deliverable | Spec | Notes |
|-------------|------|--------|
| **Hero master** | Anamorphic **2.39:1** | Matches TECHNICAL BLOCK; keep as cinematic master when generated |
| **Quest card (canonical deploy)** | Prefer **1:1** (or UI-safe crop from master) | `view_quest_api` resolves `uploads/quests/<slug>.png\|jpg\|webp` for cards |
| **File format** | PNG preferred; JPG/WEBP accepted by resolver | No DB image column — filesystem by slug |

**Production rule:** Prefer generate **2.39:1** per TECHNICAL BLOCK, then **center-crop** (or ST-approved crop) to **1:1** for `uploads/quests/<slug>.png`. Do not silently replace the master; keep widescreen staging under `images-generated/` when useful.

---

## 3. Subject Classes  

Only the opening subject line varies. Keep Phoenix 1994 truth and LotNR tone (cost, silence, reputation — no free spectacle).

### 3.1 Exterior  
Place-forward establishing or approach stills: wash channels, strip lots, club façades, equestrian barns, desert scrub at lot edges.

**Official look (canonical reference still):**  
[`images-generated/quest_exterior_official_look.png`](../../../images-generated/quest_exterior_official_look.png)  
Source master: [`images-generated/wash_foreign_blood_hunt_quest_master_v7.png`](../../../images-generated/wash_foreign_blood_hunt_quest_master_v7.png) (Foreign Blood Hunt — ST desaturation + curve on dimmed v6/v7).  
**Agents MUST** pass this file as a **fal / img2img grading + integration reference** (after portrait lock when cast is in frame; with location exterior ref when place-locked) for **exterior** and **exterior-hybrid** quest stills / cards. Match: **desaturated** muted amber sodium, **curved contrast** (deep blacks, dimmed practicals ~33% below raw fal bloom), integrated subject shadow on concrete, dry haze, one unified film still — not candy-neon, not pasted cutout.

Style-agent preset id: `quest_exterior_official_look` (`docs/style_presets/quest_exterior_official_look.md`).

**Subject pattern:**  
`[Place / event beat], seen at street level.`

### 3.2 Interior  
Bar rails, service halls, ballrooms, culvert mouths framed from doorway, office closets — still desert-city noir, not European gothic cathedral default.

**Official look (canonical reference still):**  
[`images-generated/quest_interior_official_look.png`](../../../images-generated/quest_interior_official_look.png)  
Source master: [`images-generated/weight_of_guilt_aftermath_quest_master.png`](../../../images-generated/weight_of_guilt_aftermath_quest_master.png) (Weight of Guilt Q4 Aftermath — Halcyon empty-chair interior).  
**Agents MUST** pass this file as a **fal / img2img grading + composition reference** (typically after place refs; before or with location interior refs when available) for **interior** quest stills / cards. Match: warm practical table lamps vs cool blue anamorphic flare, smoky haze, brick + neon period signage, empty place-setting as emotional beat, mid-century lounge furniture, shallow DOF background patrons, crushed blacks. Do **not** invent European cathedral gothic or wet Hong Kong interiors.

Style-agent preset id: `quest_interior_official_look` (`docs/style_presets/quest_interior_official_look.md`).

**Subject pattern:**  
`[Interior place / beat], seen from [doorway / rail / low corner].`  
(Replace “street level” only when interior framing requires it; STYLE + TECHNICAL stay locked.)

### 3.3 Character-in-frame  
One or few figures, readable silhouette, environment still carries Phoenix 1994. Do not invent clan splash-art poses.

**HARD RULE — portrait is the identity basis:** When any **named** Kindred/ghoul/mortal from the chronicle is in frame, the generator **MUST** pass their live `uploads/characters/<portrait_name>` as **`image_urls` Image 1** (and usually **Image 2 = same portrait again** for weight). Location exteriors / props are **secondary** refs after face lock. Prompt must state that Image 1 (and 2) are the **exact face identity** — wardrobe/pose/setting may change; do **not** invent a different person. **Age lock:** match the **portrait’s age** — do **not** age the figure older/weathered past the canon portrait (common fal drift). If the still ages up, `/edit` youth-lock to portrait ×2. If the face drifts, run **`fal-ai/nano-banana-2/edit`**: Image 1 = current still, Image 2+ = canon portrait, replace **only** the drifted figure. Cursor `GenerateImage` / text-only fal with no portrait refs is **not** a valid character-in-frame path.

**Subject pattern:**  
`[Named character(s) + action/beat], [place], seen at street level.`  
(or interior camera clause as in 3.2)

### 3.4 Hybrid  
Exterior with figure mid-ground, or interior with cast — still **one** coherent moment, not collage (moodboards are Part III moodboard slot, not quest cards).

---

## 4. Lighting & Color Grade  

Inherited from locked STYLE + TECHNICAL blocks and the project palette:

- Gothic Black `#0d0606`, Dusk Brown-Black `#1a0f0f`, Blood Red `#8B0000`, Parchment Light `#f5e6d3`, Muted Gold `#d4b06d`, Teal Moonlight `#0B3C49`
- Amber **sodium** practicals vs **cold blue** shadow
- Dry dust/smog halation — **nothing wet, nothing clean**
- Hard sidelight; bloom on every practical; crushed blacks with retained silhouette

---

## 5. Camera & Composition  

Locked in TECHNICAL BLOCK:

- Anamorphic **2.39:1**, **40mm**, shallow DOF  
- Horizontal blue lens flare streaks, halation/bloom  
- 35mm film grain  
- Low camera angle (default; interiors may raise eye height only via SUBJECT clause)  
- Smoke/dust diffuse the key  

**Composition DO:** one beat, readable geography, period 1994 signage and materials when exterior.  
**Composition DON'T:** poster/key-art staging, UI mockups in-frame, modern phones/cars, rain-slick Blade Runner Hong Kong pastiche, bright noon desert tourism.

**HARD RULE — looking room (thirds):** Soft glance / attention direction locks subject placement on both the **21:9 master** and the **1:1 card** — do not center a directional subject and “fix it in crop.”

| Soft look / attention | Character **vertical midline** sits on | Looking room |
|-----------------------|----------------------------------------|--------------|
| **Right** (viewer's right) | **Left 1/3 mark** (`x ≈ W/3`) | Right two-thirds |
| **Left** (viewer's left) | **Right 1/3 mark** (`x ≈ 2W/3`) | Left two-thirds |
| **Camera** (near eye contact) | Center (or slight `camera-left` / `camera-right` bias) | Balanced |

**Midline, not packed column / not outer shoulder:** the figure’s **vertical midline** (center of head+torso) lands **on** the thirds divider (±2% of frame width) — **not** the outer shoulder, outer arm, or silhouette edge. Flush-packing so a shoulder sits on 1/3 while half the body is cropped off is wrong. Compose the master with this lock first. Card crop must be **measured** so the midline stays on the card’s 1/3 / 2/3 mark (`--subject-frac` = true head+torso center on the master, not leftmost pixel). Prop-bias shifts can pull midline off thirds or amputate the outer shoulder — re-check after bias. Packing the looker flush against the side they face is wrong.

**HARD RULE — soft natural gaze:** Looking room is composition, not a painful neck twist. Default body/face **mostly forward / toward camera** with eyes or a slight (~10–20°) head turn into the empty third. **Do not** default to hard over-the-shoulder profiles or chin-to-shoulder stares. Prefer `facing mostly toward camera, soft glance right` over `looks hard over her shoulder`.

**HARD RULE — hero props in the card:** If the beat depends on a prop (napkin ledger, velvet rope, folio, crate, phone/invoices), that prop (and the hand holding it) must remain fully readable in the **1:1 card**, not only on the 21:9 master. Prefer widen/bias the crop toward the prop over regenerating.

**HARD RULE — bake gaze into SUBJECT:** Put final **soft** gaze intent in the first generate prompt. Fal `/edit` gaze turns (especially profile → toward camera) are unreliable; one edit attempt max, then regenerate with gaze baked in.

**Canonical tooling:** [`tools/repeatable/python/gen_quest_image.py`](../../../tools/repeatable/python/gen_quest_image.py) + [`quest_card_crop.py`](../../../tools/repeatable/python/quest_card_crop.py) (measured thirds + optional prop bias). See skill `vbn-quest-images`.

---

## 6. Content Rules (quest-specific)  

- Key to live **`quests.slug`** and design doc beat — no generic “vampire club” filler.  
- Spoilers: prefer **hook/atmosphere** over end-state spoilers on the default card unless ST asks for a climax still.  
- Masquerade: no obvious Discipline fireworks as hero subject.  
- Align location truth with Part III / Supabase `locations` when the quest is place-locked.  
- Align cast likeness with Part I when characters are named in SUBJECT.
- **Documents / napkins:** prefer **illegible** ink by default; readable text only when ST explicitly wants it (wrong names drift easily).
- **On-disk portraits without a DB row** are valid identity refs when the file exists under `uploads/characters/` and ST confirms the cast.

---

## 7. Technical Rules & Deploy Path  

- **Canonical card path:** `uploads/quests/<slug>.png` (also `.jpg` / `.webp` per resolver)  
- **Resolver:** `agents/quest_agent/view_quest_api.php` — filesystem convention; **no** `quests.image` DB column  
- **Staging:** `images-generated/` (or dated subfolders) until ST approval  
- **Approval:** do not overwrite an approved card without versioning (`_v2`) unless ST orders replace  
- **Naming:** slug must match live `quests.slug` exactly (hyphens)

---

## 8. Prompt Templates  

### 8.1 Locked positive template (canonical)

```
[SUBJECT], seen at street level.

STYLE BLOCK (do not modify):
Shot in the style of Blade Runner 1982, relocated to Phoenix,
Arizona in 1994. Deep night in the desert. The air is dry and
hot and thick with dust and smog, so every light source bleeds
into a visible halo and distant buildings dissolve into haze.
Heat still rises off the asphalt hours after dark. The city is
low and sprawling rather than tall — stucco, cinderblock, and
sun-bleached adobe, flat roofs, exposed swamp coolers, chain
link, dead palms, and desert scrub pushing in at the edges of
every lot. Signage is period 1994: painted metal, backlit
plastic, and neon tubing, some of it burned out. Sodium vapor
street lamps throw amber pools onto cracked concrete. The sky
above is enormous, starless, and lit orange from below by the
city. Nothing is wet and nothing is clean.

TECHNICAL BLOCK (do not modify):
Anamorphic 2.39:1 framing, 40mm, shallow depth of field,
horizontal blue lens flare streaks, halation and bloom on every
practical light, 35mm film grain, deep crushed blacks, amber
sodium against cold blue shadow, smoke and dust diffusing the
key light, hard sidelight, low camera angle.
```

For interiors, the first line may become:  
`[SUBJECT], seen from the service-hall doorway.`  
(or equivalent) — **STYLE** and **TECHNICAL** unchanged.

### 8.2 Subject examples  

**Exterior:**  
`The Wash Behind the Lights after a flash flood, a courier wreck in the channel, seen at street level.`  
(Grade + integration against **official exterior look** `images-generated/quest_exterior_official_look.png`.)

**Interior:**  
`Neon Mass bar rail at last call, empty dancefloor beyond, seen from the rail.`  
(Grade + composition against **official interior look** `images-generated/quest_interior_official_look.png`.)

**Character:**  
`Lina Reséndez at the Coyote Corner lot after last call, Neon Mass neon soft in the haze, seen at street level.`

### 8.3 Negative Prompt  

```
rain, wet streets, monsoon gloss, Hong Kong skyline, dense megacity towers, cyberpunk chrome overload,
daylight tourism, blue sky, clean modern Phoenix, post-2000 cars and phones, UI overlays, text watermarks,
poster composition, key art, splash art, symmetrical vanity portrait, magazine cover layout, illustration layout,
cartoon, anime, exaggerated comic emotion, bright smiles, oversaturated neon candy, lens dirt as clutter,
gore spectacle as hero subject, obvious Discipline FX fireworks
```

Optional when character-forward (append Part I drift ban):  
`symmetrical portrait, glamour-editorial cover framing`

---

## 9. Integration Notes  

| System | Relationship |
|--------|----------------|
| Part I Portrait | Cast likeness / identity; do not replace quest still with a headshot crop unless ST wants portrait-as-card |
| Part II Cinematic | Shared noir grade and film still language; quest image = **one** still, not a sequence |
| Part III Location | Place truth for exteriors/interiors; prefer live location description |
| Part VII Marketing | Quest cards may feed marketing grids; marketing may heighten, quest cards stay grounded |
| Part IX Naming | `uploads/quests/<slug>.*` |
| Part XI Items | Quest MacGuffins as **supporting** props in frame only unless the quest is object-forward |
| Quest agent | Catalog/dialogue unchanged; image is filesystem sidecar to slug |

**Conflict rule:** If STYLE/TECHNICAL here conflict with a generic location exterior prompt, **Part XIII wins for quest-image deliverables**. Part III still wins for the official location exterior/blueprint/moodboard triple.

---

## 10. Example Outputs  

(Described by SUBJECT class — generate against locked blocks; review as film still, then crop to card.)

| Class | Official / exemplar still |
|-------|---------------------------|
| **Interior** | `images-generated/quest_interior_official_look.png` (= WoG Aftermath master) — **canonical look** for all interior quest images |
| **Exterior / exterior-hybrid** | `images-generated/quest_exterior_official_look.png` (= Foreign Blood Hunt v7 master, ST curve + desat) — **canonical look** for exterior quest images |
| Character-in-frame (exterior) | Portrait-lock + **official exterior look** ref + location exterior when place-locked |

---
