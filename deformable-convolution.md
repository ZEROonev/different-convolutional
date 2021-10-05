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
