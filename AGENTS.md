# Codex project instructions

## Git and multi-computer workflow
- This repository belongs to sxurra and is private.
- At the start of each task, inspect `git status`, the current branch and remotes. Fetch remote updates before editing when network access is available.
- Never pull with destructive options, force-push, reset --hard, clean untracked files, or overwrite work on another computer.
- If local changes exist, preserve them. If remote changes conflict, explain the conflict and stop rather than discarding any work.
- After completing a task, run relevant available checks. If Git credentials, permissions and network access allow, commit only project files changed for the task with a descriptive message, then push to the configured upstream branch.
- Do not claim synchronization succeeded unless the push returned success.
- If push is blocked or a merge is required, report what happened and what remains to be done.
- Do not push on every keystroke, and do not make empty commits.
- For parallel worktrees or tasks, use separate branches and integrate changes safely. Never overwrite other branches.
- This policy applies to this repository only. Every other project needs its own repository or its own AGENTS.md, or global instructions.

## Secrets and safety
- Never commit .env, .env.*, credentials, tokens, API keys, private keys, local auth sessions, or other secrets.
- Before staging changes, inspect added files and diffs for secrets, generated artifacts and unrelated changes.
- Do not delete, rename, or replace existing user files without an explicit request.
- Keep the project runnable on another computer. Update README with setup steps and note required environment variable names without secret values.
- Avoid committing dependencies, build outputs, IDE caches or operating-system files.
