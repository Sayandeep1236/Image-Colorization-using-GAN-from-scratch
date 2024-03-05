# Image-Colorization-using-GAN-from-scratch

Implementation of a basic pix2pix GAN model in TensorFlow, and using it to colorize grayscale images to color images.

We first load the colored and greyscale images using TensorFlow image utils.
![image](https://github.com/Sayandeep1236/Image-Colorization-using-GAN-from-scratch/assets/143305455/3a8da39c-7216-4e89-9848-88792c3490e8)

Then we move on to building the model. Here, we use a Pix2Pix CGAN to achieve image-to-image translation. As per the paper, "Image-to-Image Translation with Conditional Adversarial Networks", we use a U-Net structure for making the generator and a PatchGAN architecture for the discriminator.

The U-Net architecture helps in mapping a high-resolution input to a high-resolution output. It makes use of the encoder-decoder network, where the input is passed through several encoders that downsample the image, reach a bottleneck, then upsample the image to the required resolution. Here, the greyscale image is given as the input and is treated as both the noise as well as the class embedding when seen relative to a normal CGAN model. The model also helps in skipping connections so that redundant information is not lost and is concatenated in the upcoming layers.

![image](https://github.com/Sayandeep1236/Image-Colorization-using-GAN-from-scratch/assets/143305455/6f5aeef9-5399-48b0-987d-2e4640ad2393)

![image](https://github.com/Sayandeep1236/Image-Colorization-using-GAN-from-scratch/assets/143305455/680c8da9-98b9-4949-960b-f31326208886)

The U-Net architecture is shown as below:

![image](https://github.com/Sayandeep1236/Image-Colorization-using-GAN-from-scratch/assets/143305455/63ed8d4a-f4f4-45a1-a078-ffabde1c77f5)

For the discriminator, we make the PatchGAN architecture, where the inputs are the generated image and the real image, that is, the colored counterpart. The real image here acts as the class on which the generated image is judged.

![image](https://github.com/Sayandeep1236/Image-Colorization-using-GAN-from-scratch/assets/143305455/f129c476-db03-4f52-a626-67f0e4c8d2b5)

The discriminator architecture is given below:

![image](https://github.com/Sayandeep1236/Image-Colorization-using-GAN-from-scratch/assets/143305455/e0a2f5d8-add1-40a1-aa6c-4372249acd8f)

For training, we first train the discriminator to distinguish between fake and real images. Then we update the weights of the generator using the trained discriminator in order to give us the required image.
![image](https://github.com/Sayandeep1236/Image-Colorization-using-GAN-from-scratch/assets/143305455/d681fd88-f2d6-43d9-9e24-4fc439de227d)

![image](https://github.com/Sayandeep1236/Image-Colorization-using-GAN-from-scratch/assets/143305455/80c86e87-4ac0-4249-9406-2f2fd32ec5ca)

Model fitting:
![image](https://github.com/Sayandeep1236/Image-Colorization-using-GAN-from-scratch/assets/143305455/2e924797-8f2a-4ea9-8395-09fef7c65b9b)

Testing the model:

![image](https://github.com/Sayandeep1236/Image-Colorization-using-GAN-from-scratch/assets/143305455/b1170f59-1061-48f7-98ad-67deb66b02e6)


-------------------------------------------------------------------------------x------------------------------------------------------------------------------------


