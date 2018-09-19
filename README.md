# TwinGAN -- Unsupervised Image Translation for Human Portraits

![result](docs/images/AX18_TwinGAN-14.png)
![identity_preservation](docs/images/AX18_TwinGAN-15.png)
![search_engine](docs/images/AX18_TwinGAN-17.png)
![search_engine](docs/images/AX18_TwinGAN-18.png)

## Use Pretrained Model.

For a pretrained model, you can download it [here](https://drive.google.com/open?id=1dXfqAODQxB2uNhyQANtZICAjwhNMWnbl):

Run the following command to translate the demo inputs.

```
python inference/image_translation_infer.py --model_path="twingan_256/256" --image_hw=256 --input_tensor_name="sources_ph" --output_tensor_name="custom_generated_t_style_source:0" --input_image_path="./demo/inference_input/" --output_image_path="./demo/inference_output/"
```

The `input_image_path` can be either one single image or a path containing images.

## Training

Download CelebA and the Getchu dataset by following the [datasets guide](docs/datasets.md). Then train your model using script from the [training guide](docs/training.md).

## Blog and Technical report.

An English [blog](docs/blog/blog_EN.md) and a [Chinese 中文 blog](docs/blog/blog_CH.md) are published in early April 2018 and are available for readers with less technical background.

Please refer to [technical report](docs/tech_report/twingan.pdf) for details on the network structure and losses. The report is still work in progress.

Extra materials:

[Presentation Slides at Anime Expo 2018](https://docs.google.com/presentation/d/1PWYFDYKzwiyK4ajBHl9N7GIS_WQ-SSIjCh50YRLqgNM/edit?usp=sharing)

## Related works

Our idea of using adaptive normalization parameters for image translation is not unique. To the best of our knowledge, at least two more work have similar ideas: [MUNIT](https://arxiv.org/abs/1804.04732) and [EG-UNIT](https://arxiv.org/abs/1805.11145). Our model is developed around the same time period as these models. 

Some key differences between our model and the two mentioned are -- we find UNet to be extremely helpful in maintaining semantic correspondence across domain, and we found that sharing all convolution filter weights speeds up training while maintaining the same output quality.


## Reference

A lot of the code are adapted from online. Here is a non-exhaustive list of the repos where I borrowed code from extensively.

[TF-Slim image models library](https://github.com/tensorflow/models/tree/master/research/slim)

[PGGAN](https://github.com/tkarras/progressive_growing_of_gans/)

## Anime related repos and datasets

Shameless self promotion of my [AniSeg](https://github.com/jerryli27/AniSeg) anime object detection & segmentation model.

Sketch coloring using [PaintsTransfer](https://github.com/lllyasviel/style2paints) and [PaintsChainer](http://paintschainer.preferred.tech/).

Create anime portraits at [Crypko](https://crypko.ai/) and [MakeGirlsMoe](https://make.girls.moe/#/)

The all-encompassing anime dataset [Danbooru2017](https://www.gwern.net/Danbooru2017) by gwern.

My hand-curated [sketch-colored image dataset](https://github.com/jerryli27/pixiv_dataset).

## Disclaimer

This personal project is developed and open sourced when I am working for Google, therefore you see Copyright 2018 Google LLC in each file. This is not an officially supported Google product. See [License](LICENSE) and [Contributing](CONTRIBUTING.md) for more details.
