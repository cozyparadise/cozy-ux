# UX Standards

The rules every `cozy-ux` command checks against. Each section is a set of standards in the
order a person meets a screen. They glance, work out what to do, do it, check that it
worked, recover, find their way, and decide whether to trust it.

Findings cite the section (`§5 No manual`). A standard is met or it is not. Taste is out of
scope. Whether a person can use the thing is in scope.

Sources are tagged where the rule comes from someone else. **[Norman]** *The Design of
Everyday Things* (rev. 2013), *Emotional Design* (2004), *Living with Complexity* (2010).
**[Apple]** Human Interface Guidelines, checked October 2026. **[WCAG]** WCAG 2.2.
**[NN/g]** Nielsen Norman Group and related research. Untagged rules are this skill's own.

## Contents

1. Stance
2. The loop
3. First glance
4. Calm
5. Know what to do
6. No manual
7. Knowledge in the world
8. Do it
9. Know it worked
10. Errors
11. Find the way
12. Everyone
13. Trust
14. Complexity is not confusion
15. Surface checklist
16. Sources

---

## 1. Stance

- **When a person fails, the design failed.** "Human error" is usually a design decision
  nobody owned. [Norman]
- **Design for people as they are.** They scan instead of reading. They are distracted, on a
  phone, holding one goal, and sure they are the only one confused.
- **Start from the activity, not the feature.** Not "the settings page". A team admin on a
  Tuesday who needs Korean added before Friday and must not break anything. [Norman]
- **Watched behavior beats reasoning.** One observed session outranks any amount of argument
  about users. Say so when a real session is possible. [Norman]
- **Every element earns its place.** Know what the product is for, and spend people's
  attention only where it serves that. [Apple: Purpose, Simplicity]
- **Stay out of the way.** Get people to the task or content directly. [Apple: Agency]

## 2. The loop

Every action is one loop with seven stages. Form a goal, form an intention, specify the
action, do it, perceive the result, interpret it, and judge it against the goal. [Norman]

A screen passes when that loop closes at every control. It fails where one of two gaps
opens. Every finding names which one.

- **Gulf of Execution.** The person can't tell what to do or how. Tells include a control
  that doesn't look like one, a disabled button with no sign of what enables it, a choice
  with no default where one is obvious, and a paragraph explaining what to do.
- **Gulf of Evaluation.** The person acted and can't tell what it meant. Tells include a
  Save with no visible change, a long job with no progress, success shown far from where
  they are looking, a state word with no referent ("Ready" for what?), and a submitted thing
  that looks unsubmitted.

Write each blocker as **gulf · control · what the person intends · what the design gives
them instead.** Most screens pass stages 1 to 4 and fail at 5 to 7, or fail at stage 2.

## 3. First glance

The look is judged before a word is read. A screen can close every loop and still lose the
person here. [Norman: visceral level]

- **The 2-second test.** In two seconds a first-time person can say what this is, who it is
  for, and what to do. Missing any one is a P0 or P1.
- **One primary action per screen or decision zone.** It is the single filled or loudest
  shape. Two loud shapes means neither is primary.
- **The squint matches the priority.** Blur the screen. What survives is the real hierarchy.
  It must match the intended order, such as headline, then action, then price, then proof.
- **Hierarchy comes from order, size, weight and space.** Put the most important thing first
  and give it the most room. Secondary content moves down, gets smaller, or goes one level
  deeper. [Apple: Simplicity, Layout]
- **The bold words alone make the argument.** Read only headings, bold text, buttons and
  numbers. If that skeleton doesn't carry the message, scanners never get it. Front-load the
  first two words of every line and heading. [NN/g]
- **It looks like what it is.** A pricing table looks like pricing. A settings page looks
  like settings. Unfamiliar layouts pay a first-impression tax. [NN/g: prototypicality]
- **No text walls near a decision.** More than three or four unbroken lines invites the
  F-pattern skim, which is a symptom of bad formatting, not a goal. [NN/g]
- **An anxious screen makes people worse at using it.** Clutter and competing focal points
  narrow attention, so small friction becomes a blocker. A calm screen forgives small
  friction. Beauty never excuses a P0 or P1. [Norman; NN/g]

The numbers behind this, all [NN/g] and related research, not Norman. A visual-appeal
judgment forms in about 50ms (Lindgaard 2006). Low complexity and high prototypicality drive
good first impressions (Tuch 2012). About 79% of people scan and 16% read word by word
(Nielsen 1997). People triage a page in about 10 seconds (Nielsen 2011).

