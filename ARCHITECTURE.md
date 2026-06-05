This repository holds the conventions, brand assets, and tooling configs that
other repos in the organization reuse — so things like commit rules, formatter
configs, the dev environment, and the brand look stay consistent everywhere.

It also provides GitHub org defaults (issue/PR templates and the public profile).

# Structure

The repository is organized into **layers → slices → segments**, inspired by
Feature-Sliced Design. Each level has a strict responsibility, and dependencies
flow only downward (layer → slice → segment), never sideways.

```
layer
└─ slice
   └─ segment
```

## Layers

The top level. A layer is a broad domain of standards. Layers are independent of
each other — one layer knows nothing about another.

## Slices

Within a layer, a slice is a self-contained domain area. Slices are isolated from
one another: no slice depends on a sibling slice.

## Segments

The lowest level. A segment groups files by their **technical purpose**, not by
domain. The same segment names recur across slices, giving a predictable shape.

## Why this shape

- **Predictability** — knowing the layer/slice/segment lets you guess a file's location.
- **Isolation** — slices don't leak into each other, so a change in one can't break another.
- **Reuse** — a slice exposes its consumable artifacts as a public API for downstream repos.
