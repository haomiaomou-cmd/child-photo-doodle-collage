---
name: child-photo-doodle-collage
description: "Transform a user-supplied photograph into a studio-style creative portrait that fuses the real photo with flat crayon hand-drawn doodle illustrations: add kawaii doodle companions (animals, monsters, geese) that physically interact with the subject, doodles that grip real photographed props (balloons, fish, bags, shoes), held props, ground contact, airborne motion lines, plus hand-written English mini-words and tiny hearts/stars. Preserve the face, pose, expression, hairstyle, and clothing. Works for children AND adults, for any pose (standing, jumping, walking, kicking, upside-down, lying down). Use for 儿童涂鸦写真, 蜡笔涂鸦照片, 手绘插画摄影, 涂鸦互动照片, 童趣插画合成, 创意写真, 照片涂鸦, kids doodle portrait, crayon doodle collage, photo doodle collage, or the user's established personal doodle-photo aesthetic."
agent_created: true
---

# Child Photo Doodle Collage

Create one believable "photo jumped into a picture-book" world: a real photograph fused with flat crayon doodles where the drawings TOUCH the subject — gripped in a hand, perched on a shoulder, growing from bare feet, sitting on a real balloon — never floating as parallel stickers.

**v1.1** — hardened by 11 verified production runs. See `Changelog` at the end.

## Core Style Contract (Non-Negotiable)

1. **Real photo as the base.** Keep the face, eyes, expression, pose, hairstyle, and clothing recognizable. Never redesign the person, never alter the face.
2. **Backdrop: studio-replace by default.** Replace busy or colored backgrounds with a plain off-white / light-warm-grey photography-studio backdrop with soft floor shadow, and generous negative space — UNLESS the Scene-Keep rule applies (below).
3. **Flat crayon doodle layer.** Childlike crayon / colored-pencil marks: flat solid color blocks, simple wobbly outlines, naive proportions, visible paper texture. No 3D rendering, no realistic shading, no anime style.
4. **Interaction over decoration.** Every major doodle must have physical contact or occlusion — with the body, with a real prop in the frame, or with the physical state of the scene (see Interaction Presets). If a generation produces only free-floating stickers, regenerate — this is the single most common failure.
5. **Palette: match the mode.** Studio-replace → warm limited palette (warm orange `#E8A33D`, mustard yellow `#F2C94C`, grass green `#7BA05B`, brick red `#C4453C`, cream `#F5F0E6`, ochre brown for branches). Scene-keep → switch to high-contrast accent colors that stand off the real background (cream, grass green, sky blue, pink). Max 4–5 hues either way. Leave most of the frame empty.
6. **Hand-written mini-text.** One to three 1–2 word lowercase English phrases (e.g. `yummy`, `cute`, `Happy day`, `Fly`, `Kick!`, `Oops!`, `Whoa!`, `Slurp!`, `Gotcha!`) plus tiny hearts, stars, exclamation marks, curly lines. Keep text small and away from the face.

## Scene Mode: Studio-Replace vs Scene-Keep

Choose deliberately before prompting — this decision matters more than the preset choice.

| Mode | When to use | What happens |
|---|---|---|
| **studio-replace** (default) | Indoor snapshot, cluttered or distracting background, plain wall | Swap in the clean off-white studio backdrop; doodle palette = warm limited set |
| **scene-keep** (variant) | The scene IS the picture: outfit colour-matched to the wall, turquoise sky with a red ball, a beach, a playground rig, a colored studio set with real props | **Do not** replace the background. Keep the real lighting and environment; switch the doodle palette to high-contrast accents (cream / grass green / sky blue / pink) so the drawings stand off the real background |

Rule of thumb: if replacing the background would destroy the image's identity (colour match, location, real props used as the set), keep the scene. Say so explicitly in the prompt: `保留{背景描述}不更换，{撞色/场景}是画面核心`.

## Workflow

