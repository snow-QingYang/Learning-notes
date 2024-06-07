
## Introduction

Convolutional Neural Networks (CNNs) are a class of deep learning models widely used in image recognition, video analysis, among other fields. CNNs learn hierarchical features from data, capable of automatically extracting features from input data without the need for manual feature engineering.

## Basic Structure of a Convolutional Neural Network

### 1. Input Layer
- We fed the raw image data into the network 

### 2. Convolutional Layer
- **Filters/Kernels:** These are small windows that slide over the input image (or the output of the previous layer) to produce feature maps. Each filter is responsible for detecting a specific feature, such as edges or textures.
- **Stride:** This is the step size of the filter when sliding over the input. A larger stride results in a smaller feature map.
- **Padding:** This is used to control the spatial size of the output volume. 'Same' padding ensures the output is the same width and height as the input.
### 3. Activation Function
- **ReLU (Rectified Linear Unit):** Describe the role of ReLU as a non-linear activation function.
- Discuss other activation functions such as Sigmoid or Tanh if applicable.

### 4. Pooling Layer
The pooling layer reduces the spatial size of the input volume, which decreases the number of parameters and computation in the network.
- **Max Pooling:**  It selects the maximum value in a patch of the input.
- **Average Pooling:** It calculates the average value in a patch of the input.

### 5. Fully Connected Layer
Feedforward neural network

### 6. Output Layer
- The final layer is designed to produce the output of the network. For a classification task, it could be a softmax layer that outputs probabilities for each class.

# ResNet (Residual Networks) Explained

## Introduction

Residual Networks, or ResNets, were introduced by Kaiming He et al. in their paper "Deep Residual Learning for Image Recognition" (2015). ResNets are a significant advancement in the field of deep learning, particularly for the task of image recognition. They address the problem of training very deep networks by introducing residual connections or skip connections.

## Key Concepts

### 1. Residual Connections
Residual connections allow the input of one layer to be added to the output of a subsequent layer. This is done to enable the training of networks that are much deeper than their predecessors.

### 2. Skip Connections
A skip connection is a direct connection between layers that skips one or more layers. This is a form of residual learning where the output of a layer is added to the output of a layer several layers deeper.

### 3. Identity Mapping
In ResNets, the skip connections perform identity mapping, meaning that the input is added to the output without any change. This is a simple yet effective way to allow gradients to flow through the network during training.

## Architecture

### Basic Block
The basic building block of a ResNet is a residual block, which consists of two layers followed by a skip connection that adds the input to the output.

- Input: \( x \)
- Layer 1: \( F(x) \) (with some learnable parameters)
- Layer 2: \( F(F(x)) \) (with some learnable parameters)
- Output: \( F(F(x)) + x \) (input added to the output of the second layer)

