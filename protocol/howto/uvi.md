# UVI Workstation — IRCAM Solo Instruments 2 · Prepared Piano 2

> Written 2026-10-20 at the Switch~ piece's container 4 (the harvest's H6-24), from the record: piece 5 *Recombination*
> `septet_LGMF_2026` RUNNING_LOG §20 … §23 · §56 · §85 and its `docs/RACK_SETTINGS.md` § 1; piece 4 *Scattered Substance*'s flute
> (`septet_2026/sandbox/instruments.js` l. 19 …). Short on purpose; the reasons and the numbers are at those sections. The tools
> named live in the latest piece's repo (`switch_2026` today): `tools/uvi_state.js` · `tools/uvi_edit.js` · `tools/apply_uvi_parts.js`.

## 1 · What an instance is

- One UVI Workstation instance = up to **16 PARTS**, one MIDI channel each. **One part per PRESET** (a technique or a keyswitch
  bank), loaded in the browser's alphabetical order from Ordinario. A technique KEY in the recipe names the preset; a KS preset
  carries the switch note (`ks`) the prelude latches before the note.
- **On UVI a channel IS a technique.** A curve channel cannot be "the same instrument again" as a Kontakt slot can: it must be a
  CURVE COPY of a technique — three copies of Ordinario on their own parts (the dynamics law's curve bank).
- **More than 16 presets → a second instance on a `b` port** (`Fluteb` · `LGBassoonb` …): the overflow and the three Ordinario
  curve copies live there. The recipe's `channels.curve` for a UVI instrument names the `b` port. Ask the preset COUNT before
  the tracks are made (the protocol's 4.1).

## 2 · The loads — his, once per preset, never twice

- **A preset must be loaded once in the GUI.** `ProgramPath` in the XML is a label UVI writes, not a reference it loads: a program
  conjured by path is an EMPTY labeled part (−154 dB). A preset the GUI has loaded once can then be **cloned, moved,
  re-channelled and re-instanced as text** (§22, proven with audio).
- He loads each preset into its part in the plugin's browser, in order; says "done loading". Everything after is text.

## 3 · The state as text (the AI's)

- `node tools/uvi_state.js info "Flute SI2"` — the parts: channel · gain · output · program. `decode … x.xml` the XML;
  `encode … x.xml --push` an edited XML into the running instance; `roundtrip … --push` proves the tool on that instance first.
- The header is **496 bytes** on this machine's UVI (a 312-byte reading once bit — §22): the tool reads the compressed length
  from the BE field before `UVI4` and rewrites every length field in its own byte order; the tail is kept. Prove the round trip
  before the first edit on a new UVI version.
- The curve copies: `tools/uvi_edit.js clone` (a loaded Ordinario's body onto parts 3 · 4 · 5, or onto the `b` instance).
- The recipe is DERIVED: `node tools/apply_uvi_parts.js` reads which part (port, channel) holds each preset and writes the
  `UVI_PARTS` block of `sandbox/instruments.js`. Re-run after any change to an instance. Nothing is typed.

## 4 · THE DIAL THAT MATTERS — "Dynamic Amount" 0.70 → 1.00

- Expression block → **Dynamic → Amount**. The factory **0.70** gives an SI2 instrument about **5 dB** from the quietest velocity to
  the loudest; **1.00** gives **23–32 dB** (§56). Expression Mode stays **Velocity** — the velocity IS the dynamic (piece 4's D13).
- **Set it on the main part AND on every curve copy, on both instances** (§85: it was set on part 1 of the main instance and the
  piece never played that part — every drawn note went to copies still at 0.70). The harvest's H-18: a technique brought in later
  needs its Dynamic checked on both.
- **To check without guessing:** `uvi_state.js decode` → the `Dynamic="…"` attribute on `<ScriptProcessor Name="EventProcessor0">`,
  once per part. A read before the card (container 5), never after.
- It is HIS hand in the UVI window (a push can carry it, but the record set it by hand); `RACK_SETTINGS.md` § 1 lists every part set.

## 5 · The masters, and what else is hand-set

- **The SI2 instruments' masters at −6 dB** (piece 5's pre-flight: the brass clipped at CC7 127, fff) — every hand-set value and
  how to revert it goes in the piece's `RACK_SETTINGS.md`.
- The velocity layers of Ordinario: 1–66 · 67–116 · 117–127 (three dynamic layers on every instrument).
- A keyswitch zone sits UNDER the instrument's range, an octave apart between instruments (the flute's C1 = MIDI 36 where the
  tuba's was lower): check each KS preset on its red keys as it loads (piece 4, l. 26 …).

## 6 · The order, at a new piece

ports (4.1, the `b` port if the count asks) → the tracks (`build_rack.js` clones a loaded instance from an earlier rack; a new
instrument is a bare track, the bridge inserts UVIWorkstation) → **his loads** → the state read (`uvi_state.js info`) → the curve
copies cloned → **Dynamic Amount 1.00 on every part the piece plays** → `apply_uvi_parts.js` → the first sound → the card (5).
