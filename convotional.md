Convolution
卷积
  
A convolution is a type of matrix operation, consisting of a kernel, a small matrix of weights,  
that slides over input data performing element-wise multiplication with the part of the input it is on,  
then summing the results into an output. 
卷积是一种矩阵运算操作,由卷积核和小的矩阵权重组成,滑过输入数据,与它所在的输入部分执行逐像素乘积,之后汇总相加. 

Intuitively, a convolution allows for weight sharing 卷积操作允许权重共享, 
- reducing the number of effective parameters减少有效参数量 
- and image translation (allowing for the same feature to be detected in different parts of the input space 
图像转换,允许在图像不同位置检测到相同的特征, 

