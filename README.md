
# Neural Network on Microcontroller (NNoM)
[![Build Status](https://travis-ci.org/majianjia/nnom.svg?branch=master)](https://travis-ci.org/majianjia/nnom)

NNoM is a higher-level layer-based Neural Network library specifically for microcontrollers. 

**Highlights**

- Deploy Keras model to NNoM model with one line of code.
- User-friendly interfaces.
- Support complex structures; Inception, ResNet, DenseNet, Octave Convolution...
- High-performance backend selections.
- Onboard (MCU) evaluation tools; Runtime analysis, Top-k, Confusion matrix... 


Guides:

[5 min to NNoM Guide](docs/guide_5_min_to_nnom.md)

[API Manual](https://majianjia.github.io/nnom/)

[RT-Thread Guide(中文指南)](https://majianjia.github.io/nnom/rt-thread_guide/)

Examples:

[MNIST-DenseNet example](examples/mnist-densenet)

[DenseNet](examples/mnist-densenet)

[Octave Convolution](examples/octave-conv)

[Keyword Spotting](examples/keyword_spotting)

[RT-Thread-MNIST example (中文)](https://majianjia.github.io/nnom/example_mnist_simple_cn/)


## Why NNoM?
The aims of NNoM is to provide a light-weight, user-friendly and flexible interface for fast deploying.

Nowadays, neural networks are **wider**, **deeper**, and **denser**.
![](docs/figures/nnom_wdd.png)
>[1] Szegedy, C., Liu, W., Jia, Y., Sermanet, P., Reed, S., Anguelov, D., ... & Rabinovich, A. (2015). Going deeper with convolutions. In Proceedings of the IEEE conference on computer vision and pattern recognition (pp. 1-9).
>
>[2] He, K., Zhang, X., Ren, S., & Sun, J. (2016). Deep residual learning for image recognition. In Proceedings of the IEEE conference on computer vision and pattern recognition (pp. 770-778).
>
>[3] Huang, G., Liu, Z., Van Der Maaten, L., & Weinberger, K. Q. (2017). Densely connected convolutional networks. In Proceedings of the IEEE conference on computer vision and pattern recognition (pp. 4700-4708).


After 2014, the development of Neural Networks are more focus on structure optimising to improve efficiency and performance, which is more important to the small footprint platforms such as MCUs. 
However, the available NN libs for MCU are too low-level which make it sooooo difficult to use with these complex strucures. 
Therefore, we build the NNoM to help developers to manage the structures, memory and parameters, even with the automatic tools for fast deploying. 

Now with NNoM, you are free to play with these more up-to-date, decent and complex structures on MCU. 

With [**Keras**](https://keras.io/) and our tools, deploying a model only takes a few line of codes, please do check the [examples](examples/).


## Available Operations

**Layers**

| Layers | Status |Layer API|Comments|
| ------ |-- |--|--|
| Convolution  | Beta|Conv2D()|Support 1/2D|
| Depthwise Conv | Beta|DW_Conv2D()|Support 1/2D|
| Fully-connected | Beta| Dense()| |
| Lambda |Alpha| Lambda() |single input / single output anonymous operation| 
| Input/Output |Beta | Input()/Output()| |
| Recurrent NN | Under Dev.| RNN()| Under Developpment |
| Simple RNN | Under Dev. | SimpleCell()| Under Developpment |
| Gated Recurrent Network (GRU)| Under Dev. | GRUCell()| Under Developpment |
| Flatten|Beta | Flatten()| |
| SoftMax|Beta | SoftMax()| Softmax only has layer API| 
| Activation|Beta| Activation()|A layer instance for activation|

**Activations**

Activation can be used by itself as layer, or can be attached to the previous layer as ["actail"](docs/A_Temporary_Guide_to_NNoM.md#addictionlly-activation-apis) to reduce memory cost.

| Actrivation | Status |Layer API|Activation API|Comments|
| ------ |-- |--|--|--|
| ReLU  | Beta|ReLU()|act_relu()||
| TanH | Beta|TanH()|act_tanh()||
|Sigmoid|Beta| Sigmoid()|act_sigmoid()||

**Pooling Layers**

| Pooling | Status |Layer API|Comments|
| ------ |-- |--|--|
| Max Pooling  | Beta|MaxPool()||
| Average Pooling | Beta|AvgPool()||
| Sum Pooling | Beta|SumPool()| |
| Global Max Pooling  | Beta|GlobalMaxPool()||
| Global Average Pooling | Beta|GlobalAvgPool()||
| Global Sum Pooling | Beta|GlobalSumPool()|A better alternative to Global average pooling in MCU before Softmax|
| Up Sampling | Beta|UpSample()||

**Matrix Operations Layers**

| Matrix | Status |Layer API|Comments|
| ------ |-- |--|--|
| Multiple  |Beta |Mult()||
| Addition  | Beta|Add()||
| Substraction  | Beta|Sub()||
| Dot  | Under Dev. |||



## Dependencies

NNoM now use the local pure C backend implementation by default. Thus, there is no special dependency needed. 



## Optimization
You can select [CMSIS-NN/DSP](https://github.com/ARM-software/CMSIS_5/tree/develop/CMSIS/NN) as the backend for about 5x performance with ARM-Cortex-M4/7/33/35P. 

Check [Porting and optimising Guide](docs/Porting_and_Optimisation_Guide.md) for detail. 



## Contacts
Jianjia Ma

J.Ma2@lboro.ac.uk or majianjia@live.com

## Citation Required
Please contact us using above details. 


