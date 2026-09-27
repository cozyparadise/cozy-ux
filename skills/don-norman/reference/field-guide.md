# The Norman field guide, applied to apps

This is the lens every `don-norman` command reads first. It takes the framework of *The Design of
Everyday Things* (2013 revised edition — the one that says **discoverability** and **signifiers**),
*Emotional Design* (2004) and *Living with Complexity* (2010), and points it at the one artifact
you actually audit: **a person trying to do something with a screen someone built.** The examples
are app surfaces — forms, uploads, settings, waits, approvals — because that is what most targets
are; a lesson or a wizard is the same machine with steps in a row.

Read it once, then hold it while you walk the target. The point is to stop reviewing like a
generic UX checklist and start seeing the screen the way Norman saw doors, stoves, and phones: a
machine whose usability is decided by whether an ordinary person can tell what to do, do it, and
tell whether it worked — with nobody there to explain.

## Table of contents

1. The stance: human-centered, and the design takes the blame
2. The Seven Stages of Action, per action
3. The two Gulfs (your primary hunting ground)
4. Discoverability: the six principles, and the conceptual model over them
5. The no-manual law: labels are a confession
6. Knowledge in the world vs. in the head
7. The error taxonomy: slips vs mistakes
8. Design for error: constraints, undo, forcing functions, and why confirmations fail
9. Complexity vs confusion (and what "Apple has no manual" actually means)
10. Conventions, standards, and cultural mappings
11. Feedback: immediate, informative, and not too much
12. Flows: the arc-level checks
13. Surface cheat sheet: where each kind of screen tends to fail
14. Provenance

---

## 1. The stance: human-centered, and the design takes the blame

Norman's whole project rests on one reversal: **when a person fails to use a thing, the thing
failed.** The chapter is titled "Human Error? No, Bad Design." People blame themselves for the
door they pushed instead of pulled; the designer knew the door had two possibilities and gave no
sign. Engineers design for the logical user they wish they had; Norman insists we accept human
behaviour as it is — scanning not reading, distracted, interrupted, on a phone, holding one goal
at a time, and certain that they are the only one who finds this confusing.

Human-centered design, in his practice:

