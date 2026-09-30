# MCP_test — agent notes

Unreal Engine **5.8** project for **cinematic video production** (Sequencer + Movie Render Pipeline), built on the cinematic template with MetaHuman and virtual production plugins.

## Layout

| Path | Purpose |
|------|---------|
| `MCP_test.uproject` | Project definition and plugin list |
| `Config/` | Engine, game, input, editor defaults |
| `Content/CinematicTemplate/` | Template maps and cinematic assets |
| `Content/Characters/` | Character-related content |
| `Content/Collections/` | Editor collections |

Generated/cache (do not track in git): `Intermediate/`, `Saved/`, `DerivedDataCache/`, `Binaries/`.

## MCP in Unreal

These editor plugins are enabled: **ModelContextProtocol**, **MCPClientToolset**, **EditorToolset**, **AIAssistant**. Use them when driving the editor from Cursor; there is no project-local `mcp.json` — MCP servers are configured in Cursor user settings.

## Common tasks

1. **Shot work:** Level Sequence in Sequencer, cameras, MetaHuman performance, lighting pass.
2. **Final render:** Movie Render Queue job from the active sequence / map.
3. **Project tuning:** `Config/DefaultEngine.ini` for renderer and startup map.

## Git

Repository initialized for Cursor workflow. Initial commit and remote (e.g. Cursor Origin) only when the user requests it.
