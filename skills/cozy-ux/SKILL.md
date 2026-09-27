---
name: cozy-ux
description: Use when auditing, shaping, hardening, or polishing ANY user interface for usability through Don Norman's eyes (The Design of Everyday Things, Emotional Design, Living with Complexity) — an app screen, a settings page, a form, an upload or dropzone, a dashboard, a rail or navigation, an empty state, a long wait, a review or approval step, a destructive action, an onboarding, a wizard, a checkout. Human-centered design for people as they actually are: the person must be able to tell what to do, do it, and tell whether it worked, WITHOUT a manual — a label or helper sentence that has to be read before a control can be used is a confession that the control failed. Grounded in the Seven Stages of Action, the Gulfs of Execution and Evaluation, discoverability's six principles (affordances, signifiers, constraints, mappings, feedback, conceptual model), knowledge in the world, slips vs mistakes, design for error, and the three levels of emotional design. Reach for this whenever someone says "run Norman on it", "is this intuitive", "would someone get stuck", "too much helper text", "does this need a manual", "can't tell what to do", "can't tell if it worked", "make it more Apple", "this should just be obvious", or points at any screen or flow and wants it checked or made better for humans. Keyword functions: `audit` (find the usability blockers, read-only), `shape` (design a new screen or flow so nobody can get lost), `harden` (design against error — slips vs mistakes, constraints, undo, forcing functions), `polish` (final pass — strip the manual, close the last gulfs), `glance` (judge one rendered screen at 2-second scan speed through the visceral level). One screen or one flow at a time. Not for aesthetic taste or brand voice.
version: 0.3.0
user-invocable: true
argument-hint: "[audit|shape|harden|polish|glance] [screen, flow, or route]"
---

Audits and improves user interfaces the way Don Norman would — any app, any screen, any flow.
The unit of design is **a person trying to do something with a thing someone built**. Norman's
framework applies literally: every action is a small loop of the Seven Stages (form a goal, work
out what to do, do it, read what happened). A thing is usable when that loop closes at every step
with no instruction manual. It fails wherever a **Gulf of Execution** opens (the person can't tell
what to do or how) or a **Gulf of Evaluation** opens (they did something and can't tell what it
meant or whether it worked).

This skill finds those gulfs, names them at the exact control or step, and closes them.

