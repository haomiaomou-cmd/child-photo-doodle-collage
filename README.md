# Child Photo Doodle Collage

Turn a supplied photograph into a studio creative portrait where a real person and flat crayon doodles live in one picture — the drawings **hold hands, sit on shoulders, grip clothing, grow from bare feet, ride real balloons, and hang off real bags** instead of floating around as stickers.

![Child Photo Doodle Collage showcase](showcase/comparisons/showcase-overview.jpg)

**v1.1** — hardened by 11 verified production runs on children *and* adults, in poses from standing to upside-down.

## What it does

The skill keeps the subject's face, expression, pose, hairstyle, and clothing recognizable, handles the background deliberately, and builds a crayon-doodle ecosystem that physically interacts with the body **and with real objects already in the photo**.

### Three interaction tiers

**Tier A — doodle ↔ body**

- **held** — a doodle ice cream cone gripped by an open hand
- **shoulder-rider** — a doodle kitten perched on the shoulder, paws gripping the shirt
- **leg-cling** — a small creature hooked onto the trouser leg, head peeking out
- **finger-perch** — a bird landing exactly on a pointing fingertip
- **ground-grow** — hand-drawn grass and tulips sprouting beside the shoes
- **hand-to-hand** — a doodle character handing something over
- **peek** — a small creature looking out from behind the body
- **mimic** — a doodle animal copying the subject's exact pose, heads close together

**Tier B — doodle ↔ real prop in the frame** (the strongest grade)

- **real-prop-perch** — a bird sitting on a real shoe toe, bag chain, or balloon top
- **bag-peek** — a kitten peeking out of the real tote, paws on the rim
- **toss-real-prop** — a doodle seal head-butting the real ball, joined by a hand-drawn arc
- **about-to-step** — a doodle mouse right under a giant foreground shoe, looking back in alarm
- **steal-sip** — a gull with its own straw poked into the subject's real drink
- **balloon-play** — a bird on the real balloon, a cat swinging from its string

**Tier C — doodle ↔ motion and physical state**

- **motion-lines** — wind lines and floating feathers under an airborne subject
- **speed-lines** — dashed streaks and footprints behind a walking subject
- **kick-hit** — a doodle ball struck and deforming at the toe, impact stars, dashed arc
- **gravity-fall** — candy and coins falling out of the pocket of an upside-down subject
- **imaginary-puddle** — a rippling puddle under a raised foot
- **sea-interact** — doodle fish leaping out of a real sea

Every result also gets a small hand-written English word (`yummy`, `cute`, `Happy day`, `Fly`, `Kick!`, `Oops!`, `Slurp!`), plus tiny hearts and stars.

### Children

![Child comparison](showcase/comparisons/child-ice-cream-before-after.jpg)

### Poses with a built-in interaction

![Pointing comparison](showcase/comparisons/pointing-bird-before-after.jpg)

### Action and movement

![Walking comparison](showcase/comparisons/walking-dog-before-after.jpg)

### Scene-keep variant

When the outfit and background are deliberately color-matched (an orange suit against an orange wall, a red ball in a turquoise sky), the skill keeps the real scene instead of replacing it, and switches the doodle palette to high-contrast cream, green, and sky blue.

![Kick comparison](showcase/comparisons/kick-ball-before-after.jpg)

## Install

Ask your agent to install the skill from GitHub:

```text
Install the skill from https://github.com/haomiaomou-cmd/child-photo-doodle-collage/tree/main/skill/child-photo-doodle-collage
```

Or copy the skill folder manually into your skills directory:

```bash
# user-level (available in every project)
cp -r skill/child-photo-doodle-collage ~/.workbuddy/skills/

# project-level (shared with the repository)
cp -r skill/child-photo-doodle-collage <project>/.workbuddy/skills/
```

The skill becomes available on the next turn after installation.

## Use

Attach a photograph and invoke:

```text
$child-photo-doodle-collage
```

or simply:

```text
帮我把这张照片做成涂鸦写真
```

The skill inspects the photo, decides the scene mode, finds the interaction anchors (empty hands, bare feet, held props, real bag, balloon, mid-air pose), picks a doodle theme that echoes the clothing print, states the image-generation cost, and generates one finished image. Then it asks what to adjust.

## Iteration

Ask in plain language and the skill regenerates from the **original** photo with only the requested part changed:

```text
小猫直接趴在肩膀上
把它换成一顶手绘帽子
让互动再强一点，她咬一口冰淇淋
```

## Layout

```text
skill/child-photo-doodle-collage/
├── SKILL.md                    # workflow, style contract, 23 interaction presets, pose playbook, validation policy
├── references/
│   ├── style-system.md         # reference analysis, interaction grading table, scene-mode cheat-sheet, element vocabulary
│   └── prompt-recipes.md       # 10 copy-ready generation prompts and correction briefs
└── assets/
    ├── style-ref-01..05.jpg    # authoritative style references
    ├── input-photo-example.png # verified input
    └── standard-output.png     # verified output
```

## How the style works

1. Real photo as the base, identity untouched.
2. **Scene decision first**: clean studio backdrop by default, or deliberately keep a scene that carries the image.
3. Flat crayon marks only — solid color blocks, wobbly outlines, naive proportions.
4. Contact beats decoration. Doodles are graded 0–5; a frame must reach grade 3+ at least twice.
5. A limited palette — warm set for studio, high-contrast accents for scene-keep.

See [`references/style-system.md`](skill/child-photo-doodle-collage/references/style-system.md) for the full breakdown.

## Changelog

- **v1.1** — 6 → 23 interaction presets across three tiers; added scene-keep mode and palette-switch rules; added a pose-adaptive playbook (10 poses); added optional watermark cleanup; validation now checks real-prop contact and scene mode; verified on adults as well as children.
- **v1.0** — initial release: 6 presets, 4 prompt templates, 5 style references.

## License

MIT