1. **Inspect the input photo.** Record: pose and limbs (empty hands, raised hand, bare feet, kicked leg, outstretched arms are contact anchors); expression; clothing theme and print; **any real prop in frame** (balloon, balloon string, fish on a line, bottle with straw, bag, big shoe, ball, hat, playground rig); background type (studio / colored wall / outdoor / real set). Pick portrait `1024x1536`, `1024x1024` for square, landscape for wide shots.
2. **Pick the scene mode** (studio-replace vs scene-keep) using the table above.
3. **Pick the theme** (user's request or inferred from clothing/props): ice cream + kitten, balloons + puppy, geese + pond, fishing cat gang, etc. The doodle theme must echo the clothing print or the real props when they exist.
4. **Select 2–3 interaction presets** (see below; aim for at least two Tier-A/B contacts, and always add a Tier-C motion/state layer when the pose is dynamic). Read `references/prompt-recipes.md` for the recipe and `references/style-system.md` for element vocabulary.
5. **Build the generation call** with the ImageGen tool (or an equivalent image-editing model):
   - `image1` = the user's photo. Optionally add 1–2 style refs from `assets/` as `image2`/`image3` when multi-image input is supported.
   - `input_fidelity` = high. `quality` = high.
   - Prompt structure: 保留面容/姿势/服装 → 场景（替换或保留）→ 逐条列出互动式涂鸦（用"握住/趴在/停在/扒着/从…探出/顶起/长出来"等接触动词）→ 蜡笔质感与色板（按场景模式）→ 手写字与小符号 → 留白构图 → `不是简单平行贴图`.
6. **Optional cleanup.** If the source has a watermark, timestamp, or UI text, add `去除左上角的水印文字` (or the relevant location) to the prompt.
7. **Inform before generating.** State that image generation consumes roughly 5–10 credits per image before the first call and before any retry.
8. **Save to a new file.** Never modify the source photo in place. Deliver via present_files.
9. **Validate before delivering** — see Validation and Repair Policy.

## Interaction Presets

### Tier A — doodle ↔ body (contact with the person)

- **held**: a doodle prop (ice cream cone, flower bouquet, star wand) is gripped by the subject's open hand; the handle aligns with the fingers.
- **shoulder-rider**: a doodle animal (cat, capybara, duck, monster) perches on a shoulder or peeks from behind the back, paws gripping the clothing, tail wrapping along the arm.
- **leg-cling**: a small doodle creature clings to the leg, paws hooked on the trouser / skirt hem, head peeking out.
- **ground-grow**: doodle grass, tulips, or wheat sprouts beside bare feet or shoes, leaves touching toes or shoe edges.
- **finger-perch**: a doodle bird / butterfly lands exactly on an outstretched fingertip or a raised index finger — the strongest preset for a "pointing" or "reaching" gesture.
- **hand-to-hand**: a doodle character hands something to the subject, matching an outstretched or surprised gesture.
- **peek**: a small doodle creature peeks out from behind the torso or hip, half-occluded by the body.
- **mimic**: a doodle animal copies the subject's exact pose (lying down with paw propping the head, hanging upside-down on the railing, mid-stride) and sits beside them, the two heads close together.
- **crown-hover**: a doodle sun, bird, or leafy branch hangs above the head (hover tier — never counts as one of the two required contacts).

### Tier B — doodle ↔ real prop in the frame (the strongest grade)

Use whenever the photo already contains an object. Drawings that touch real photographed objects read as the highest grade of interaction.

- **real-prop-perch**: a doodle bird / butterfly sits on a real object — shoe toe, bag chain, balloon top, hat brim, handlebar.
- **bag-peek**: a doodle kitten / monster peeks out of the real bag or tote, paws hooked on the rim, hanging on the strap.
- **toss-real-prop**: a doodle seal / creature balances a real ball, or a doodle bird hand-in-wing leads the subject's real hand; connect them with a hand-drawn parabola or arc. The ball is "theirs" now.
- **about-to-step**: a doodle mouse / snail sits right under a big foreground shoe, looking back in alarm, the sole millimetres away — instant comedy and a story.
- **steal-sip**: a doodle gull / creature holds its own little straw poked into the subject's real drink bottle, sharing the drink.
- **balloon-play**: a doodle bird stands on top of a real balloon; a doodle cat bites the balloon string and hangs on it, swinging, bending the string.
- **queue-jump**: a doodle cat leaps at a real fish on a line; behind it a doodle bird and a monster in a queue, the monster holding a hand-drawn frying pan.
- **prop-move**: a giant doodle monster lifts or pulls a REAL photographed object (cap, scarf, balloon) — the strongest gag in the reference set.
- **ground-rest**: a doodle cat sits beside the subject on the same surface, its tail laid on the subject's trouser leg.

### Tier C — doodle ↔ motion / state (for dynamic poses)

- **motion-lines**: airborne / jumping → replace ground grass with hand-drawn wind lines, dashed streaks, and floating feathers beneath the feet.
- **speed-lines**: walking / running → several hand-drawn speed lines and dashed footprints trailing behind.
- **kick-hit**: a kicked leg → a doodle ball struck and deforming at the toe, impact stars and short lines at the contact point, a dashed arc tracing the whole kicking path; nearby doodle birds scatter.
- **gravity-fall**: upside-down / inverted → small doodle objects (candy, coins, stars, milk) fall OUT of the subject's pocket past their hair, physics only possible in that pose.
- **swirl-dizzy**: a few hand-drawn spiral lines and stars around the subject = dizziness visualised.
- **imaginary-puddle**: a raised foot → draw a small blue puddle with ripples and bubbles under it, as if standing in a pond (fiction anchored to a real gesture).
- **sea-interact**: an outdoor water scene → doodle fish leap out of the REAL sea, with hand-drawn splashes, merging the doodle layer into the photographed water surface.

**Selection priority:** Tier B (real prop) > Tier A (body) > Tier C (motion). Always include at least **two** contact-type doodles (Tier A or B); Tier C elements are additive layer, not substitutes. `crown-hover` alone is never enough.

## Pose-Adaptive Playbook

| Pose in the photo | Reach for |
|---|---|
| Standing, arms open, surprised | held + shoulder-rider + ground-grow |
| Pointing up / reaching out | finger-perch + ground-grow |
| Jumping / airborne | motion-lines + hand-to-hand + bag-peek on a real bag |
| Walking / striding | speed-lines + leash-walk style trailing doodle (a doodle dog mid-stride beside the front leg, its leash end landing on the trailing fingertips) + ground contact under the planted foot |
| Kicking (front or back kick) | kick-hit + impact stars + dashed arc + a doodle onlooker ducking (mimic-comedy) |
| Upside-down / hanging | gravity-fall + mimic (a doodle bird hanging the same way nearby) + swirl-dizzy + a smiley face drawn on the real shoe sole |
| Lying / propped on the floor | mimic (doodle animal in the SAME propped pose, heads close) + a doodle snail creeping toward the shoe + ground-grow |
| Low-angle shot with a huge foreground prop (giant shoe, oversized object) | about-to-step + make the foreground prop the story's hero |
| Seated, still | ground-rest + real-prop-perch + crown-hover |
| Holding a real prop (balloon, fish, drink, bag, ball) | the matching Tier-B preset — always prioritise it over inventing a new prop |

## Prompt Templates

Use and adapt the full Chinese templates in [references/prompt-recipes.md](references/prompt-recipes.md). Key phrases that reliably produce contact:

- `正好被她张开的右手"握住"，甜筒柄与手指紧密贴合`
- `整只猫趴在肩膀上，四只爪子抓住T恤布料，尾巴绕过手臂`
- `小鸟正好站在她举起的食指指尖上，爪子踩在手指上`
- `小猫从她真实的米色托特包里探出头，爪子扒着包口`
- `白色小鸟正好停在真实黑色气球的顶部，爪子抓着气球皮`
- `小狗同频小跑，狗绳的一端正好搭在他后摆的手指尖上`
- `脚尖正好踢中一个手绘足球，球被踢飞变形，踢点炸开 impact 星星`
- `涂鸦与人物和真实道具之间有遮挡和接触关系，不是简单平行贴图`

## Validation and Repair Policy

- Inspect the result before delivery. A completed generation is not automatically a finished image.
- Check, in order: (1) face / pose / clothing preserved; (2) scene handled per the chosen mode (studio-replace done cleanly, or scene-keep left intact); (3) at least two doodles physically contact the body **or a real prop**; (4) crayon flat texture, palette matches the mode; (5) mini-text spelled correctly and small; (6) no leftover watermark / UI text if cleanup was requested.
- One targeted regeneration per output by default; name only the failed requirement in the correction brief and keep everything that already passed. Tell the user a retry consumes additional credits first.
- If the face drifted, raise input fidelity and re-run from the ORIGINAL photo, not from the failed output.
- If doodles float without contact, re-issue with the exact contact phrasing above and the sentence `不是简单平行贴图`.
- If the model added a doodle but ignored the real prop, name the prop explicitly and describe the exact physical relation (`爪子扒着包口`、`停在气球顶部`、`绳端搭在手指尖`).
- If the model replaced a scene that should have been kept (or vice versa), restate the scene decision as the first clause of the prompt.

## Conflict Priority

When requirements compete, preserve in this order:

1. subject identity: face, expression, pose, clothing;
2. the scene decision (clean studio backdrop OR the deliberately kept real scene);
3. interaction / contact between doodles and the body or real props;
4. theme coherence and palette limits;
5. decorative micro-marks and text.

Simplify the lowest-priority element instead of breaking a higher one.

## Iteration Protocol

When the user asks for adjustments (change animal, move element, stronger interaction), regenerate from the ORIGINAL photo with a revised prompt, not from the previous output. Keep all previously approved elements verbatim in the prompt and change only the requested part. Preserve each approved version's file separately.

## Assets

- `assets/style-ref-01-monster-cap.jpg` … `style-ref-05-happy-geese.jpg` — five authoritative style references (monster lifting a real cap; capybara shoulder-rider with toy cars; carrot-backpack with birds and tulips; watercolour sun with cape and leaves; flying geese with `Happy day`).
- `assets/input-photo-example.png` + `assets/standard-output.png` — a verified input→output pair demonstrating the interaction contract.
- Pass one or two style refs as `image2`/`image3` when multi-image input is supported; when only single-image input is supported, rely fully on the prompt templates.

## Changelog

- **v1.1** — hardened from 11 production runs:
  - Added `Scene Mode` section: studio-replace vs **scene-keep** (colour-matched outfits, sea, playground, coloured studio sets) with palette-switch rules.
  - Interaction presets grew from 6 to **23**, split into Tier A (body), Tier B (**real prop** — the highest grade), Tier C (motion / physical state).
  - New presets: finger-perch, leg-cling, mimic, real-prop-perch, bag-peek, toss-real-prop, about-to-step, steal-sip, balloon-play, queue-jump, prop-move, ground-rest, motion-lines, speed-lines, kick-hit, gravity-fall, swirl-dizzy, imaginary-puddle, sea-interact, leash-walk.
  - Added **Pose-Adaptive Playbook** mapping 10 common poses to preset sets.
  - Added optional watermark / UI-text cleanup step.
  - Validation gained a real-prop-contact check and a scene-mode check.
  - Scope broadened: verified on adults as well as children.
- **v1.0** — initial release: 6 presets, 4 prompt templates, 5 style references.
