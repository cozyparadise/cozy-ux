# cozy-ux — a usability skill for Claude, built on Don Norman's principles

A Claude skill that reviews any screen or flow the way Don Norman would. It walks the interface
as a first-time person, finds where they can't tell what to do (Gulf of Execution) or can't tell
whether it worked (Gulf of Evaluation), and names the exact control that failed.

Its sharpest rule: **if a control needs a sentence under it to be used, the control failed.** It
sorts every piece of on-screen text into *instruction* (delete it, fix the control) or
*consequence* (keep it, one line, at the point of action).

Built from *The Design of Everyday Things* (2013), *Emotional Design* (2004), and *Living with
Complexity* (2010). Unofficial — not affiliated with or endorsed by Don Norman.

## Commands

| Command | What it does |
|---|---|
| `audit [screen or flow]` | Read-only. Walks every action, scores six lenses (0–24), ranks blockers P0–P3, counts instruction words. |
| `glance [screen]` | Read-only. Judges one rendered screen at 2-second scan speed: squint test, bold-words-only read, signifiers, density. |
| `shape [idea]` | Designs a new screen or flow before any code: the person, the one-sentence model, every action loop. Stops for your OK before building. |
| `harden [target]` | Error-proofs what exists: slips vs mistakes, constraints, undo over "Are you sure?", visible releases on every gate. Edits. |
| `polish [target]` | Final pass: strips the manual, tightens feedback, mapping, and visible state. Edits, lightly. |

Or just ask in plain words: "where would someone get stuck on the upload screen?", "is this
intuitive?", "there's too much helper text here."

## Install

Claude Code, Codex, Cursor and other agents:

```bash
npx skills add cozyparadise/cozy-ux
```

Then run `/cozy-ux audit <screen>` or ask Claude to "run Norman on" a screen.

Claude.ai / Claude Desktop: zip the `skills/cozy-ux` folder and upload it under
Settings → Capabilities → Skills.

## What's in it

```
skills/cozy-ux/
├── SKILL.md                    # entry point, the lens, routing
└── reference/
    ├── field-guide.md          # Norman's framework applied to app screens (read by every command)
    ├── visceral-guide.md       # Emotional Design's visceral + reflective levels, scan-speed tests
    ├── audit.md  glance.md  shape.md  harden.md  polish.md
```

## Provenance

The Seven Stages, the Gulfs, signifiers, slips vs mistakes, design for error, and the three
levels are Norman's. The scan-speed numbers (50 ms, 79% scan) come from Nielsen Norman Group and
related research, cited as such. The instruction-vs-consequence split, the cover test, the
scorecards, and the app translations are this skill's own.

## License

MIT — see [LICENSE](LICENSE).
