

### 自动标注（AutoLabel）

`automatic_label` 示例:

```python
from paddlemix import Appflow
from ppdiffusers.utils import load_image
task = Appflow(app="auto_label",
               models=["paddlemix/blip2-caption-opt2.7b","GroundingDino/groundingdino-swint-ogc","Sam/SamVitH-1024"]
               )
url = "https://paddlenlp.bj.bcebos.com/models/community/CompVis/stable-diffusion-v1-4/overture-creations.png"
image_pil = load_image(url)
blip2_prompt = 'describe the image'
result = task(image=image_pil,blip2_prompt = blip2_prompt)
```

效果展示

<div align="center">

| Input Image | prompt| Generate Description | annotated image|
|:----:|:----:|:----:|:----:|
|![dog](https://github.com/LokeZhou/PaddleMIX/assets/13300429/badcfbdc-6b5a-40c4-9128-65259b3d1995) |describe the image| of the dog sitting on the bench in the field | ![dog_mask](https://github.com/LokeZhou/PaddleMIX/assets/13300429/6a1bd63e-6253-4354-8828-b4f45301fb30)|
|![horse](https://github.com/LokeZhou/PaddleMIX/assets/13300429/2c68bf76-a402-4b7e-992a-20b9d19b017c) |describe the image| of the horse in the field with the mountains in the background |![horse_mask](https://github.com/LokeZhou/PaddleMIX/assets/13300429/f1188dce-457c-4116-9a34-cd95ec459cd6) |
</div>
