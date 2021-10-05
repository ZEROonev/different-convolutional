Grouped Convolution 组卷积
Introduced by Krizhevsky et al. in ImageNet Classification with Deep Convolutional Neural Networks
 

A Grouped Convolution uses a group of convolutions 组卷积是一组卷积
- multiple kernels per layer 每层不同的卷积核
- resulting in multiple channel outputs per layer. 每层由多个channel 输出 
This leads to wider networks helping a network learn a varied set of low level and high level features.
这将导致网络学习一组从高级到低级的特征
The original motivation of using Grouped Convolutions in AlexNet 原始的使用在AlexNet
was to distribute the model over multiple GPUs as an engineering compromise. 
But later, 
with models such as ResNeXt, it was shown this module could be used to improve classification accuracy. 
Specifically by exposing a new dimension through grouped convolutions, 
cardinality (the size of set of transformations), we can increase accuracy by increasing it.
早期用于提高分类准确性
![image](https://user-images.githubusercontent.com/84374554/135972763-99478ed6-ae5c-41a4-a2f5-3cc65f71c1c4.png)

