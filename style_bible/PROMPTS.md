# vbn-game Art Bible - Prompt Templates

This document provides an index and guide to all reusable prompt templates in the Art Bible.

**In this Unreal repo:** all chapters live **in this same folder** as `PROMPTS.md` (flat `style_bible/`). Paths below say `docs/` for upstream naming — open the matching `Art_Bible_*.md` file here.

## Prompt Template Locations

### Portrait System Prompts
**Location**: `Art_Bible_I_PORTRAIT_SYSTEM__.md` (Section 9)

Includes:
- Positive prompt template
- Negative prompt template
- Clan-specific prompt modules

### Cinematic System Prompts
**Location**: `Art_Bible_II_CINEMATIC_SYSTEM__.md` (Section 13)

Includes:
- Master cinematic prompt
- Negative prompt
- Shot-type templates
- Lighting modules
- Mood templates + seasonal beats (§9b)

### Location & Architecture Prompts
**Location**: `Art_Bible_III_LOCATION_&_ARCHITECTURE_SYSTEM__.md` (Section 9)

Includes:
- Master environment prompt
- Negative environment prompt
- Architectural modules
- Clan-specific modules
- Lighting modules

### 3D Asset System Prompts
**Location**: `Art_Bible_IV_3D_ASSET_SYSTEM__.md` (Section 12)

Includes:
- Character generation prompts
- Prop creation prompts
- Texture generation prompts
- Era-accurate asset prompts

### UI & Web Art Prompts
**Location**: `Art_Bible_V_UI_&_WEB_ART_SYSTEM__.md` (Section 10)

Includes:
- Master UI prompt
- Clan glyph prompt
- Interface element prompts

### Storyboard & Animatic Prompts
**Location**: `Art_Bible_VIb_STORYBOARD_PROMPT_TEMPLATES__.md` (Part 06b; overview in Part VI §11)

Includes:
- Master storyboard prompt
- Negative prompt
- Shot composition prompts

### Marketing Materials Prompts
**Location**: `Art_Bible_VII_MARKETING_MATERIALS_SYSTEM__.md` (Section 9)

Includes:
- Character poster prompt
- Location poster prompt
- Social banner prompt
- Announcement card prompts

### Floorplan & Blueprint Prompts
**Location**: `Art_Bible_VIII_FLOORPLAN_&_BLUEPRINT_SYSTEM__.md` (Section 11)

Includes:
- Master blueprint prompt
- Parchment blueprint prompt
- Architectural detail prompts

### Quest Images Prompts
**Location**: `Art_Bible_XIII_QUEST_IMAGES_SYSTEM__.md` (Section 8)

**Canonical structure**: `[SUBJECT], seen at street level.` + locked STYLE BLOCK + locked TECHNICAL BLOCK (do not modify). Interior subjects may replace only the “seen at…” clause. Negatives in Part XIII §8.3.

Includes:
- Exterior / interior / character-in-frame SUBJECT patterns
- Locked STYLE + TECHNICAL blocks
- Quest-card negative prompt

## Core Prompt Elements

All prompts should include these core elements:

### Style Keywords
- `gothic-noir`
- `Phoenix 1994`
- `desert modern`
- `cinematic lighting`
- `moody atmosphere`
- `period-accurate`

### Color Palette References
- `Gothic Black (#0d0606)`
- `Dusk Brown-Black (#1a0f0f)`
- `Blood Red (#8B0000)`
- `Parchment Light (#f5e6d3)`
- `Muted Gold (#d4b06d)`
- `Teal Moonlight (#0B3C49)`
- `Desert Amber (#C87B3E)`

### Lighting Keywords
- `warm candlelight`
- `sodium amber streetlights`
- `teal moonlight`
- `directional lighting`
- `deep shadows`
- `soft rim light`
- `no harsh specular`

### Emotional Tone Keywords
- `restrained emotion`
- `hidden danger`
- `noir tension`
- `introspection`
- `slow-burning menace`
- `predatory stillness`

### Technical Specifications
- `1024×1024` (portraits)
- `1920×1080` (cinematics)
- `PNG or WEBP format`
- `no compression artifacts`
- `film grain`
- `cinematic depth of field`

## Negative Prompt Elements

All negative prompts should exclude:

