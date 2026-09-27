# polish — the final Norman pass

The last step, not the first. Use when the screen or flow is structurally sound and free of
error-traps, and you want to strip the manual, close the last half-open gulfs, and make every
action loop feel effortless. `polish` edits, but lightly: it removes instruction text, sweats
feedback quality, natural mapping, and visibility of state — the small things that separate a
screen a person *tolerates* from one they glide through.

Don't polish a target that still has P0/P1 blockers. Those are `harden` or `shape` work;
polishing around them is decoration on a broken loop. If a prior `audit` shows unresolved
P0/P1, say so and send the user there first.

## Pull in the prior audit

If `/don-norman audit` has run on this target, its P2/P3 findings, its instruction-word count,
and its "already working" list are your backlog and your do-not-break list. Start there. If not,
do a quick walk yourself (field guide §2 per control) so you're polishing against the real
loops, not a guess.

## Polish in order of leverage

**1. Strip the manual (field guide §5) — the highest-leverage polish on any app screen.**
Take every sentence on the screen that is not a label on a control, and sort it:
- **Instruction** (what a control is for, how to use it, what to pick, why this page exists) →
  delete it. Before deleting, ask what signifier it was covering for, and fix that if it is
  missing: a placeholder that shows the expected value, a label that names the effect, a
  default, a constraint, a preview, a convention. Then run the cover test: hide the sentence,
  walk the action; if it still walks, the sentence goes.
- **Consequence** (what happens, what can't be undone, cost, rights, deadline, honesty) → keep,
  cut to one line, and move it to the point of action if it isn't there.
- **Reassurance** ("this is the real thing", "nothing breaks", "safe to…") → almost always
  delete; where a real fear exists, answer it with a visible state, not a promise.
Report the instruction words before and after. Do not re-read your own justification for a
sentence; the cover test is the judge.

**2. Feedback quality.** Every action's feedback is a loop closing; make each one carry weight:
- **Specific, not generic.** "Saved" closes nothing when the person can't see what changed. The
  thing they touched changes; the count moves; the state word flips; the new row appears.
- **Located.** Where the eyes are — on the control, on the row — not a corner toast.
- **Immediate**, within the action; and **not too much** — remove feedback that fires for
  things nobody asked about, so the one that matters is heard.
- **Waits and failures speak in the person's terms:** what's happening, how long, whether it's
  safe to leave; on failure, the failing step's own sentence and the next action.

**3. Natural mapping.** Tighten the places where control and effect don't quite line up: the
per-thing action on the thing's row; the shared setting under the shared owner; the primary
action in the primary place; the back where back goes.

**4. Visibility of state.** Make the current state legible without thought: where am I (which
team, which video); what is this setting's scope; is this saved, applied, pending, live; what
enables the disabled button. If a state has to be explained, show it instead.

**5. Conceptual-model consistency.** A final read for through-line: the same nouns everywhere
(the person's, not the code's); the same shape for the same kind of thing; no screen where the
framing shifts without a bridge. The end of a flow says what is now true.

## The arc's peak and end

Norman cares that frustration compounds and that endings colour the whole memory. Find the
hardest moment in the flow and confirm the person gets relief there — a visible result, not a
sentence. Confirm the end lands as "here is what happened and what you can do now," not a flat
stop.

## Apply and verify

Make surgical edits to the project's real source, matching its conventions and copy rules. Polish touches many small things but changes no
structure; if you find yourself restructuring, stop — that's `shape` or `harden`. Run the
project's gates, and look at the rendered result: the screen with the sentences gone must still
walk.

In your summary, list the sentences removed (with the signifier that replaced each, where one was
needed), the consequence lines kept, the loops tightened, and the instruction-word count before
and after. If you left something because it's really a voice or taste matter, name the owner
rather than reaching outside Norman's lane. Suggest a final `/don-norman audit <target>` to
confirm the score moved and nothing regressed.
