---
name: cozy-ux
description: >-
  UX standards for any user interface, built from Don Norman's books and Apple's Human
  Interface Guidelines, checked the way an agent can apply them. Use when auditing, shaping,
  hardening, or polishing a screen or flow (a form, settings page, upload, dashboard,
  navigation, empty state, long wait, approval, destructive action, onboarding, checkout,
  or AI output) or judging one rendered screen at a glance. Covers the two gulfs, signifiers,
  constraints, mapping, feedback, the no-manual law (instruction text means the control
  failed), slips vs mistakes, undo over confirm, hierarchy and calm (no card soup), Apple's
  eight design principles, wayfinding, and accessibility numbers (target size, contrast, text
  size, reduced motion). Reach for it on "run Norman on it", "is this intuitive", "would
  someone get stuck", "too much helper text", "make it more Apple", "this feels busy", "is
  this accessible", or any screen someone wants checked or made better for people. Commands
  are audit, glance, shape, harden, and polish. One screen or flow at a time. Not for brand
  taste or motion craft.
version: 0.4.0
user-invocable: true
argument-hint: "[audit|glance|shape|harden|polish] [screen, flow, or route]"
---

UX standards for any screen or flow. A screen passes when a first-time person can tell what
to do, do it, and tell whether it worked, with no manual, at any text size, on any input.

[STANDARDS.md](STANDARDS.md) holds the rules, from Norman, Apple's HIG, WCAG and NN/g, with
sources tagged. Every command checks against it. Findings cite its sections.

**The stance.** When a person fails, the design failed. Design for people as they are. They
scan, they get distracted, they are on a phone, and they hold one goal at a time.

## Setup

Do these before any command.

1. **Resolve the target to one screen or one flow, and find what it really renders.** Find
   the route, components and data behind it. Reconstruct what the person sees, can do, and is
   told at each moment, including every control, its label, its state, the text near it, and
   what changes when it is used. Drive the browser when the rendered result is otherwise
   unknowable. Screenshots beat guesses. If you can't tell how something renders, say so. If
   the target is a whole app, ask which screen or flow.
2. **Read [STANDARDS.md](STANDARDS.md).** Required for every command. Without it you fall
   back to generic review habits.
3. **Read the command file** (`reference/<command>.md`). It defines the steps and the report.

## The standards in one screen

The full rules and tests are in STANDARDS.md. This is the index.

| § | Standard | The test |
|---|---|---|
| 2 | The loop | Every control closes the loop. Each finding names a Gulf of Execution or Evaluation |
| 3 | First glance | In 2 seconds, what is it, who is it for, what do I do. One primary action. The squint matches the priority |
| 4 | Calm | Space groups before lines, lines before boxes. No card soup. Few accents. Controls look different from content |
| 5 | Know what to do | Every control signals itself. Only the possible is offered. Controls sit on what they change. Conventions hold |
| 6 | No manual | Instruction text is deleted and the control is fixed. Consequences stay, one line, at the point of action. The cover test decides |
| 7 | Knowledge in the world | Defaults, visible state and previews carry what each action needs. Nothing must be remembered from another screen |
| 8 | Do it | Targets meet size and spacing minimums. Press shows instantly. Gestures have visible twins. Keyboard reaches everything |
| 9 | Know it worked | Feedback is immediate, specific and located. Waits say what, how long, and whether leaving is safe |
| 10 | Errors | Slips get constraints, mistakes get a better model. Undo over confirm. Every gate has a reachable release |
| 11 | Find the way | Where am I, where can I go, what's there, how do I get out. Flows start truthfully and end clearly |
| 12 | Everyone | 4.5:1 text contrast, never color alone, text scales, Reduce Motion respected |
| 13 | Trust | Clear about what it does. Permission with a reason. Delight is earned, not added |
| 14 | Complexity | Remove confusion, not capability. Never hide state to look simple |

## Commands

| Command | What it does | Reference |
|---|---|---|
| `audit [target]` | Walk the screen or flow as the person. Find and rank every blocker. Count the instruction words. Read-only report with the Usability Scorecard | [reference/audit.md](reference/audit.md) |
| `glance [screen]` | Judge one rendered screen at scan speed. 2-second test, squint, bold-words read, signifiers, density, calm. Read-only Glance Scorecard | [reference/glance.md](reference/glance.md) |
| `shape [idea]` | Design a new screen or flow before code. The person, the one-sentence model, every action loop. Stops for approval before building | [reference/shape.md](reference/shape.md) |
| `harden [target]` | Error-proof what exists. Slips vs mistakes, constraints, undo over confirm, reachable releases, graceful recovery. Edits | [reference/harden.md](reference/harden.md) |
| `polish [target]` | Final pass. Strip the manual, close the last gulfs, tighten feedback, mapping, state and calm. Edits lightly | [reference/polish.md](reference/polish.md) |

## Routing

1. **The first word is a command.** Run setup, read that command's file, and follow it.
   Everything after the command is the target.
2. **The intent is clear without a command.** "Where would someone get stuck on upload?" is
   `audit`. "Design the invite flow" is `shape`. "Make sure nobody deletes a language by
   accident" is `harden`. "Too much helper text" is `polish` to fix it or `audit` to find it.
   "Does this land at first glance?" or "this feels busy" is `glance`. "Is this accessible?"
   is `audit` with §12 weighted first.
3. **No argument.** Offer `audit` on the screen the conversation implies, then show the
   commands. Don't auto-run.
4. **No clear match.** Do a general review of the named target against STANDARDS.md.

## Scope

- **One screen or one flow at a time.** For a whole app, go screen by screen and say so.
  `glance` the key screens and `audit` the flow between them.
- **The auditor is not the author.** If you wrote the copy or control under review, say so,
  and run the cover test literally instead of rereading your own reasons.
- **Function, not taste.** Palette, typeface choice and brand voice are out of scope. Name
  the owner and move on. Whether a screen can be read at a glance is in scope. "The serif
  feels wrong" is taste. "The squint surfaces the wrong element" is a finding.
- **Motion craft is out of scope.** Curves, durations and springs belong to an animation
  skill. Whether motion explains a change and respects Reduce Motion is in scope (§9, §12).
- **Findings name the exact control and quote its content.** "Improve feedback" is useless.
  "The Invite button on /settings/team shows nothing after press. The email sends and the
  form clears, but nothing says so. Gulf of Evaluation at the moment of commitment." That is
  a finding.
- **Make the right action easy before forbidding the wrong one.** Reach for a default, a
  constraint, a signifier or an undo before a block, a dialog or a sentence.
