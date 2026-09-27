# audit — walk the screen or flow as the person, find every usability blocker

The flagship command. Read-only: you diagnose and report, you do not edit. The deliverable is a
specific, ranked list of the exact spots where a person's action loop fails, each named at the
control or step and tied to the Norman principle it breaks, plus the count of words they would
have to read to get through. `harden` and `polish` fix them later.

"As specific as you can" is the whole job. A finding that doesn't name the control and quote
its content is not a finding.

## Method: walk every action in order, in character

You have the rendered truth of the target (screens, controls, states, text — from source, the
browser, or screenshots) and the field guide. Now become the person — the coldest plausible one:
first time here, on a phone, mid-distraction, holding one goal — and walk from arrival to the
goal, one action at a time. Do not skim to the interesting screens; gulfs hide in the boring
ones (the settings page that opens with a paragraph, the Save that says nothing).

For each screen, and each control on it that the goal touches, run the loop (field guide §2):

1. **Name it** — route or screen, the control, and a short quote of its label or content so
   the finding is locatable.
2. **Goal / intention:** what does the person want, and can they tell what this screen wants of
   them *by looking*? (Gulf of Execution; signifiers, §4.)
3. **Execute:** can they do it without slipping? (Look-alikes, tiny targets, a destructive
   control where the finger lands.)
4. **Perceive / interpret / evaluate:** after they act, can they tell what happened and whether
   it worked? (Gulf of Evaluation; feedback, §11.)
5. **Model check:** does this screen build the right conceptual model and nothing false? Is it
   consistent with the screens around it? Is scope visible — mine or everyone's, now or future?
6. **Memory check:** does it need a fact from a screen the person left? (§6)
7. **The manual check (§5):** for every sentence on the screen that is not a label on a
   control, classify it — *instruction* or *consequence* — and run the cover test: hide it;
   does the flow still walk? Count the instruction words. Each instruction sentence is a
   finding whose real subject is the control it was covering for.

Then zoom out and run the **arc-level checks** (§12) on the flow as a whole, and the **surface
cheat sheet** (§13) against each screen type you met.

**If you authored any of this** — the copy, the control, the layout — say so in the report and
run step 7 literally rather than from memory. The author of a sentence can always justify it.

**Final consideration — the visceral pass (rendered targets only).** Finish by running the
glance battery from [visceral-guide.md](visceral-guide.md) §5 on the key screen(s): 2-second
test, squint test, bold-words-only read, signifier check, density at the decision, affect read.
The behavioral walk scores whether each loop closes; this pass scores whether the ~50 ms
appearance verdict lets the person reach the first loop at all. Skip it only for targets with
no rendered surface, and say so.

Keep a running list. Most controls produce zero findings; that's correct. Flag only real loop
failures, not style preferences.

## Scoring: the Six Gulfs Scorecard

Score the target 0–4 on each of six lenses. Be honest; a 4 is genuinely excellent, and most real
screens land 2–3 on their weak axes. The score exists to make the weak axis obvious and to show
movement on re-audit, not to reward a number.

