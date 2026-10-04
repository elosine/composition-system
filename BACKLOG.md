# BACKLOG — the standing "later" list

> Real, but not now. Each item is dated and names the piece it came from.
> **Refreshed at each harvest** (the protocol's step 1 and 9.6): the new harvest's LATER items are added below, under their own date.
> **An item taken up leaves by a dated line** — it is not deleted: `— 2026-MM-DD: taken up in <piece>, <plan ID>`.
> A reference like `NITS §264`, `LG-88` or `PLAN 1k` is the source piece's.
>
> Kinds: **fix** a tool or code fix · **rule** an engraving / layout rule · **arch** an architecture item · **feature** a wish.

## From piece #6, `septet_LGMF_2026` — its harvest of 2026-10-03 (12)

- **H-36** THE MORPH TOOL'S REVISION — `MORPH_NOTES.md` §4 is its spec (the cycles stated as a duration and a count · a take as a
  first-class source for every model · `min` as a hard floor · the ceiling read at the loudest level · the transition into a morph on
  the panel · `fadeWeight.to` for the release · a destination as a PARTIAL number · per-pair dials · the red "N hard" seams · `heard()`
  empty on a model that names its voices · `1k` the peaks against the sequence · *"something is off there"*) — his: *"after the last
  piece or this one"* — arch · MORPH_NOTES §4 · PLAN 1k · 1s · 1t
- **H-37** A GLOBAL volume normalization of the whole composer by the texture's split (B2) — *"if I ever want to tackle"* — arch ·
  NITS §264 · LG-88
- **H-38** The strikes drawer's INSERTED plain strikes may strike louder than Hear (read in the code, never captured; one field
  `velAbs`) — a capture first — fix · NITS §204
- **H-39** A curve channel freed 0.05 s after a note's end does not cover a release tail (one constant) — flag if a tail is heard to
  duck — fix · NITS §91
- **H-40** The partial checkboxes in the HARMONIC SERIES banner (1c.7, his MAYBE) — feature · NITS · LG-32
- **H-41** Texture's LIVE section hidden, not ported (the tubas' lanes and presets) — feature · NITS §199
- **H-42** `multitempo.js` LO / HI still the tuba bank's range — per-lane ranges when MT is first used — fix · NITS
- **H-43** The rest of phase 1 never reached: the rest of `1m` (the percussion row · re-attack) · the Rhythm sequence panel and `1l.8` ·
  multitempo as a rhythm source (LG-61) · the pattern tool LG-7 · the morph to a held beating LG-8 · conductions LG-3 — feature ·
  journal §2 table N0 … N3
- **H-44** `1u`'s offers: the strip's buttons blurred · a status that leads with WHY · `neighbours` in a morph from the others' "to"
  notes — feature · §396 · §400
- **H-45** The orange pitch line's corners eased like the green line (held at §513 D) · the percussion's rest (the ball's higher arc · a
  let-ring mark · `sub.` · the beam-vs-standard-stem at 378.5) — rule · journal §2 table — *if the devices return*
- **H-46** The generated scores share one object-id space (`wc-1 …` across scores) — a per-score prefix when convenient — arch · NITS §75
- **H-47** In Hear, CC7 127 pre-arms a channel 16 ms before its fader value — *"do not raise again unless heard"* — fix · NITS §158 · §162
