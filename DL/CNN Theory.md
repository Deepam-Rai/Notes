# Mathematical Convolution Function
Convolution is an operation on two functions of real valued arguments, and is defined as  
Let,  
$I$ = Input,  $K$ = Kernel  
In 1D:  

$$ (I*K)(c)=\sum _{a+b=c}I(a)K(b) = \sum _a I(a)K(c-a)$$

In 2D:  

$$\Large (I*K)(c_1,c_2)=\sum _{a_1}\sum _{a_2}I(a_1,a_2)K(c_1-a_1, c_2-a_2) = \sum_{a_1}\sum_{a_2}I(c_1-a_1, c_2-a_2)K(a_1,a_2)$$

- It is equivalent to flipping the kernal and performing normally perceived DL convolution operation.
- It is commutative.

# Cross Correlation (Referred as Convolution in DL)
Cross-correlation is an operation on two functions of real valued arguments and is defined as,  

$$\Large (I*K)(c_1, c_2) = \sum_{a_1}\sum_{a_2}I(c_1+a_1, c2_+a_2)K(a_1, a_2)$$

- Normally perceived DL convolution: It is equivalent to sliding the kernel over the input and performing element wise product and summing to get an output value.

----
# Padding
The convolution operates lesser on the edge pixels, thus extracting less information from edges. To prevent this we use padding - adding extra layer of zeroes(typically) around the image.
- Helps to prevent loss of information at image edges.
- Helps to keep the size of volume same.
**Valid Padding**: No-padding, thus the output will have smaller dimension.  
**Same Padding**: Padding with zeroes such that output has the same dimension as input.  

# Output Dimension
Let,  
$m$= Input height,  
$n$ = input width,  
$p$ = padding,  
$k_1$ = kernel height,  
$k_2$ = kernel width,  
$s$ = kernel stride,  
then output dimension is:  

$$\Large (m',n')= (\frac{(m+2p - k_1)}{s} + 1,  \frac{n+2p - k_2}{s}+1 )$$

## Padding required for "same padding"
Input dimension = output dimension  

$\Large \therefore \frac{(n+2p - k)}{s}+1=n$  
$\Large p = \frac{(n-1)s -n+k}{2}$  

Thus, for stride=1  
$\large p=\frac{k-1}{2}$  


----
# Examples of 2D kernels

# Gaussian Blur

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

