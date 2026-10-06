# cozy-ux

UX standards an agent can check, from Don Norman's books and Apple's Human Interface Guidelines.

```bash
npx skills add cozyparadise/cozy-ux
```

Ask an agent to review a screen and you usually get vibes. "Feels a bit cluttered." "Could be more intuitive." This skill gives it rules to check instead, and makes every finding name the exact control that failed.

The sharpest rule is that **a control needing a sentence under it has failed.** The skill sorts every line of on-screen text into two kinds. Instructions get deleted and the control gets fixed. Consequences, like "this can't be undone", stay as one line where the person acts. To settle it, hide the sentence and walk the flow again. If it still works, the sentence goes.

## What it checks

| Standard | The test |
| --- | --- |
| First glance | In 2 seconds, what is it, who is it for, what do I do |
| Calm | Space does the grouping. No card soup. One primary action |
| Know what to do | Every control signals itself. Only the possible is offered |
| No manual | Instruction text goes. Consequences stay, one line |
| Do it | 44pt targets on iOS, 24px minimum on the web. Press shows instantly |
| Know it worked | Feedback is immediate, specific, and where the eyes are |
| Errors | Undo over "Are you sure?". Every gate has a way out |
| Find the way | Where am I, where can I go, how do I get out |
| Everyone | 4.5:1 text contrast. Never color alone. Text scales. Reduce Motion works |
| Trust | Clear about what it does. Delight is earned, not added |

The full rules, with their sources tagged, are in [`STANDARDS.md`](skills/cozy-ux/STANDARDS.md).

## Commands

| Command | What you get |
| --- | --- |
| `audit` | Walks the screen or flow as a first-time person. Ranked blockers, a 7-lens score out of 28, and a count of the words someone must read to get through. Read-only |
| `glance` | Judges one rendered screen at scan speed with the squint test and a bold-words-only read. Read-only |
| `shape` | Plans a new screen or flow before code, then stops for your OK |
| `harden` | Error-proofs what exists. Splits slips from mistakes, swaps confirms for undo, frees stuck gates |
| `polish` | The last pass. Strips the manual and tightens feedback, state, and calm |

Or ask in plain words. "Where would someone get stuck on upload?" "Is this accessible?" "There's too much helper text."

## Where the rules come from

- **Don Norman** gave the core loop. A person must be able to tell what to do and tell whether it worked. Signifiers, slips and mistakes, and design for error come from him.
- **Apple's HIG** gave the eight design principles, calm hierarchy, and the numbers for target size, spacing, contrast, and text size. All were checked against Apple's pages in October 2026.
- **WCAG 2.2** gave the web minimums, cited by number.
- **Nielsen Norman Group** gave the scan-speed research and response-time limits.
- **Emil Kowalski's** [`apple-design`](https://github.com/emilkowalski/skills) skill (MIT) shaped the web versions of Apple's material, type, and feedback guidance.

The no-manual split, the cover test, the scorecards, and the screen checklists are this skill's own. Norman and Apple haven't reviewed or endorsed it.

Motion craft lives in [tune-animations](https://github.com/cozyparadise/tune-animations).

## License

MIT
