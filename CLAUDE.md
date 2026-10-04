# composition-system — read this first

The home of the composer's custom composition system: **what belongs to the SYSTEM, not to a PIECE.**

Made 2026-10-03 at the composer's word — his name for it, public (the new-piece protocol's step 9.9;
`septet_LGMF_2026` RUNNING_LOG §800).

**It is not a piece.** No score, no engine code, no piece's record. A piece's journal, plan, lab journal
and sketch pad stay in that piece's repo — always.

## What lives here

- **The index** — `INDEX.md`. One line per shared thing: what it is · where its authoritative copy lives
  (repo · path · commit) · when last refreshed · who uses it. **Pointers, not copies.**
- **The few things written once, because they have no other home:**
  - the protocol for starting a new piece — `protocol/NEW_PIECE_PROTOCOL.md`
  - the harvest's template — `protocol/HARVEST_TEMPLATE.md`
  - the skeletons — `skeletons/`, the blank record docs for a new piece's repo
  - the backlog — `BACKLOG.md`, the standing "later" list
  - the laws — *not written yet* (the protocol's 9.10)
  - the module manifest — *not written yet* (9.11)
  - the instrument knowledge base's shelf — *not opened yet* (9.5; the composer's flags 4.9 · 5.10)
- **This repo's own log** — `LOG.md`, one line per change.

## The rules

1. **Never a piece's record.** What happened in one piece stays in that piece's repo.
2. **Point, don't copy.** If a thing has an authoritative copy in a piece's repo, the index points to it.
   Only what has no home is written here.
3. **The protocol changes by a DATED ENTRY** under the step it touches (`— 2026-MM-DD: …`). The IDs stay
   stable. A reversed call is written as reversed, never erased. A changed step bumps the version line (10.3).
4. **A law changes only by a dated entry under it** (9.2).
5. **The backlog:** an item taken up leaves by a dated line; the list is refreshed at each harvest (9.6).
6. **Every change gets one line in `LOG.md`,** and the index's "refreshed" date is brought current.
7. **Not exhaustive.** A thing is added to the index when a piece sends us to it (9.7), not before.
8. **Stop and ask the composer:** a law's wording · a change to a UNIVERSAL step of the protocol
   (1 · 2 · 9 · 10) · anything that would move a piece's record out of its repo.

## How a new piece uses this repo

- Its `/session-start` reads `INDEX.md` first.
- Then the protocol, from 2.1 the profile.
- At 2.5 the skeletons are copied into the new repo (`skeletons/_ABOUT.md` says how).
- During the start, each departure from the protocol is one line in the piece's
  `docs/PROTOCOL_DEVIATIONS.md` (10.2). At the end of the start they come back here as dated entries (10.0).

## Reading the protocol's references

The protocol was drafted inside piece #6. In it, a bare `§N` (lab journal), `LG-N` (sketch pad), `H-N`
(harvest), `D-N` (decision), `PLAN …` or `docs/…` path is **piece #6's** — `septet_LGMF_2026` — unless it
says otherwise. Another piece's are written `#5 §182`.

## How the composer reads

His reading and reply preferences are in his user-level `CLAUDE.md` and hold here: plain words, bullets,
short lines, one idea per chunk, one decision at a time.

## Git

- Stage explicit paths only, never `git add -A`.
- **Push: asked per repo, never inherited** (the protocol's 2.2). Not yet decided for this repo — ask him.
