---
type: format
aliases: [RESTBL]
game-version: 1.1.1
---

# restbl

The RESTBL is a database of every resource and its unpacked size on the game's heap, which the game reads to know how much memory to allocate for each resource. It is shared by every ModuleSystem game (OOT, TotK, Mario Wonder, Splatoon 3, and more). (confirmed)

## Purpose

If a resource is allocated too little, it fails to load, and the symptom is a freeze, a black screen, or the asset simply not appearing. Any mod that adds or resizes a resource therefore needs a matching RESTBL entry. (confirmed)

## Layout

The internal structure hasn't been documented yet. ([[restbl-layout]])

## Tooling

- [[restbl-calculator]] builds a RESTBL from a mod folder, keeping every vanilla entry and adding the modified ones
