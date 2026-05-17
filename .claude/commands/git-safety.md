Review the current git state for anything risky before committing or pushing.

1. Run `git status` to see all staged and unstaged files.
2. Run `git diff --staged` to inspect staged changes.
3. Run `git log --oneline -5` to see recent commit history.

Check for the following risks and report each one clearly:
- Hardcoded secrets, API keys, tokens, or passwords in staged files.
- Large files (over 1MB) accidentally staged.
- Changes to CI/CD pipeline files (.github/workflows, Dockerfile, etc.) — flag for extra review.
- Modifications to sensitive config files (.env, secrets.json, credentials, etc.).
- Any staged deletions of critical files.
- Commits that would be hard to revert (e.g., database migrations, schema changes).

Output a risk report with:
- A GREEN / YELLOW / RED overall safety rating.
- A bullet list of specific issues found (or "No issues found" if clean).
- A recommended next step.
