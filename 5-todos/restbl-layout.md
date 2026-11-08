---
type: todo
status: unknown
game-version: 1.1.1
---

# RESTBL Layout

The internal structure of the [[restbl]]: how entries are keyed, how sizes are stored, and whether the file is compressed.

## What We Know

It holds an unpacked heap size for each resource, and the game uses it to decide how much to allocate. Documenting the layout isn't needed for modding today, because [[restbl-calculator]] builds it for you.

## Tried

Nothing yet.

## Lead

None yet.
