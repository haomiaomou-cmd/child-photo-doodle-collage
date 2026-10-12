# Style System — Analysis of the Five Reference Images

## Shared DNA

| Element | Rule |
|---|---|
| Base | Real studio photo of a child; clean plain background (off-white / light grey / soft warm white), soft natural floor shadow |
| Drawing medium | Flat crayon / colored-pencil / gouache marks: solid color blocks, single wobbly outline, naive proportions, childlike hand |
| Composition | Subject centered or slightly off-center; 40–60% of the frame is empty background |
| Palette (studio-replace) | Warm orange #E8A33D, mustard yellow #F2C94C, grass green #7BA05B, brick red #C4453C, cream #F5F0E6, ochre brown for branches. Cool accents only in tiny doses |
| Palette (scene-keep) | Cream, grass green, sky blue, pink, white — chosen to stand off the real background at high contrast |
| Scale contrast | Doodles range from tiny marks (hearts, sparks) to larger-than-life companions (a monster taller than the child) |
| Text | Lowercase hand-written English, 1–4 words, small, placed in empty space (`cool cool cool`, `cute`, `Fresh air`, `Happy day`, `Fly`, `Kick!`, `Oops!`, `Whoa!`, `Slurp!`, `Gotcha!`, `Boom!`, `hi`) |

## Reference Breakdown

### style-ref-01-monster-cap.jpg — Big Companion + Gag
- An ochre furry monster taller than the child stands behind her, its long arm lifting her green cap off her head (physical gag, direct contact with a real object).
- Small green slime creatures hug her hip and shirt. Yellow dashed lines circle her head like shock waves.
- Text: `cool cool cool` in orange lowercase; `Fresh air` in green; hand-drawn spiral sun top-right.
- Lesson: doodles may grab or move REAL photographed objects — the strongest interaction grade.

### style-ref-02-capybara-cars.jpg — Shoulder-Rider + Props
- A capybara rides on the boy's shoulder, leaning on his head; a small yellow hamster reaches for his toy car.
- Real props (toy cars) scattered on the floor become the set; hand-drawn grass tufts and wheat sprout between them.
- A hand-drawn branch with birds hangs in the top-left. Text: `cute` + two red hearts.
- Lesson: real toys on the floor + doodle animals reaching for them = natural interaction.

### style-ref-03-carrot-backpack.jpg — Imaginary Costume Element
- A giant hand-drawn carrot with green leaves sticks out behind the boy's back like a backpack, overlapping his red real scarf.
- Yellow birds fly top-left; tulips and a puddle grow at his feet; real toy cars form a circle around him.
- Big hand-drawn exclamation mark beside his head.
- Lesson: a doodle can become a "worn" costume piece (backpack, wings, tail) behind the body.

### style-ref-04-watercolor-sun.jpg — Soft Watercolor Variant
- Large watercolor-style sun and clouds (not line crayon) dominate the top third.
- Hand-drawn leaves and ferns frame the bottom corners, overlapping the boy's socks/feet.
- Real plush toys in both hands; face marks drawn on his real socks.
- Lesson: one soft watercolor element (sun/cloud) may break the flat-crayon rule for atmosphere; ground foliage should touch the feet.

### style-ref-05-happy-geese.jpg — Character Echo
- Hand-drawn white geese with orange beaks fly around the girl; one giant goose head enters from the right edge.
- Theme matches her real yellow duck hoodie and rubber ducks on the floor — doodles echo the photographed props.
- Text: `Happy day` in large outlined lowercase; `eee~` scribble near her face.
- Lesson: the doodle theme must echo the child's clothing print or props.

## Interaction Grading (v1.1)

Grade every planned doodle before prompting. Aim for at least two **grade 3+** items.

| Grade | Description | Examples |
|---|---|---|
| 5 | Doodle moves / operates a REAL photographed object | monster lifts the real cap; seal head-butts the real ball; cat bites and swings on the real balloon string |
| 4 | Doodle touches a REAL prop statically | bird perched on the real shoe toe / bag chain / balloon top; mouse beside the giant shoe sole |
| 3 | Doodle physically contacts the BODY | held in hand; shoulder-rider; clinging to the trouser leg; bird on the fingertip; snail at the shoe tip |
| 2 | Doodle occupies the same ground plane and overlaps a body part | grass touching the toes; tail laid on the trouser leg |
| 1 | Doodle is spatially near but unconnected | sun above the head, birds flying past |
| 0 | Sticker pasted in parallel — **failure** | any doodle that could be cut out without changing the person |

Rule: never deliver a frame whose highest grade is 1.

## Scene Mode Cheat-Sheet

- **Studio-replace** — indoor snapshots, busy rooms, plain walls, generic streets. Swap in the clean off-white studio backdrop.
- **Scene-keep** — the environment carries the image: outfit colour-matched to the wall, turquoise sky with a red ball, beach with sea, playground rig, coloured studio set with real props. Keep the real light and background; switch the doodle palette to high-contrast accents.

## Element Vocabulary (pick per theme)

- Companions: kitten, puppy, capybara, duck/goose, gull, chick, seal, hamster, snail, crab, mouse, slime monster, bear, dinosaur
- Props (doodle): ice cream cone, balloon, carrot, lollipop, milk bottle, star wand, frying pan, straw, football, candy, coin
- Props (real, for Tier-B presets): balloon + string, ball, fish on a line, drink with straw, tote bag, hat, big shoe, playground railing, toy cars
- Ground: grass tufts, tulips, wheat, dandelion, small puddle, ripples, bubble
- Sky: spiral or ray sun (optionally wearing sunglasses), clouds, birds, leafy branch entering from an edge, wind lines, floating feathers
- Marks: hearts, stars, exclamation/question marks, sparkles, dashed motion lines, curly wind lines, swirl lines, impact stars, dashed arc, footprints
- Text: `yummy`, `cute`, `Happy day`, `Fresh air`, `wow`, `cool`, `Fly`, `Kick!`, `Oops!`, `Whoa!`, `Slurp!`, `Gotcha!`, `Boom!`, `hi`, `go go go`
