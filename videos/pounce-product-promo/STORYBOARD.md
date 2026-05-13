# Storyboard

**Format:** 1920x1080
**Duration:** 20 seconds
**Audio:** Local macOS voiceover from `narration.txt`; no music bed in source by default.
**VO direction:** Calm, product-demo delivery with clear pauses after the hook and before the closing line.
**Style basis:** `DESIGN.md` and the captured local Pounce dashboard page.

## Global Direction

The promo should feel like a security product coming alive, not a slide deck. Every beat keeps the light dashboard identity: warm surfaces, dark ink, teal trust accents, amber warnings, red blocks, and mono package details. Motion is precise and auditable: typed commands, verdict rows snapping into place, connector paths drawing across panels, and screenshots drifting with subtle camera depth.

## Asset Audit

| Asset | Type | Assign to Beat | Role |
| --- | --- | --- | --- |
| `capture/screenshots/scroll-000.png` | Hero capture | Beat 1 | Full website context and recognizable source page |
| `capture/assets/pounce-dashboard.png` | Product screenshot | Beat 2, Beat 4 | Dashboard proof and final product surface |
| `capture/assets/git_main.png` | Product screenshot | Beat 3 | README/product overview layer behind hook timeline |
| `capture/assets/pounce-icon.svg` | SVG icon | Beat 1, Beat 4 | Brand/security mark |
| `capture/assets/pounce-logo.svg` | SVG logo | Beat 4 | Closing brand lockup |

## Beat 1 - Before Repo State (0.00-4.80s)

**VO cue:** "Dependency changes shouldn't quietly become repo state."

**Concept:** The website is already in frame, but the viewer is pulled into the high-risk moment: dependency changes are about to become repository state. The hero page drifts behind a sharp foreground warning line, then resolves into a simple thesis.

**Visual description:** The source website screenshot fills the right and rear of the frame with a slow push. A teal protection dot pulses near the Pounce icon. Large kinetic type enters from the left: "Before repo state." A mono command strip types the install command under it. Small verdict chips orbit near the dashboard edge: ALLOW, WARN, BLOCK.

**Techniques:** Product screenshot Ken Burns drift, per-word kinetic typography, typed command reveal, SVG connector line drawing.

**Transition:** Velocity-matched blur push into Beat 2.

## Beat 2 - Exact Releases First (4.80-9.80s)

**VO cue:** "Pounce checks exact releases before the install,"

**Concept:** The dashboard becomes the decision surface. Instead of generic "security", the viewer sees concrete releases and concrete outcomes.

**Visual description:** Three verdict route rows cascade into the center: `jose@6.2.2` clean, `axios@1.15.0` script, `plain-crypto-js@4.2.1` IOC. The Pounce dashboard screenshot sits in a tilted device frame to the right. A counter locks to "3/3 hook events" and "5 MiB feed cap" as proof points.

**Techniques:** Cascading UI rows, counter animation, 3D product screenshot tilt, color-coded semantic states.

**Transition:** Steel-blue connector line sweeps across the screen into the hook timeline.

## Beat 3 - The Turn Holds Context (9.80-15.20s)

**VO cue:** "watches the shell while agents work, and keeps every allow, warn, and block verdict attached to the same workspace."

**Concept:** The product story shifts from one package check to the whole agent turn. The workspace, shell, and Stop-phase diff all stay tied together.

**Visual description:** A three-stage timeline draws from left to right: UserPromptSubmit, PreToolUse, Stop. Under each stage, a short mono explanation appears. The README screenshot floats as a secondary proof layer. A live queue card stack slides in on the right, showing block, warn, allow, and seed trust states.

**Techniques:** SVG path drawing, timeline stage reveal, floating queue cards, screenshot parallax.

**Transition:** Blur-through with a teal pulse into the trust state beat.

## Beat 4 - Trust Stays Visible (15.20-20.00s)

**VO cue:** "Feed trust stays visible. Risky packages stop before they settle."

**Concept:** Close on the value: reviewers can see the active trust source and Pounce stops risky dependency changes before they become quiet state.

**Visual description:** The dashboard screenshot grows into the center. A source-precedence ladder appears: hosted feed, local cache, bundled seed. A red BLOCK stamp lands over the risky package, then a teal Protected pill settles beside the Pounce logo. The final frame holds a compact CTA line: "Vet dependencies before they land."

**Techniques:** Dashboard zoom, source ladder reveal, block stamp impact, final brand lockup.

**Transition:** Final scene only fades to the held brand frame in the last half second.

## Production Architecture

```
videos/pounce-product-promo/
├── index.html
├── DESIGN.md
├── SCRIPT.md
├── STORYBOARD.md
├── narration.txt
├── narration.wav
├── transcript.json
├── capture/
│   ├── screenshots/
│   ├── assets/
│   └── extracted/
├── assets/
├── compositions/
└── snapshots/
```