**The stance (Norman's, and non-negotiable here):** when a person fails, the design failed. "Human
error" is the name engineers give to bad design. We design for humans as they are — scanning, not
reading; distracted; on a phone; holding one goal at a time — not as we wish they were.

## Setup

Do these before running any command. They are what let you audit the real experience rather
than the code's idea of it.

1. **Resolve the target to ONE screen or ONE flow, and find its rendered truth.**
   - **An app screen or flow:** the target is a route, a component, a URL, or a description ("the
     team settings page", "upload → first video"). Find what defines it (the page, its
     components, the store or data it reads) and **reconstruct what the person actually sees, can
     do, and is told** at each moment: every control, its label, its state, the text near it, what
     changes when it is used. Drive the browser when the rendered reality is otherwise unknowable;
     screenshots beat guesses. If you cannot tell how something renders, say so.
   - If the target names a whole app or module, ask which single screen or flow. **One at a
     time**; a pile audited at once produces mush.
2. **Read [reference/field-guide.md](reference/field-guide.md).** Non-optional for every command.
   It is the Norman lens applied to apps: the stance, the Seven Stages, the two Gulfs, the six
   principles of discoverability, the no-manual law, knowledge in the world, the error taxonomy,
   design for error, complexity vs confusion, conventions, feedback, flows, and a cheat sheet of
   where each kind of surface (forms, settings, uploads, waits, approvals, destructive actions,
   navigation, dialogs) tends to fail. Without it you fall back to generic UX-review reflexes and
   lose the point, which is to see the thing the way Norman saw doors, stoves, and phones.
   **Also read [reference/visceral-guide.md](reference/visceral-guide.md)** for `glance`
   (non-optional there) and for any `audit` whose target renders visually — the visceral and
   reflective levels of Emotional Design that decide whether the person engages at all.
3. **Read the command reference** for the function invoked (`reference/<command>.md`). It
   defines that command's flow. Skipping it drops steps the user expects.

## The lens in one screen

Judge every control and every step against Norman's principles. The field guide expands each.

- **Conceptual model.** Does the screen build the *right* model of what this thing is and does,
  and never a wrong one? The designer's model reaches the person only through the **system
  image** — what is on screen. If the model needs a paragraph to arrive, the system image failed.
- **Discoverability.** By looking, can the person tell what state things are in and what they
  can do? Its parts: **affordances** (what actions are possible), **signifiers** (the visible cue
  that says so — a button that looks pressable, a field that looks typeable, a drop target that
  looks droppable), **constraints** (what is not possible is not offered), **mappings** (the
  control sits where its effect is, and moves the way its effect moves), **feedback** (every
  action produces an immediate, specific, visible result).
- **The no-manual law.** "When simple things need pictures, labels, or instructions, the design
  has failed." Text on a screen comes in two kinds. **Instruction** — what a control is for, how
  to use it, what to pick — is a confession; delete it and fix the control. **Consequence** —
  what will happen, what can't be undone, a right or a cost or a deadline — is knowledge the
  world owes the person; keep it, one line, at the point of action. The **cover test** settles
  every sentence: hide it; if the flow still walks, it was never load-bearing.
- **Knowledge in the world vs in the head.** Put what the person needs where they need it —
  as defaults, constraints, visible state, previews, labels ON controls, conventions. Not as
  paragraphs. Memory is expensive; and a screen where everything shouts has no visibility left.
- **Slips vs mistakes.** A **slip** is the right intention, wrong action (mis-tap, look-alikes).
  A **mistake** is the wrong intention from a wrong model (the design taught them wrong). Fix
  slips with constraints and layout; fix mistakes with the model. Never fix either with more words.
- **Design for error.** Errors are normal use. Make them impossible (constraints), visible,
  cheap to undo, and hard to make when irreversible. Confirmation dialogs mostly fail — people
  confirm the *action*, not the *object*; prefer undo.
- **Complexity vs confusion.** Apple ships no manual not because it ships fewer things, but
  because each thing signifies itself and follows a convention. Hidden state behind a "simple"
  surface is worse than visible richness with a good model. Never trade discoverability for
  the look of simplicity.
- **The visceral layer.** Before any loop runs, a ~50 ms appearance verdict decides whether the
  person engages. A screen can close every loop and die at the glance. `glance` owns this.

## Commands

| Command | What it does | Reference |
|---|---|---|
| `audit [target]` | Walk the screen or flow as the person, find and rank every usability blocker, count the words that must be read to use it. Read-only report with the Six Gulfs Scorecard. The flagship: "run Norman on this." | [reference/audit.md](reference/audit.md) |
| `shape [idea]` | Design a new screen or flow so the person can't get lost: who, what activity, the conceptual model, then every action loop — before any code. | [reference/shape.md](reference/shape.md) |
| `harden [target]` | Error-proof what exists through Norman's error framework: slips vs mistakes, constraints, undo over confirm, forcing functions with reachable releases, graceful recovery. Edits. | [reference/harden.md](reference/harden.md) |
| `polish [target]` | Final Norman pass: strip the manual (cover test), close the last half-open gulfs, tighten feedback, mapping, and visible state. Edits, lightly. | [reference/polish.md](reference/polish.md) |
| `glance [screen]` | Judge ONE rendered screen at scan speed through the visceral level: 2-second test, squint test, bold-words-only read, signifiers, density, affect. Read-only Visceral Scorecard. | [reference/glance.md](reference/glance.md) |

## Routing

1. **First word matches a command** (`audit` / `shape` / `harden` / `polish` / `glance`): run
   setup, read that command's reference, follow it. Everything after the command is the target.
2. **First word doesn't match but the intent is clear** ("where would someone get stuck on the
   upload screen?" → `audit`; "design the invite flow" → `shape`; "make sure nobody deletes a
   language by accident" → `harden`; "there's too much helper text" → `polish` if they want it
   fixed, `audit` if they want it found; "does this land at first glance" → `glance`): load that
   command and proceed as if invoked.
3. **No argument**: offer `audit` on the screen or flow the conversation implies, then show the
   table. Never auto-run; recommend and let the user confirm.
4. **No clear match**: treat it as a general Norman review of the named target — setup, the
   lens above, the field guide.

## Scope discipline

- **One screen or one flow at a time.** Sweeping an app means doing its screens one by one and
  saying so. `glance` the key screens; `audit` the flow between them.
- **The auditor is not the author.** If you wrote the copy or the control under review, say so,
  and run the cover test literally (hide the text, walk again) rather than re-reading your own
  justification. Thirty rounds of self-audit passed a manual once; the rule exists because of it.
- **Usability, not decoration — with the visceral amendment.** Typeface taste, palette, brand
  voice, and prose rhythm stay out of scope; name the owning skill and move on. Visceral
  FUNCTION — can the screen be parsed at a glance: hierarchy, density, signifiers — is in scope
  and `glance` owns it. "The serif feels wrong" is taste; "the squint surfaces the wrong element"
  is a finding; "this field needs a sentence to be understood" is a finding.
- **Findings name the exact control and quote the exact content.** "Improve feedback" is
  useless. "The Invite button on /settings/team gives no visible result after press — the
  email is sent, the form clears, nothing says so: a Gulf of Evaluation at the moment of
  commitment" is a finding. Specificity is the entire value.
- **Norman prefers making the right action easy to forbidding the wrong one.** When you
  recommend a fix, reach for a default, a constraint, a signifier, or an undo before a block,
  a dialog, or a sentence.
