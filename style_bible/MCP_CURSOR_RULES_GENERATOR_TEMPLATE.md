# Cursor rule template — vbn style_agent + Art Bible

Copy into `.cursor/rules/<your_name>.mdc` (or `.md`) and fill bracketed fields. Goal: any agent touching vbn art/prompts loads **RULES + PROMPTS + right chapter** before writing.

---

## Front matter (Cursor)

```yaml
---
description: Enforce vbn visual style via style_agent MCP and on-disk fallbacks.
globs:
  - "**/uploads/**"
  - "**/reference/**"
  - "**/agents/style_agent/**"
alwaysApply: false
---
```

Adjust **`globs`** to match where your team generates prompts or art notes.

## Rule body

When editing or generating **character portraits, cinematic frames, location exteriors, blueprints, or moodboards** for Valley by Night / vbn-game:

1. **Prefer MCP** (if `style-agent` is enabled):
   - Call **`getRules`** and **`getPrompts`** before composing image prompts.
   - For Lilith Haven hero exterior plates: **`getLilithHavenHeroStylePreset`** after rules/prompts.
   - For space layout / architecture language: **`getLocationAndArchitectureChapter`**.
   - Use **`lintPromptAgainstStyle`** with workflow **`portrait`**, **`exterior`**, or **`cinematic`** before finalizing user-visible prompts.
   - Optional one-shot context: **`composeStyleBrief`** with explicit `rules_max_chars`, `prompts_max_chars`, `include_lilith_preset`, and passthrough **`tags`** (e.g. `workflow`, `clan`, `time_of_day`).

2. **If MCP is unavailable**: read repo files directly:
   - [`RULES.md`](../RULES.md)
   - [`PROMPTS.md`](../PROMPTS.md)
   - Relevant chapter under [`docs/`](./) per [`INDEX.md`](../INDEX.md).

3. **Do not** invent preset text that contradicts **`RULES.md`**. Presets are **deltas**, not replacements.

4. **Resources**: use **`resources/list`** / **`resources/read`** on this MCP for the user guide and quick start when onboarding.

## Project-specific overrides

- **Chronicle / table tone**: [ADD ST NOTES]
- **Banned terms or motifs**: [ADD LIST]
- **Default preset id** (if not Lilith): [e.g. `lilith_haven_hero` or other stem from `listStylePresets`]

---

_End of template — delete instructional lines above when committing._
