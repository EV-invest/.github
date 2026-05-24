# Git Commit Convention Standard

> Standard version: 1.1.0

---

## Commit Format

`tag: description`

```bash
# Examples
init: Initialize project
feat: Add dark theme
fix: Remove memory leak in WebSocket handler
chore: Update dependencies
```

---

## Change Tags

| Tag        | Description                              | Version impact          |
| ---------- | ---------------------------------------- | ----------------------- |
| `INIT`     | Project or module initialization         | —                       |
| `FEATURE`  | New functionality                        | **MINOR** ↑             |
| `FIX`      | Bug fix                                  | **PATCH** ↑             |
| `HOTFIX`   | Urgent fix on production                 | **PATCH** ↑             |
| `MAJOR`    | Breaking change, API incompatibility     | **MAJOR** ↑             |
| `REFACTOR` | Refactoring without behavior change      | **PATCH** ↑             |
| `PERF`     | Performance improvement                  | **PATCH** ↑             |
| `NUKE`     | Strict removal of  code                  | ANY                     |
| `MOVE`     | Prefer committing large moves separately | —                       |
| `STYLE`    | Formatting, linting, indentation         | —                       |
| `DOCS`     | Documentation                            | —                       |
| `TEST`     | Adding or updating tests                 | —                       |
| `CHORE`    | Routine: dependencies, configs, CI/CD    | —                       |
| `REVERT`   | Reverting a previous commit              | **PATCH** ↑             |
| `RELEASE`  | Release commit, version bump             | —                       |

---

## Semantic Versioning (SemVer)

Version format: **`MAJOR.MINOR.PATCH`**

| Level     | When it increments                                                                 |
| --------- | ---------------------------------------------------------------------------------- |
| **MAJOR** | breaking user-space (`MAJOR`)                                                      |
| **MINOR** | New functionality (`FEATURE`), small breaking changes                              |
| **PATCH** | Fixes and minor changes (`FIX`, `HOTFIX`, `REFACTOR`, `REVERT`, `PERF`, `FEATURE`) |
| **—**     | No version change (`STYLE`, `DOCS`, `TEST`, `CHORE`, `INIT`, `RELEASE`)            |

---

## Release Commit and Git Tag

tag format: `v{major}.{minor}.{patch}`

no requirement for `[RELEASE]` commit or what not, - just attach the tag and that's it:

```bash
git tag "v1.2.3"
git push --tags
```

---

## Description Formatting Rules

- Length — no more than **72 characters**
- Use the **imperative mood**: _Add_, _Fix_, _Remove_, _Update_
- Do not end with a period
- Write in the English
- If more context is needed — add a commit body after a blank line:

```
feat: Add OAuth2 authorization via Google

Implemented authorization via Google OAuth2.
Added environment variables GOOGLE_CLIENT_ID and GOOGLE_CLIENT_SECRET.
Affected modules: auth, config, middleware.
```

### Edge-cases

if the fix is trivial (eg typo), it is allowed to use `_` for description.

when parsing commit history, it should be possible to have intuition about significance of changes from commit length alone.

similarly, tag also can be omitted, if changes are not important, or are outside of the framework.

therefore, when fixing a type, the following commits are valid: `_`, `chore: _`
