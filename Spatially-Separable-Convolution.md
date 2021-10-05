Spatially Separable Convolution
空间可分离卷积
A Spatially Separable Convolution decomposes a convolution into two separate operations.   
In regular convolution, if we have a 3 x 3 kernel then we directly convolve this with the image.   
We can divide a 3 x 3 kernel into a 3 x 1 kernel and a 1 x 3 kernel.   
Then, in spatially separable convolution, we first convolve the 3 x 1 kernel then the 1 x 3 kernel.   
This requires 6 instead of 9 parameters compared to regular convolution,  
and so it is more parameter efficient (additionally less matrix multiplications are required).  
首先使用3x1之后使用1x3卷积,优点是使用6个参数,代替9个参数,更少的卷积计算.
![image](https://user-images.githubusercontent.com/84374554/135945770-f97920bc-d952-48e2-929a-7bfdfc285d92.png)
