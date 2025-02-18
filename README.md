# Generative-Approaches

## Bayes Generation - HW_1

The task was to develop an algorithm that would choose each pixel's RGB values using probabilities we had previously determined from a set of avatar pictures.

The avatars:
<p><img src="HW_1/pics/avatars.png"></p>

The result of the algorithm:

<p><img src="HW_1/pics/result.png"></p>

Since the algorithm doesn't take into account that neigbouring pixels are supposed to correlate and actually depend on each other, the resulting avatar has a specific appearance, proving that this particular type of generation isn't the best option for picture generation.
 


## Autoencoders - HW_2

The task was to implement and train different types of autoencoder architectures such as autoencoder (AE), variational autoencoder (VAE), and convolutional variational autoencoder (ConvVAE). MNIST and CelebA datasets were used for training the mentioned models. The following results are provided for the CelebA part of the assignment.

What CelebA dataset looks like (center crop 128x128 pixels):
<p><img src="HW_2/pics/celeba.png"></p>

The results of Convolutional VAE generation:
<p><img src="HW_2/pics/result.png" height="180px"></p>
<p><img src="HW_2/pics/results.png"></p>

As could be expected, the results are better than just a simple bayesian generation. We don't see any artifacts or randomly placed pixels; however, we didn't avoid the widely-known problem of simple autoencoders - the pictures look blurry, especially the background.



## GANs - HW_3

The task was to train a DCGAN architecure and implement and train a new GAN architecture, which would be based on DCGAN and altered with CSP-blocks used in a generator network. The CelebA dataset (64 x 64 pixels) was used for training. The results of the DCGAN performance after 10 epochs of training:

<p><img src="HW_3/pic_examples/dcgan.png"></p>

However, the new architecture didn't perform as hoped. It was difficult to achieve any signs of convergeance and whatever was produced didn't particulary fit what had been expected:

<p><img src="HW_3/pic_examples/csp_gan_2.png"></p>

Although faces can be seen, it mostly looks like the beginning of a mode collapse, a known problem in the generative adversarial approach.



## Inpainting - HW_4

The task was to research and try different pretrained networks for picture inpainting/enhancement. Such networks as MAT and GPEN were used for the assignment. The original picture, masked pictures, and results are as follows:

Original picture:
<p><img src="HW_4/pics_and_gifs/cropped_original.png"\></p>

Masks №1 & №2:
<p><img src="HW_4/pics_and_gifs/img_0_small_mask.png"\></p>
<p><img src="HW_4/pics_and_gifs/img_1_bigger_mask.png"\></p>

MAT inpainting (CelebA weights):
<p><img src="HW_4/pics_and_gifs/img_0_CelebA.png"\></p>
<p><img src="HW_4/pics_and_gifs/img_1_CelebA.png"\></p>

MAT inpainting (FFHQ weights):
<p><img src="HW_4/pics_and_gifs/img_0_FFHQ.png"\></p>
<p><img src="HW_4/pics_and_gifs/img_1_FFHQ.png"\></p>

GPEN inpainting:
<p><img src="HW_4/pics_and_gifs/img_0_GPEN.jpg" height="512px"\></p>
<p><img src="HW_4/pics_and_gifs/img_1_GPEN.jpg" height="512px"\></p>

MAT inpainting (FFHQ weights) seems to be slightly better than MAT (CelebA weights) and a lot better than GPEN inpainting. Further experiments were conducted on the 1st masked picture after MAT inpainting (FFHQ weights).

GPEN enhancement after MAT inpainting (FFHQ weights):
<p><img src="HW_4/pics_and_gifs/img_0_FFHQ_GPEN.jpg" height="512px"\></p>

The picture became brighter, the resolution became higher. It looks like some make up was added, but GPEN enhancement didn't improve any previous inpainting errors such as with the nose and lips (asymmetry).