- **Start from the activity, not the feature.** What is the person trying to get done, in what
  situation, with what already in their head? (Not "the settings page" — "a team admin, on
  a Tuesday, wants Korean added before Friday's launch and doesn't want to break anything.")
- **Observe, don't ask.** People cannot report what they do; watch one real person do the real
  task, saying nothing. One observed session outranks any amount of reasoning about users.
- **Iterate.** Prototype, watch, fix, watch again. Usability is not decided at review; it is
  decided at design time and *found* at test time.
- **The five whys.** When someone errs, the first cause named is almost never the root. Ask why
  until you reach the design decision.

Everything below is how to see the failures once you hold that stance.

---

## 2. The Seven Stages of Action, per action

Norman models every human action as seven stages: form a **goal**, form an **intention**,
**specify** an action, **execute** it, **perceive** the new state of the world, **interpret** it,
**evaluate** it against the goal. Execution is the first four; evaluation is the last three.

Every control on a screen is a tiny instance of this loop. Walk it literally:

- **Goal.** What does the person want here? Usually something outside the app ("this week's video
  in Korean by Friday"). Is the screen's sub-goal one the person actually holds, or one the
  design assumes?
- **Intention + specify.** Given the goal, can they tell *what to do* on this screen — which
  control, what gesture? If they'd hesitate ("what does this want from me?"), that hesitation
  is a **Gulf of Execution**.
- **Execute.** Can they actually do it? Is the target obvious and reachable? Are two controls so
  alike they'll hit the wrong one (a slip)?
- **Perceive.** After they act, does the screen visibly change? Did the button register? Did the
  thing they touched change? If nothing perceptibly happens, the loop can't close.
- **Interpret + evaluate.** Can they tell *what the change meant* and whether it advanced the
  goal? "I pressed Invite, the row appeared with 'invited', the field cleared" closes the loop.
  "I pressed Invite and the field cleared" leaves them wondering whether it sent.

Most screens are fine on stages 1–4 and fail on 5–7 (feedback and interpretation), or on 2 (the
person can't tell what the screen wants). Those are the two gulfs.

---

## 3. The two Gulfs (your primary hunting ground)

In Norman's terms (paraphrased): the **Gulf of Execution** is the distance between what a person
intends and what the system lets them do; the **Gulf of Evaluation** is the effort it takes to read
the system's state and tell whether the intention was met.

Almost every real blocker is one of these two. Name which one, at which control, every time.

**Gulf of Execution — "I don't know what to do / how to do it."** App tells:

- A control that doesn't look like one (a link styled as text; a drop target that looks like a
  box; an editable title with no pencil and no hover).
- A disabled primary button with nothing saying what enables it.
- A screen that changed what it asks without signalling it (the form that used to take a file
  now wants a link, and the field looks the same).
- A choice with no default where one is obviously right, forcing a decision the person can't
  make yet.
- A paragraph explaining what to do — the strongest possible tell, because it means the design
  already knows the control doesn't say it (§5).

**Gulf of Evaluation — "I did something but can't tell what it meant."** App tells:

- Save that produces no visible change ("did it take?").
- A long job with no progress, no time estimate, and no statement of whether closing the tab
  kills it.
- Success reported far from where the person is looking (a toast at the bottom-right for a
  change made top-left).
- A state word with no referent: "Ready" — ready for what, for whom?
- A submitted thing that looks exactly like an unsubmitted one.

For each blocker, write it as: **which gulf · which control · what the person intends · what
the design gives them instead**.

---

## 4. Discoverability: the six principles, and the conceptual model over them

The 2013 edition replaces "visibility" with **discoverability** — can the person figure out what
actions are possible and where and how to do them — and breaks it into five things you can
audit for, with a sixth over the top:

**Affordances.** The relationship between the thing and the person: what actions are actually
possible. A text field affords typing; a bucket affords dropping. Audit for *false* affordances
(looks pressable, isn't) and *hidden* ones (is pressable, doesn't look it).

**Signifiers.** The perceivable cue that communicates the affordance. **"Forget affordances: what
people need, and what design must provide, are signifiers."** This is the principle most apps
fail. A button looks like a button. A drop zone has a dashed edge and a verb. An editable thing
shows an edge on hover. A required decision is visibly unmade. The primary action is the one
filled shape on the screen. A signifier can be a word — "Invite" on a button is a signifier —
but a sentence *near* a control explaining it is not a signifier, it is a substitute for one.

**Constraints.** Physical, cultural, semantic, logical. What is not possible is not offered.
The language picker only lists languages the narrator can voice; the Start button is disabled
until a file exists; the date can't be in the future. Constraints are how the right action
becomes the only action. They are the best form of knowledge in the world (§6).

**Mappings.** The spatial and behavioural relationship between control and effect. The control
for a thing sits next to that thing. The thing that gets bigger is on the right of the thing
that gets smaller. A per-language action lives on the language's row, not in a global menu. A
setting that affects every operator sits under the team, not the person.

**Feedback.** Every action produces an immediate, visible, specific result — §11.

**Conceptual model.** Over all of it: the story the person holds about what this thing is and
how it works. The designer's model reaches the person only through the **system image** — what
is on screen and what happens when it is used. Manuals, tooltips, and onboarding tours exist
because the system image failed to carry the model. Audit: does the screen teach the right model
and nothing false? Is it consistent screen to screen? (A "Save" that applies to future videos
only but says nothing installs the model "saved = applied", and the support ticket follows.)

---

## 5. The no-manual law: labels are a confession

> "When simple things need pictures, labels, or instructions, the design has failed."

This is Norman's sentence and this skill's sharpest test. The door with a PUSH sign is the
door that failed. An app whose fields need sentences under them is the same door.

**Sort every piece of on-screen text into two kinds.**

| Kind | What it does | Verdict |
|---|---|---|
| **Instruction** | Says what a control is for, how to use it, what to pick, what will appear, why it's here. "Pick more than one if…", "This is the name printed on…", "Add whatever you have and…", a paragraph opening a settings page. | **Delete it and fix the control.** The sentence is the design admitting the signifier isn't there. Replace with a constraint, a default, a preview, a label on the control, a convention. |
| **Consequence** | Says what will happen and can't be undone, what it costs, a right, a deadline, an honesty disclosure. "Other devices will be signed out." "This link works for 24 hours." "Finished videos keep the name they were made with." "This is sample footage." | **Keep it — one line, at the point of action.** This is knowledge the world owes the person before they commit. Apple ships exactly this ("You can't undo this action"). People read *after a surprise*, not before an action, so it lives where the surprise would be. |

Marketing copy on a landing page is a third thing — meant to be read — and out of scope.

**The cover test.** Hide every helper sentence on the screen and walk the flow again. Anything
that still works without the sentence loses the sentence. Anything that stops working has found
a missing signifier: fix that, then remove the sentence. Run it literally — do not re-read the
justification for the text; the author of a sentence can always justify it.

**Two cautions.** A *label on a control* ("Team name", "Invite", "Make the video in") is a
signifier, not a manual; keep those, and make them verbs and nouns, not sentences. And a good
conceptual model still has to arrive — through the system image, not prose: a live preview of
the video frame teaches "this name is printed on the video" better than the sentence did.

---

## 6. Knowledge in the world vs. in the head

Norman's rule: put knowledge *in the world* so people don't have to hold it *in the head*. Memory
is expensive and lossy; visible information is free at the point of use. **Precision is not
required** — things need only be distinguishable enough to act on.

What "in the world" means in an app — and this is where the rule gets misread into paragraphs:

- **Defaults.** The team's own languages pre-picked; the last-used voice remembered.
- **Constraints.** Only the possible options offered (§4).
- **Visible state.** The current value, the current step, the thing being waited on, on screen.
- **Previews.** Show the effect, don't describe it.
- **Labels on controls.** The verb on the button, the noun on the field.
- **Conventions.** The gear means settings; the avatar row is the account; ⋯ hides the rest.
- **Placement.** The action beside the thing it acts on (mapping).

What it does **not** mean: restating context in prose. A screen drowning in reminders has its own
gulf — visibility collapses when everything shouts. The skill is putting *exactly what this
action needs* where the person is already looking, in the smallest form that carries it.

Tells of knowledge wrongly in the head:
- An action that needs a fact from a screen the person left (which team am I in? which
  language did I add?). Show the fact where the action is.
- A code or ID the person must copy between screens.
- Two similar options that differ only by something explained elsewhere.

---

## 7. The error taxonomy: slips vs mistakes

Norman splits human error into two kinds, with different fixes. Tag every error-risk you find.

**Slip: right intention, wrong action.** The person knew what they meant and mis-executed.
- Two controls that look alike or sit too close (Remove next to Rename; two chips one pixel apart).
- A tap target too small; a destructive action where the finger lands after the last one.
- A field that accepts the wrong thing silently (a YouTube link in the title box).
- **Memory-lapse slips:** they forgot a step because the design let them (left without saving;
  saved and forgot to press "make it again").
Fix slips with **constraints and layout**: separate, differentiate, widen, make the dangerous one
look dangerous, make the forgotten step impossible to forget. **Don't fix a slip with words**;
the person already understood.

**Mistake: wrong intention, from a wrong model.** The person did exactly what they meant, but
what they meant was wrong because the design taught them wrong.
- "Save" applied to future videos only, and nothing said so → they wait for the old ones.
- A screen that looked personal was team-wide → they changed everyone's colours.
- A menu item named for what the code does, not what the person wants.
Fix mistakes with **the conceptual model**: the system image, the name, the placement, the
one-line consequence at the point of action. If any sensible person reaches the wrong action,
it is a design mistake to fix, not a user error to warn about.

The most important move in the skill: when a person would do the "wrong" thing, decide **whose
fault the design made it.** It is almost always the design's.

---

## 8. Design for error: constraints, undo, forcing functions, and why confirmations fail

Norman: the best error message is the one that never needs to appear. Design so that errors are
impossible, and where not impossible, visible, cheap, and reversible. His list, applied:

- **Understand the causes and design to minimize them** — usually a slip or a mistake (§7).
- **Sensibility checks.** Does this action make sense? Deleting the only language; publishing
  with no approver email; a file of 0 bytes. Catch it before it runs.
- **Make it possible to reverse actions — or make it harder to do what cannot be reversed.**
  Undo beats confirm every time. Where undo is impossible (money spent, an email sent), slow
  the action down: a distinct control, a distance, a held press, a typed name.
- **Make errors easy to discover and easy to correct.** The failure shows where it happened,
  says what to do next, and never destroys the person's work.
- **Don't treat the action as an error; treat it as an approximation of what is wanted.** The
  person meant something. Offer the nearest right thing.

**Forcing functions** stop the flow until a condition holds. Three kinds: **interlocks** (the
sequence is enforced — no Start without a file), **lock-ins** (you can't leave until done — the
unsaved-changes guard), **lock-outs** (you can't enter a dangerous state — no delete while a
run is live). Good when the gate is *visible* and the release is *reachable*. A gate the person
can't see, or can't satisfy, strands them with the goal intact and no allowable action — the
worst failure in the book. Every forcing function needs a visible, reachable release.

**Why confirmation dialogs fail.** People confirm the *action* they intended, not the *object*
they are about to act on; "Are you sure?" arrives when they are sure and is dismissed by habit.
Prefer: make the object visible in the control itself ("Remove Korean" not "Remove"), make the
result undoable, and reserve a real gate for the truly irreversible.

**Recover gracefully.** Treat error as normal use, not a failure to scold. The message says what
happened in the person's terms, what still stands, and the next action — one line each.

---

## 9. Complexity vs confusion (and what "Apple has no manual" actually means)

*Living with Complexity* (2010): complexity is not the enemy; **confusion** is. Rich tools are
complex because life is; the answer is not fewer features but a conceptual model that makes the
complexity understandable, plus signifiers that make each part self-evident. Norman warns
against the simplicity fetish in both directions: "featuritis" that piles controls on, and the
minimalist surface that hides state and controls to *look* simple, forcing the person to hold
the hidden part in their head.

So "Apple ships no manual" means: **every control signifies itself, follows a convention, and
shows its state; consequences are one line; nothing needs to be explained because nothing is
hidden or unfamiliar.** It does not mean fewer things, and it does not mean less text at any
cost — the consequence line (§5) is the text Apple keeps. When you cut, cut *instruction*; when
you simplify, remove *confusion*, not capability. A screen with six clear controls beats a
screen with two mysterious ones.

Audit tells of the wrong kind of simple: a single vague button ("Continue") in place of the
real decision; an icon with no label where the convention is weak; state you can only learn by
pressing; a menu that hides the one thing this screen is for.

---

## 10. Conventions, standards, and cultural mappings

When natural mapping is impossible, **standardize** — Norman's last resort, and in apps it is
the everyday case. A convention is knowledge already in the person's head from every other app;
following it is the cheapest signifier there is. Breaking one has to buy something.

- Platform conventions: back on the left, primary on the right; gear = settings; avatar = me;
  ⋯ = more; a dashed box = drop here; red = destructive; a filled shape = the one action.
- Domain conventions: the person's own vocabulary, not the code's. "Make the video in" beats
  "Target languages"; "Who approves videos" beats "Notify recipients".
- Cultural mappings: reading direction, date and time in *their* zone, their calendar day.

Tell: a clever control where a boring one would have been understood; a renamed convention;
an icon that means something only to the team.

---

## 11. Feedback: immediate, informative, and not too much

Norman's feedback is not "show a toast." It is: **immediate** (within the action, not after a
round trip if it can be helped), **informative** (says what happened to *this* thing — the row
you touched changes, the count moves, the state word flips), **located** (where the eyes are —
on the control, not in a corner), **prioritized** (the important result is the loud one), and
**not too much** — feedback that fires for everything is noise, and people learn to ignore it,
which then hides the one that mattered.

For long jobs: the job's state visible on its own screen, what is happening now, a truthful
estimate, whether leaving is safe, and how the person will learn it finished. Reassurance that
says nothing ("Processing…") is a Gulf of Evaluation with a spinner on it.

For failures: the failing step's own sentence, in the person's terms, with the next action
attached. Not the code's error; not a generic "something went wrong."

---

## 12. Flows: the arc-level checks

Zoom out from single actions. Onboarding, a wizard, an upload-to-publish pipeline, a checkout,
a lesson: sequences have their own usability.

- **Does the start set a truthful model of the journey?** What it will take, what it will cost,
  what comes back, how long. A step that hides a big demand (money, a phone, a second person)
  behind a bland line is a slow-motion Gulf of Execution.
- **Is the model consistent end to end?** The same nouns, the same shapes, the same place for
  the primary action. Note every screen where the framing shifts without a bridge.
- **Does the demand ramp?** Warm-up before commitment. A cold commitment at step two — pay, or
  invite, or publish — with no sense of what it is for, is a cliff.
- **Where is the commitment point, and is everything the person needs there?** Whose name is
  on it, what it costs, what can't be undone. (§5 consequence text lives here.)
- **Peak and end.** Frustration compounds and endings colour the memory. Where is the hardest
  moment, and does the design offer relief there? Does the end say what happened and what is
  now true — the loop of the whole flow closing?
- **Hand-offs to other people.** A review link, an invite, a share: the receiver has *none* of
  the sender's context. Their screen must stand alone — who this is from, what is being asked,
  what pressing the button does.

---

## 13. Surface cheat sheet: where each kind of screen tends to fail

Fast reference for the failure modes each surface invites. Use it to move quickly, not instead
of walking the actual screen.

- **Forms and settings.** Explainer paragraphs under fields (§5); scope invisible (is this mine
  or everyone's?); Save with no visible result; Save that means "future only" and doesn't say
  so; a shared setting placed under the person; no default where one is obvious.
- **Uploads and dropzones.** The target doesn't look droppable; what fits is unstated (the one
  constraint line — "PDF up to 10 MB" — is a signifier, keep it); the alternative path (paste a
  link) hidden; progress absent; the classified result ("this is your recording") not shown.
- **Long waits.** No progress, no estimate, no "safe to close"; state visible only on reload;
  failure reported as a generic banner; no way to learn it finished without watching.
- **Approvals and reviews.** The approver arrives with no context (§12 hand-offs); the
  commitment point lacks whose name, what it publishes, what can't be undone; the expiring link
  fails silently; "send it back" is a smaller signifier than "publish" when both are legitimate.
- **Destructive actions.** Delete next to Edit; "Are you sure?" instead of undo (§8); the object
  not named in the control; deleting a thing a running job still needs.
- **Navigation, rails, switchers.** Where am I (which team, which video) not visible on every
  screen; the active item indistinguishable; the account door and the settings door confused;
  two "primary" shapes competing (§4 signifiers; visceral-guide §3).
- **Empty states.** A paragraph where the one action should be; or no action at all — the
  empty state IS the signifier for the first action.
- **Dialogs and toasts.** Feedback in the wrong place; a dialog for what a state change on the
  control would do; a toast for what should be permanent on screen.
- **Emails and notifications.** The receiver's screen with no sender context; a link with no
  statement of its lifetime; a failure email that says "re-upload" when "try again" is what works.
- **Onboarding and first run.** A tour instead of a self-evident screen (the tour is the manual);
  asking for what has an obvious default; a second team created when the person meant to join.

---

## 14. Provenance

The Seven Stages, the Gulfs, discoverability and its principles, signifiers, knowledge in the
world, slips vs mistakes, design for error, forcing functions, and the "labels mean the design
failed" sentence are Norman's — *The Design of Everyday Things* (revised 2013; the 1988
original has the same bones under the older words "visibility" and "affordance"). Complexity vs
confusion is *Living with Complexity* (2010). The three levels and "attractive things work
better" are *Emotional Design* (2004) — see [visceral-guide.md](visceral-guide.md), which also
holds the provenance discipline for the scan-speed numbers (those are the Norman-Nielsen
ecosystem, not Norman personally). The instruction-vs-consequence split, the cover test, and the
app translations are this skill's; say so if asked.
