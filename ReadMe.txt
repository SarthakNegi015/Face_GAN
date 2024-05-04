# Face-GAN
Generates random faces using generative AI technique's Generative Adversarial Networks. 

This code defines a Generative Adversarial Network (GAN) for generating images. Here's a brief summary of the hyperparameters and layers used:

### Hyperparameters:
- `image_size`: Size of the input images (e.g., 64x64).
- `batch_size`: Number of images in each batch during training (e.g., 128).
- `latent_size`: Size of the latent space, which is the input to the generator network.
- `stats`: Mean and standard deviation for normalizing the image data.
- Learning Rate (`lr`): Learning rate of 0.0002 for the Adam optimizer used in training both the generator and discriminator networks.
- `momentum`: Momentum parameter used in batch normalization layers.

### Layers:
#### Generator:
- The generator network consists of a series of transposed convolutional layers (`ConvTranspose2d`) followed by batch normalization (`BatchNorm2d`) and ReLU activation functions.
- The final layer uses the Tanh activation function to ensure the pixel values of generated images are in the range [-1, 1].

#### Discriminator:
- The discriminator network is composed of convolutional layers (`Conv2d`) with batch normalization and LeakyReLU activation functions.
- The last layer is a fully connected layer (`Flatten`) followed by a Sigmoid activation function, producing a probability score indicating whether the input image is real or fake.

### Training:
- The training loop consists of alternating updates between the generator and discriminator networks.
- The generator aims to minimize the binary cross-entropy loss by fooling the discriminator into classifying generated images as real.
- The discriminator aims to minimize the binary cross-entropy loss by correctly classifying real and fake images.
- The Adam optimizer with specified learning rates and betas is used for both networks.

Overall, this code defines a GAN architecture for image generation, where the generator learns to produce realistic images, while the discriminator learns to distinguish between real and fake images.
