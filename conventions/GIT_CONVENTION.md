# Git Commit Convention Standard

> Standard version: 1.0.0

---

## Commit Format

```
[TASK-ID/TAG] Short description of the change
```

| Part        | Required | Description                                                    |
| ----------- | -------- | -------------------------------------------------------------- |
| `TASK-ID`   | Optional | Task identifier (matches the branch name)                      |
| `TAG`       | Required | Change type tag (see table below)                              |
| Description | Required | Short description in the project language, up to 72 characters |

---

## Usage Modes

### Full format — task and branch exist

Used when work is done in a dedicated branch tied to a task.  
The branch name matches the `TASK-ID`.

```
[TASK-ID/TAG] Description
```

```bash
# Examples
[AUTH-42/FEATURE] Add OAuth2 authorization via Google
[PAY-7/FIX] Fix amount rounding on currency conversion
[API-15/MAJOR] Change response structure of /users endpoint
[UI-3/REFACTOR] Extract buttons into a separate Button component
```

---

### Short format — no task or small project

Used when:

- The project is small and tasks are not formalized
- No issue tracking system is in place
- Single developer
- Commit goes directly to `main` or `dev`

```
[TAG] Description
```

```bash
# Examples
[INIT] Initialize project
[FEATURE] Add dark theme
[FIX] Remove memory leak in WebSocket handler
[CHORE] Update dependencies
[RELEASE] v1.3.0
```

---

## Change Tags

| Tag        | Description                           | Version impact          |
| ---------- | ------------------------------------- | ----------------------- |
| `INIT`     | Project or module initialization      | —                       |
| `FEATURE`  | New functionality                     | **MINOR** ↑             |
| `FIX`      | Bug fix                               | **PATCH** ↑             |
| `HOTFIX`   | Urgent fix on production              | **PATCH** ↑             |
| `MAJOR`    | Breaking change, API incompatibility  | **MAJOR** ↑             |
| `REFACTOR` | Refactoring without behavior change   | **PATCH** ↑             |
| `PERF`     | Performance improvement               | **PATCH** / **MINOR** ↑ |
| `STYLE`    | Formatting, linting, indentation      | —                       |
| `DOCS`     | Documentation                         | —                       |
| `TEST`     | Adding or updating tests              | —                       |
| `CHORE`    | Routine: dependencies, configs, CI/CD | —                       |
| `REVERT`   | Reverting a previous commit           | **PATCH** ↑             |
| `RELEASE`  | Release commit, version bump          | —                       |

---

## Semantic Versioning (SemVer)

Version format: **`MAJOR.MINOR.PATCH`**

| Level     | When it increments                                                      |
| --------- | ----------------------------------------------------------------------- |
| **MAJOR** | Breaking changes (`MAJOR`)                                              |
| **MINOR** | New functionality (`FEATURE`, `PERF` for significant improvement)       |
| **PATCH** | Fixes and minor changes (`FIX`, `HOTFIX`, `REFACTOR`, `REVERT`, `PERF`) |
| **—**     | No version change (`STYLE`, `DOCS`, `TEST`, `CHORE`, `INIT`, `RELEASE`) |

### Rule for determining the next version

Look at all commits since the last `RELEASE`:

```
At least one MAJOR?            → MAJOR++,  MINOR = 0, PATCH = 0
At least one FEATURE / PERF*? → MINOR++,  PATCH = 0
Everything else (FIX, HOTFIX…)? → PATCH++
Only STYLE / DOCS / TEST / CHORE → no version change
```

> \*`PERF` bumps `MINOR` only if the change is significant for the end user.

---

## Release Commit and Git Tag

```bash
# Release marker commit
git commit --allow-empty -m "[RELEASE] v1.3.0"

# Git tag
git tag -a v1.3.0 -m "Release v1.3.0"
git push origin v1.3.0
```

---

## Description Formatting Rules

- Length — no more than **72 characters**
- Use the **imperative mood**: _Add_, _Fix_, _Remove_, _Update_
- Do not end with a period
- Write in the language agreed upon by the team (defined in this file)
- If more context is needed — add a commit body after a blank line:

```
[AUTH-42/FEATURE] Add OAuth2 authorization via Google

Implemented authorization via Google OAuth2.
Added environment variables GOOGLE_CLIENT_ID and GOOGLE_CLIENT_SECRET.
Affected modules: auth, config, middleware.
```

---

## Branch Naming

The branch name must match the `TASK-ID` in the commit.

```
AUTH-42     ← branch for task AUTH-42
PAY-7       ← branch for task PAY-7
```

Permanent branches (`main`, `dev`) have no `TASK-ID` — use the short commit format for them.

---

## Quick Reference

```
Has branch / task?
  YES →  [TASK-ID/TAG] Description
  NO  →  [TAG] Description

Does TAG affect the version?
  MAJOR   → x+1.0.0
  FEATURE → x.y+1.0
  FIX     → x.y.z+1
  others  → no change
```
