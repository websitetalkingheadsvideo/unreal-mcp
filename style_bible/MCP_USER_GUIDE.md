# Style Agent MCP — User guide

This pack exposes **vbn-game** visual style: Art Bible chapters, distilled `RULES.md` / `PROMPTS.md`, delta presets, and narrative `secondDraft` refinement.

## What you get

| Surface | Purpose |
|--------|---------|
| **Tools** | Pull files, search, compose briefs, lint prompts, load named chapters. |
| **Prompts** (`prompts/list`, `prompts/get`) | Instructional workflow text for the host model (no server-side LLM). |
| **Resources** (`resources/list`, `resources/read`) | Static guides and templates (this file and siblings) for humans and agents. |

## Merge order (image / location work)

1. **`getRules`** and **`getPrompts`** — non-negotiable baseline.
2. **Preset** — **`getLilithHavenHeroStylePreset`** for Lilith Haven hero exterior, or **`getStylePreset`** with a known id after **`listStylePresets`**.
3. **Deep chapter** when needed — e.g. **`getLocationAndArchitectureChapter`** for space grammar; not replaced by presets alone.

Use **`composeStyleBrief`** when you want one JSON blob (excerpts + optional preset + passthrough **`tags`**).

## Discovery without globbing

- **`listChapters`** — filesystem-backed chapter list.
- **`listArtBibleIndex`** — human `INDEX.md` plus optional Enhanced Index; **`missing_files`** flags Quick Reference drift.

## Safety

- **`getChapter`** only accepts known filenames under the pack `docs/` tree (no arbitrary paths).
- Resources use fixed URIs (`vbn-style-agent://resource/...`); the server maps them to pack files only.

## Related files on disk

- [`../README.md`](../README.md) — full tool table and MCP Prompts list.
- [`RULES.md`](RULES.md), [`PROMPTS.md`](PROMPTS.md) (this folder); [`INDEX.md`](INDEX.md) when copied from vbn-game.
