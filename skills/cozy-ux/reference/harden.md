# harden — design the screen or flow against error

Use to error-proof what exists. Where `audit` finds gulfs, `harden` closes the ones about
**error**: the spots where a person slips, gets trapped, is set up to make a mistake, or does
something they can't take back. Norman's error framework (field guide §7–§8) is the whole method.
This command edits.

Norman's governing idea: the best error message is the one that never fires, because the design
made the error impossible or harmless. So `harden` prefers redesign over warnings, undo over
confirmation, and gentle constraints over hard blocks. **It never fixes an error-risk with a
sentence.**

## Step 1: inventory the error-risks

If a recent `audit` exists, start from its error-design findings. Either way, walk the target
and at every control ask Norman's two questions:

- **Where can a person slip?** Right intention, wrong action. Look for: destructive beside
  routine (Remove next to Rename; a delete where the finger lands after Save); look-alike
  controls or chips; tiny or crowded targets; a field that silently accepts the wrong kind of
  input; a step that is easy to forget (leaving unsaved; saving and not re-rendering).
- **Where is a person set up to make a mistake?** Wrong intention from a wrong model. Look for:
  a setting whose scope is invisible (mine vs everyone's); a Save that means "future only"; a
  control named for what the code does; two paths where one silently does something bigger
  (create a team vs join one); an action with a cost or a recipient that isn't shown.

Then the third question, the one apps add to lessons:

- **Where is the irreversible?** Money spent, an email sent, a publish, a delete, a cancel of a
  running job. List every one.

Tag each risk **slip**, **mistake**, or **irreversible**, because the fix differs.

## Step 2: fix by kind

**Slips → constraints, layout, and forcing functions.** The person already understood; don't add
words. Instead:
- Separate or differentiate look-alikes; make the destructive control look destructive and sit
  apart; widen and space targets; keep the primary action clear of just-used controls.
- Constrain the input: the field accepts only what belongs; the impossible option isn't offered.
- Make the forgettable step impossible to forget — an interlock (can't leave with unsaved
  changes without a visible choice), a default that does the right thing, or a state that
  visibly says "not yet applied."

**Mistakes → the conceptual model.** The person did what they meant; what they meant was wrong
because the design taught it. So:
- Fix the system image: name the control for what it does to whom ("Remove Korean", "Invite to
  Acme"); put the shared thing under the shared owner; show scope on the screen.
- Where a model has to arrive before the action, deliver it as a preview or a visible state, and
  as a **one-line consequence at the point of action** only when nothing visual can carry it.
- If two paths are confusable and one is bigger, make the bigger one look bigger and name the
  smaller one where the person would look for it.

**Irreversible → undo first, then friction, then a real gate.**
- Can it be made reversible? A soft delete, a cancel window, a "put it back" — do that, and make
  the undo visible where the action was.
- If not: slow the action down in proportion — a distinct control, a distance, a typed name for
  the truly destructive. Name the object in the control. Show the cost or the recipient beside it.
- **Do not reach for "Are you sure?"** People confirm the action they intended, not the object;
  the dialog is dismissed by habit and catches nothing. A real gate is for the truly
  irreversible only, and it must show *what* is about to happen to *which* thing.

## Step 3: audit the forcing functions you already have

Every gate — a disabled Start, a locked step, an unsaved-changes guard, a "can't delete while
running" — is a forcing function. For each:
- **Is the gate visible?** The person must be able to tell the thing is blocking and *what
  releases it* — by looking, not by reading a paragraph. Add the signal if missing.
- **Is the release always reachable?** Confirm there is no state where the person has done what
  they can and the gate stays shut. A forcing function with no reachable exit strands them with
  the goal intact and no allowable action — the worst failure in the book.
- **Is the gate honest?** A gate that blocks for the system's convenience, not the person's
  safety, is friction; remove it or make it a default.

## Step 4: recover gracefully

For any action that can fail or land wrong: the failure shows where it happened, says what still
stands, and names the next action — one line each, in the person's terms, with the fix attached
(Try again, not re-upload). Nothing destroys their work; nothing scolds a good-faith attempt.
Norman: treat the action as an approximation of what was wanted, and offer the nearest right thing.

## Step 5: apply and verify

Edit the project's real source, matching its conventions and copy rules. Keep changes surgical: touch the controls with real
error-risk, leave working ones alone. Run the project's gates. Look at the result — in the
browser where possible — and confirm the constraint is *seen*, the undo is *findable*, and the
gate's release is *visible*.

In your summary, list each risk, its kind (slip / mistake / irreversible), and what you changed —
or why you left it and pointed elsewhere. Hand off to `/cozy-ux polish <target>` for the final
pass, or `/cozy-ux audit` to confirm the error-design axis moved.
