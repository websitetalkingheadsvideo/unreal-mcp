# Next Git Sync

You are a careful Git assistant working in this repository.

## Gate (HARD) — do not run unless this command was invoked

**This workflow runs only when the user explicitly used the Cursor `/next` command** (this file injected into the turn).

- **Do not** run version bump, `git add`, commit, or push because a task finished, the user said they are “done,” or they asked to sync / ship / push / commit in ordinary chat.
- **Do not** infer `/next` from the word “next” in other contexts (next quest, next NPC, next step).
- **Do not** offer, suggest, or remind the user to run `/next`.
- If this file is **not** in the current user/command payload: **stop**. Do not execute any step below.

## Objective

Do the following as a single workflow:

1. **Always** increment the project version. **The only canonical version string is `includes/version.php`** (`VBN_GAME_VERSION`)—see step 2. **Do not treat the workflow as complete without a successful version bump** unless the user explicitly opts out in the same message.
2. Stage and commit all new and modified files that should be in version control.
3. Push the commit to the current branch’s upstream on GitHub.
4. Provide a concise summary of what has changed since the last push.

## Steps

1. **Verify repo + branch**
   - Make sure you are in the Git repository root.
   - Detect the current branch and use **that** branch for all operations.
   - Do **not** create or switch branches.

2. **Increment version (mandatory for vbn-game / this repo)**

   **Canon (read this first):**

   - **`includes/version.php` is the canonical source of truth** for the app version. The defined constant `VBN_GAME_VERSION` is what the running app and UI should use (`require_once` + `VBN_GAME_VERSION`). No other file overrides it.
   - **`VERSION.md` is not a second authority**—it is the **changelog / release log**. You still update it every bump so humans have history, but the **numeric bump always originates in** `includes/version.php`.

   **Files to touch each bump:**

   1. **`includes/version.php`** (canonical) — update `define('VBN_GAME_VERSION', '…');` and the `* Version …` file header comment.
   2. **`VERSION.md`** (changelog) — prepend a **Current Version** block with date, type (patch/minor per `.cursor/rules/versioning.mdc`), and one-line summary of this commit.

   **Procedure:**

   - Read the current value **only** from `includes/version.php` (the canon).
   - Increment **patch** (Z in `X.Y.Z`) for typical syncs (docs, fixes, small changes). Use **minor** (Y) only when the user’s change set is a complete new working feature per versioning rules—**major** (X) only if the user explicitly requests it.
   - Update the `define('VBN_GAME_VERSION', '…');` line and the `* Version …` file header comment to match.
   - Update `VERSION.md`: new “Current Version”, shift previous current to “Previous Version”, keep history.

   **Do not:**

   - Use `package.json`, `composer.json`, `pyproject.toml`, or ad-hoc `VERSION` files as the version canon—they are **not** authoritative here. If they exist, ignore them for bumping unless the user explicitly asks to align them with `includes/version.php`.
   - Skip version bump because root-level Node/Python manifests are missing—the canon is **`includes/version.php` only**.
   - Report “version skipped” as success. If you cannot read or edit `includes/version.php`, **stop** and say what blocked you.

3. **Inspect Git status**
   - Run `git status -sb` and `git diff --stat` to see what has changed.
   - Make sure you understand which files are:
     - New (untracked)
     - Modified
     - Deleted/renamed

4. **Stage changes**
   - **Always use `git add -A`** so every new and modified file is staged. Do not cherry-pick paths; never leave created or modified files unstaged.
   - If a file is new (untracked), it must be added to the commit. Do not leave it out.
   - Only exclude what is in `.gitignore` or clearly not versioned (e.g. build artifacts, caches). If in doubt, stage it.
   - After staging, verify with `git diff --cached --stat`. Resolve any push-blocking issues (e.g. secrets in code → use env vars) before pushing.

5. **Create commit**
   - If there are **no staged changes**, stop here and:
     - Explain that there is nothing to commit or push.
     - Still compute and summarize commits since the last push (step 7).
  - Otherwise:
    - Craft a short, imperative commit message that describes the change set **and includes the new version** (e.g. `chore: docs and bump v0.9.297`).
      - Keep the first line under ~72 characters.
    - Run `git commit -m "<your message>"`.
    - **PowerShell compatibility (important):**
      - Prefer a plain one-line commit message via `-m` in this command (do not use bash heredoc syntax like `$(cat <<'EOF'...)` in PowerShell sessions).
      - If chaining commands in PowerShell, prefer `;` for sequential execution to avoid parsing issues with shell-specific constructs.

6. **Push to GitHub**
   - Use the current branch’s upstream:
     - If an upstream exists, run `git push`.
     - If no upstream exists yet, set it with `git push -u origin <current-branch>`.
   - Do **not** create tags or new branches.

7. **Compute “since last push” summary**
   - If the current branch has an upstream:
    - Use `git log --oneline --stat "@{u}..HEAD"` and
      `git diff --stat "@{u}..HEAD"` to see what is new since the last push.
    - **PowerShell note:** always quote `@{u}..HEAD` to prevent hash-literal parser errors.
   - If there is no upstream or this is the first push:
     - Use `git log --oneline --stat` and `git diff --stat` for the current branch.

8. **Final response to me**
   - In your reply, do **not** show the raw commands you ran unless it helps explain something.
   - Instead, provide:
     - **Commit & push status**
       - Whether a new commit was created
       - Whether it was pushed successfully, and to which branch
     - **Version info (required)**
       - **From → to** (e.g. `0.9.296 → 0.9.297`) per **`includes/version.php` (canon)**, plus confirmation that `VERSION.md` changelog was updated to match.
       - If there was truly nothing to commit, still state the **current** `VBN_GAME_VERSION` read from **`includes/version.php`**.
     - **Summary since last push**
       - 3–7 bullet points highlighting key changes:
         - new files / major edits
         - important features or fixes
         - any structural or config changes
   - Keep the summary focused and high-signal so I can quickly see what we just shipped.
