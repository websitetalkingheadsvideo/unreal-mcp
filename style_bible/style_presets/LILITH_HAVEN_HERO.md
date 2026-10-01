# Style preset: Lilith Haven hero exterior (delta)

## Graph

- Pack: [[agents/style_agent/README|Style Agent]]
- Chapter: [[agents/style_agent/docs/Art_Bible_III_LOCATION_&_ARCHITECTURE_SYSTEM__|Part III Location]]
- Guide: [[agents/style_agent/docs/Location_Style_Guide|Location Style Guide]]
- Index: [[agents/style_agent/INDEX|Art Bible index]]

## Purpose

Optional **hero-grade exterior** look: prestige horror / cinematic still energy for **key location frames** or A/B comparisons against the default VbN location stack. Derived from the lighting and staging grammar of the reference still—not from copying a Victorian mansion when your subject is a strip, trailer park, or warehouse.

## Baseline (mandatory merge)

This file is **delta-only**. It does **not** replace Art Bible enforcement.

1. Load **`getRules`** and **`getPrompts`** (style-agent MCP) first.
2. For environments, still apply **Part III — Location & Architecture** (`Art_Bible_III_LOCATION_&_ARCHITECTURE_SYSTEM__.md`) and Phoenix 1994 / gothic-noir / desert-modern constraints from RULES.
3. **Append** the sections below to your final image prompt (or merge into your cinematography notes). If the reference’s distant skyline or polish would break a given beat (e.g. east-fringe dirt realism), use **only** the lighting/composition/grade lines, not every clause.

## Reference (on-disk)

Repo-relative: `uploads/locations/exterior/lilith_haven.png`  
Use as **grading and atmosphere reference**; for Lovart / Firefly / img2img pipelines, upload the image separately where the tool requires an HTTPS URL.

## Visual recipe (from reference)

- **Warm / cool split:** strong **warm practicals** from architecture (window leak, porch/interior glow) vs **cool exterior** fill (moon/teal in shadow, cooler street pool). Sodium or white street lamp acceptable if it reads **1990s**, not LED retail.
- **Layered depth (back to front):** far silhouette / sky read → mid subject mass → **barrier** (iron, wall, or chain-link) → **street/foreground** with **one** period vehicle or empty asphalt—restraint beats clutter.
- **Atmosphere:** **low ground fog** or haze hugging the curb and fence line; occlusion without extra props.
- **Grade:** high but **controlled** contrast; **muted** global saturation; **subtle film grain**; shadow areas retain detail (no crushed black mud).
- **Era:** **1980s–1994** vehicles and props only; avoid readable modern signage; no on-image text.

**Non-mansion locations:** keep this block as **lighting + depth + grade**; swap the “mansion” subject in the reference for your actual geometry (mobile home rows, strip mall, hospital) while preserving the recipe above.

## Suggested prompt fragment (paste after your location prompt)

```text
Hero exterior grade (Lilith Haven delta): cinematic photoreal, strong warm window and interior leak against cool blue-teal shadows; low ground fog along fence and curb; layered depth from street foreground through barrier into subject and distant silhouettes; controlled contrast, muted saturation, subtle 35mm film grain, shadow detail preserved; single period vehicle or empty road; 1990s practical street lighting only; no readable text or logos; prestige horror still, not illustration.
```

**MCP:** dedicated tool **`getLilithHavenHeroStylePreset`** (no arguments) after baseline `getRules` + `getPrompts`. **Preset id** for generic `getStylePreset`: `lilith_haven_hero`.