- `bright smiles`
- `exaggerated cartoon emotion`
- `comedic expressions`
- `modern LED lighting`
- `flat, even lighting`
- `full daylight`
- `futuristic architecture`
- `clean, sterile visuals`
- `crowded streets`
- `slapstick`
- `high action`
- `superheroic movement`
- `compression artifacts`
- `plastic shine`
- `lacquered hair`
- `modern vehicles`
- `contemporary design`

## Clan-Specific Prompt Modules

### Toreador
- `soft bloom`
- `velvet textures`
- `warm candlelight`
- `satin materials`
- `elegant folds`

### Brujah
- `cracked concrete textures`
- `warm sodium lighting`
- `tougher shadows`
- `worn leather`
- `heavy denim`

### Gangrel
- `desert moonlight`
- `earthy tones`
- `slight feral hints (not literal)`
- `rugged outdoor wear`
- `moonlit ridges`

### Nosferatu
- `harsh industrial rim`
- `muted palette`
- `shadow concealment`
- `industrial rags`
- `patchwork clothing`

### Malkavian
- `fractured symmetry`
- `violet edge light`
- `subtle distortion`
- `dutch angle (cinematic only)`

### Ventrue
- `marble & gold accents`
- `businesslike demeanor`
- `cold-blue fill lighting`
- `clean business attire`

### Giovanni
- `grayscale candlelight`
- `Italian classic motifs`
- `dark wood`
- `stone floors`
- `old-world formal wear`

### Setite
- `red velvet`
- `gold serpents`
- `incense haze`
- `exotic and sensual materials`

## Prompt Construction Guidelines

### 1. Start with Core Style
Begin every prompt with the core aesthetic:
```
gothic-noir, Phoenix 1994, desert modern, cinematic lighting, moody atmosphere
```

### 2. Add Technical Specs
Include resolution, format, and quality requirements:
```
1024×1024, PNG format, no compression artifacts, film grain, cinematic depth of field
```

### 3. Include Lighting
Specify lighting requirements:
```
warm candlelight, soft rim light from upper-right, key light at 35-45°, deep shadows retain detail
```

### 4. Add Clan-Specific Elements
If applicable, include clan motifs:
```
[Toreador: soft bloom, velvet textures, warm candlelight]
```

### 5. Include Emotional Tone
Specify the emotional quality:
```
restrained emotion, hidden danger, noir tension, introspection, slow-burning menace
```

### 6. Add Negative Prompt
Always include a negative prompt excluding forbidden elements:
```
no bright smiles, no exaggerated cartoon emotion, no comedic expressions, no harsh digital specular, no modern LED lighting
```

## Example Prompt Structure

### Portrait Prompt Template
```
[Core Style] + [Resolution/Format] + [Lighting] + [Clan Motifs] + [Emotional Tone] + [Composition] + [Technical Quality]

Negative: [Forbidden Elements]
```

### Cinematic Prompt Template
```
[Core Style] + [Scene Length] + [Shot Structure] + [Lighting] + [Environment] + [Character Behavior] + [Color Grade] + [Technical Specs]

Negative: [Forbidden Elements]
```

### Location Prompt Template
```
[Core Style] + [Architectural Fusion] + [Location Category] + [Lighting] + [Textures/Props] + [Camera/Composition] + [Technical Specs]

Negative: [Forbidden Elements]
```

## Integration with Master Index

The Master Index (`Art_Bible_X_MASTER_INDEX_&_INTEGRATION_LAYER__.md`) includes a Master Prompt Integration Layer (Section 8) that provides unified prompt construction across all systems.

## Usage Notes

1. **Always reference the full chapter files** for complete, detailed prompts
2. **Combine modules** as needed for specific use cases
3. **Maintain consistency** across all generated art
4. **Update prompts** when Art Bible rules change
5. **Test prompts** and refine based on output quality
6. **Optional hero-exterior A/B (style-agent MCP):** after `getRules` and `getPrompts`, call **`getLilithHavenHeroStylePreset`** (dedicated tool, no args) to load the **delta-only** Lilith Haven addendum (warm/cool split, fog, depth, grade). Alternatively `listStylePresets` / `getStylePreset` with id `lilith_haven_hero`. It does not replace RULES.md; merge into location or cinematic prompts as needed. Files live under `docs/style_presets/`.

## Prompt Versioning

Prompts are versioned with the Art Bible. Current version: **1.0.0**

When prompts are updated:
- Update version number
- Document changes
- Update this index
- Notify all users

## For Full Prompts

See the individual `Art_Bible_*.md` chapter files in this folder for complete prompt templates with full expansions and variations.