## 4. Calm

Structure should come from space and alignment first. Lines and boxes come second.
Decoration that does no work is noise.

- **Group with space before lines, and lines before boxes.** Related items sit close.
  Unrelated groups get more space. Use a separator or container only when space can't carry
  the grouping. [Apple: Layout]
- **No card soup.** Not every block gets its own box. Cards inside cards need a reason.
- **No dashboards for task screens.** A job that needs a list, a form or a detail view
  doesn't become a grid of widgets.
- **Product screens aren't landing pages.** Centered marketing stacks don't belong inside a
  working tool.
- **Few accents.** Accent color, badges and highlights mark what matters. When everything is
  highlighted, nothing is. Shadows, gradients, tints and glass need a structural job.
- **Controls look different from content.** A person can tell at a glance which parts act
  and which parts are read.
- **Type hierarchy is a set.** Size, weight and line height change together. Weight adds
  emphasis without taking space. Large text gets tighter tracking and leading. Body text
  stays near zero tracking with comfortable leading. Start from the system font unless there
  is a reason not to.
- **Dim to focus, separate to keep flow.** A blocking task gets a scrim behind it. A side
  panel the person works beside gets no scrim, so the flow stays open.
- **Text over translucent surfaces stays legible.** Never stack one light translucent layer
  on another. Text over blur needs more contrast and weight than text over a solid surface.

## 5. Know what to do

By looking, a person can tell what state things are in and what they can do. [Norman:
discoverability]

- **Every control signals what it does.** A button looks pressable. A field looks typeable.
  A drop zone looks droppable. An editable title shows an edge on hover. The cue that tells
  people what to do is a **signifier**, and it is what most screens lack. [Norman]
- **No false or hidden actions.** Nothing looks pressable that isn't. Nothing pressable looks
  inert. [Norman: affordances]
- **Only offer what's possible.** A picker lists only valid options. Start stays off until a
  file exists. A date field rejects dates that can't happen. Constraints make the right
  action the only one. [Norman]
- **Controls sit on the thing they change.** A per-row action lives on the row. A team-wide
  setting lives under the team, not the person. Layout mirrors effect. [Norman: mapping]
- **Use the convention.** Back on the left. Gear for settings. Avatar for account. A dashed
  box means drop here. Red means destructive. Things that look the same behave the same and
  live in the same place. Breaking a convention has to buy something, and must be tested.
  [Norman; Apple: Familiarity]
- **Pick the screen's type and follow it.** List, detail, form, editor, settings, search or
  empty state. An accidental hybrid has no convention to lean on.
- **Specific labels over safe ones.** Name things by what they hold or do ("Progress",
  "Invite to Acme") rather than vague umbrellas ("Home", "Submit"). Use the person's words,
  not the code's. "Who approves videos" beats "Notify recipients".
- **Defaults carry the obvious choice.** Never make people decide what the design already
  knows.
- **Show what's needed now, hint at the rest.** Advanced and rare options go one level
  deeper, with a visible way in. [Apple: Layout, progressive disclosure]
- **The screen builds the right model.** The person's understanding of what this thing is
  comes only from what's on screen and what happens when they use it. It must be the right
  model, nothing false, and the same on every screen. A Save that applies only to future
  items, with nothing saying so, teaches "saved means applied". [Norman: conceptual model]

## 6. No manual

"When simple things need pictures, labels, or instructions, the design has failed." [Norman]

Sort every piece of on-screen text that isn't a label on a control into one of two kinds.

| Kind | What it says | Standard |
|---|---|---|
| **Instruction** | What a control is for, how to use it, what to pick, why it is here | Delete it and fix the control. The sentence admits the signifier is missing |
| **Consequence** | What will happen, what can't be undone, a cost, a right, a deadline, an honesty note | Keep it. One line, at the point of action, where the surprise would be |

- **The cover test.** Hide every helper sentence and walk the flow again. If the flow still
  works, the sentence goes. If it breaks, a signifier is missing. Fix that, then remove the
  sentence. Run it literally. Whoever wrote a sentence can always justify it.
- **Labels on controls are not a manual.** "Team name", "Invite" and "Make the video in" are
  signifiers. Keep them as nouns and verbs, not sentences.
