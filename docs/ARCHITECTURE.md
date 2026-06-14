This repository holds the conventions, brand assets, and tooling configs that
other repos in the organization reuse — commit rules, formatter configs, the dev
environment, and brand look stay consistent everywhere.

It also provides GitHub org defaults (issue/PR templates and the public profile).

# Structure

**code/** — coding standards consumed by all repos in the org. Rules here must
apply universally across every language and project. Anything situational belongs
in that project's own `docs/ARCHITECTURE.md` or `docs/spec/`. Splits into
conventions (versioned, named standards) and setup (bootstrapping guides for
shared tooling).

**resources/** — read-only reference material for contributors. Not tooling, not
enforced — context.

The `.github/` folder at root is consumed by GitHub directly as org-level
defaults. Repos that don't override these files inherit them automatically.
