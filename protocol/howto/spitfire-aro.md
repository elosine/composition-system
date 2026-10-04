# Spitfire's own plugin — Abbey Road Orchestra Percussion

> From pieces #2 · #6 and the Decibel piece (`septet_LGMF_2026` RUNNING_LOG §33 … §42; `decibel_TENOR_2026`
> RUNNING_LOG §21 … §25).

## 1 · One instance per instrument

- The plugin cannot switch instruments by MIDI. So: one track per instrument, every track on the ONE percussion
  port, each filtering on ITS channel. Up to 16 per port.
- In the recipe the percussion lane needs `curveTechniques: []` (see rack.md § 5).

## 2 · Loading — the plugin's own browser is the only loader

- A state restores only what the plugin has itself loaded once. A preset never loaded costs ONE load by hand, in
  the browser, with the All-in-One selected.
- After that it is text: `tools/aro_state.js` reads the state (`info`), saves it (`decode` → `bank/aro_states/`),
  clones it onto another track, and switches the articulation inside a loaded preset (`edit --artic`).
- So an instrument an earlier rack holds is CLONED (rack.md § 2). A family preset that holds many instruments
  (Small Metals) gives any of them by a clone and an articulation switch.

## 3 · Key maps — almost never by hand

- The catalog (`bank/aro_percussion_catalog.json`, piece #2's) maps each All-in-One key by key. About half of its
  78 instruments are complete.
- **The check that needs no sound:** `aro_state.js info "<track>"` prints each articulation's top key. The
  All-in-One's top key = the catalog entry's last key → the map is this preset's.
- The plugin's preset names are not the catalog's ("China Cymbal" is the catalog's `china_cymbals`); match by
  the top key and the block layout, not by the name.
- A preset can hold several All-in-Ones (Suspended Cymbals: dark, mellow, bright; Toms: low, high). What he
  selects decides the catalog entry — read it back after he loads.
- TWO-HANDED LAYOUT repeats the keys 24 semitones up; the catalog's map says which it assumes.
- The keys start at C2 = 36, in blocks with gaps. A test note on a gap is silent.
- Then: the selection (`bank/perc_selection.json`, instrument → channel) → `tools/apply_perc.js` → the recipe.

## 4 · Never send CC7

- The plugin binds CC7 to its own gain. A probe or a schedule that sends it rewrites his mix.

## 5 · Round robins

- Left as shipped (5 or 6 per key, reset on transport). Measured by the loudest 400 ms of a hit.