- **Reassurance is usually instruction in disguise.** "Don't worry, nothing breaks" answers a
  fear the design created. Answer it with a visible state instead.
- **A tour is a manual.** Onboarding that explains the screen means the screen doesn't
  explain itself.
- **Use exactly the words needed.** [Apple: Simplicity]
- **Count the instruction words.** Report the number. It makes the manual visible and shows
  progress on the next pass.

## 7. Knowledge in the world

Put what people need where they need it, so they don't have to remember it. Things only need
to be different enough to act on. [Norman]

- **In the world means** defaults, constraints, visible state, previews, labels on controls,
  conventions, and actions placed beside their objects.
- **It does not mean paragraphs.** A screen full of reminders has no visibility left.
- **Show the effect instead of describing it.** A live preview of the frame teaches "this
  name is printed on the video" better than a sentence.
- **Fails when** an action needs a fact from a screen the person left, a code must be copied
  by hand between screens, or two options differ only by something explained elsewhere.

## 8. Do it

- **Targets are big enough and far enough apart.** Two controls too close invite a slip.

  | Platform | Default target | Minimum target | Source |
  |---|---|---|---|
  | iOS, iPadOS, watchOS | 44×44 pt | 28×28 pt | [Apple] |
  | macOS | 28×28 pt | 20×20 pt | [Apple] |
  | visionOS | 60×60 pt | 28×28 pt | [Apple] |
  | tvOS | 66×66 pt | 56×56 pt | [Apple] |
  | Web | 44×44 CSS px (AAA) | 24×24 CSS px (AA) | [WCAG 2.5.5, 2.5.8] |

  Leave about 12 pt around controls with a visible bezel and about 24 pt around ones without.
  [Apple]
- **Respond on press, not on release.** The pressed state shows the instant a finger or
  pointer goes down. Drags, sliders and sheets follow the pointer one to one the whole way,
  not only at the end.
- **Every gesture has a visible way to do the same thing.** The gesture is a shortcut, not
  the only path. [Apple]
- **Destructive sits apart from routine.** Remove isn't next to Rename. Delete isn't where
  the finger lands after Save.
- **Inputs accept only what belongs.** A link can't be pasted silently into a title field.
- **Everything works by keyboard,** with a visible focus state. [WCAG 2.1.1, 2.4.7]

## 9. Know it worked

Feedback closes the loop. It is not "show a toast". [Norman]

- **Immediate.** Under 0.1s feels instant. Up to 1s keeps the flow of thought but shows
  nothing special. Past 1s, show that work is happening. Past 10s, show progress and let
  people do something else. [NN/g: Nielsen 1993]
- **Specific.** The thing the person touched changes. The row appears, the count moves, the
  state word flips. "Saved" closes nothing if nothing visible changed.
- **Located.** On the control or the row, where the eyes are. Not a corner toast for a
  change made across the screen.
- **Prioritized and not too much.** Feedback that fires for everything trains people to
  ignore it, which hides the one that mattered.
- **Covers four kinds.** Status (what's happening), completion (it's done), warning (before a
  problem), and error (what went wrong). Validate inline, not only on submit.
- **Long waits say four things.** What is happening now, a truthful estimate, whether it is
  safe to leave, and how the person will learn it finished. "Processing…" alone is a Gulf
  of Evaluation with a spinner on it.
- **Important information doesn't vanish on a timer.** Auto-dismissing UI fails people who
  need longer to read or who use assistive tech. [Apple; WCAG 2.2.1]
- **Motion explains, it doesn't decorate.** Things enter and leave along the same path and
  grow from the control that opened them, so the person sees where things went. Motion craft
  (curves, timing, springs) belongs to an animation skill, not this one.

## 10. Errors

Errors are normal use. Make them impossible, then visible, then cheap to undo. The best error
message is one that never appears. [Norman]

- **Slips and mistakes need different fixes.** A **slip** is the right intention done wrong,
  such as a mis-tap or a forgotten step. Fix it with constraints and layout. A **mistake** is
  the wrong intention from a wrong model, such as changing everyone's setting while thinking
  it was personal. Fix it with the model. Fix neither with more words. [Norman]
- **If a sensible person takes the "wrong" action, the design caused it.** This judgment is
  the most valuable thing an audit produces.
