# Denoising-Diffusion-Model

The provided code implements a Denoising Diffusion Probabilistic Model (DDPM) for image generation using TensorFlow and Keras


1)Preprocessing and Data Loading:
The CIFAR-10 dataset is loaded and normalized to a range of [0, 1].



2)Diffusion Schedules:
Three different diffusion schedules are defined: linear, cosine, and offset cosine. These schedules determine how noise is added to the images over the diffusion process.



3)Sinusoidal Embeddings:
Sinusoidal embeddings are used to encode noise variances for better diffusion process handling.



4)UNet Architecture:
A UNet model is built with residual blocks, downsampling, and upsampling blocks to denoise images.



5)Diffusion Model Class:
A)The DiffusionModel class inherits from keras.Model and integrates the UNet model.

It includes methods for:
i)Normalizing and denormalizing images.

ii)Performing the denoising process.

iii)Reverse diffusion to generate new images from noise.

iv)Training and testing steps for model optimization.

v)The call method is defined to handle the inputs and forward pass.


B)Training and Evaluation:
i)The model is compiled with the AdamW optimizer and mean absolute error loss.

ii)The model is trained on the CIFAR-10 dataset using the fit method.

iii)TensorBoard callback is used for logging.


6)Image Generation:
After training, the model generates new images by reversing the diffusion process starting from random noise.
