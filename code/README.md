each language folder in [./per_language], can have its own:
- STYLE.md \
  We're able to define this simple standard, cause all the structural considerations go into the [top-level style-guide](./STYLE.md)
  **standard**: for each, mention sections (last 3 prefixed with the (boldened) keyword):
  - what
  - wrong way
  - right way
  - reasoning
  > must not contradict top-level.
- shared_lib.md \
  list of shared libs, which could be treated as `std`, - meaning many of our projects rely on them already, and there is no benefit from rewriting any primitives they are exposing by hand
  > careful to only add light deps there