| # | Lens | What a low score looks like | What a 4 looks like |
|---|------|------|------|
| 1 | Conceptual model | A screen installs a false model (saved = applied; mine = everyone's), or the framing shifts between screens | One coherent model carried by the system image alone, nothing false, consistent end to end |
| 2 | Discoverability (signifiers, constraints, mappings) | Controls don't look like what they do; the possible isn't offered and the impossible is; actions far from their objects | Every control signifies itself; only the possible is offered; the action sits on the thing it acts on |
| 3 | The manual (instruction text) | Fields need sentences; pages open with paragraphs; a tour explains the screen | Zero instruction text; only one-line consequences at the point of action; the cover test removes nothing |
| 4 | Feedback | Save says nothing; waits show a spinner; failures are generic; success lands off-screen | Immediate, specific, located feedback that closes every loop; waits and failures speak in the person's terms |
| 5 | Knowledge in the world (memory load) | An action needs a fact from a screen the person left; IDs copied by hand; scope invisible | Defaults, constraints, visible state, and previews carry what each action needs, where it happens |
| 6 | Error design | Delete beside Edit; "Are you sure?" instead of undo; gates with no visible release; a good-faith action punished | Slips constrained, mistakes designed out, undo where possible, every forcing function has a reachable release |

**Score bands** (out of 24): 22–24 excellent (ship, minor polish) · 17–21 good (fix the weak
axes) · 11–16 rough (real work before a person is served) · 0–10 broken (the loop fails
somewhere central; redesign that stretch).

## The report

Present this in chat as the primary deliverable. Lead with the verdict, not the table.

### 1. The person's-eye verdict
Two or three sentences: could an ordinary person get from arrival to the goal, forming the right
model, always knowing what to do and whether it worked, without reading anything but labels and
consequences? Name the single biggest gulf up front.

### 2. Scorecard

| # | Lens | Score | Sharpest finding |
|---|------|-------|------|
| 1 | Conceptual model | ?/4 | [one line or "solid"] |
| 2 | Discoverability | ?/4 | |
| 3 | The manual | ?/4 | [instruction words counted: N across M sentences] |
| 4 | Feedback | ?/4 | |
| 5 | Knowledge in the world | ?/4 | |
| 6 | Error design | ?/4 | |
| **Total** | | **??/24** | **[band]** |

For rendered targets, follow with the **Visceral Scorecard** (5 lenses, 0–20 — format in
[glance.md](glance.md)). The two cards stay separate — different levels of processing — but the
verdict in §1 draws on both, and visceral findings merge into §3's ranked list labeled by level.
A visceral P0 outranks a behavioral P1 on the same screen: the person never reaches it.

### 3. Blockers, ranked
The real output. Order by severity. For each:

- **[P?] Short name** — one line stating the blocker.
- **Where:** route or screen + the control + quoted label or content.
- **Gulf / principle:** which lens, and whether it opens a Gulf of Execution or Evaluation.
- **What the person intends → what the design gives them:** the concrete mismatch, in the
  person's voice ("I pressed Save expecting the video to change and got a green 'Saved' and an
  unchanged video").
- **Slip or mistake:** if it's an error-risk, which kind, and therefore whether the fix is a
  constraint (slip) or the model (mistake).
- **Fix direction:** what would close the gulf — a signifier, a constraint, a default, a
  preview, an undo, a one-line consequence, a relocation — and which command owns it
  (`harden` for error and constraint work, `polish` for feedback, mapping, visible state and
  stripping the manual, `shape` if the screen needs redesign; the project's copy or design owner
  if it's purely voice or taste). Don't fix it here; point at the owner.

**Severity:** P0 the person cannot complete the goal or forms a flatly wrong model that costs
them (money, a publish, someone else's data) · P1 they can finish but get lost, misled, or can't
tell if they succeeded · P2 friction with a workaround · P3 polish. Reserve P0 for real loop
breaks; if everything is P0, nothing is.

### 4. What's already working
Two or three things the target does *right* by Norman's lights, specifically — the signifier
that carries, the constraint that makes the wrong action impossible, the consequence line at the
right spot. This marks the patterns to preserve when other commands edit.

### 5. Recommended next moves
A short ordered list of commands to run, mapped from the blockers, highest severity first. End
with `/don-norman audit <target>` again after fixes to see the score move.

## Rules

- **Quote the content.** Every blocker names its screen and control and quotes enough to find it.
- **Decide whose fault a "wrong" action is.** If a sensible person reaches it, it's a design
  mistake to fix, not a user error to warn about. This judgment is the most valuable thing the
  audit produces.
- **Count the manual.** Report instruction words as a number. A screen can be beautiful and
  still need reading to use; the number makes that visible and shows movement on re-audit.
- **Don't invent blockers to fill the report.** Three real gulfs and a 20/24 beats a padded list
  of P3 nitpicks. Noise buries the P0.
- **Stay in Norman's lane.** Taste, prose rhythm, and brand voice belong elsewhere; when a
  finding is really one of those, say which owner has it and move on. Your domain is whether the
  thing *works* for a human with no manual.
