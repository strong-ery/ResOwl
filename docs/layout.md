![RES](../assets/LogoRES_Transparent.png)
The **RES** architecture is split into 5 carefully chosen categories, and where a page belongs depends on what it explains, not how big it is.

# 1 - Architecture

The horizontal slices of the game: each page explains one layer of the engine entirely on its own terms, with no regard for what is built on top of it, much like a namespace.

# 2 - Systems

The vertical slices, where each page follows a single feature (the Ocarina Song System, for example) down through every architectural layer it touches and links to those pages instead of re-explaining them.

# 3 - Blueprints

Actionable steps for recreating a process that resulted in something, like `create-basic-actor` or `duplicate-npc`, and they lean on the first two categories for the "why" so the steps themselves stay clean. See [example-blueprint](../3-blueprints/example-blueprint.md) for the structure.

# 4 - References

Everything you look up mid-task, split between common concepts, file formats, and tooling.

# 5 - To-do's

The intake queue for anything not yet understood, including dead ends, so nobody has to try the same failed idea twice.
