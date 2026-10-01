# Style preset: Quest exterior official look (delta)

## Graph

- Pack: [[agents/style_agent/README|Style Agent]]
- Chapter: [[agents/style_agent/docs/Art_Bible_XIII_QUEST_IMAGES_SYSTEM__|Part XIII Quest Images]]
- Index: [[agents/style_agent/INDEX|Art Bible index]]
- Skill: [[.cursor/skills/vbn-quest-images/SKILL|vbn-quest-images]]

## Purpose

**Canonical exterior / exterior-hybrid look** for Part XIII quest cards / quest stills. Derived from ST-approved **Foreign Blood Hunt** master after desaturation + curve pass — muted Phoenix 1994 wash-channel noir with dimmed practicals and integrated cast.

## Baseline (mandatory merge)

This file is **delta-only**. It does **not** replace Art Bible enforcement.

1. Load **`getRules`** and **`getPrompts`** (style-agent MCP) first.
2. Apply **Part XIII — Quest Images** locked STYLE + TECHNICAL blocks (`Art_Bible_XIII_QUEST_IMAGES_SYSTEM__.md`).
3. For place truth, still apply **Part III** location/exterior notes when the quest is site-locked.
4. **Append** the recipe below; pass the on-disk reference as fal / img2img **grading + integration reference** for exterior and exterior-hybrid quest generations (after portrait lock, with location exterior ref).

## Reference (on-disk)

Repo-relative (canonical): `images-generated/quest_exterior_official_look.png`  
Source master: `images-generated/wash_foreign_blood_hunt_quest_master_v7.png` (ST curve + desaturation pass on v6/v7 dim)  
Beat: `wash-foreign-blood-hunt` — Paris Giovanni, tux, Wash channel adjudication

## Visual recipe (from reference)

- **Grade:** **desaturated** palette — muted amber sodium, restrained orange sky glow, no candy-neon saturation.
- **Contrast:** **curved** — deep crushed blacks, controlled highlights on practicals (~33% dimmer than raw fal output); readable silhouette retained.
- **Integration:** subject and environment share **one photograph** — matching grain, shadow under feet, sodium grade on face and concrete; no pasted cutout look.
- **Atmosphere:** dry dust/smog haze; distant streetlight bloom soft, not blown out; faint horizontal blue anamorphic flare acceptable.
- **Place:** wash channel / cracked concrete / chain-link / low industrial Phoenix 1994 — not wet, not Hong Kong, not noon tourism.
- **Camera:** Part XIII TECHNICAL (anamorphic 2.39:1 master; 40mm; shallow DOF; low angle).

## Suggested prompt fragment (paste after SUBJECT + locked STYLE/TECHNICAL)

```text
Exterior quest grade (official look): match images-generated/quest_exterior_official_look.png — desaturated Phoenix 1994 noir, curved contrast with deep blacks and dimmed sodium practicals (~33% below raw bloom), muted amber sky glow, integrated subject shadow on concrete, dry haze, one unified film still, no oversaturated neon candy, no pasted composite look.
```

## Post-generation (ST-approved path)

When fal output is too hot/saturated, ST may apply desaturation + curve in editor on the master, then copy to `quest_exterior_official_look.png` only when establishing a new canonical grade. Day-to-day quest gens should **match** this file, not re-derive from raw fal defaults.

**MCP:** `getStylePreset` with id **`quest_exterior_official_look`**. Skill: `.cursor/skills/vbn-quest-images/SKILL.md`.
