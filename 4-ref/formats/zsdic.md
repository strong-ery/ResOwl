---
type: format
aliases: [ZsDic, ZsDic.pack.zs]
game-version: 1.1.1
---

# zsdic

ZsDic is how most ModuleSystem games, Owl included, compress files with ZStandard (zstd) using custom dictionaries. Each game has its own set. (confirmed)

The dictionaries live in `Pack/ZsDic.pack.zs`, a SARC compressed with dictionary-less zstd. Inside are a few dictionaries, and which one applies depends on the filetype being compressed. (confirmed)

## Tooling

- [[zsdicsharp]] selects the correct dictionary for a file
