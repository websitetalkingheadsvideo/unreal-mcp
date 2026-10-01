# Style preset: Blueprint — parchment residential (delta)

## Graph

- Pack: [[agents/style_agent/README|Style Agent]]
- Catalog: [[agents/style_agent/docs/blueprint_reference_catalog|Blueprint reference catalog]]
- Chapter: [[agents/style_agent/docs/Art_Bible_VIII_FLOORPLAN_&_BLUEPRINT_SYSTEM__|Part VIII Floorplan]]
- Index: [[agents/style_agent/INDEX|Art Bible index]]

## Preset id

`blueprint_parchment_residential`

## Purpose

Havens, lofts, apartments, hotel suites — **lived-in domestic** plans on warm parchment with burgundy zones and gold dimension lines.

## Baseline (mandatory merge)

1. Load **`getRules`**, **`getPrompts`**, and **`getChapter`** `Art_Bible_VIII_FLOORPLAN_&_BLUEPRINT_SYSTEM__.md`.
2. Append this delta after interior-only or residential layout hints.

## Reference (on-disk)

Primary: `agents/style_agent/reference_images/blueprints/roosevelt_row_artists_loft_blueprint.png`

## Visual recipe

- **Sheet:** warm parchment with optional deckled/torn edge; subtle vignette at margins.
- **Structure:** black ink; wall cross-hatching on heavy masonry; thin dimension ticks.
- **Accents:** burgundy `#722F37` for seating/sleep zones; pale gold `#d4b06d` for dimension lines and highlight labels.
- **Materials:** stipple/hatch for exposed brick, polished concrete, heavy curtains (labeled, not illustrated).
- **Annotations:** ALL CAPS labels with leader lines; dimension strings in feet-inches.

## Positive fragment

```text
Crisp architectural floor plan on warm aged parchment, black technical ink, optional deckled paper edge. Burgundy velvet zones for seating and sleep alcoves. Pale gold dimension lines and highlight labels. Material hatching for brick and concrete. ALL CAPS room labels with leader lines. One north arrow and scale bar. Residential loft or haven interior, not suburban house sprawl.
```

## Negative fragment

```text
color photograph, 3D render, isometric perspective, bright blue CAD, neon, tactical red security overlays, mansion cross plan, dozen bedroom corners, white sterile background, moodboard collage
```
