# The rack — ports, the file, the tracks, the first sound

> From the Decibel piece's build, 2026-10-04 (`decibel_TENOR_2026` RUNNING_LOG §19 … §22 · §35). The AI builds it;
> the composer's hands are named where they are needed.

## 1 · The ports (loopMIDI) — the AI makes them

- loopMIDI keeps its ports as values of the registry key `HKCU\Software\Tobias Erichsen\loopMIDI\Ports`
  (name = the port, DWORD 1) and creates them when it starts.
- **Reaper closed.** Export the key (a backup) → stop loopMIDI → add the values → start loopMIDI.
- **Wait about two minutes.** New names do not show to other programs at once; old ones are back in seconds.
  Verify by name, in and out (winmm).
- **One port per instrument.** A Kontakt instance has 16 channels; a library with many patches needs its own port.
- **HIS, once:** Reaper → Preferences → MIDI Inputs → select the new ports → Enable input. Reaper does not
  enable new ports by itself, and the setting cannot be reached by script.
- A port name carries the piece's prefix (`DEC…`); ports are machine-global.

## 2 · The rack file — built as text, cloned from an earlier rack

- A Reaper track chunk carries its plugin WITH its loaded state. An instrument an earlier piece already set up is
  CLONED, not loaded: `tools/build_rack.js` (the header of an old rack + the named tracks).
- Three lines of a cloned track are rewritten — NAME, the fader to 0 dB, the input to none. The plugin state is
  carried byte-exact (a hash is checked before and after). Never edit a state blob.
- **Ask once: from git, or from the rack on disk?** The disk file is the one the last piece was finished on; git may
  be weeks older. (`--source disk` reads it, never writes.)
- A track he has not set up before is a bare track; the plugin is inserted by the bridge.
- **Once he has saved the file it is HIS.** After that a track is added or re-cloned THROUGH THE BRIDGE
  (`build_rack.js --emit` → `SetTrackStateChunk`), never by rebuilding the file.

## 3 · The tracks — inputs by port NAME

- A MIDI device number is Reaper's own; never write it into the file. `reaper/bridge/jobs/make_tracks.lua` sets
  each track's input by port name, arms it, turns monitoring on, inserts the sampler if the track has none.
- Percussion: one track per instrument, each on ITS channel of the percussion port (`make_perc_tracks.lua`).
- Re-running `make_tracks.lua` puts every listed fader back to 0 dB — after the trims, run `apply_trims.lua` again.
- The AI may open Reaper on the file itself; the bridge's heartbeat says when it is ready.

## 4 · Does it sound? — three tools, smallest first

- `reaper/bridge/jobs/sound_check_vkb.lua` — one note into a track from INSIDE Reaper (no port). Proves a clone.
- `tools/note_to_port.ps1` + `peakwatch.lua` — one note through a port, the meter read. Proves the port.
- `tools/key_sweep.js "<track>" --channels … --keys …` — many keys, which sound. Proves a range or a channel map.
  A bowed or slow sound needs `--hold 2.5`; an Xsample preset is chosen with `--cc0 n`.
- **A silent test is not a diagnosis.** Ask Reaper what MIDI it received (`MIDI_GetRecentInputEvent`) before
  blaming the plugin; check the key is inside the instrument's mapped range.

## 5 · The first sound from the composer score

- `tools/build_first_sound.js` → a save with one note on every TRACK. He plays it in his Chrome.
- BEFORE he does: capture the app's own playback on the throwaway server (`docs/VERIFICATION_RECIPE.md`) and read
  the port and channel of every note.
- **A lane whose channels 2 … 4 are OTHER instruments or patches needs `curveTechniques: []`** in its recipe —
  otherwise a held note is dealt to the curve channels and plays the wrong instrument. (Percussion; a mallets lane.)
