# shape — design a new screen or flow so the person can't get lost

Use before building, when the user wants a *new* screen, flow, or feature, or wants an existing
one rethought from the studs. `shape` produces the thinking that makes the build good: who the
person is, what they are doing, the conceptual model the screen must carry, and every action loop
— established before any component is written. Norman's point: most usability failures are
decided at design time, not fixed at polish time.

This command plans, then (only after the user confirms the plan) builds. It does not silently
jump to code.

## Phase 1: the person and the activity, first

Human-centered design starts outside the app. Answer, in conversation with the user (ask, don't
assume; 2–3 questions per round; if the user has watched a real person do this, that outranks
everything else):

- **Who, in what situation.** Not a persona name — a moment. "A team volunteer, Monday
  evening, phone, with the weekend's recording in a WhatsApp thread." What is in their head walking
  in? What do they already know how to do from other apps?
- **The activity.** What are they trying to get done, in their words? What does "done" look
  like to them — not to the system?
- **The one model.** In a single sentence the person could repeat afterward, what should they
  believe this thing is and does? ("Drop in the recording, get back every language, the lead approves
  before anyone sees it.") This is the designer's model; the screen's job is to project it
  through the system image so cleanly the person rebuilds it without being told.
- **The wrong models to prevent.** What plausible-but-false model might they already hold or
  form here? (Saved means applied. This setting is mine. Creating makes me a member.) The design
  must not reinforce it, and where it can, make it impossible.
- **The commitment points.** Where does the person spend money, send something to another
  person, publish, or do what can't be undone? Each one gets its consequence line and its
  error design up front.

Don't move on until the one-sentence model is sharp. A fuzzy model produces a screen that can't
be audited later because there's nothing to measure against.

## Phase 2: the loops — every action closes, and nothing needs a manual

Now design the screen or sequence. Each action is one Seven-Stages loop (field guide §2); a flow
is loops in series (§12). Design so every loop closes and nothing on the screen needs a sentence.

For each screen, decide:

- **The one thing this screen is for**, and the one control that does it — the single filled
  shape. Everything else is quieter.
- **What is visible by looking:** which state, whose scope (mine / everyone's), where I am.
- **What is offered:** only the possible (constraints); the obvious choice already made
  (defaults); the action on the thing it acts on (mapping).
- **What each control signifies on its own** — button, field, drop target, editable thing. If
  you catch yourself writing a sentence under a control, that is a design gap; fix the control.
- **The consequence line**, if any, at the commitment point: one line, what happens, what can't
  be undone.
- **The feedback** for each action: what changes, where, immediately. What the wait looks like.
  What the failure says, in the person's terms, with the next action attached.
- **The failure it must avoid:** the slip or mistake most likely here; design it out now with a
  constraint, a separation, an undo, a name on the control.

For a flow, also: the truthful start (what it takes, costs, returns, how long), the ramp before
commitment, the hand-off screens that must stand alone, and the end that says what is now true.

## Phase 3: present the brief, then stop

Present a compact brief and **end the turn**. The user confirms before you build anything.

Brief shape (tight; a clear plan is 6–10 bullets, not a wall):

1. **Who, in what situation, doing what.**
2. **The one model** (the sentence) and the wrong models it must kill.
3. **The screens or steps**, each as: its one thing → its controls and what they signify →
   feedback → the failure designed out. Show the ramp and the commitment points.
4. **Consequence lines**, verbatim, one per commitment point — and the sentence you *refused*
   to write, with the control change that replaced it.
5. **Open questions:** only genuinely unresolved ones; if you'd write "recommend X," decide X.

Then stop and ask for confirmation. The pause is the point; it separates shaping from premature
building.

## Phase 4: build (only after confirmation)

Build into the project's real source, matching its structure, conventions, and copy rules (read
a neighboring screen first; follow the project's CLAUDE.md or AGENTS.md). Every loop you build must close as declared in the brief, and
the cover test (§5) must pass before you call it done. Run the project's gates (typecheck, lint,
build).

Hand off: suggest `/don-norman audit <target>` on the built thing — in the browser, with
screenshots — to confirm the loops close in practice. If a real person can be watched doing the
task, that beats the audit; say so.
