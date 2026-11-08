---
type: reference
aliases: [romfs, exefs]
game-version: 1.1.1
---

# romfs-vs-exefs

A game is split into two halves: **romfs** holds its data (`Pack/`, `System/Resource/`, and the rest of the folders [[modulesystem]] games share), and **exefs** holds its executable code.

## Which to Use

Romfs is always preferred. Editing exefs is powerful, because it can change what the game does and not just the data it reads, but it's hard, and romfs is far more forgiving. A mistake in data usually breaks one asset or feature, while a mistake in code can take the whole game down.

Reach for exefs only when the behavior you want can't be reached through data.

## Romfs Modding

Romfs mods replace or add files through [[layeredfs]], so the game's own data is never modified. Anything that adds or resizes a resource also needs a matching entry in the [[restbl]], which [[restbl-calculator]] builds for you.
