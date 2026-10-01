# PART VIb — STORYBOARD PROMPT TEMPLATES
## (Part 06b — image-gen prompt library for Part VI boards)

*vbn-game · Phoenix 1994 · Laws of the Night Revised · grayscale charcoal storyboards only*

Use with [Art_Bible_VI_STORYBOARDS_&_ANIMATICS__.md](Art_Bible_VI_STORYBOARDS_&_ANIMATICS__.md).  
Compliant reference board: `reference/Scenes/Character Teasers/Storyboards/scn_character_teasers_butch_and_brutis.md`.  
Helena lab keyframe = Part II cinematic still — **not** a Part VI board.

---

## 1. Master storyboard panel prompt

```
grayscale charcoal storyboard panel, Phoenix 1994 gothic-noir, rough graphite line weight,
80% dark values, 15% mid-tone, 5% white highlights, thick silhouette outlines,
1920x1080, single cinematic frame, film storyboard composition, dust haze, soft vignette,
mild grain, no color, no photoreal polish, no 3D render look,
{SHOT_TYPE} shot, {LENS} lens equivalent framing,
{ACTION},
camera movement: {CAMERA_ARROW},
lighting: {LIGHTING_CUE},
{mood_module}
```

## 2. Master negative prompt

```
color, full color, watercolor wash, painted color, photorealistic, 3D CGI, Unreal Engine,
anime, cartoon, bright daylight, flat even lighting, modern LED, clean sterile,
handheld shake, whip pan, slapstick, exaggerated cartoon emotion, bright smiles,
compression artifacts, plastic shine, text overlay, watermark, panel borders in-image,
multiple panels in one image, speech bubbles, UI chrome
```

## 3. Shot-type modules

| Code | Module fragment |
| --- | --- |
| EST | wide establishing composition, environment dominates frame, sparse human presence, skyline or architecture sets tone |
| WIDE | environment context shot, figures small in frame, negative space, slow readable staging |
| MCU | medium close-up, face and upper torso, dialogue-ready framing, emotional beat readable |
| CU | close-up, symbolic detail or eye reaction, shallow depth emphasis, object or face fills frame |
| OTS | over-the-shoulder composition, confrontation or surveillance geometry, foreground shoulder soft |
| INSERT | insert detail shot, prop or symbolic object isolated, hands or object primary subject |
| DUTCH | dutch angle 8–12 degrees, disorientation, Malkavian fracture only |

## 4. Lens modules

| Lens | Use |
| --- | --- |
| 35mm | EST, WIDE, closing pull-back |
| 50mm | MCU, OTS, dialogue, emotional beat |
| 85mm | CU, INSERT, supernatural eye beat |

## 5. Camera-arrow vocabulary

| Arrow | Meaning |
| --- | --- |
| → static hold | locked frame |
| ← push-in | slow dolly toward subject |
| → pull-back | slow dolly away |
| ↔ pan | slow horizontal pan |
| ↕ rack focus | focus shift between planes |
| ↗ track | lateral tracking move |

## 6. Lighting modules

| Module | Fragment |
| --- | --- |
| sodium_night | sodium amber streetlight key, deep shadow pools, teal sky rim, desert heat haze |
| noir_interior | warm practical key 35–45°, hard shadow falloff, cool fill from darkness, no fill blowout |
| institutional | flickering fluorescent overhead, sick green cast, offset shadows, institutional dread |
| desert_moon | teal moonlight backlight, dust air bloom, warm ground bounce minimal |
| candle_elysium | candlelight warm right, marble shadow left, gold rim on silhouette |
| tiki_warm | warm amber tiki lamp key, carved wood mid-tones, sincere kitsch shadows |
| velvet_club | single warm amber spotlight, audience swallowed by black, crimson neon edge bleed |

## 7. Location modules

Append one when location is known from shot heading:

- **residential_phoenix** — low-slung 1994 Phoenix homes, chain-link, cracked concrete, oil-and-heat air
- **hawthorne_elysium** — Northern Scottsdale estate hall, marble, candle practicals, court formality
- **24th_street** — industrial sodium, teal moon, sparse foot traffic, Masquerade-safe emptiness
- **mesa_setite** — red velvet, gold serpent motif, incense haze, backroom theater
- **giovanni_compound** — dark wood, stone floor, grayscale candle, Italian classic restraint

## 8. Discipline hint modules (subtle only)

- **auspex** — pupil dilation, audio-wave distortion at frame edge, highlight shimmer
- **presence** — warm bloom intensifies, crowd hush implied, spotlight bends toward subject
- **obfuscate** — edge blur, reflection mismatch, one-frame true face in mirror
- **potence** — pressure without performance, knuckles blanch, object lands with absolute weight
- **animalism** — room stillness, small life absent, predator-read in animal posture

## 9. Mood modules

- **restrained_emotion** — introspective, predatory stillness, noir tension
- **working_class_kindred** — grease, keys, practiced calm, threat under domesticity
- **court_presentation** — etiquette pressure, Harpy gaze implied, neonate uncertainty
- **desert_menace** — slow-burning menace, hidden danger, 1994 Valley isolation

## 9b. Seasonal scene-prompt beats (Phoenix 1994)

Use as `{mood_module}` or descriptive `{ACTION}` filler when the chronicle calendar matches. One beat per season anchor; do not stack unless the scene is explicitly about weather.

**June 29 heat record (1994-06-29):** Arizona’s hottest day on record—128 °F at Lake Havasu, Phoenix still punishing after sundown. Storyboard and cinematic prompts should show **heat as a character**: asphalt radiating through sole leather, parking-lot mirages under sodium lamps, strip-mall AC units rattling in sync, characters’ shadows too crisp at midnight. Kindred move slower, speak shorter; blood seems thin. Wide shots: empty sidewalks, heat shimmer between low roofs; inserts: a wrist against a sun-warmed door frame, a cracked thermometer in a gas-station window. Lighting cue: `sodium_night` with extra haze; forbid cool relief unless the scene is haven-interior.

## 10. Assembly recipe (per panel)

1. Start **Master storyboard panel prompt** with `{SHOT_TYPE}`, `{LENS}`, `{ACTION}`, `{CAMERA_ARROW}`, `{LIGHTING_CUE}`, `{mood_module}` filled from board spec annotation.
2. Append one **location module** when heading names a known place.
3. Append one **discipline hint module** only when script beat requires it (never default).
4. Append **Negative prompt** block on a separate line prefixed `Negative:`.

## 11. Grid export note

Board **specs** (Prompt 3.1) are markdown annotation documents — one file per `scene_key`.  
Image-gen prompt **files** per panel are Prompt 3.2 (`generate_storyboard_prompts.php`).

---

*Part 06b · version 1.0.0 · pairs with Art Bible VI v1.0.0*
