# The visceral guide — Norman's other two levels, applied at glance speed

Read this before running `glance`, and before an `audit` whose target renders visually (a
landing page, a pricing section, an app screen — anything a person SEES before they act).
The field guide teaches the **behavioral level**: whether the interaction loop closes. This
guide teaches the floors above and below it, from *Emotional Design* (2004): the **visceral**
judgment that fires before any reading happens, and the **reflective** read that decides what
the thing says about its maker and its user. A flow can close every behavioral loop and still
die at the visceral level — the visitor bounced before the first loop began.

## §1. The three levels, and where each skill-lens lives

Norman's model: three levels of processing run simultaneously and interact.

- **Visceral** — pre-conscious, appearance-driven, biologically wired. Fires in the first
  fraction of a second, from color, shape, size, symmetry, density — the look before the
  reading. It judges good/bad, safe/dangerous, credible/sketchy, and it has already ruled
  by the time the reader reaches the first sentence. Visceral design concerns itself with
  appearances (Norman's own framing, paraphrased — see §6 on quote provenance).
- **Behavioral** — the use level: function, understandability, usability, feedback. All of
  *The Design of Everyday Things*, the Seven Stages, and the field guide live here.
- **Reflective** — conscious, after-the-fact meaning: self-image, memory, story. For a page:
  does this feel like *my kind of company*; would I forward it; do I trust them with money.

Mechanics that matter for auditing: visceral processing runs **bottom-up** (the look colors
everything downstream), reflective runs **top-down** (a strong enough brand/meaning can
override a visceral dislike — ugly but it's a Leica). Practical consequence: a bad visceral
hit poisons the behavioral experience before it starts, so a visceral P0 outranks a behavioral
P1 on the same screen — the visitor never reaches the behavioral gulf you found.

## §2. Attractive things work better — the mechanism, not the platitude

Norman's essay "Emotion & Design: Attractive Things Work Better" (Interactions, 2002; later
ch. 1 of *Emotional Design*): **"Positive affect broadens the thought processes"** and
**"Pleasing things work better, are easier to learn, and produce a more harmonious result."**
The mechanism (via Alice Isen's experiments): attractive design induces positive affect →
positive affect broadens cognition and raises tolerance of minor friction → the same interface
objectively performs better in the user's hands.

The audit-usable half is the **anxiety corollary**: negative affect *narrows* cognition.
A page that induces anxiety — clutter, a text wall, competing focal points, distrust — makes
the visitor measurably worse at using it. Friction that is survivable on a calm page becomes
a blocker on an anxious one. When you find a behavioral gulf on a visually stressful screen,
say so: the two findings compound.

**The honesty caveat (NN/g, and it protects the audit):** aesthetics forgive MINOR problems
only, and beauty masks problems during testing. Never let a pretty screen downgrade a real
P0/P1 behavioral finding, and never let this guide turn into "make it prettier" — the visceral
lens tests *function at a glance*, not taste.

## §3. Signifiers at glance speed

DOET revised edition (2013), and the 2008 jnd.org essay it grew from: an **affordance** is
what actions are possible; a **signifier** is the perceivable cue that communicates them.
**"Forget affordances: what people need, and what design must provide, are signifiers."**

The glance-speed version of the test: before reading a word of body copy —

- Does the primary CTA *look* like the one thing to press? (Count the elements competing to
  be "primary." More than one filled/loud shape = a signifier conflict.)
- Does the price look like a price, at the size and position a price is expected?
- Do comparable options (plans, tiers, cards) *look* comparable — same anatomy, scannable
  as a set?
- Does the next action's location match convention (prototypicality — §4)?

A button that must be read to be recognized as a button has an affordance with no signifier.
That is a visceral finding even when the behavioral loop (click → works) closes perfectly.

## §4. How people actually take in a screen — the numbers to hold

These come from the Norman-Nielsen ecosystem (NN/g eyetracking corpus) and adjacent academia —
cite them as that, not as Norman personally:

- **~50ms**: visual-appeal verdict forms (Lindgaard 2006), detectable at 17ms (Tuch 2012);
  the halo carries into credibility and purchase judgments. The verdict is in before reading.
- **Low visual complexity + high prototypicality** drive positive first impressions (Tuch
  2012). Prototypicality = the page looks like the kind of page it is. A pricing section that
  doesn't look like pricing pays a visceral tax whatever its copy says.
- **79% scan, 16% read** word-by-word (Nielsen 1997). Design for the 79%; the prose serves
  the 16% who arrive already convinced enough to read.
- **Scan patterns** (Pernice 2019): the **layer-cake** (headings, subheads, bolds) is by far
  the most effective scan — it is the design goal. The **F-pattern is a failure symptom**: it
  is what eyes do to an unformatted text wall. The spotted pattern follows bolds, links,
  numbers. Front-load the first 1-2 words of every line and heading; that is where gaze lands.
- **10 seconds** of ruthless triage; survive ~30s and the visitor stays minutes (Nielsen
  2011). The value proposition must land inside the triage window.

## §5. The test battery

The method for `glance`, and for the visceral pass inside `audit`. Each test is executable by
reconstructing the rendered screen from source (or a screenshot when available). Report what
each test yields, in character as the first-time visitor.

1. **2-second test.** Describe only what registers in a two-second exposure: *what is this,
   who is it for, what do they want me to do?* Any of the three missing → P0/P1. (The 50ms
   verdict and the 10s triage say this test decides whether the rest of the page exists.)
2. **Squint test.** Blur the layout; report what survives. The surviving hierarchy IS the
   visual hierarchy. Does it match the intended priority (headline > CTA > price > proof)?
   A mismatch is a broken visceral mapping — the design shouts the wrong thing.
3. **Bold-words-only read (layer-cake probe).** Read only headings, bolds, buttons, numbers.
   Does that skeleton alone make the argument? If not, the 79% who scan never receive it.
   Keywords that are moody rather than informative fail here even when the full sentence
   resolves them.
4. **Signifier check** (§3): CTA, price, next action recognizable without reading.
5. **Density at the decision.** Word count within one viewport of the CTA/price; longest
   unbroken text run (more than 3-4 lines = text-wall flag, F-pattern bait); count of
   elements competing above the fold. High complexity = negative first impression (Tuch).
6. **Affect read.** Name the visceral emotional response — calm/confident/expensive vs
   crowded/anxious/skeptical — and its specific cause. Per §2, an anxious screen widens
   every behavioral gulf downstream, so this read modulates the whole audit.
7. **Reflective read** (light, one paragraph). What does this screen say the maker is like,
   and what does engaging with it say about the visitor? For a premium offer: does it look
   like the work being sold? Incongruence here (a craft studio with a template-looking page)
   is a reflective finding, not a taste note.

## §6. Provenance discipline

When you write findings, keep the attribution honest — it is part of the skill's credibility:

- The three levels, attractive-things-work-better, and signifiers are **Norman, primary**
  (the 2002 and 2008 essays are on jnd.org; the levels are *Emotional Design* 2004). Quote
  the two essay lines in §2/§3 freely; paraphrase the book (its widely-reproduced quotes are
  likely exact but unverified against the text).
- Scan patterns, 50ms/17ms, 79%, 10s — **NN/g and adjacent academia** (Nielsen, Pernice,
  Lindgaard, Tuch, Tractinsky, Kurosu & Kashimura). Say "the Norman-Nielsen ecosystem," never
  "Norman found."
- Norman has written nothing specifically about pricing or landing pages. The application to
  them is ours; the levels and mechanisms are his.
