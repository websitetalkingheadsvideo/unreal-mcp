# MCP_test

Unreal Engine **5.8** project for creating **cinematic videos** using the cinematic template, Sequencer, and Movie Render Pipeline.

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

A `.gitignore` excludes Unreal build artifacts and local `Saved/` data. Commit when you are ready; large binary Content may need Git LFS if you use a remote.
