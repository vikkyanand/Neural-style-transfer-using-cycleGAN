# Neural-style-transfer-using-cycleGAN

This project we learn the  artistic style from one painting, and apply the artistic style to another painting . FIrst we create two networks Generator and Discriminator.
The Generator generates new classes of data while the Discriminator tries to evaluate the authenticity of this new data. 

# Why CycleGAN?
While there has been a great deal of research into this task, most of it has utilised supervised training, where we have access to (x, y) pairs of corresponding images from the two domains we want to learn to translate between. CycleGAN is interesting because it did not require paired training data.

Step 1: Dataset Loading and Preprocessing
Load the Dataset and extract images to convert to an array of images which will be stored in a compresses NumPy array format. We will also need helper functions to load & generate real samples and to generate fake samples.

Step 2: Making the Discriminator (D) model
The Discriminator is a deep convolutional neural network that performs image classification. It takes a source image as input and predicts the likelihood of whether the target image is a real or fake image. Two discriminator models are used, one for Domain-A  and one for Domain-B .

Step 3: Making the Generator (G) Model
The generator is an encoder-decoder model architecture. The model takes a source image (e.g. horse photo) and generates a target image (e.g. zebra photo). It does this by first downsampling or encoding the input image down to a bottleneck layer, then interpreting the encoding with a number of ResNet layers that use skip connections, followed by a series of layers that upsample or decode the representation to the size of the output image. So, we first define a ResNet block and then our Generator Model.

->The discriminator models are trained directly on real and generated images, whereas the generator models are not.

Step 4: Combine the models

Step 5: Train the model
We will need helper functions in order to save Models at checkpoints, summarise Performance during training and update Image Pool for fake images.
