# Moodboard reference example (canonical)

**ST lock:** 2026-08-13  
**Location:** Biltmore Partnership Desk (`locations.id` **156**)  
**Deployed asset:** [`uploads/locations/moodboard/biltmore_partnership_desk.png`](../../../uploads/locations/moodboard/biltmore_partnership_desk.png)  
**Backend:** fal.ai `fal-ai/nano-banana-2` · square 1:1

Prior example (superseded): Camelback Colonial Garage (`locations.id` **145**) `camelback_colonial_garage_moodboard.png` — keep on disk; do not treat as the bar.

## What “good” means

A vbn-game location moodboard’s job is to answer: **what materials, light, and surface grit belong in this place?**

The Biltmore Partnership Desk board is the **gold standard** because it is a **texture / materials / lighting reference grid**, not a façade hero and not a story corkboard. Corkboards remain valid when the ST wants taped ephemera; they are **not** the default bar for “real moodboard.”

## Prompt pattern that produced it

Square 1:1 moodboard collage only — materials light and texture for the location. NOT a building exterior photo, NOT a floor plan. Grid collage of location-specific swatches (frosted storefront glass, reception-desk laminate, map paper, press-kit folder stock, brass handle, beige commercial carpet, fluorescent glow, muted gold fascia trim). Gothic noir Desert Modern palette. No people, no readable logos, no cars as hero subjects, no watermark.

## Agent wiring

- Workflow prompt: [`agents/style_agent/prompts/mcp_workflows/location_moodboard_pass.md`](../prompts/mcp_workflows/location_moodboard_pass.md)
- Cursor rule: [`.cursor/rules/vbn-location-moodboard.mdc`](../../../.cursor/rules/vbn-location-moodboard.mdc)
- Pipeline skill: [`.cursor/skills/vbn-location-images/SKILL.md`](../../../.cursor/skills/vbn-location-images/SKILL.md)
- Art Bible III §11: [`Art_Bible_III_LOCATION_&_ARCHITECTURE_SYSTEM__.md`](Art_Bible_III_LOCATION_&_ARCHITECTURE_SYSTEM__.md)
