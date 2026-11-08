---
type: format
aliases: [BYML, bgyml]
extensions: [.byml, .bgyml]
game-version: 1.1.1
---

# byml

BYML (Binary YAML) is the main parameter format ModuleSystem games use to store parametric data. It shadows the legacy AAMP, which Owl barely uses outside a few places where BotW-era code is still clearly in play. (confirmed)

## Extensions

- `.byml` is a hand-authored parameter file.
- `.bgyml` (Binary Generated YAML) is generated from a schema or a UI instead of written by hand. Most BYMLs in the game are this kind. (confirmed)

## Compression

Owl compresses with zstd using its own custom dictionaries, like most ModuleSystem games. See [[zsdic]].

## Tooling

- [[tkvsc]] to edit them
- [[zsdicsharp]] to handle the compression
