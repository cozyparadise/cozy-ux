# glance — judge one rendered screen at scan speed

The visceral-level command. Read-only, like `audit`: you diagnose and report, you do not edit.
Where `audit` walks a SEQUENCE step-by-step through the Seven Stages, `glance` judges ONE
rendered screen the way a first-time visitor's pre-conscious processing does — in the first
two seconds, before reading. The deliverable is a verdict on whether the screen survives the
triage window, a Glance Scorecard, and ranked blockers.

Unit of analysis: **a screen, not a flow.** A landing page section, a pricing module, a step
of an onboarding as it renders. If the user points at a whole funnel, `glance` the key screens
one at a time and `audit` the flow between them — say that's what you're doing.

## Method

1. **Reconstruct the rendered screen.** From source (data + components + styles) or a
   screenshot/live page when available. You need what the visitor SEES: sizes, weights,
   order, density, what's bold, what's filled, what competes. If you cannot tell how it
   renders, say so rather than guessing.
2. **Read STANDARDS §3 First glance and §4 Calm** if you haven't this session. Without them
   you'll produce generic "too cluttered" notes instead of findings.
3. **Run the battery** (below) in order, in character as the coldest plausible
   visitor (arriving from an ad, on a phone, mid-distraction): 2-second test → squint test →
   bold-words-only read → signifier check → density and calm → affect read →
   reflective read. Report what each test yields, concretely — quote the actual bolds you
   read, name the actual element that won the squint.

## The battery

Each test runs from the rendered screen, or from source when no render is available. Report
what each test yields, in character as the first-time visitor.

1. **2-second test.** Describe only what registers in a two-second look. What is this, who
   is it for, what do they want me to do? Any of the three missing is a P0 or P1.
2. **Squint test.** Blur the layout and report what survives. The surviving hierarchy is the
   real hierarchy. Does it match the intended priority? A mismatch means the screen shouts
   the wrong thing.
3. **Bold-words-only read.** Read only headings, bold text, buttons and numbers. Does that
   skeleton make the argument alone? Quote the words you read. Moody words that only make
   sense in the full sentence fail here.
4. **Signifier check** (§5). The primary action, the price and the next step are
   recognizable without reading. Count the shapes competing to be primary.
5. **Density and calm** (§3, §4). Word count within one viewport of the decision. Longest
   unbroken text run (over 3 to 4 lines is a text wall). Elements competing above the fold.
   Containers that only add boxes, accents that mark nothing, and decoration with no
   structural job.
6. **Affect read.** Name the feeling the screen gives before thought, such as calm and
   confident or crowded and anxious, and its specific cause. An anxious screen widens every
   behavioral gulf downstream.
7. **Reflective read** (one paragraph). What does this screen say about its maker, and about
   the person using it? A craft studio with a template-looking page is a reflective finding,
   not a taste note.

## Scoring: the Glance Scorecard

Separate from `audit`'s Usability Scorecard — different level of processing, different card.
Score 0-4 per lens; be honest, most real screens land 2-3 on their weak axes.

| # | Lens | What a low score looks like | What a 4 looks like |
|---|------|------|------|
| 1 | First impression (2s) | Can't tell what it is, who it's for, or what to do | All three land inside the triage window, unprompted |
| 2 | Scan hierarchy | Bold-skeleton reads as mood; squint surfaces the wrong element | Layer-cake scan alone makes the argument in priority order |
| 3 | Density & calm | Text walls, card soup, competing focal points, accents everywhere, anxious read | Space does the grouping; few accents; prose budgeted to the decision it serves |
| 4 | Glance signifiers | CTA/price/next-action must be read to be recognized; >1 "primary" | The one action, the number, and the path are unmistakable unread |
| 5 | Reflective read | Screen contradicts what's being sold (template look for a craft offer) | The screen IS evidence of the claim; visitor upgraded by association |

**Score bands** (out of 20): 18-20 excellent (ship) · 14-17 good (fix the weak axes) ·
9-13 rough (the scan fails; real work before ads send traffic) · 0-8 broken (the visceral
verdict kills the page before any behavioral loop begins).

## The report

Lead with the verdict, not the table.

### 1. The two-second verdict
What actually registered in the exposure, in the visitor's voice — and the single biggest
visceral failure up front. Then one sentence on affect: what the screen makes the visitor
FEEL before they think.

### 2. Glance Scorecard
The 5-lens table with a sharpest-finding line per row and the banded total.

### 3. Blockers, ranked
Same P0-P3 discipline and format as `audit` (quote the content, name the mismatch, point at
the fix's owner). For each, name WHICH test caught it and which level it lives on (visceral
vs reflective). Severity calibration: P0 the 2-second test loses "what is this" or "what do
I do" · P1 the scan skeleton fails or the primary signifier is contested · P2 density/affect
friction with the message still surviving · P3 polish. A visceral
P0 outranks a behavioral P1 on the same screen. The visitor never gets that far.

### 4. What's already working
The visceral moves to preserve, specifically — what won the squint that should win it, which
bolds carry real information.

### 5. Recommended next moves
Ordered, mapped from blockers. Structural/layout fixes and density cuts name their owner
(the project's design workflow); copy compressions are flagged as the operator's to redline
if the project treats copy as owner-held. End with `glance` again after fixes, and `audit`
if the screen's ACTIONS also need their loops checked.

## Rules

- **Function at a glance, not taste.** "The serif feels wrong" is not a finding; "the squint
  surfaces the decorative numeral instead of the price" is. Aesthetic taste stays with the
  project's design owner.
- **Quote what you scanned.** The bold-words-only read reports the actual words; the density
  test reports the actual counts. No vibes without receipts.
- **Honor the honesty caveat** (STANDARDS §3): a beautiful screen does not excuse a behavioral
  P0/P1, and this command never overrules an `audit` finding — the levels compound, they
  don't trade.
- **Don't pad.** A screen that passes the battery with two P3s is a great outcome; say so
  and stop.
