#Depthwise Convolution:深度卷积

Depthwise Convolution is a type of convolution where we apply a single convolutional filter for each input channel.  
In the regular 2D convolution performed over multiple input channels,  
the filter is as deep as the input and lets us freely mix channels to generate each element in the output.  
In contrast, depthwise convolutions keep each channel separate.   
To summarize the steps, we:  

Split the input and filter into channels.  
We convolve each input with the respective filter.  
We stack the convolved outputs together.  
来源:https://paperswithcode.com/method/depthwise-convolution#
'''
深度卷积是一种卷积,我们使用单个卷积核过滤每个输入通道,在常规的2D卷积中执行不同通道,过滤器的深度核输入的通道数一样,输出的每一个元素是由自由的混合不同通道计算得到的
,相比较,深度卷积使得每个通道分离,
将输入的每个通道分离,每个通道计算得到每个channel的输出,然后stack
![image](https://user-images.githubusercontent.com/84374554/135942957-5e6b10f6-0d0e-45f3-bac4-36ce8f8c4fe2.png)


具体实现:
来源:https://github.com/tstandley/Xception-PyTorch/blob/master/xception.py
```
class SeparableConv2d(nn.Module):
    def __init__(self,in_channels,out_channels,kernel_size=1,stride=1,padding=0,dilation=1,bias=False):
        super(SeparableConv2d,self).__init__()

        self.conv1 = nn.Conv2d(in_channels,in_channels,kernel_size,stride,padding,dilation,groups=in_channels,bias=bias)
        self.pointwise = nn.Conv2d(in_channels,out_channels,1,1,0,1,1,bias=bias)
    
    def forward(self,x):
        x = self.conv1(x)
        x = self.pointwise(x)
        return x
```