- **Undo beats confirm.** People confirm the action they meant, not the object they are about
  to hit. "Are you sure?" is dismissed by habit. Name the object in the control ("Remove
  Korean") and make the result undoable. [Norman; Apple: Agency]
- **Irreversible actions slow down in proportion.** Money spent, a message sent, a publish, a
  hard delete. Use a distinct control, distance, a held press, or a typed name. A real
  confirmation is for these only, and it shows what will happen to which thing.
- **Catch nonsense before it runs.** Deleting the only item, publishing with no recipient, a
  file of 0 bytes. [Norman: sensibility checks]
- **Every gate has a visible, reachable release.** Interlocks (no Start without a file),
  lock-ins (unsaved-changes guard) and lock-outs (no delete while running) are good when the
  person can see what is blocking and how to clear it. A gate with no reachable release
  strands them, which is the worst failure in the book. [Norman: forcing functions]
- **Recover gracefully.** The error shows where it happened, says what still stands, and
  names the next step, one line each, in the person's words. It never destroys their work or
  scolds a good-faith attempt. Offer the nearest right thing. [Norman; Apple: Agency]

## 11. Find the way

- **Every screen answers four questions.** Where am I? Where can I go? What will I find
  there? How do I get out? Never trap the person.
- **The current place is visible on every screen.** Which team, which project, which step.
  The active item looks active.
- **Guided flows can be skipped or escaped.** Don't lock people into modes they didn't ask
  for. [Apple: Agency]
- **Content and controls stay in predictable places** across sizes and platforms. [Apple:
  Flexibility]
- **Flows have their own standards.** [Norman]
  - The start tells the truth about what the journey takes, costs, returns, and how long.
  - The model stays consistent. Same nouns, same shapes, same place for the primary action.
  - Demand ramps. A cold commitment at step two, such as paying, inviting or publishing,
    with no sense of why, is a cliff.
  - The commitment point holds everything needed. Whose name, what it costs, what can't be
    undone.
  - The hardest moment gets relief, and the end says what happened and what is now true.
    Frustration compounds, and endings color the memory.
  - Hand-offs stand alone. A review link, invite or share reaches someone with none of the
    sender's context. Their screen says who it's from, what is asked, and what the button
    does.

## 12. Everyone

Accessibility is design quality, not a compliance pass. It makes things easier for
everyone. [Apple: Flexibility]

- **Contrast.**

  | Text | Minimum | Source |
  |---|---|---|
  | Up to 17 pt (Apple), body text (web) | 4.5:1 | [Apple; WCAG 1.4.3] |
  | 18 pt and up, or bold (Apple). 18 pt, or 14 pt bold (web) | 3:1 | [Apple; WCAG 1.4.3] |
  | Icons, borders and control states | 3:1 | [WCAG 1.4.11] |

- **Never color alone.** State also shows through an icon, label, shape or position. [Apple;
  WCAG 1.4.1]
- **Text size follows the person's setting.** Default body text is 17 pt on iOS (11 pt
  minimum) and 13 pt on macOS (10 pt minimum). [Apple] On the web, size and space in `rem`
  so layouts survive 200% text and a 320px-wide viewport. [WCAG 1.4.4, 1.4.10] A dense
  layout that breaks at larger text isn't done.
- **Respect system settings.** Reduce Motion cuts automatic and repetitive animation,
  including zooming, scaling and peripheral motion, and swaps slides for fades. [Apple]
  Reduced transparency makes glass solid. Increased contrast adds borders and stronger color.
  On the web these are `prefers-reduced-motion`, `prefers-reduced-transparency` and
  `prefers-contrast`.
- **No autoplay without controls** to start and stop it. [Apple]
- **Support many inputs.** Touch, pointer, keyboard, voice and assistive tech each reach
  every action. [Apple: Flexibility]

## 13. Trust

- **Be clear about what the product does and why** from the first interaction. [Apple:
  Responsibility]
- **Ask for permission when it is needed,** with the reason, and collect only what the
  product needs. [Apple: Responsibility]
- **Anticipate misuse and harm.** Especially with AI output, add previews, honesty notes and
  limits where a wrong result could hurt someone. [Apple: Responsibility]
- **Consequence lines are trust.** The cost, the recipient, the lifetime of a link, and that
  something is sample data all appear at the point of action (§6).
- **Delight is the result, not decoration.** It comes from getting the rest right. Save
  celebration for earned moments, never let it slow the task, and pick the feeling on
  purpose (calm, confident, energized). [Apple: Delight]

