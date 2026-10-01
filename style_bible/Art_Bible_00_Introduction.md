# PART 0 — INTRODUCTION  
## vbn-game Art Bible

This chapter orients artists, developers, writers, and **AI agents** to the vbn-game Art Bible: what it is, how the major parts fit together, and how to consume the pack without fighting the aesthetic.

---

## 1. Purpose and scope

The Art Bible is the **single visual and tonal contract** for *Valley by Night* (vbn-game): gothic–noir atmosphere, **Phoenix 1994** authenticity, and **emotional restraint** across portraits, cinematics, locations, UI, marketing, and supporting art pipelines.

It exists so that:

- Generated and hand-made art **stay in the same world**.
- Technical choices (resolution, palette, lens language, motion) **do not drift** between systems.
- Anyone onboarding—human or model—can find **authoritative** rules instead of improvising from memory.

This introduction does **not** replace the numbered parts (Portrait, Cinematic, Location, and so on). It frames them. For distilled constraints, use [`../RULES.md`](../RULES.md). For prompt scaffolding, use [`../PROMPTS.md`](../PROMPTS.md). For the compiled linear reference, see [`Valley_by_Night_Art_Bible_Master_Edition.md`](Valley_by_Night_Art_Bible_Master_Edition.md).

---

## 2. Unifying aesthetic

These principles appear again in every part; they are **non-optional** for vbn-game art direction:

| Pillar | Meaning |
|--------|--------|
| **Gothic–Noir** | Dark, moody, controlled; danger implied, not shouted. |
| **Phoenix 1994** | Period-accurate desert city texture: heat, dust, concrete and glass, sparse vegetation, credible night. |
| **Emotional restraint** | Subtle expressions, predatory stillness, introspection, slow-burning menace—not cartoon emotion or comedy beats. |
| **Desert Modern** | Environment and architecture vocabulary that belongs in the American Southwest urban fringe of the era. |

Mandatory palette anchors and do/don’t lists live in [`../RULES.md`](../RULES.md). When a detail is missing from this introduction, **the chapter for that system wins**—then Part X for cross-system integration.

---

## 3. How the major parts fit together

Part **X — Master Index & Integration** ([`Art_Bible_X_MASTER_INDEX_&_INTEGRATION_LAYER__.md`](Art_Bible_X_MASTER_INDEX_&_INTEGRATION_LAYER__.md)) is the glue: it defines how portrait, cinematic, location, 3D, UI, marketing, floorplans, naming, and items **must** line up (lighting continuity, palette inheritance, prop vocabulary, and so on).

At a high level:

- **Part I — Portrait** — Square character art, clan read, noir lighting, emotional anchors.
- **Part II — Cinematic** — Cutscenes and VO-driven sequences: pacing, lens, discipline subtlety.
- **Part III — Location & architecture** — Environments that read as Phoenix 1994 + gothic noir + desert modern.
- **Parts IV–IX** — 3D, UI, storyboards, marketing, floorplans, naming—each constrains a slice of production.
- **Part XI — Items** — Object art and UI presentation consistent with portraits and panels.
- **Part XII — Creative writing** — Voice, registers, and narrative craft aligned to the same tone map as visuals.
- **Part XIII — Quest Images** — Quest card / quest still art: locked Phoenix 1994 cinematic blocks; subject-only variation; deploy by `quests.slug`.

Use [`../INDEX.md`](../INDEX.md) for a **chapter → file → “use when”** quick reference. Use [`../indexes/Valley_by_Night_Art_Bible_Enhanced_Index.md`](../indexes/Valley_by_Night_Art_Bible_Enhanced_Index.md) for short summaries when you need orientation without opening every file.

---

## 4. Reading order (recommended)

1. **This introduction (Part 0)** — orientation.
2. **[`../RULES.md`](../RULES.md)** — hard constraints and palette (fast pass before any generation).
3. **Relevant numbered chapter(s)** in `docs/` for the asset class you are making (e.g. Part III for a location exterior).
4. **[`Art_Bible_X_MASTER_INDEX_&_INTEGRATION_LAYER__.md`](Art_Bible_X_MASTER_INDEX_&_INTEGRATION_LAYER__.md)** — when your asset touches more than one surface (e.g. portrait in UI modal inside a cinematic frame).

For **full** linear depth, the Master Edition aggregates the system in one file; for **day-to-day** work, prefer the split chapter files plus RULES/PROMPTS.

---

## 5. Style Agent MCP (machines and integrators)

The same pack powers the **style-agent** MCP in Cursor: it exposes tools to read rules, prompts, chapters, optional **delta style presets** under `docs/style_presets/`, and narrative refinement (`secondDraft`).

**Authoritative list of MCP tool names and purposes:** [`../README.md`](../README.md) (section *Cursor MCP tools*). That table is maintained with the server; **do not treat this Part 0 file as the live tool registry**—it would drift.

**Default workflow for image-style work:** load distilled constraints first (`getRules`, `getPrompts`), then pull the relevant **Art Bible chapter** (generic `getChapter` or a named chapter tool if your client exposes one), then apply any **delta preset** only as an add-on (presets do not replace `RULES.md`). For prose refinement, use `secondDraft` with its required fields and schema.

When the MCP is unavailable, read [`../RULES.md`](../RULES.md) and [`../PROMPTS.md`](../PROMPTS.md) from disk the same way the server would.

---

## 6. What this introduction does not do

- It does not list every technical limit (aspect ratios, shot counts, lens sets)—those live in the **numbered parts** and in **RULES**.
- It does not duplicate **laws** or **game mechanics** adjudication; the Art Bible governs **look, feel, and craft** of art and writing tone, not table rules.
- It does not replace **Part X** for integration matrices—see Part X when systems intersect.

---

## 7. Document status

This file (`Art_Bible_00_Introduction.md`) is the canonical **Part 0** chapter referenced by [`../INDEX.md`](../INDEX.md) and the Valley_by_Night Art Bible indexes. It was **authored to close a packaging gap**: the indexes and MCP onboarding docs cited this path before the file existed in `docs/`.

**Current game version** (elsewhere in the repo) always lives in [`../../includes/version.php`](../../includes/version.php) as `VBN_GAME_VERSION`—use that when you need “what release is this checkout,” not when you need “when did Part 0 land.”

- **Part 0 introduced at game version:** `0.9.345` — **fixed milestone** when this file was added to `docs/`. It is **not** updated to track every later bump of `VBN_GAME_VERSION`; that would read like this chapter was rewritten each release. If you ever make a **major** revision worth re-stamping, change this line deliberately and note it in commit history.

If the MCP surface or chapter set changes materially, update **[`../README.md`](../README.md)** first, then adjust this introduction only when the **conceptual** onboarding story changes—not for every new tool name.

---

*End of Part 0 — Introduction*
