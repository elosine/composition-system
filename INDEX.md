# INDEX — where every shared thing lives

> One line per entry: **what** — where (repo · path @ commit) · refreshed · who uses it.
> **Pointers, not copies:** the authoritative copy is the one named; nothing here is duplicated from it.
> **Not exhaustive:** an entry is added when a piece sends us to it (the protocol's 9.7).
> "Path not pinned" = the repo is known, the file was not looked up yet; pin it at the first fetch.
>
> First version 2026-10-03 (9.1). The commits are each repo's HEAD on that day.

## The pieces

| # | Repo | What it is | HEAD 2026-10-03 |
|---|---|---|---|
| 1 | `string_quartet_no1-composer` | string quartet | `9843c340` |
| 2 | `composition_for_two_pianos_and_two_percussion` | two pianos, two percussion | `e9306f8` |
| 3 | `for_bass_clarinet_harp_and_accordion` | bass clarinet, harp, accordion | `1e72f97` |
| 4 | `for_seven_tubas` | seven tubas | `d203801` |
| 5 | `septet_2026` | the Tempus septet | `ba318e1` |
| 6 | `septet_LGMF_2026` | _Recombination_, the Lake George septet | `33ba534` |
| 7 | `decibel_TENOR_2026` | the Decibel piece — the protocol's FIRST RUN (v1); made 2026-10-04, the kit only, no code yet | `7a77bde` (2026-10-04) |

Beside them: `composition-planning-and-notes` (the composer's planning lists) · `live-electronics-engine` · `live-electronics-system` (the shared live-electronics engine of the three electronics pieces — a module set, not a piece; see The module manifest)
(the sandbox for the live-electronics kind of start).

## The protocol

- **The new-piece protocol, v1** — here: `protocol/NEW_PIECE_PROTOCOL.md` · refreshed 2026-10-03 · used by every new piece's start.
  The record of its drafting: `septet_LGMF_2026/docs/plans/NEW_PIECE_PROTOCOL.md` (frozen) and its RUNNING_LOG §786 … §798.
- **The harvest's template** — here: `protocol/HARVEST_TEMPLATE.md` · refreshed 2026-10-03 · used at a piece's close (step 1).
  Its first run: `septet_LGMF_2026/docs/HARVEST.md` @ `33ba534`.
- **The skeletons** — here: `skeletons/` · refreshed 2026-10-03 · used at step 2.5.
- **The deviations register's template** — here: `skeletons/docs/PROTOCOL_DEVIATIONS.md` · refreshed 2026-10-03 · used during a start (10.2).
- **The last start's record** — `septet_LGMF_2026/docs/plans/PORT_FROM_TEMPUS.md` @ `33ba534` · the copy-forward of #5 into #6, step by step.

## The method docs

Carried whole into each piece at step 2.4. The latest piece's copy is the authoritative one.
All in `septet_LGMF_2026` @ `33ba534` · refreshed 2026-10-03 · used by every piece.

- `docs/AI_METHODOLOGY.md` — how the AI scopes, decides and claims confidence (governing)
- `docs/PLANNING_METHOD.md` — the three phases of a plan item; § THE DEVICE SHEET
- `docs/HOW_WE_WORK.md` — the working preferences
- `docs/SESSION_PROTOCOL.md` — how a session opens and closes
- `docs/SESSION_HYGIENE.md` — clears, checkpoints, which model for what
- `docs/MORPH_NOTES.md` — the central notes for the morph tool (while it lives)
- `.claude/commands/checkpoint.md` · `.claude/commands/postclear.md` — the two project commands

## The laws

*Not written yet* — the protocol's 9.10. Their seeds:

- `septet_LGMF_2026/docs/HARVEST.md` H-34 @ `33ba534` — the six laws, one line each
- `septet_LGMF_2026/docs/DYNAMICS_LAW.md` @ `33ba534` — the dynamics law
- `septet_LGMF_2026/docs/MORPH_NOTES.md` §4 @ `33ba534` — where most of them were found

## The standards as data

All in `septet_LGMF_2026` @ `33ba534` · refreshed 2026-10-03 · used by any piece with a notated score.

- `notation/registry/rules.json` — the engraving rules: anchors · column · objects · colours · faces · the ladder.
  Read through the generated `docs/ENGRAVING_RULES.md`; held by `tools/check_rules.js`.
- `notation/registry/page_rules.json` — the page edges; every drawn kind's edge class, screen and print
- `docs/DYNAMICS_LAW.md` — the two kinds of note; the fader on the curve channels
- `docs/PLANNING_METHOD.md` § THE DEVICE SHEET — how a new notation begins
- `tools/palette_check.js` — the per-instrument tables, checked against the rack
- `docs/research/just_partials_notation.md` §1a · §1b — how a just-intoned note is written

## The colours

- `septet_LGMF_2026/notation/registry/rules.json` (`colours`) @ `33ba534` — every colour the score draws
- `septet_LGMF_2026/docs/CURVE_LOOK.md` @ `33ba534` — the two curve colours and where they came from
- `string_quartet_no1-composer` — where limeGreen (crescendo) and brightOrange (glissando) were first named · path not pinned

## The manuals

- `for_bass_clarinet_harp_and_accordion/docs/manuals/extracted/` @ `1e72f97` — the sampler manuals as text:
  IRCAM Solo Instruments 2 · IRCAM Prepared Piano 2 · the Xsample library · Xsample AIL scripting ·
  Xsample notation keywords · Xsample bass clarinet · used when a rack is built (step 4)

## The maps

- **Percussion (Spitfire Abbey Road Orchestra):** `composition_for_two_pianos_and_two_percussion` — its journal · path not pinned.
  This piece's selection: `septet_LGMF_2026/bank/perc_selection.json` @ `33ba534`
- **Xsample strings** (articulations, channel banks, glissando keyswitches): `string_quartet_no1-composer` · path not pinned
- **Xsample woodwinds, the deep map:** `for_bass_clarinet_harp_and_accordion` · path not pinned
- **IRCAM Solo Instruments 2 brass:** `for_seven_tubas` (the tuba maps) · path not pinned

## The tool docs

The current copies, in `septet_LGMF_2026/docs/` @ `33ba534`. Most still describe the tools as built for
piece #5 (the harvest's H-33). **The one piece-neutral copy of each is not made yet** — the protocol's 9.12.

- composing tools: `STRIKES_TOOL.md` · `SEQUENCE_TOOL.md` · `TRILLS_TOOL.md` · `BEATING_TOOL.md` · `CRESCENDO.md` · `PANEL_CAPTURES.md`
- the rack and the render: `RACK_SETTINGS.md` · `SAMPLER_QUIRKS.md` · `REAPER_CONTROL.md` · `RENDER.md` · `NAMING.md`
- the notation: `NOTATION_STANDARDS.md` (the history) · `NOTATION_WORKFLOW.md` · `NOTATION_IDENTITY.md` · `GLYPH_SIZING.md` · `TRILL_NOTATION_SPEC.md`

## The instrument knowledge base

*The shelf is not opened yet* — the protocol's 9.5, filled when the composer takes up his flags (4.9 · 5.10). Its seeds:

- `septet_LGMF_2026/bank/instrument_card.json` @ `33ba534` — every instrument measured on the channels the piece plays
- `septet_LGMF_2026/docs/RACK_SETTINGS.md` · `docs/SAMPLER_QUIRKS.md` @ `33ba534`
- the harvest's H-35 — piece #5 measured all five Xsample instruments at ±1 semitone of bend

## The module manifest

*Not written yet* — the protocol's 9.11. Until it says a module can travel alone, the rule is CARRY ALL, USE SOME.

- **The shared live-electronics engine — the manifest's FIRST MEMBER:** `live-electronics-system` (`github.com/elosine/live-electronics-system`, public, pushes after every commit) · made 2026-10-03 · its `docs/PLAN.md` is the plan of the engine for the three electronics pieces (the Decibel piece · the Switch~ piece · the improviser piece); its `docs/SEAMS.md` names where it plugs into a piece's stack, its `docs/TAKE.md` how a piece takes it (a git submodule) · planned in `septet_LGMF_2026` RUNNING_LOG §805 … §814.

## The backlog

- **The standing "later" list** — here: `BACKLOG.md` · refreshed 2026-10-03 (from #6's harvest, H-36 … H-47) · read at each harvest
