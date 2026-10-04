# Measuring — the card, the trims, the dynamics curves

> Piece #6's method (its PLAN 1b, `septet_LGMF_2026` RUNNING_LOG §73 … §89), re-run on the Decibel rack
> (`decibel_TENOR_2026` RUNNING_LOG §29 · §40 … §43). About an hour of the AI's work; twelve minutes of sound.

## 0 · First: what is ALREADY measured

- A track CLONED from an earlier rack keeps its measurement. Put its old trim back on the fader; do not re-measure.
  Look in that piece's `bank/trims.json` and `docs/RACK_SETTINGS.md` before planning anything.
- A piece that balanced RELATIVELY (piece #5) gives no absolute trim — those instruments need one short run.
- His monitor level was set once, on the reference tone (piece #6). It is the room's, not a rack's.

## 1 · The chain

1. `tools/card_schedule.js` — the timetable, FROM THE RECIPE: held instruments on CURVE CHANNEL A with CC7 127 and
   their CC0, three pitches × velocities 24 · 64 · 100 · 127, 4 s + 3 s, one half-bend note; struck instruments on
   their own channel, NO CC7, three keys × 127 · 64, 0.2 s + 5 s.
2. `reaper/bridge/jobs/make_rec_track.lua` — the REC track: a receive from every track, unity, master send off.
3. `rec_mode_solo.lua` → `probes/card_run.ps1` (run it in the background: it outlasts ten minutes) →
   `rec_mode_restore.lua`. He must not play or touch Reaper while it runs — tell him before it starts.
4. `python probes/analyze_card.py <wav>` → `bank/instrument_card.json`. Needs numpy, scipy, soundfile.
5. `tools/compute_trims.js --only <the new ones>` → `bank/trims.json` → `gen_apply_trims.js` → `apply_trims.lua`.
   Held: the integrated level at 127. Struck: the loudest 400 ms at 127.
6. `tools/build_remap_card.js --only <held>` to a scratch file → `tools/remap_merge.js` into
   `bank/velocity_remap.json` (so a carried curve is kept). The CC7 law: carried (kontakt.md § 2).
7. `tools/dyn_table_check.js` · `palette_check` · his CTRL+S.

## 2 · Prove the chain with the clones

- Put the cloned instruments in the schedule too, on the old piece's own pitches, at their old trims.
  If they read what they read there (within ~0.5 dB), the chain IS the old proven one, and its
  `bank/reference.json` may be carried instead of re-recorded. Forty seconds.

## 3 · The target

- Each voice at one level on the card's scale (piece #6: −31.84 dB = a nine-voice tutti at −20 LUFS-S).
  Keep the old piece's figure if trims are carried from it; another ensemble size is one uniform shift.

## 4 · Before the run — what cost a re-run

- **Check that velocity moves the level on every slot** (`key_sweep --vel 24` against `--vel 127`). A preset that
  takes its loudness from the mod wheel reads the same at every velocity, to a hundredth of a dB.
- Round robin left on shows as single notes out of order (a louder velocity reading softer). Accept it or fix it
  (kontakt.md § 5) BEFORE measuring.
- Paths passed to PowerShell from bash: forward slashes.

## 5 · What the numbers will not tell you

- One main patch per mallet instrument was measured; the other patches share the track's fader and can differ by
  tens of dB. Measure a patch when the music uses it.
- An instrument with a steep register (the bass flute: 15 dB from bottom to top at fff) gets a curve that clamps.
  Three pitches are too few for it; a fine register run is the remedy.
