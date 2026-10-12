---
name: child-photo-doodle-collage
description: "Transform a user-supplied child photograph into a studio-style creative portrait that fuses the real photo with flat crayon hand-drawn doodle illustrations: replace busy backgrounds with a clean off-white studio backdrop, add kawaii doodle companions (animals, monsters, geese) that physically interact with the child, held props (ice cream, balloon), ground contact (grass, tulips), overhead marks (sun, birds), plus hand-written English mini-words and tiny hearts/stars. Preserve the child's face, pose, expression, hairstyle, and clothing. Use for 儿童涂鸦写真, 蜡笔涂鸦儿童照, 手绘插画儿童摄影, 涂鸦互动照片, 童趣插画合成, kids doodle portrait, photo doodle collage, or the user's established personal children-photo aesthetic."
agent_created: true
---

# Child Photo Doodle Collage

Create one believable "photo jumped into a picture-book" world: a real child photograph fused with flat crayon doodles where the drawings TOUCH the child — held in a hand, perched on a shoulder, growing from bare feet — never floating as parallel stickers.

## Core Style Contract (Non-Negotiable)

1. **Real photo as the base.** Keep the child's face, eyes, expression, pose, hairstyle, and clothing recognizable. Never redesign the child, never alter the face.
2. **Clean studio backdrop.** Replace busy or colored backgrounds with a plain off-white / light-warm-grey photography-studio backdrop with soft floor shadow. Large negative space around the subject.
3. **Flat crayon doodle layer.** Doodles are childlike crayon/colored-pencil marks: flat solid color blocks, simple wobbly outlines, naive proportions, visible paper texture. No 3D rendering, no realistic shading, no anime style.
4. **Interaction over decoration.** Every major doodle must have physical contact or occlusion with the child's body (see Interaction Presets). If a generation produces only free-floating stickers, regenerate — that is the single most common failure.
5. **Warm limited palette.** Warm orange, mustard yellow, grass green, brick red, cream; brown/ochre for branches. Maximum 4–5 hues. Leave most of the frame empty.
6. **Hand-written mini-text.** One 1–2 word lowercase English phrase (e.g. `yummy`, `cute`, `Happy day`, `Fresh air`) plus tiny hearts, stars, exclamation marks, curly lines. Keep text small and away from the face.

## Workflow

1. **Inspect the input photo.** Record the child's pose (especially empty hands and bare feet — these are interaction anchors), expression, clothing theme, framing, and free space around the body. Choose portrait `1024x1536` for vertical photos, `1024x1024` for square.
2. **Pick the theme** (user's request or inferred from clothing): e.g. ice cream + kitten, balloons + puppy, ducks + pond, cape + plush dinosaurs. The doodle theme must echo the clothing print when one exists.
3. **Select 1–2 interaction presets** from `references/prompt-recipes.md` and read `references/style-system.md` for the element vocabulary and palette.
4. **Build the generation call** with the ImageGen tool (or equivalent image-editing model):
   - `image1` = the user's photo. Optionally add 1–2 style refs from `assets/` as `image2`/`image3` when the model supports multi-image input.
   - `input_fidelity` = high (preserve the child's identity).
   - `quality` = high.
   - Prompt structure: 保留面容/姿势/服装 → 干净米白摄影棚背景 → 逐条列出互动式涂鸦（用"握住/趴在/从…长出来/搭在"等接触动词）→ 蜡笔质感与限定色板 → 手写字与小符号 → 留白构图。Use the templates in `references/prompt-recipes.md` and adapt the theme.
5. **Inform before generating.** State that image generation consumes roughly 5–10 credits per image before the first call.
6. **Save to a new file.** Never modify the source photo in place. Deliver via present_files.
7. **Validate before delivering** (see Validation and Repair Policy).

## Interaction Presets (choose 1–3 per image)

- **held**: a doodle prop (ice cream cone, balloon string, flower bouquet) is gripped by the child's open hand; the handle aligns with the fingers.
- **shoulder-rider**: a doodle animal (cat, capybara, duck, monster) perches on a shoulder or peeks from behind the back, paws gripping the clothing, tail wrapping along the arm.
- **ground-grow**: doodle grass, tulips, or wheat sprouts from beside the bare feet, leaves touching the toes.
- **crown-hover**: a doodle sun, bird, or leafy branch hangs above the head.
- **hand-to-hand**: a doodle character hands something to the child (matching an outstretched or surprised gesture).
- **peek**: a small doodle creature peeks out from behind the child's torso or hip, half-occluded by the body.

Priority: held > shoulder-rider > ground-grow > others. At least two contact-type doodles must appear; pure hover-type elements alone are not enough.

## Prompt Templates

Use and adapt the full Chinese templates in [references/prompt-recipes.md](references/prompt-recipes.md). Key phrasing that reliably produces contact:

- `正好被她张开的右手"握住"，甜筒柄与手指紧密贴合`
- `整只猫趴在肩膀上，四只爪子抓住T恤布料，尾巴绕过手臂`
- `小草从她脚边长出来，叶子与脚趾相接触`
- `涂鸦与人物之间有遮挡和接触关系，不是简单平行贴图`

## Validation and Repair Policy

- Inspect the result before delivery. A completed generation is not automatically a finished image.
- Check, in order: (1) child's face/pose/clothing preserved; (2) background replaced with clean studio white; (3) at least two doodles physically contact the body; (4) crayon flat texture, warm limited palette; (5) mini-text spelled correctly and small.
- One targeted regeneration per output by default; name only the failed requirement in the correction brief and keep everything that already passed. Tell the user a retry consumes additional credits first.
- If the face drifted, raise input fidelity and re-run from the original photo, not from the failed output.
- If doodles float without contact, re-issue with the exact contact phrasing above and the sentence `不是简单平行贴图`.

## Conflict Priority

When requirements compete, preserve in this order:

1. child's identity: face, expression, pose, clothing;
2. clean studio backdrop and generous negative space;
3. interaction/contact between doodles and the body;
4. theme coherence and palette limits;
5. decorative micro-marks and text.

Simplify the lowest-priority element instead of breaking a higher one.

## Iteration Protocol

When the user asks for adjustments (change animal, move element, stronger interaction), regenerate from the ORIGINAL user photo with a revised prompt, not from the previous output. Keep all previously approved elements verbatim in the prompt and change only the requested part. Preserve each approved version's file separately.

## Assets

- `assets/style-ref-01-monster-cap.jpg` … `style-ref-05-happy-geese.jpg` — five authoritative style references (monster lifting cap; capybara shoulder-rider with toy cars; carrot-backpack with birds and tulips; watercolor sun with cape and leaves; flying geese with `Happy day`).
- `assets/input-photo-example.png` + `assets/standard-output.png` — a verified input→output pair demonstrating the interaction contract.
- Pass one or two style refs as `image2`/`image3` when multi-image input is supported; when only single-image input is supported, rely fully on the prompt templates.
