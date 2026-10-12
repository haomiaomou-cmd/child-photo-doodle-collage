# Prompt Recipes

All templates are for the ImageGen tool (image-to-image). Default parameters:

```
size: 1024x1536 (vertical photos) / 1024x1024 (square)
quality: high
input_fidelity: high
image1: the user's original photo
image2/image3 (optional): one or two style refs from assets/
```

Always tell the user that each generation consumes roughly 5–10 credits before the first call and before each retry.

## Template 1 — Ice Cream + Shoulder Kitten (default, verified)

```
儿童创意写真摄影，真实照片与蜡笔手绘涂鸦融合。保留小女孩/小男孩的面容、{姿势}、{服装描述}，背景为干净米白色摄影棚。
重点：一只手绘蜡笔风的小橘猫整只趴在他/她{左/右}侧肩膀上，四只爪子抓住T恤布料，尾巴自然垂落绕过手臂，脑袋靠在脸旁好奇地看；
一个手绘蜡笔风彩色冰淇淋甜筒正好被他/她张开的{左/右}手"握住"，甜筒柄与手指紧密贴合，看起来是真的拿着；
手绘小草和郁金香从光脚旁边长出来，叶子与脚趾相接触；头顶手绘太阳。
涂鸦为蜡笔质感、扁平色块、线条简单稚拙，颜色为暖橙、黄、草绿、砖红。
涂鸦与人物之间有遮挡和接触关系，不是简单平行贴图。
配 "yummy" 手写小字、爱心、星星。留白多、构图简洁、童趣梦幻。
```

## Template 2 — Big Monster Gag (ref-01 style)

```
儿童创意写真摄影，真实照片与蜡笔手绘涂鸦融合。保留{儿童}的面容、姿势、服装，背景为干净浅灰白摄影棚。
一只手绘橙色毛茸茸大怪兽站在他/她身后，比他/她高，正伸长手臂轻轻摘下他/她头上的{真实帽子}（与真实物体发生接触）；
一两只绿色小涂鸦怪兽抱着他/她的手臂或裤腿；黄色虚线在他/她头顶画一圈惊讶波纹；
手绘小草从脚边长出来并接触脚趾；手写英文 "{cool/…}" 与 "Fresh air"、螺旋太阳、爱心星星点缀。
蜡笔质感、扁平色块、稚拙线条，暖橙黄绿砖红限定色板，涂鸦与人物有真实遮挡接触，不是平行贴图。留白多、童趣梦幻。
```

## Template 3 — Prop Echo (ref-05 style, doodles echo real props)

```
儿童创意写真摄影，真实照片与蜡笔手绘涂鸦融合。保留{儿童}的面容、姿势、{与道具呼应的服装}，背景干净米白摄影棚。
围绕他/她画出手绘的{大鹅/鸭子/气球/…}：一只巨大的{鹅}头从画面边缘探入，几只小的飞在头顶和身侧；
地面上真实摆放的{小黄鸭/玩具车/…}旁画出手绘小草和小花，草叶与光脚相接触；
他/她的手正握着真实的{道具}，一只手绘小动物伸爪去碰它；
手写英文 "Happy day" 与 "eee~" 手绘线、爱心点缀。
蜡笔质感、扁平色块、暖黄橙限定色板，涂鸦与人物和真实道具均有接触，不是平行贴图。留白多、童趣梦幻。
```

## Template 4 — Imaginary Costume Piece (ref-03 style)

```
儿童创意写真摄影，真实照片与蜡笔手绘涂鸦融合。保留{儿童}的面容、姿势、服装，背景干净米白摄影棚。
一个手绘巨型{胡萝卜/气球/翅膀}从他/她背后探出，像背在身上的背包，与真实衣物重叠遮挡；
黄色小鸟飞过头顶；手绘郁金香和小草从脚边长出，叶片接触光脚；
头部旁一个大号手绘感叹号；手写英文小字与爱心星星点缀。
蜡笔质感、扁平色块、暖橙黄绿砖红限定色板，涂鸦与人物有真实接触遮挡，不是平行贴图。留白多、童趣梦幻。
```

## Correction Briefs (one targeted retry each)

- Face drifted: `面容与原图完全一致，不要改变五官、发型和表情` + raise input_fidelity; regenerate from the ORIGINAL photo.
- Doodles floating: append `所有涂鸦必须与人物身体发生物理接触或遮挡：握在手中、趴在肩上、从脚边长出；不是简单平行贴图`。
- Background busy: `背景必须替换为干净的米白色摄影棚纯色背景，保留柔和地面阴影，画面大量留白`。
- Wrong texture: `涂鸦必须是扁平蜡笔/彩铅质感，纯色块+简单稚拙线条，禁止3D渲染和写实阴影`。
- Text wrong: `手写字必须准确拼写为 "{word}"，小号，位于空白区域，不遮挡面部`。

## Delivery

- Save every output to a new file (never overwrite the source or previous versions).
- Present via present_files with a 2–4 bullet summary of the interactions realized.
- Offer iteration: change animal/element/position, or a stronger interaction variant.
