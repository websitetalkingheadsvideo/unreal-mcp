# Style preset: Blueprint — tactical aged (delta)

## Graph

- Pack: [[agents/style_agent/README|Style Agent]]
- Catalog: [[agents/style_agent/docs/blueprint_reference_catalog|Blueprint reference catalog]]
- Chapter: [[agents/style_agent/docs/Art_Bible_VIII_FLOORPLAN_&_BLUEPRINT_SYSTEM__|Part VIII Floorplan]]
- Index: [[agents/style_agent/INDEX|Art Bible index]]

## Preset id

`blueprint_tactical_aged`

## Purpose

Strip retail, markets, industrial yards, nightclubs — **surveillance and service-access** readability on aged parchment with blood-red tactical accents.

## Baseline (mandatory merge)

1. Load **`getRules`**, **`getPrompts`**, and **`getChapter`** `Art_Bible_VIII_FLOORPLAN_&_BLUEPRINT_SYSTEM__.md`.
2. Append this delta to the blueprint positive prompt after location layout rules.

## Reference (on-disk)

Primary: `agents/style_agent/reference_images/blueprints/desert_star_market_blueprint.png`

## Visual recipe

- **Sheet:** aged cream parchment `#f5e6d3`, slight yellowing and foxing, hand-drawn ink feel.
- **Structure:** charcoal/sepia linework; exterior walls heaviest; interior walls medium.
- **Accents:** blood-red `#8B0000` for security paths, surveillance cones, high-interest labels (dashed red overlays).
- **Annotations:** ALL CAPS sans-serif room labels; compass rose optional; one north arrow + scale bar.
- **Mood:** quiet menace — overnight security, hidden stash, surveillance zones without turning plan into illustration.

## Positive fragment

```text
Top-down architectural floor plan on aged cream parchment paper, hand-drawn charcoal and sepia ink lines, slight yellowing and foxing, tactical annotation style. Blood-red dashed overlays for security paths and surveillance zones only. Elongated strip-retail interior: open front sales floor or parallel aisles along long walls — NOT four corner rooms or empty center. Compass rose optional. Maximum 8 ALL CAPS room labels. One north arrow and one scale bar. Printed plan-sheet document, not painterly illustration.
```

## Negative fragment

```text
color photograph, 3D render, isometric perspective, white sterile CAD background, bright blue lines, neon outlines, furniture photoreal detail, moodboard collage, cinematic exterior perspective, heavy grunge obscuring walls
```
