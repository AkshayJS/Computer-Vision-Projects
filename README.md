# Computer-Vision-Exercises

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
