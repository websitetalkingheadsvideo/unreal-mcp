# Style preset: Quest interior official look (delta)

## Graph

- Pack: [[agents/style_agent/README|Style Agent]]
- Chapter: [[agents/style_agent/docs/Art_Bible_XIII_QUEST_IMAGES_SYSTEM__|Part XIII Quest Images]]
- Index: [[agents/style_agent/INDEX|Art Bible index]]
- Skill: [[.cursor/skills/vbn-quest-images/SKILL|vbn-quest-images]]

## Purpose

**Canonical interior look** for Part XIII quest cards / quest stills. Derived from the Weight of Guilt Q4 Aftermath Halcyon empty-chair master — warm practicals, cool anamorphic flare, smoky Phoenix 1994 lounge noir.

## Baseline (mandatory merge)

This file is **delta-only**. It does **not** replace Art Bible enforcement.

1. Load **`getRules`** and **`getPrompts`** (style-agent MCP) first.
2. Apply **Part XIII — Quest Images** locked STYLE + TECHNICAL blocks (`Art_Bible_XIII_QUEST_IMAGES_SYSTEM__.md`).
3. For place truth, still apply **Part III** location/interior notes when the quest is site-locked.
4. **Append** the recipe below; pass the on-disk reference as fal / img2img grading ref for interior quest generations.

## Reference (on-disk)

Repo-relative (canonical): `images-generated/quest_interior_official_look.png`  
Source master: `images-generated/weight_of_guilt_aftermath_quest_master.png`  
Deployed card twin: `uploads/quests/weight-of-guilt-aftermath.png` (1:1 crop — use master for widescreen grade)

## Visual recipe (from reference)

- **Warm / cool split:** table / booth **warm amber practicals** vs **cold blue** anamorphic horizontal flare and shadow.
- **Atmosphere:** interior **smoke/haze**; every practical blooms; crushed blacks with retained silhouette.
- **Period interior:** brick, mid-century lounge furniture, **1994 neon** (Halcyon-style painted/neon tubing), no LED retail, no wet streets.
- **Emotional beat:** empty place-setting / unused chair / absence as subject — not a packed party collage.
- **Depth:** sharp foreground table/rail → soft patron bokeh → window or neon wall read.
- **Camera:** Part XIII TECHNICAL (anamorphic 2.39:1 master; 40mm; shallow DOF; low or rail-height interior clause).

## Suggested prompt fragment (paste after SUBJECT + locked STYLE/TECHNICAL)

```text
Interior quest grade (official look): Phoenix 1994 lounge noir matching images-generated/quest_interior_official_look.png — warm table-lamp practicals against cold blue anamorphic flare, smoky haze, brick and period neon, empty place-setting or unused chair as emotional beat, mid-century furniture, shallow DOF background patrons, crushed blacks, no European cathedral gothic, no wet Hong Kong, no packed Elysium collage.
```

**MCP:** `getStylePreset` with id **`quest_interior_official_look`**. Skill: `.cursor/skills/vbn-quest-images/SKILL.md`.
