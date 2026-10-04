# ‹repo name› — ‹the piece's short name›

**Title: ‹the working title — it may come later›**

Composition #‹N› in the custom-composition-system lineage
(#1 `string_quartet_no1-composer` → #2 `composition_for_two_pianos_and_two_percussion`
→ #3 `for_bass_clarinet_harp_and_accordion` → #4 `for_seven_tubas` → #5 `septet_2026`
→ #6 `septet_LGMF_2026` → ‹… → this›).

Written for ‹the occasion or the call — and whether the AI has read it›.

Instrumentation, ‹fixed by the composer, the date, journal D1›: ‹…›

**THE PROFILE** (the new-piece protocol's 2.1 — it decides which of containers 3 … 8 this piece runs):

- the kind of start: ‹copy-forward · from a sandbox · fresh›
- the layers taken: ‹the instrument · the score · both · neither›
- the score type(s): ‹the animated scrolling score · a new type · none›
- the protocol version run: ‹v1› — `composition-system/protocol/NEW_PIECE_PROTOCOL.md`

‹What this piece inherits and how: the stack · the delivery format · the contract between the composer's save and every
downstream score · the libraries. One short paragraph each, with the journal's D-numbers.›

**State of the piece (keep this line current):** **► ‹one line: where the piece stands · the next step · which journal §2
block is the cold-start block.›**

## READ FIRST — how to work here

**`docs/AI_METHODOLOGY.md`** is the composer's standing instruction on scoping, decisions,
and confidence (inherited unchanged from piece #4 by way of #5). It governs everything below
and outranks the working-preference docs where they conflict. In short: fix what blocks the
piece and flag the rest to `docs/NITS.md` · don't make the composer decide minutiae ·
prefer one robust build over a fragile one · **a confidence claim must be verified in the
running app** · no clear evidence means no diagnosis.

The composer's own rule for a port (said of the last one, 2026-09-03; it holds here):
*"I don't want to get too bogged down in technical details of porting and code and such,
but I want to do a good, solid job and not leave out things now that might bite later ...
leaving everything we can for when the time comes."* Keep the conversation at the
conceptual level; consult the code yourself.

**How he reads (his user-level CLAUDE.md, 2026-08-24):** succinct
language, clear spatial division between chunks, short lines, one idea per chunk, bullets
first. A one-line TL;DR leads any reply over two paragraphs. One step at a time.

‹If the piece takes THE SCORE layer with the animated scrolling score, add the device-sheet rule here: a NEW notation begins
with a DEVICE SHEET (`docs/PLANNING_METHOD.md`); the rules are `notation/registry/rules.json`, read through the generated
`docs/ENGRAVING_RULES.md`; change a ROW, never a code number.›

## Orient from docs, not from scanning

- **What the pieces share — the index, read at every session start:** `composition-system/INDEX.md`
- ‹**ANY WORK ON THE SOUND PATH — READ THIS FIRST:** `docs/DYNAMICS_LAW.md` — if the piece takes THE INSTRUMENT layer›
- **What now / what next:** `docs/PLANNER.md` — the **NOW ►** line, then the outline
- **Living plan:** `docs/PLAN.md` — stable IDs; rules in its header; its § 0 is the protocol, for this piece's profile
- **Session state, decisions:** `docs/PROJECT_JOURNAL.md` — §2 Resume Here first
- **The lab journal:** `docs/RUNNING_LOG.md` — append-only, written as the work happens
- **The sketch pad:** `docs/COMPOSITION_NOTES.md` — the composer's musical ideas, verbatim
- **Building a plan item / analyzing an issue for the plan:** `docs/PLANNING_METHOD.md` — three phases, fixed formats
- **Where this start left the protocol:** `docs/PROTOCOL_DEVIATIONS.md` — one line at the moment of each deviation
- **Faults met while composing:** `docs/SWEEP_LIST.md` · **Deferred, real but not now:** `docs/NITS.md`
- **The performance notes — what they must cover, collected as decided:** `docs/PERFORMANCE_NOTES.md`
- **Working preferences & routines:** `docs/HOW_WE_WORK.md` · `docs/SESSION_PROTOCOL.md`
  · `docs/SESSION_HYGIENE.md` (clear between chunks; the docs are the handoff)
- ‹this piece's own pointers, added as the docs appear: the settings that live only in his plugins · the notation standards · the tool docs›

Do NOT scan or analyze the codebase unprompted. Name the question first, then read only
what answers it. High bar for subagents / background processes.

**After `/clear` + `/postclear` (his standing rule, 2026-09-11):** play back, then **STOP
and ask**. No edits, no builds, no tool calls beyond the resume reads. Start only on his
word. At `/session-start`: orient, agree the agenda, then work.

## Standing practice: the lab journal (composer, 2026-09-03 — not optional, never asked for)

> *"I'd like to keep a running journal like lab notes, so I can look back on decisions or
> comments, theory, philosophy, etcetera, or how we actually made something, if I wanted
> to write a paper later about this — and I would expect the AI agent to do this
> automatically as a habit."*

The rules, adopted from `live-electronics-engine` (its CLAUDE.md and `docs/journal/README.md`):

- **When:** at the end of any exchange that produced a decision, a result, a rejection, a
  measurement, a theoretical or philosophical point, or a question worth remembering.
  Not at session end — by then the reasoning has blurred.
- **What each entry carries:** what prompted it, in the composer's words, quoted not
  paraphrased · what was tried, in order · the numbers · what was rejected and why (dead
  ends at the same weight as successes) · what was decided, and why that rather than the
  alternative · corrections as NEW entries, never edits.
**EXTENDED TO THE COMPOSING ITSELF (composer, 2026-09-18, at the start of phase 1):** *"could you remember to take
journal notes during the comp process and remind somehow future agents to do the same, lab notes so if I want to come back
and write a paper on how I wrote this piece."* The lab journal does not pause when the building stops and the WRITING
starts. Every compositional exchange that settles something goes into `RUNNING_LOG.md` as it happens — the material chosen
and why, what was tried and rejected, what he heard, the numbers behind a harmonic or rhythmic decision, the theory or the
reference behind a move. His musical ideas still go to `COMPOSITION_NOTES.md` verbatim; the RUNNING_LOG is where the
REASONING and the process live. **The test: could someone write the paper "how this piece was written" from the log alone?**
Future agents: this is not optional and he will not ask for it.

- **Append-only.** The journal is the record of how the thinking went; it is never tidied.
  Current state lives in the plan, the journal §2 and the READMEs, which are rewritten freely.
- **The sketch pad is the same habit for musical ideas:** every compositional idea the
  composer voices goes into `docs/COMPOSITION_NOTES.md` verbatim, dated, the moment it is
  said — with the AI's reading kept separate and marked as such.

‹The section below — only while the morph tool lives in this piece. Its closing sentences are piece #6's; rewrite them.›

## Standing practice: the morph notes (composer, 2026-09-06 — #5's CN-29)

> *"I want to institute a process where we're taking notes in a central document that will inform the eventual revision."*

Every remark about the morph tool — an awkwardness, a wish, a piece-specific adjustment made, what an all-purpose tool would
need — goes into **`docs/MORPH_NOTES.md`** §3 the moment it is said, dated, verbatim, the AI's reading marked. The tool is
adjusted for the current use now; the file is the memory for its revision into *"an easier to use all purpose tool"* after the
last piece or this one. Not optional, never asked for — the lab journal's rule, for one tool. The file was carried WHOLE from
piece #5 (he named "this piece and the next piece" when he started it); this piece's form is a rondo whose refrain is a morph
(LG-6), so the file matters more here than it did there.

## THE RHYTHM — next steps · model · clear (standing, composer 2026-08-23; carried whole 2026-09-17)

*(It was in piece #4's CLAUDE.md and the copy-forward to piece #5 dropped it, so it loaded
in no septet session for a week and the advice came only sometimes — his own verdict,
2026-09-10: "This was happening for a while, but then is inconsistent." It is carried here
from the first commit, deliberately.)*

**REFINED by him, 2026-09-18 (guidelines, not hard rules — his user-level CLAUDE.md, "The shape of a working reply"):**
*"the next model clear dialog is good, but lets keep that more focused and local, only when we are moving on to something
that needs a model change or clear"* — and *"no more things left to do, or left pending or even whats next unless I
specifically ask."* So **in the CHAT:** model / clear advice only at a real switch point, one or two lines; no next-steps
list unless he asks; replies are a goal heading, a short ✓ trail, the one thing in hand with a brief why per step, and ONE
compact notes section at the bottom for the honest side-matter. **And (2026-09-18, after the key-mapping sweeps):**
*"avoid unnessary extra work unless asked for, so like verifications and such unless we write these into a plan as necessary
verifications and qc"* — no probe, no cross-check, no QC pass that he did not ask for or that the plan does not name as a
required step; if something looks worth checking, ONE line offering it, and he decides. This does not relax
`AI_METHODOLOGY`'s rule that a confidence CLAIM must be verified in the running app — unverified simply means unclaimed.
**In the DOCS nothing changes:** journal §2's NEXT STEPS ·
MODEL · CLEAR table is still kept current — it is the handoff, and it is what makes the chat free to stay on one thing.
The paragraph below is the 2026-08-23 original; read it through this.

At every juncture — a chunk wrap, a milestone, a mode change (execution ↔ conversation),
or when asked "where are we" — the AI **states the next 2–4 logical steps, each with a
recommended model and whether to clear before it**, and **says out loud when a good clear
or switch point has arrived** ("this is a good time to clear", "switch to Opus for this").
Not when asked — as a habit, like the lab journal. The rule for the recommendation is in
`docs/SESSION_HYGIENE.md` § Model strategy (Fable = judgment / verdicts / design;
Opus = executing a written plan; clear at milestones and mode changes; the cold-execution
test before any clear).

**The running thread lives in `docs/PROJECT_JOURNAL.md` §2 → "NEXT STEPS · MODEL · CLEAR".**
Keep it current as steps complete — it is the first thing a model reads after a clear, and
it must say what is next, with what model, right now.

**Fable's allotment is separate and is the one he watches** (composer, 2026-09-10). So the
routing advice is also credit advice, and these bind every Fable turn:
- **Fewest round trips.** Batch independent reads and tool calls into one response; no
  exploratory reads; name the question before opening anything.
- **No screenshots unless the screenshot IS the proof he asked for.** `read_page` otherwise.
- **Never spawn a subagent on Fable.** If one is ever justified, pass `model: "sonnet"`.
- **Wrap on Opus.** `/checkpoint` and `/session-end` are mechanical work at the long,
  expensive end of a session: switch to Opus, wrap, `/clear`, switch to Fable, `/postclear`.
- **A `Resume reads:` list names what the NEXT STEP needs, not what the last session wrote.**
  Every line on it is re-read in every turn of the session that follows.

## Apps

- ‹**Each app:** how it is started · its port · what it is. The pair of ports is the next in the lineage
  (#3 5100/4600 · #4 5200/4700 · #5 5300/4800 · #6 5400/4900).›
- ‹**`.claude/launch.json`:** the names · a throwaway server for verification · a `<prev>-<port>` entry that runs the
  previous piece's server side by side while it is unfinished, removed when it is.›
- ‹**The MIDI ports** — their prefix, and why: loopMIDI ports are machine-global and the last piece's rack may still be live.›
- ‹**The notation app · print · video** — if the piece takes THE SCORE layer.›

⚠ ‹**Standing warnings:** the ports never to bind · the AI never holds his port and never saves from its own browser
pane · the in-app browser has no Web MIDI, so every MIDI path is verified on his Chrome · …›

**Checks this piece owns:** ‹each battery · its count · when it must be run.›

## Reference repos (read-only context)

- ‹**#N** `path` — what it is the source of, and what to consult it for.›

Consult only when a specific named question requires it. Never edit them.
‹If one has the composer's own uncommitted files, say so here: never stage, move or edit anything there.›

## Git

- Commit at the natural wrap of an approved chunk; reference plan IDs in messages.
- Stage **explicit paths only, never `git add -A`**.
- **Push:** ‹ASKED at the protocol's 2.2 — pushing is outward-facing and is never inherited from the last piece.
  Write his answer here, with the date and his words.›
