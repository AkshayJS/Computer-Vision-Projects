# Computer Vision - Exercises

This repository consists of all the projects completed during my learning phase in computer vision.

## 1. CNN Architectures with MNIST, CIFAR and Flowers Datasets

### a. MNIST Dataset
In this notebook, I have tried with different CNN architectures with MNIST dataset. Below are the key startegies I followed.
-  In the first architecture, I tried not to use FC layers. My main intention was to reduce the number of parameters significantly.
-  Padding: Padding is omitted in each CONV layer to avoid addition of blank pixels to the image.
-  Pooling: Maxpool layers are used minimally to avoid information loss.
-  Kernels: Kernel size of 3x3 were used as it consumes less trainable parameters when compared to subsequent kernels. (Eg: 5x5, 7x7...)
-  Optmizers: RMSprop was found to the best optimizer followed by adam and adagrad optimizers.
-  Best Architecture: Combination of CONV and Dense architecture gave best accuracy. However, pure CNN architecture were not much far behind and had significantly less trainable parameters. This could be advantageous while building lightweight deep learning architectures.

### b. CIFAR Dataset
CIFAR dataset has 10 class dataset and 100 class benchmark datasets. For practice purpose, I have taken CIFAR-10 dataset with 32x32 pixels size.
-  Combination of CONV and FC layers were used for all 5 architectures.
-  Startegy followed for Padding, Pooling operations and choices for kernel size and optimizers were kept same as MNIST.
-  Dropout was used as replacement for Maxpool to avoid information loss and to eliminate inactive neurons (Architectures 3,4 and 5). This gave significant boost in performance of the architectures.
-  Accuracy achieved was around 63%.


### c. Flowers Dataset
[Flowers dataset](https://www.kaggle.com/alxmamaev/flowers-recognition) contains 4317 images belonging to 5 different classes (daisy, dandelion, rose, sunflower, tulip). Each image is in RGB format and has size (224x224). Since the data is huge, ImageDatagenerator is used to generate batch of images for each epoch.

Validation Accuracy: 66.3%

## 2. CNN for MNIST dataset with less than 10,000 parameters:

| Layer | Filters | Kernel | Activation |
|:-----:|:-------:|:------:|:----------:|
|Conv|32|(3,3)|ReLU|
|Conv|32|(3,3)|ReLU|
|MaxPool|--|(2,2)|--|
|Conv|32|(3,3)|ReLU|
|Conv|32|(3,3)|ReLU|
|Conv|64|(3,3)|ReLU|
|Conv|64|(3,3)|ReLU|
|Conv|10|(4,4)|Softmax|
|||||
|Trainable params:|93,738|


## 3. Inception Network with CIFAR-10:
Pretrained Inception network was used as base architecture.
a. Pretrained Inception network with weights derived from imagenet was used as base architecture.
b. Images were upsampled 3 times to get the image size of (256x256).
c. FC Layers were used as closing layers to get finely trained model.

Validation Accuracy achieved at the end of 2nd epoch: 70%

## 4. Inception implementation from scratch:
Complete implemention of Inception modules along with aux outputs.
a. CIFAR-10 dataset was taken as benchmark dataset
b. Inception V1 block was designed as on [Inception Research Paper](https://arxiv.org/pdf/1409.4842.pdf)

Validation Accuracy: 81.11%
