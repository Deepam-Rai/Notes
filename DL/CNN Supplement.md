

----
# History

1959: David Hubel and Torsten Wiesel discovered that parts of visual cortex were responsible for detecting edges in vision.  
Further it was known that visual cortex was organized in layers.  
Each layer had same feature detectors spread over it.  
Each layer build upon the features detected in previous layer.  
This ideas significantly impacted design of CNN.  

2001: Paul Viola and Michael Jones exploited shades and structures of face to create detectors manually. All detectors when used together they achieved 91.4% detection rate.  
Manually crafted features were used in computer vision.  
ImageNet: Benchmark dataset with ~450,000 images of 200 possible classes.  
2011: ImageNet benchmark winner had error rate of 25.7%.  
2012: Alex Krizhevsky from Geoffrey Honton's lab at University of Toronto created AlexNet, winning ImageNet with 16% error rate.  
AlexNet put deep-learning on the map of computer vision.  


----
# Mathematical Convolution Function
Convolution is an operation on two functions of real valued arguments, and is defined as  
Let,  
$I$ = Input,  $K$ = Kernel  
In 1D:  

$$ (I*K)(c)=\sum _{a+b=c}I(a)K(b) = \sum _a I(a)K(c-a)$$

In 2D:  

$$\large \begin{aligned}
(I*K)(c_1,c_2) &= \sum _{a_1}\sum _{a_2}I(a_1,a_2)K(c_1-a_1, c_2-a_2) \\
&= \sum_{a_1}\sum_{a_2}I(c_1-a_1, c_2-a_2)K(a_1,a_2)
\end{aligned}$$

- It is equivalent to flipping the kernal and performing normally perceived DL convolution operation.
- It is commutative.

# Cross Correlation (Referred as Convolution in DL)
Cross-correlation is an operation on two functions of real valued arguments and is defined as,  

$$\large (I*K)(c_1, c_2) = \sum_{a_1}\sum_{a_2}I(c_1+a_1, c_2+a_2)K(a_1, a_2)$$

- Normally perceived DL convolution: It is equivalent to sliding the kernel over the input and performing element wise product and summing to get an output value.


----
# Examples of 2D kernels

## Gaussian Blur

$$\frac{1}{16}\begin{pmatrix}
1 & 2 & 1 \\
2 & 4 & 2 \\
1 & 2 & 1 \\
\end{pmatrix}$$

## Sharpness

$$\begin{pmatrix}
0 & -1 & 0 \\
-1 & 5 & -1 \\
0 & -1 & 0 \\
\end{pmatrix}$$

## Edge Detection

$$\begin{pmatrix}
-1 & -1 & -1 \\
-1 & 8 & -1 \\
-1 & -1 & -1 \\
\end{pmatrix}$$  

$$Vertical Edges\begin{pmatrix}
-1 & 0 & 1 \\
-1 & 0 & 1 \\
-1 & 0 & 1 \\
\end{pmatrix}$$

$$Horizontal Edges\begin{pmatrix}
-1 & -1 & -1 \\
0 & 0 & 0 \\
1 & 1 & 1 \\
\end{pmatrix}$$

----

