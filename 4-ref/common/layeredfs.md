---
type: reference
aliases: [LayeredFS]
game-version: 1.1.1
---

# layeredfs

LayeredFS lets a mod replace files in a game's romfs without repacking or modifying the game's own data. The loader layers the mod's files over the original romfs, so any file the mod provides is used and everything else falls through to the original.

## How It Works

The mod's romfs folder mirrors the game's folder structure and holds only the files being changed. When the game asks for a path, the loader checks the mod first and only uses the original if the mod has nothing at that exact path. A mod containing just `romfs/Pack/ZsDic.pack.zs`, for example, replaces that one file and leaves everything else untouched.

Matching is by exact path, so a file in the wrong folder or with the wrong name is never loaded. Nothing warns you either, because the game just keeps using the original.

## What It Means for Modding

Removing a mod is deleting its folder, since the game's files are never changed. Mods can coexist as long as no two provide the same path.

Single shared files are where that breaks down. The [[restbl]] is one file, and [[restbl-calculator]] builds it from a single mod folder, so two mods that each ship their own will override each other and leave one of them under-allocated. (inferred)

## Limits

LayeredFS only covers romfs. Changes to the executable (exefs) don't layer per file and are applied as patches instead.
