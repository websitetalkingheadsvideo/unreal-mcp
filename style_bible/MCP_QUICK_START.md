# Style Agent MCP — Quick start

## 1. Cursor

1. Add / enable the **style-agent** MCP (stdio → `php` … `agents/style_agent/server.php`).
2. Reload MCP after `server.php` edits.
3. In chat, the client should send **`initialize`** then **`tools/list`**.

## 2. Golden path — exterior / location plate

1. **`getRules`** `{}`
2. **`getPrompts`** `{}`
3. **`getLilithHavenHeroStylePreset`** `{}` (if Lilith Haven hero exterior delta applies)
4. Optional: **`getLocationAndArchitectureChapter`** `{}`
5. Optional: **`lintPromptAgainstStyle`** `{ "prompt": "<your prompt>", "workflow": "exterior" }`

Or use **`prompts/get`** with name **`location_exterior_pass`** and arguments **`location_text`**, optional **`notes`**.

## 3. Golden path — square portrait

1. **`getRules`**, **`getPrompts`**
2. **`getPortraitSystemChapter`**
3. Build prompt with **`subject_description`**; optional **`clan`** for motifs.

Or **`prompts/get`** **`portrait_pass`**.

For coterie group portraits: **`prompts/get`** **`coteries`** (cast-locked **1:1** group still; Cursor skill [`.cursor/skills/coteries`](../../../.cursor/skills/coteries/SKILL.md)).

## 4. Fast distilled search

- **`searchRules`** — only `RULES.md` + `PROMPTS.md`.
- **`searchArtBible`** — all `docs/*.md` chapters.

## 5. Resources (this pack)

- **`resources/list`** — URIs for user guide, quick start, Cursor rule template.
- **`resources/read`** — `{ "uri": "<uri from list>" }` returns markdown `text`.

## 6. On failure

Read from repo: [`RULES.md`](RULES.md), [`PROMPTS.md`](PROMPTS.md) (this folder).
