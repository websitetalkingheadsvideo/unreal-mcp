# Blueprint reference catalog

## Graph

- Pack: [[agents/style_agent/README|Style Agent]]
- Chapter: [[agents/style_agent/docs/Art_Bible_VIII_FLOORPLAN_&_BLUEPRINT_SYSTEM__|Part VIII Floorplan]]
- Preset: [[agents/style_agent/docs/style_presets/blueprint_tactical_aged|blueprint_tactical_aged]]
- Preset: [[agents/style_agent/docs/style_presets/blueprint_parchment_residential|blueprint_parchment_residential]]
- Preset: [[agents/style_agent/docs/style_presets/blueprint_chantry_formal|blueprint_chantry_formal]]
- Preset: [[agents/style_agent/docs/style_presets/blueprint_noir_occult|blueprint_noir_occult]]

Curated floor-plan references for vbn-game **Modern Gothic** blueprint generation. Each file has exactly one **role** and (when applicable) one **family**.

**Families:** `tactical_aged` | `parchment_residential` | `chantry_formal` | `noir_occult`

**Roles:** `primary` (mood + palette target) | `layout_grammar` (symbols/dimensions only) | `anti_pattern` (negative prompt only) | `production_primary` (shipped game asset used as family anchor)

---

## Shared visual language (all on-brand blueprints)

| Attribute | Observable pattern |
|-----------|-------------------|
| Projection | Strict top-down orthographic; no perspective, isometric, or 3D render |
| Line hierarchy | Exterior walls thickest; interior medium; doors/windows/fixtures thin; dashed for hidden/service |
| Readability | ≤8 room labels, ALL CAPS, 1–3 words; one north arrow + one scale bar |
| Framing | Plan centered on sheet; optional double-line border; title block at top |
| Symbols | Door swing arcs; window breaks; stair UP/DN; service easement hatched ≠ street frontage |
| Texture | Paper grain / light foxing on sheet; subtle edge vignette; no grunge over room boundaries |
| Gothic mood | Archival secret-document feel; selective accent color; tactical/occult labels imply menace without illustration |

---

## Catalog table

| Path | Family | Role | Notes |
|------|--------|------|-------|
| `agents/style_agent/reference_images/blueprints/desert_star_market_blueprint.png` | `tactical_aged` | `primary` | Aged cream parchment, charcoal ink, blood-red tactical overlays, compass rose |
| `agents/style_agent/reference_images/blueprints/roosevelt_row_artists_loft_blueprint.png` | `parchment_residential` | `primary` | Deckled parchment, burgundy zones, gold dimension lines, material hatching |
| `uploads/locations/blueprint/Tremere Chantry-Floor Plan.jpg` | `chantry_formal` | `production_primary` | Navy ink on cream, serif titles, faint grid, double border |
| `uploads/locations/blueprint/eye_of_the_nile_imports_curiosities_blueprint.png` | `noir_occult` | `production_primary` | High-contrast B&W, grain, occult glyphs, strip-mall geometry |
| `uploads/locations/blueprint/desert_star_market_blueprint.png` | `tactical_aged` | `production_primary` | Shipped twin of reference folder tactical primary |
| `uploads/locations/blueprint/roosevelt_row_artists_loft_blueprint.png` | `parchment_residential` | `production_primary` | Shipped twin of reference folder residential primary |
| `agents/style_agent/reference_images/blueprints/architectural-floorplan-drawings-v0-4i9palsrl4d91.webp` | — | `layout_grammar` | Black on cream; wall hierarchy and dimension style only |
| `agents/style_agent/reference_images/blueprints/pdrw.webp` | — | `layout_grammar` | Clean B&W two-story; door symbols and dimension lists |
| `agents/style_agent/reference_images/blueprints/plan-top-house-sketch-hand-drawn_03.jpg` | — | `layout_grammar` | Hand-sketch layout grammar (optional) |
| `agents/style_agent/reference_images/blueprints/Floor+Plans.webp` | — | `layout_grammar` | Optional layout ref; convert to PNG if tooling fails |
| `agents/style_agent/reference_images/blueprints/blueprint-house-plan-design-architecture-home-drawing-structure-plan-vector-illustration_1284-47688.avif` | — | `layout_grammar` | Optional layout ref; convert to PNG if tooling fails |
| `agents/style_agent/reference_images/blueprints/images.jfif` | — | `anti_pattern` | Bright blue CAD, drop shadows, modern brochure — negatives only |

---

## Family → primary reference (generation pick order)

| Family ID | Primary path (first) | Layout grammar (second) |
|-----------|----------------------|-------------------------|
| `tactical_aged` | `agents/style_agent/reference_images/blueprints/desert_star_market_blueprint.png` | `agents/style_agent/reference_images/blueprints/architectural-floorplan-drawings-v0-4i9palsrl4d91.webp` |
| `parchment_residential` | `agents/style_agent/reference_images/blueprints/roosevelt_row_artists_loft_blueprint.png` | `agents/style_agent/reference_images/blueprints/pdrw.webp` |
| `chantry_formal` | `uploads/locations/blueprint/Tremere Chantry-Floor Plan.jpg` | `agents/style_agent/reference_images/blueprints/architectural-floorplan-drawings-v0-4i9palsrl4d91.webp` |
| `noir_occult` | `uploads/locations/blueprint/eye_of_the_nile_imports_curiosities_blueprint.png` | `agents/style_agent/reference_images/blueprints/architectural-floorplan-drawings-v0-4i9palsrl4d91.webp` |

---

## MCP / PHP

- **`listBlueprintReferences`** — returns rows from this catalog (scanned from disk + static metadata).
- **`getBlueprintStyleBrief`** — resolves family from location fields, loads preset markdown, returns paths + prompt blocks.
- Router: `includes/blueprint_style_family.php`

Preset ids: `blueprint_tactical_aged`, `blueprint_parchment_residential`, `blueprint_chantry_formal`, `blueprint_noir_occult` (files under `docs/style_presets/`).
