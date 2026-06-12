Set of convensions upkeep across all repos and languages in this organization.

> **NB:** some will be enforced programmatically (through [v_flakes](https://github.com/valeratrades/v_flakes) and [codestyle](https://github.com/valeratrades/codestyle)), and thus not even mentioned here.

Every statement must be the source of truth for how it is done across the entire organization. If it's not ubiquitous, - it's doesn't warrant adding.
In cases where you wish to enforce situational conventions, - pin them in `docs/ARCHITECTURE.md` or `docs/spec/`[^1] of the project directly.
[^1]: https://github.com/bearcove/tracey

> In absence of a stated convention, assume language defaults.

# Style
## General

TODO: . <!--could heavily pull from https://github.com/tigerbeetle/tigerbeetle/blob/main/docs/TIGER_STYLE.md; and equally so https://github.com/valeratrades/.github/tree/main/best_practices-->

## Lang-specific
**standard**: for each, mention sections:
- what
- wrong way
- right way
- reasoning

### Rust
#### derives
when using derives from libraries, write them out:

wrong:
```rust
use serde::Deserialize;
#[derive(Deserialize, Ord)]
struct Yak;
```

right:
```rust
#[derive(Ord, serde::Deserialize)]
struct Yak;
```

reason: this way, auto-formatter for derives won't mix them together.
