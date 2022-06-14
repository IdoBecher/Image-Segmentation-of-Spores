# Image-Segmentation-of-Spores
Segmentation of microscope images of spores in a petry dish taken in a laboratory.

## Dataset
Images of surfaces that are scattered in spores and taken using a microscope.
Small images of spores that have been cut into images of a maximum of 100X100 pixels.

## Model Used

The model that was used is UNET model: 
The UNET model architecture contains two paths. First path is the contraction path (also called as the encoder) which is used to capture the context in the image. The encoder is just a traditional stack of convolutional and max pooling layers. The second path is the symmetric expanding path (also called as the decoder) which is used to enable precise localization using transposed convolutions. Thus it is an end-to-end fully convolutional network (FCN), i.e. it only contains Convolutional layers and does not contain any Dense layer because of which it can accept image of any size.


Input images are resized to an optimal size and then fed into the Convolutional layer. These images are converted to their pixel values, which can be imagined as a three-dimensional matrix for the purpose of visualization. The Convolutional layer has a kernel. This kernel is generally a small matrix of specified kernel size mxnx3 (3 for RGB images). 


**Rectified Linear Unit (ReLU)** is the activation layer used in CNNs.The activation function is applied to increase non-linearity in the CNN. Images are made of different objects that are not linear to each other.


**Max Pooling:** A limitation of the feature map output of Convolutional Layers is that they record the precise position of features in the input. This means that small movements in the position of the feature in the input image will result in a different feature map. This can happen with re-cropping, rotation, shifting, and other minor changes to the input image. A common approach to addressing this problem from signal processing is called down sampling. This is where a lower resolution version of an input signal is created that still contains the large or important structural elements, without the fine detail that may not be as useful to the task.


**Transposed convolution:** (sometimes called as deconvolution or fractionally strided convolution) is a technique to perform up sampling of an image with learnable parameters.transposed convolution is exactly the opposite process of a normal convolution i.e., the input volume is a low resolution image and the output volume is a high resolution image.

An illustration of UNET model:

![image](https://user-images.githubusercontent.com/97231735/173613910-2a1af78c-f3c9-48af-b70c-47e9b8041ec7.png)

Credit for demonstration: https://towardsdatascience.com/understanding-semantic-segmentation-with-unet-6be4f42d4b47
