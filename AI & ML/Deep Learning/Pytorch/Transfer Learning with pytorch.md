- before using model from `torchvision.models` there's some requirements
	- All pre-trained models expect input images normailzed
		-  image rande = [0,1]
		- mean = [0.485, 0.456, 0.406]
		- srd = `[0.229, 0.224, 0.225]`.

``` python
normalize = transforms.Normalize(mean=[0.485, 0.456, 0.406], std=[0.229, 0.224, 0.225])
``` 

- After setup a model from `torchvision.models` then select **Pretrained model weights** 

```python
weights = torchvision.models.EfficientNet_B0_Weights.DEFAULT
```

> `default` = best available weights( best performce in `ImageNet` model)

- but if you have import weights from `torchvision.models` you can do **Auto Transform** instead of create manual transform by using `transform` method

#### which pretrained model should you use?
- the higher number in model means better performace but larger model
	- e.g. effieicnetnet_b0() -> b1 -> ... -> b7
- **performance vs speed vs size tradeoff** will be come with time.


