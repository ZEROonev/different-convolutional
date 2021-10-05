Deformable Convolution
Introduced by Dai et al. in Deformable Convolutional Networks
 可变形卷积
 Edit
Deformable convolutions add 2D offsets to the regular grid sampling locations in the standard convolution. 
可变形卷积增加2Doffset到常规的网格位置采样,
It enables free form deformation of the sampling grid. 
使得网格自由变形
The offsets are learned from the preceding feature maps, via additional convolutional layers.
偏移量是通过额外的卷积层从前面的特征图中学习的。  
Thus, the deformation is conditioned on the input features in a local, dense, and adaptive manner. 
因此，变形卷积的局部、密集和自适应的方式取决于输入特征。  
![image](https://user-images.githubusercontent.com/84374554/135979386-3e300f2e-3344-4ce0-9fe7-3f1c79af9d88.png)

代码: https://github.com/chengdazhi/Deformable-Convolution-V2-PyTorch/blob/2f57c5db49161bd6c899670a5e4fba50e6b8fd26/modules/deform_conv.py#L10
```
import math

import torch
import torch.nn as nn
from torch.nn.modules.module import Module
from torch.nn.modules.utils import _pair
from functions import deform_conv_function


class DeformConv(Module):
    def __init__(self,
                 in_channels,
                 out_channels,
                 kernel_size,
                 stride=1,
                 padding=0,
                 dilation=1,
                 num_deformable_groups=1):
        super(DeformConv, self).__init__()
        self.in_channels = in_channels
        self.out_channels = out_channels
        self.kernel_size = _pair(kernel_size)
        self.stride = _pair(stride)
        self.padding = _pair(padding)
        self.dilation = _pair(dilation)
        self.num_deformable_groups = num_deformable_groups

        self.weight = nn.Parameter(
            torch.Tensor(out_channels, in_channels, *self.kernel_size))

        self.reset_parameters()

    def reset_parameters(self):
        n = self.in_channels
        for k in self.kernel_size:
            n *= k
        stdv = 1. / math.sqrt(n)
        self.weight.data.uniform_(-stdv, stdv)

    def forward(self, input, offset):
        return deform_conv_function(input, offset, self.weight, self.stride,
                             self.padding, self.dilation,
                             self.num_deformable_groups)
