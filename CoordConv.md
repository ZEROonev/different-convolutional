A CoordConv layer is a simple extension to the standard convolutional layer. 
It has the same functional signature as a convolutional layer,
but accomplishes the mapping by first concatenating extra channels to 
the incoming representation. 
These channels contain hard-coded coordinates, the most basic version 
of which is one channel for the  coordinate and one for the  coordinate.

The CoordConv layer keeps the properties of few parameters and efficient
computation from convolutions, but allows the network to learn to keep or 
to discard translation invariance as is needed for the task being learned.
This is useful for coordinate transform based tasks where regular convolutions
can fail.


![image](https://user-images.githubusercontent.com/84374554/136122031-5d0993f5-4e2f-4b78-91f1-c34a1c6f4dba.png)
由图中可以看到就是在原来的基础上加了坐标信息,i和j
