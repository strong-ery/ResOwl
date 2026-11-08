![RES](../assets/LogoRES_Transparent.png)
# Standards

Your #1 priority while contributing to any resource should be finding the perfect balance between information density and information quality. 

Density is how much true information a reader gets per word, and quality is whether they can actually use it without having to go looking for the missing half. Chasing only one of them ruins the other, so take a look at these three statements trying to convey the same thing:

```
The Actor System in OOTNS2E, and by extension ModuleSystem, operates at the most basic level on a datatype labelled BaseProc. From BaseProc's, every game actor, system actor, item actor, etc all inherit from this base class.
```

```
Actors extend BaseProc.
```

```
BaseProc is the root datatype of the Actor System and ModuleSystem. Every game, system, and item actor inherits from it.
```

The first buries two facts under filler, and the second is so dense it drops half of them: which systems use BaseProc, and which kinds of actor inherit it. The third keeps every fact the first one had in about half the words, and that is the target.

A good test is to remove a word and see if anything is lost. If nothing is, it didn't belong, and if something is, put it back.

# Confidence

Most of what goes in a RES project is not fully known, so every claim should say how sure you are by ending with one of these tags:

- **(confirmed)** means you verified it directly, by testing it in game or reading it in a decompile.
- **(inferred)** means it fits everything you've seen but you haven't proven it.
- **(unknown)** means you know there's something here and not what it is. These also get a page in `5-todos`.

An untagged claim reads as confirmed, so tag anything that isn't.

# Sourcing

When a claim isn't obvious, say where it came from, whether that is a decompiled function, a runtime trace, a diff between two files, or someone else's research. Link or credit the original when it's not yours.

For anything tied to the executable, record the address as an offset relative to the module and name the game version, since absolute addresses move with every patch.

# Linking

Dependencies run one direction. Systems link down into the architecture pages they use, and architecture pages never link back up to a system. If two systems need the same fact, that fact belongs in architecture.

Link to another page the first time you mention it instead of re-explaining it, and give the link its in-game name (`[[base-proc|BaseProc]]`) so the page still reads naturally.

# What Not to Commit

This is a store of notes, so it should hold knowledge and offsets only. Dumped assets, encryption keys, and decompiled code from the game itself stay out of the project.

# File Naming

Every file is lowercase kebab-case, so `[[wikilinks]]` stay easy to type and nothing breaks between operating systems.

Architecture, systems, and references are named after the thing they explain (`base-proc`, `ocarina-song-system`), with the exact in-game symbol added as an alias so searching the real name still finds the page. Formats are named after their extension (`byml`, `sarc`) since that's what people will search for, and blueprints are named verb-first for the action they perform (`create-basic-actor`, `duplicate-npc`).

Game versions never go in a filename. They live in frontmatter, so links survive when a patch changes things.

Todos are named by what is unknown (`ocarina-song-table-layout`) and use a `status` of `unknown`, `dead-end`, or `done`, so a todo can change state without being renamed.

# Frontmatter

Frontmatter is the block of properties at the very top of a page, fenced by `---` lines. Obsidian shows it as a panel instead of body text, and it can be searched and filtered, which is how you can ask for every todo with a status of `unknown`.

```
---
type: architecture
aliases: [BaseProc]
game-version: 1.0.0
---
```

`aliases` gives a page extra names, `game-version` records the version the page was verified on, and `type` and `status` say what kind of page it is and where it stands. The example in each folder shows the fields that type uses.
