---
type: todo
status: unknown
game-version: 1.1.1
---

# OcarinaMgr

How the game tracks the notes Link plays, decides whether they match a song, records which song was played, and runs that song's event.

## What We Know

Nothing confirmed. Everything below comes from an unverified writeup and must be checked in Ghidra before it goes into an architecture page.

## Tried

Nothing yet.

## Lead

The first step for all three questions is confirming the function and field names exist in the 1.1.1 database.

### Song Matching

The writeup claims:

- `OcarinaMgr::evaluateSongMatches` at `0x7103238270` compares the played notes to songs, and caps the search at 13 songs.
- Link's learned songs are a fixed 12-byte array at `OcarinaMgr + 0x264`.
- The note history buffer is at `OcarinaMgr + 0x158` and the note count at `OcarinaMgr + 0x25c`.
- `mLastMelodyType` is at `OcarinaMgr + 0x220`.

### The 13 Sentinel

Whether 13 is the game's only "no song" or "invalid song" value, and what else depends on it. The writeup claims two places treat it as a failure: `QueryMelodyTypeForNormal::execute` at `0x7102a0a004` (turns 13 into -1), and a blackboard dispatcher at `0x7100693cbc` that skips writing `OcarinaLastMelodyType` when the value is 13.

Find every other place that reads, writes, or compares against 13, including where `mLastMelodyType` is initialised and reset. If 13 also means "no song yet" anywhere, raising the failure value to 0xff would turn every empty state into a valid song, so this has to be answered before any custom song IDs are added.

### Event Dispatch

How a successfully played song becomes the event it triggers. The writeup claims `Dm_SY_Ocarina.bfevfl` starts when Link pulls out the Ocarina, and that the request goes through `OcarinaMgr::onSongSuccess` and `EventSystem::requestEvent`. Neither name has been checked.

Open `Dm_SY_Ocarina.bfevfl` and find how its branch node chooses what to run for each song, then look for the code that starts it. This decides whether custom songs can be dispatched by a code hook or only by editing that event flow.
