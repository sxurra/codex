# codex

Private repository for a project worked on with Codex.

## Website handoff

The editable website is in `site/`. Keep `site/index.html`, `site/assets/`, and
`site/uploads/` together when sharing it with another editor or AI assistant.
The page template, styles, and copy are embedded in `site/index.html` as a JSON
string inside `<script type="__bundler/template">`; edits must preserve valid
JSON and the surrounding HTML. The site is static and needs no environment
variables. To preview it locally, run `python -m http.server 8000 --directory
site` and open `http://localhost:8000/`.

GitHub Pages serves the `gh-pages` branch from its root. Publishing changes
requires copying `site/index.html` to `index.html` on that branch and copying
the `site/assets/` and `site/uploads/` folders alongside it, then pushing the
branch. Changes on `main` alone do not update the public site.

## Windows computers

Install Git for Windows and sign in to GitHub using Git Credential Manager (HTTPS) or an SSH key. Never put a token in the remote URL or commit it. In PowerShell, clone this repository on the first computer:

```powershell
git clone https://github.com/sxurra/codex.git
cd codex
git switch main
```

Open this folder in Codex. Keep project files and changes inside the clone, and commit only files needed by the project. Before staging, inspect `git status` and the diff; `.gitignore` excludes environment files, keys, tokens, dependency folders, and temporary files. Ignore rules do not remove files already tracked, so inspect those explicitly before the first push. Keep required `.env` values local and share variable names through `.env.example` without values.

## Using the second computer

Clone the same repository on the second computer using the commands above. Before starting work on either computer, fetch and update the local `main` branch:

```powershell
git switch main
git pull --ff-only origin main
```

After making changes, review and commit them, then push:

```powershell
git status
git diff
git add <project-files>
git diff --cached
git commit -m "Describe the change"
git push origin main
```

Finish and push work on one computer before switching to the other. If a push is rejected, fetch and integrate the remote changes; never force-push or discard work to make histories align. Install project dependencies separately on each computer using the project's documented instructions.

## Important
- Codex conversations are not synced by Git. The repository stores committed files and their commit history.
- The repo-level `AGENTS.md` asks Codex to fetch at the start and commit/push at the end of a completed task where safe and permitted. These are instructions, not guaranteed automatic background synchronization.
- Every independent website or application is best kept in a separate repository.
- Global Codex instructions for all projects belong in `~/.codex/AGENTS.md` on each computer.
