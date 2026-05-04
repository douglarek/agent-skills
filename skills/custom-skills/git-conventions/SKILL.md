---
name: git-conventions
description: Git commit message conventions and workflow rules. Use when making git commits, pushing changes, or performing git operations.
---

# Git Commit Conventions

## Rule Priority

1. **Hard Rules (MUST)**
2. **Recommended Rules (SHOULD)**

---

## Hard Rules (MUST)

### 1) Commit Message Language

- All commit messages must be in **English only**.

### 2) Commit Message Format

Use Conventional Commit style:

```text
<type>(<scope>): <subject>
```

- `<scope>` is recommended; omit only when no clear scope exists.
- `<subject>` must be concise, imperative mood, no trailing period.

Examples:

- `feat(blog): add Hugo post translation checklist`
- `fix(ci): handle missing npm cache`
- `docs: update contribution guide`

### 3) Allowed Types

- `feat`: add new feature
- `fix`: bug fix
- `docs`: documentation only
- `style`: formatting/style only (no logic change)
- `refactor`: code restructuring (no behavior change)
- `test`: tests added/updated
- `chore`: tooling/build/maintenance tasks

### 4) Breaking Changes

For breaking changes:

- add `!` after type/scope, and/or
- include `BREAKING CHANGE:` footer in commit body.

Example:

```text
feat(api)!: rename auth endpoint

BREAKING CHANGE: /v1/login is replaced by /v2/auth/login
```

### 5) Push Safety

- Always ask for confirmation before `git push --force` (or force-with-lease).
- After local commit, always ask whether to push to remote.
- After successful push, display repository URL (or remote URL if repo URL is unavailable).

### 6) Commit Granularity

- Consolidate changes into meaningful, reviewable commits.
- Do not mix unrelated changes in one commit.

---

## Recommended Rules (SHOULD)

- Keep subject length around **<= 72 characters**.
- Put rationale/details in commit body when needed.
- Group related file changes before committing.
- Prefer `--force-with-lease` over `--force` when force push is truly needed.

---

## Quick Checklist

- [ ] Commit message is English-only
- [ ] Message matches Conventional Commit format
- [ ] Type is valid (`feat|fix|docs|style|refactor|test|chore`)
- [ ] Breaking change marked properly (if applicable)
- [ ] User confirmed before any force push
- [ ] User asked whether to push after local commit
- [ ] Remote/repository URL shown after push
