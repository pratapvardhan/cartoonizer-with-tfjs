# Cartoonizer with TensorFlow.js

[Try application][liveapp]

We used Generative Adversarial Network (GAN) model proposed in 
[Learning to Cartoonize Using White-box Cartoon Representations][cvpr2020] (CVPR 2020) by Xinrui Wang and Jinze Yu.

Our idea was to test if it is reasonably possible to perform model inferences in
the browser clients with CPUs only. Without needing to send any of user's data (images) to servers.

**[App preview][liveapp]**: Upload an image or try examples

[![demo](./assets/demo.jpg)][liveapp]

Here's the application flow and architecture:

<p align="center">
  <img src="./assets/flow.jpg" style="max-width:650px;width:100%;"/>
</p>

TensorFlow's Saved models are converted to TensorFlow.js models.
Images are padded and scaled to 256px before they are fed to the model.
This rescaling is done to speed up the processing and might reduce the quality too.

Model footprint is ~1.5MB. These models in the browsers without GPU acceleration could manage to cartoonize,
but takes anywhere between 5-10 seconds for processing.
This is much slower than tflite models performance in mobile devices.
However, web browsers benefit from users not needing to install anything or transmitting data outside of their systems.

## Credits

This work was possible due to 
- [Margaret Maynard-Reid](https://twitter.com/margaretmz) and [Sayak Paul](https://twitter.com/RisingSayak)'s work on [How to Create a Cartoonizer with TensorFlow Lite](https://blog.tensorflow.org/2020/09/how-to-create-cartoonizer-with-tf-lite.html)
- [Xinrui Wang](https://github.com/SystemErrorWang/) and Jinze Yu's original work on [White-box CartoonGAN][cvpr2020]

## Citation
Xinrui Wang and Jinze Yu are the original authors of [White-box CartoonGAN][cvpr2020].
```
@InProceedings{Wang_2020_CVPR,   
author = {Wang, Xinrui and Yu, Jinze,     
title = {Learning to Cartoonize Using White-Box Cartoon Representations,   
booktitle = {IEEE/CVF Conference on Computer Vision and Pattern Recognition (CVPR)},   
month = {June}, year = {2020} }
```

### Links

- Original [White-box Cartoonization Repo](https://github.com/SystemErrorWang/White-box-Cartoonization)
- Cartoonizer with [TensorFlow Lite Repo](https://github.com/margaretmz/Cartoonizer-with-TFLite)
- [Live application][liveapp]
- [Repo](https://github.com/pratapvardhan/cartoonizer-with-tfjs/), Notebook, Colab

[cvpr2020]: https://openaccess.thecvf.com/content_CVPR_2020/papers/Wang_Learning_to_Cartoonize_Using_White-Box_Cartoon_Representations_CVPR_2020_paper.pdf
[liveapp]: https://gramener.com/cartoonizer/
[repo]: https://github.com/pratapvardhan/cartoonizer-with-tfjs/