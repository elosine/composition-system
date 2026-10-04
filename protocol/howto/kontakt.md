# Kontakt libraries — Xsample · Spitfire Ricotti Mallets

> From pieces #3 · #5 · #6 and the Decibel piece (`decibel_TENOR_2026` RUNNING_LOG §20 … §43; `septet_LGMF_2026`
> `docs/RACK_SETTINGS.md`). Kontakt needs the FULL version for both libraries.

## 1 · What a script can and cannot do inside Kontakt

- **Can:** load an instrument file into a slot, set its MIDI channel, output, volume and name, remove it, read
  all of those back. Scripts: `reaper/kontakt/*.lua`, run from Kontakt's menu → Run Lua script… (or dragged onto
  it). Developer features must be on (Options → Developer).
- **Cannot:** load a preset file (.nka) into an instrument's own panel · change anything behind an instrument's
  own buttons · run without a hand starting it. One menu item per Kontakt instance is the composer's.
- Every script writes a START file before it touches Kontakt, then a read-back. The AI reads those; he sends nothing.
- Parse-check a script through the Reaper bridge first (`loadfile`) — a script that does not parse runs nothing.
- A broken instance is put right by a RESET script: remove every slot, load fresh (`reset_bass_flute.lua`).

## 2 · A sustained instrument (Xsample) — four slots, and CC7

- **Four slots of the same instrument:** channel 1 the MAIN, channels 2 · 3 · 4 the CURVE COPIES A · B · C.
- **Why copies:** CC7 is the slot's volume. A drawn, shaped note moves CC7 — so it plays on a curve copy, and a
  plain note on channel 1 is never disturbed. Three copies so three shaped notes can overlap.
- So: MEASURE on channel 2, not 1 — that is where the piece plays.
- CC7's law is Kontakt's, the same for every instrument (about −17.7 dB at 64, −27.5 at 44). Carry it; do not
  re-measure it.
- All four slots must be in the SAME state. Before measuring, check velocity 24 against 127 on each slot.

## 3 · Articulations

- **Xsample:** CC0 selects the preset, CC0 = the preset's number − 1, sent before every note.
  The roster: read the manual that ships with the library first, then ONE screenshot of the Preset Menu in his
  Kontakt — the menu is the truth (the bass flute's manual listed 30, the menu had 32).
- Name a preset's key as the same playing style is keyed on the other instruments.
- **By-key presets** (multiphonics, key noises, air noises): leave unmapped until the music uses one.
- **Ricotti:** each instrument ships as one keyswitched file AND as single patches. Use the single patches:
  ONE SLOT PER PATCH, each on its own channel — a technique is then a channel, two beaters can sound at once,
  nothing is latched. The catalog (`bank/ricotti_catalog.json`) fixes the channels; never re-deal them.
- Ricotti's rolls, tremolos and bowed patches take their loudness from CC1, not velocity.

## 4 · Ranges

- He reads the lit keys on Kontakt's keyboard (a screenshot); "main" holds for every patch unless he names an
  exception. Kontakt names middle C "C3" = MIDI 60.
- The AI proves the edges with `tools/key_sweep.js` (one key outside, one inside, at each end).

## 5 · Round robin (Xsample)

- It is stored IN each preset. A dropdown change, or CC82, is undone by the next preset switch.
- The only fix: a COPY of the preset with round robin off, saved as a preset, in ALL FOUR slots, and the recipe
  pointed at its number.
- **Make the copy from the right preset.** Kontakt shows preset 1 when it opens; a copy made there is a
  mod-wheel preset and plays at one loudness whatever the velocity. Select the wanted preset first.
- It is per preset per instrument — worth it for an ordinary voice that repeats a pitch, not for every
  articulation. The Decibel piece skipped it.
