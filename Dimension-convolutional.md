Dimension-wise Convolution
Introduced by Mehta et al. in DiCENet: Dimension-wise Convolutions for Efficient Networks
 
 Edit
A Dimension-wise Convolution, or DimConv, is a type of convolution that can encode depth-wise, width-wise, 
and height-wise information independently. 
To achieve this, DimConv extends depthwise convolutions to all dimensions of the input tensor , where , , and
corresponds to width, height, and depth of . 
DimConv has three branches, one branch per dimension. 
These branches apply  depth-wise convolutional kernels  along depth,  
width-wise convolutional kernels  along width, and  height-wise convolutional kernels  kernels along height to produce outputs , ,
and  that encode information from all dimensions of the input tensor. 
The outputs of these independent branches are concatenated along the depth dimension, such that the first spatial plane of , ,
and  are put together and so on, to produce the output {, , } .

https://production-media.paperswithcode.com/methods/Screen_Shot_2020-06-21_at_11.34.22_PM.png

Source:  DiCENet: Dimension-wise Convolutions for Efficient Networks
https://paperswithcode.com/method/dimconv#
