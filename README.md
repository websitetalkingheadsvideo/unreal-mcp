# MCP_test

Unreal Engine **5.8** project for **VbN Videos** (*Valley by Night* cinematics) using the cinematic template, Sequencer, and Movie Render Pipeline.

Style contract: [`style_bible/VbN_Unreal_Engine_LookDev.md`](style_bible/VbN_Unreal_Engine_LookDev.md).

## Open the project

1. Install UE 5.8 (matches `EngineAssociation` in `MCP_test.uproject`).
2. Double-click `MCP_test.uproject` or open it from the Epic Games Launcher / Unreal Project Browser.
3. Default editor map: `CinematicTemplate/Maps/Main`.

## Content

- `Content/CinematicTemplate/` — template cinematic setup
- `Content/Characters/` — character assets

## Rendering

Project defaults target high-end desktop (Lumen, hardware ray tracing, path tracing). Use **Movie Render Pipeline** for final video output.

## Cursor

Project rules live in `.cursor/rules/`. See `AGENTS.md` for structure and MCP-related plugins.

## Git

A `.gitignore` excludes Unreal build artifacts and local `Saved/` data.

**Remote:** https://github.com/websitetalkingheadsvideo/unreal-mcp.git

As `Content/` grows, consider Git LFS for large `.uasset` / `.umap` files.
