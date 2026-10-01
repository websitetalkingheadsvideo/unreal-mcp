# Valley by Night — Unreal Engine Look Dev

**Document type:** Portable style contract for real-time cinematics (Unreal Engine)  
**Authority:** vbn-game Art Bible — distilled rules + Part II (Cinematic) + Part VI (Storyboards & Animatics) + Cinematic Intro Guide  
**Use:** Canonical **Unreal execution** contract for **VbN Videos**. On conflict with other docs here, **[RULES.md](RULES.md)** and full Art Bible chapters win; this file is the UE/MRQ distillation.

**Source files in this repo:**

- [RULES.md](RULES.md) — distilled mandatory rules (all media)
- [PROMPTS.md](PROMPTS.md) — prompt modules + construction (pair with Style Agent or offline lint)
- [Art_Bible_II_CINEMATIC_SYSTEM__.md](Art_Bible_II_CINEMATIC_SYSTEM__.md) — Part II (full)
- [Art_Bible_VI_STORYBOARDS_&_ANIMATICS__.md](Art_Bible_VI_STORYBOARDS_&_ANIMATICS__.md) — Part VI (previs)
- [Colors.md](Colors.md) — UI/badge palette (vbn-game web; not MRQ grade)
- MCP pack: [MCP_USER_GUIDE.md](MCP_USER_GUIDE.md), [MCP_QUICK_START.md](MCP_QUICK_START.md), [MCP_CURSOR_RULES_GENERATOR_TEMPLATE.md](MCP_CURSOR_RULES_GENERATOR_TEMPLATE.md)

**Also in `style_bible/`:** full Art Bible set, [Valley_by_Night_Cinematic_Intro_Guide.md](Valley_by_Night_Cinematic_Intro_Guide.md), [Art_Bible_VIb_STORYBOARD_PROMPT_TEMPLATES__.md](Art_Bible_VIb_STORYBOARD_PROMPT_TEMPLATES__.md), [style_presets/](style_presets/), [INDEX.md](INDEX.md) if present.

**Style Agent MCP (optional lint):** `getCinematicSystemChapter`, `getRules`, `composeStyleBrief`, `lintPromptAgainstStyle` with `workflow: cinematic`.

---

## North star

**Gothic–noir, Phoenix 1994, desert modern:** warm sodium/practical gold versus teal moon/shadow, low saturation, filmic contrast, slow camera, restrained performance. Not daylight comedy, not superhero VFX, not clean LED modernism.

---

## Master palette

Use for **Post Process Volume** grading and **light colors** on practicals and neons.

| Role | Hex | Unreal use |
|------|-----|------------|
| Gothic black / crush floor | `#0d0606` | Shadow tint, letterbox bars, sky/atmosphere base |
| Dusk brown-black | `#1a0f0f` | Interior ambient, dark fog albedo |
| Blood / crimson accent | `#8B0000` | Neon signs, restrained red grade |
| Parchment / ivory read | `#f5e6d3` | Skin highlight rolloff target (not blown white) |
| Muted gold | `#d4b06d` | Practical bulbs, Elysium warmth |
| Teal moonlight | `#0B3C49` | Fill, night exterior, split-tone cool side |
| Desert amber | `#C87B3E` | Street sodium, exterior warmth |

**Cinematic intro accents** (secondary): Deep Crimson `#7A1E1E`, Noir blue-black `#0D0E10`, Muted Gold `#B89B64`, Ivory `#F5F2E7`, Ash Gray `#2F2F2F`. Do not let these override the core seven.

### Color grade stack (Part II §6)

- **Contrast:** lifted blacks slightly (retain shadow detail), strong mids without clipping.
- **Split tone:** shadows → teal (`#0B3C49`); highlights → amber/gold (`#C87B3E` / `#d4b06d`).
- **Saturation:** global roughly −15% to −30%; localized saturation on neons/crimson only.
- **Vignette:** soft; on for cinematics.
- **Grain:** light film grain (composite or UE grain, sparing).
- **Haze:** subtle exponential fog / aerial perspective (desert dust, not horror smoke).

### Forbidden lighting

- Pure white LED
- Flat, even fill
- Full midday sun / bright daylight exteriors

---

## Lighting recipes

Directional, moody, low saturation, filmic. Prefer **in-scene practicals** (lamps, neons, CRT glow) over invisible sun.

| Beat | Key | Fill | Accents |
|------|-----|------|---------|
| Alley / 24th St | Sodium amber spot/street | Teal moon / skylight | Crimson neon |
| Camarilla Elysium | Warm gold practicals | Deep shadow, low ambient | Marble spec (controlled) |
| Giovanni | Candle warmth | Gray shadow | Low saturation overall |
| Setite / theater | Red velvet bounce | Hard spot | Incense haze |
| Desert ridge | Cool moon | Warm rim on silhouettes | Minimal fill |

### Location art direction