## 14. Complexity is not confusion

Rich tools are complex because the work is. The enemy is confusion, not features. [Norman:
*Living with Complexity*] "Simplicity isn't minimalism." [Apple]

- **Don't hide state or controls to look simple.** A minimal surface that makes people hold
  the hidden part in their head is worse than visible richness with a clear model.
- **Six clear controls beat two mysterious ones.**
- **When you cut, cut instruction. When you simplify, remove confusion, not capability.**
- **Fails when** one vague "Continue" stands in for the real decision, an unlabeled icon
  relies on a weak convention, state can only be learned by pressing, or a menu hides the
  one thing the screen is for.

## 15. Surface checklist

Where each kind of screen tends to fail. Use it to move fast, not instead of walking the
real screen.

- **Forms and settings.** Explainer paragraphs under fields. Scope hidden (mine or
  everyone's?). Save with no visible result, or Save that means "future only" without saying
  so. A shared setting placed under the person. No default where one is obvious. Errors only
  on submit.
- **Uploads and drop zones.** Target doesn't look droppable. What fits is unstated (the one
  line "PDF up to 10 MB" is a signifier, keep it). The other path, like pasting a link, is
  hidden. No progress. The result isn't shown back.
- **Long waits.** No progress, estimate or "safe to close". State only visible on reload. A
  generic failure banner. No way to learn it finished without watching.
- **Approvals and reviews.** The approver lands with no context. The commitment point lacks
  whose name, what it publishes, and what can't be undone. An expired link fails silently.
  "Send back" is smaller than "Publish" when both are valid.
- **Destructive actions.** Delete beside Edit. "Are you sure?" instead of undo. The object
  isn't named in the control. Deleting something a running job still needs.
- **Navigation.** Current place not visible. Active item looks like the rest. Account and
  settings doors confused. Two primary shapes competing. Vague umbrella labels.
- **Empty states.** A paragraph where the first action should be, or no action at all. The
  empty state is the signifier for the first action.
- **Dialogs, sheets and toasts.** A dialog where a state change on the control would do. A
  toast for something that should stay on screen. A scrim on a panel people need to work
  beside. A modal with no clear way out.
- **Dashboards.** Widgets where a task view belongs. Every tile the same weight. Numbers with
  no comparison or meaning.
- **Emails and notifications.** No sender context. A link with no stated lifetime. A failure
  email whose fix doesn't work.
- **Onboarding and first run.** A tour instead of a self-evident screen. Asking for what has
  an obvious default. Creating a second team when the person meant to join one.
- **AI output.** No sign of what the model did or what it used. No way to correct or undo.
  Confident wording on uncertain results.

## 16. Sources

Keep attribution honest. It is part of the skill's credibility.

- **Norman.** The Seven Stages, the two gulfs, discoverability, affordances and signifiers,
  constraints, mappings, feedback, the conceptual model, knowledge in the world, slips and
  mistakes, design for error and forcing functions come from *The Design of Everyday Things*
  (revised 2013). The visceral, behavioral and reflective levels, and "attractive things work
  better", come from *Emotional Design* (2004). Complexity versus confusion comes from *Living
  with Complexity* (2010). Paraphrase the books. The quote in §6 is widely reproduced but not
  checked against the page.
- **Apple.** The eight principles (Purpose, Agency, Responsibility, Familiarity, Flexibility,
  Simplicity, Craft, Delight) and their quoted lines come from the HIG "Design principles"
  page, reintroduced June 8, 2026, and WWDC26 session 250, "Principles of Great Design". The
  target, spacing, contrast and text-size figures come from the HIG Accessibility and
  Typography pages. Grouping and progressive disclosure come from HIG Layout. All were checked
  in October 2026.
- **WCAG 2.2.** Success criteria are cited by number.
- **NN/g and related research.** Scan patterns, the 50ms judgment, 79% scanning, the
  10-second triage and the response-time limits. Say "Nielsen Norman Group found", never
  "Norman found".
- **Web translations** of Apple's material, type and feedback guidance (§4, §8, §9) draw on
  Emil Kowalski's `apple-design` skill (MIT).
- **This skill's own.** The instruction-versus-consequence split, the cover test, the
  scorecards, the surface checklist, and every application to app screens. Norman and Apple
  have not reviewed or endorsed any of it.
