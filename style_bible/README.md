# VbN style bible — document map (Unreal repo)

Offline copy of **vbn-game** `style_agent` docs (live MCP + PHP server stays on `amber`). Sync from `\\amber\htdocs\agents\style_agent` when Art Bible changes.

## Authority order (VbN Videos / UE)

1. **[RULES.md](RULES.md)** — mandatory distilled rules; wins on conflict.
2. **[PROMPTS.md](PROMPTS.md)** + **Art Bible chapters** (this folder).
3. **[VbN_Unreal_Engine_LookDev.md](VbN_Unreal_Engine_LookDev.md)** — Unreal/MRQ/Sequencer execution.
4. **[Valley_by_Night_Cinematic_Intro_Guide.md](Valley_by_Night_Cinematic_Intro_Guide.md)** — intro-specific beats when doing 30–60s openers.

Optional: **[Art_Bible_X_MASTER_INDEX_&_INTEGRATION_LAYER__.md](Art_Bible_X_MASTER_INDEX_&_INTEGRATION_LAYER__.md)** + **[INDEX.md](INDEX.md)** for navigation.

## VbN Videos — read first

| Doc | Use |
|-----|-----|
| `RULES.md` / `PROMPTS.md` | Law + prompt modules |
| `VbN_Unreal_Engine_LookDev.md` | PPV, lighting recipes, Sequencer, MRQ 1080p |
| `Art_Bible_II_*` + `Art_Bible_VI*` + `Art_Bible_VIb_*` | Cinematic + storyboard + prompt templates |
| `Art_Bible_III_*` + `Location_Style_Guide.md` + `Room_Style_Guide.md` | Sets / Phoenix 1994 spaces |
| `Art_Bible_I_*` | Portraits / character stills (MetaHuman refs) |
| `Art_Bible_IV_*` | 3D import (CC5, textures, era props) |
| `style_presets/` | Delta presets (e.g. Lilith Haven hero exterior) |

## Lower priority for UE video

Quest images (XIII), UI (V), marketing (VII), floorplans (VIII), creative writing (XII), blueprint QA catalogs — unless that shot needs them.

## Pipeline

Storyboard (VI, grayscale) → animatic → UE env/lighting (III + LookDev) → Sequencer → MRQ **1920×1080** → grain/vignette in-engine or post (Part II §14).

## MCP

**Style Agent** (Cursor): point MCP at amber `server.php`. **Unreal Editor**: ModelContextProtocol plugin — separate. Offline: read files in this folder.

## Optional upstream (not copied)

`reference_images/`, `indexes/Valley_by_Night_Art_Bible_Enhanced_Index.md`, `server.php`, `src/` — remain on amber.