Fuse **Phoenix 1994**, **gothic noir**, **desert modern:**

- Textures: peeling paint, cracked walls, dusty floors, sand buildup, rusted metal
- Props: CRTs, rotary phones, paper files, 90s signage, chain-link, neon signs
- Architecture: concrete, glass, sparse vegetation — not futuristic or generic modern LED interiors

---

## Camera (Sequencer)

| Rule | Value |
|------|--------|
| Focal lengths | 35 mm, 50 mm, 85 mm only (ultra-wide mainly for establishing) |
| Movement | Slow dolly, slow pan, slight zoom |
| Forbidden | Handheld, shaky cam, whip pans, frenetic tracking |
| Dutch angle | Malkavian scenes only |
| Depth of field | Shallow to medium; eyes/faces as anchor on characters |
| Intro length | 30–60 s (ideal 45 s), **7–9 shots**, fade to black + title card |
| Emotional hold | ~4–6 s on MCU beats |

Ease in/out on all Sequencer moves; no snap cuts unless storyboard explicitly calls for them (forbidden motions still apply).

### Cinematic shot structure (Part II)

1. Establishing (EST)
2. Character reveal (MCU)
3. Insert / symbolic detail
4. Emotional beat (MCU/CU)
5. Secondary action or VO shift
6. Supernatural subtle moment
7. Closing shot
8. Fade to black → title card

---

## Characters and performance

- **Motion:** controlled gestures, predatory stillness, emotional restraint
- **Avoid:** slapstick, high action, superheroic movement
- **Expression:** no exaggerated cartoon emotion, no bright smiles
- **Conflict staging:** social/tension beats (LARP/table resolution), not FPS cover/chase staging unless the beat is explicitly physical and sourced

### Disciplines on screen (subtle only)

| Discipline | Cinematic read |
|------------|----------------|
| Auspex | audio distortion, pupil dilation, faint highlight glow |
| Presence | crowd silence, warm bloom |
| Obfuscate | edge blur, light distortion |
| Protean | shadow shapes, slight eye reflection change |
| Necromancy | candle dimming, vapor breath |

No full-body glow, no game-trailer power VFX.

### Clan lighting cues (when relevant)

- **Toreador:** soft bloom, velvet, warm candlelight
- **Brujah:** cracked concrete read, warm sodium, tougher shadows
- **Gangrel:** desert moonlight, earthy tones, slight feral hint (not literal monster)
- **Nosferatu:** harsh industrial rim, muted palette, shadow concealment
- **Malkavian:** fractured symmetry, violet edge, subtle distortion (Dutch angle allowed)
- **Ventrue:** marble/gold accents, cold-blue fill
- **Giovanni:** grayscale candlelight, classic motifs
- **Setite:** red velvet, gold accents, incense haze

---

## Audio (same identity as picture)

| Layer | Direction |
|-------|-----------|
| Ambient | Wind, AC hum, city murmur — subtle, rarely silent |
| Music | Slow jazz, low strings, soft synth pads |
| VO | Close, confessional; light reverb |
| SFX | Diegetic, minimal, sharp (footsteps, glass, cloth) |
| Silence | Before cuts or key lines |

---

## Unreal setup checklist

1. **Master Post Process Volume:** split tone, vignette, grain; expose for `#f5e6d3` highlights, not clip-white.
2. **Sky / atmosphere:** night or blue hour; avoid clear noon desert.
3. **Materials:** base desaturate ~10–20%; grime/dust on exteriors.
4. **Neon emissive:** crimson/gold — not candy-saturated cyan/purple.
5. **Export:** **1920×1080** (Art Bible cinematic pipeline).
6. **Script lint:** Style Agent `getRules` + `getPrompts`, then `lintPromptAgainstStyle` (`workflow: cinematic`); offline: compare prose to [PROMPTS.md](PROMPTS.md) negatives + negative block below.

---

## Negative prompt block (ban list)

Use for look-dev reviews, Sequencer notes, or generative fill plates:

```text
handheld, shaky cam, whip pan, dutch angle (except Malkavian),
full daylight, pure white LED, flat lighting, oversaturated neon,
slapstick, high action, superhero movement, exaggerated supernatural VFX,
modern 2020s streetwear, futuristic architecture, bright smiles,
cartoon emotion, lens dirt clutter, HDR halos, video-game render look,
anime, illustration, painterly brush strokes, glam beauty retouch
```

---

## Quick reference — core hex (copy/paste)

```text
Gothic Black      #0d0606
Dusk Brown-Black  #1a0f0f
Blood Red         #8B0000
Parchment Light   #f5e6d3
Muted Gold        #d4b06d
Teal Moonlight    #0B3C49
Desert Amber      #C87B3E
```

---

*Valley by Night — Unreal Engine Look Dev — derived from style_agent Art Bible. Not a replacement for RULES.md; on conflict, live Art Bible + RULES.md win.*
