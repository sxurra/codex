# codex

Private repository for a project worked on with Codex.

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
