---
type: blueprint
status: example
game-version: <version / build ID this was tested on>
tools: [<tool-1>, <tool-2>]
requires: [<other-blueprint>]
---

# Duplicate an NPC

> This is the structure every blueprint follows. Delete this note and the bracketed hints when you copy it, and keep the headings in this order so they all read the same.

## Goal

One or two sentences on exactly what you end up with, written so someone can tell whether this is the blueprint they need before reading further. Eg: a second copy of an existing NPC in a scene, with its own name and position, that behaves independently of the original.

## Prereqs

What you need before step 1, with links so nobody has to guess.

- Tools: [[{tool-name}]], with the version if it matters
- Files: the exact paths you'll be touching (`romfs/...`, `exefs/...`)
- Knowledge: [[{other-blueprint}]] if this builds on one, and the [[{system-or-architecture-page}]] that explains the "why"

## Steps

Each step is one action someone can copy and perform without interpreting it. The reasoning belongs in the linked pages above, not here.

1. Open `{file}` in `{tool}`.
2. Find `{entry}` and copy it.
3. Change `{field}` to a new unique value.
4. Repack with `{command}`.

## Result

What the finished thing looks like, so there's something to compare against. Screenshots and the final file layout go here.

## Verify

The quickest way to confirm it worked in game or in the tool, and what a failure looks like.

## Pitfalls

Mistakes that already cost someone time, each with the symptom and the fix. If you hit something new, add it here.

- **Symptom:** the game crashes on load. **Cause:** the new entry reuses an existing ID. **Fix:** give it a unique one.

## Tested on

The game version, platform (hardware or emulator), and date this was last confirmed working. If you're on a different version and it still works, add a line.
