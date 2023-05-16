----
# Why CNN?
Brief history of CNN is in [CNN Supplement](./CNN%20Supplement.md).

## The shortcomings of feature selection
To recognize the object in an image, we can just check for the presence of features of the object in that image. But number of such features, selecting appropriate features, features for different(stupendously many) object, different size or orientation of the same feature, different shades and colors of same feature, handling noise in the image, etc etc makes manual selection of features infeasible.

## Vanilla Deep Neural Networks and Images
Full connectivity of feed forward neural network means:
1. Very very large number of parameters
2. Doesn't scale well
3. Very large search space
4. Very high chance of overfitting
5. Doesn't take image structure into account

## Advantages of CNN
Convolutional network:
1. Takes image structure into consideration
2. Constrains the architecture accordingly
	1. Reducing the number of parameters drastically
	2. Reducing the search space
3. CNN layers have sparse interactions.
4. Parameters are shared.
5. Many operations equivariant: If input changes then the output changes in the same way.
	1. scale, rotation are not equivariant to convolution.

----
# Elements of CNN
Convolutional layer is a specialized layer, based upon mathematical operation of cross-correlation, for processing data with grid-like topology.  
Compared to Feed-Forward instead of matrix multiplication, mathematical cross-correlation operation is performed.

Mathematical [cross correlation operation](./CNN%20Supplement.md), referred as convolution by DL people:    

1D:

$$\large I\ast K(c) = \sum_a I(c+a)K(a)$$

2D:

$$\large I\ast K(c_1,c_2)=\sum_{a_1}\sum_{a_1}I(c_1+a_1,c_2+a_2)K(a_1,a_2)$$

where, 
$I =$ input,  
$K =$ kernel,  
$S=I\ast K =$ feature map.  

## Stages in CNN
1. Convolution stage: Applying convolutions using kernels.
2. Detector stage: Passing through activation function
3. Pooling

## Kernels/Filters
Some 2D kernels are given in [CNN supplement](./CNN%20Supplement.md).

## Padding
The convolution operates lesser on the edge pixels, thus extracting less information from edges. To prevent this we use padding - adding extra layer of zeroes(typically) around the image.
- Helps to prevent loss of information at image edges.
- Helps to keep the size of volume same.
**Valid Padding**: No-padding, thus the output will have smaller dimension.  
**Same Padding**: Padding with zeroes such that output has the same dimension as input.  

----
# Convolutional Layer


Let,  
$w_{in} =$ width of input volume,  
$h_{in}=$ height of input volume,  
$d_{in} =$ depth of input volume,  
$p_w =$ width padding,  
$p_h =$ height padding,  
Typically $p_w=p_h=p$,  

$K =$ number of kernel/filters,  
$w_k =$ width of k'th filter,  
$h_k =$ height of k'th filter,  
Typically height and width of filters are equal,  
$e_k =$ spatial extent of filter = width = height,  
$s_k =$ stride of k'th kernel,  
$b_k =$ bias of k'th kernel,  

then, for feature map corresponding to k'th kernel:   
$w_{f,k} = \Large{\ceil{\frac{w_{in} +2p_w - w_k}{s_k}}} + 1$,  
$h_{f,k} = \Large{\ceiling{\frac{h_{in}+2p_h-h_k}{s}}}+1$,  
$d_{f,k}=1$,  

We make sure that the width and height of all K feature maps are same.  
Thus, combining all K feature maps we get output volume:  
$w_{out}= w_{f,1}= w_{f,2}=...= w_{f,K}$,  
$h_{out}= h_{f,1}= h_{f,2}=...= h_{f,K}$,  
$d_{out} =K$.  

**Depth slice:** i'th feature map in output volume.  

## 2D Convolutional Layer
Let,  
$m$= Input height,  
$n$ = input width,  
$p$ = padding,  
$k_1$ = kernel height,  
$k_2$ = kernel width,  
$s$ = kernel stride,  
then output dimension is:  

$$\Large (m',n')= \left(\frac{(m+2p - k_1)}{s} + 1,  \frac{n+2p - k_2}{s}+1 \right)$$

### Padding required for "same padding"
Input dimension = output dimension  

$\Large \therefore \frac{(n+2p - k)}{s}+1=n$  
$\Large p = \frac{(n-1)s -n+k}{2}$  

Thus, for stride=1  
$\large p=\frac{k-1}{2}$  

----
# Special Layers


## Pooling
It replaces the output at a location with the summary statistic of nearby outputs.  
1. Reduces the dimensionality of feature maps
2. Helps to bring down input to desired dimension.
3. sub-sampling step
4. Gives some invariance to spatial translation.
5. sharpens the features

$e=$ spatial extent = width = height,  
$s=$ horizontal stride = vertical stride,  

Dimension of output feature map:  
$w_{out}= \Large\ceil\frac{w_{in}-e}{s}+1$,  
$h_{out}= \Large\ceil\frac{h_{in}-e}{s}+1$,  
$d_{out}=$ number of feature maps,  

**Overlapping Pooling:** when $s \lt e$.  
**Non-overlapping pooling:** when $s \ge e$.  

**Locally invariant pooling:** When the output of the input is same even when the input shifts around little bit within spatial extent. e.g., max pooling.  

Some pooling techniques:
1. Max pooling: Taking maximum of neighbourhood.  
2. Average of rectangular neighborhood.
3. L2 norm of rectangular neighborhood.
4. Weighted average based on the distance from the central pixel.
5. Global pooling: Reduces each feature map to a single value in convolutional layer. e.g., Global Max pooling, Global average pooling.

----
## Batch Normalization
As the parameters of a layer get updates, the output distribution of that layer also changes. This means that the subsequent layers have to learn this shifting distribution of this layers except from other things that they are supposed to learn.  
Batch normalization mitigates this issue by normalizing the output of a layer.  
Steps:
1. For a batch:
	1. For each neuron grab it's aggregation function output for each example to get vector of logits for that layer.
	2. Normalize each neuron's vector logits.
		1. Subtract mean and divide by the standard deviation. Moments are tracked using exponentially weighted moving average.
	3. Affine transform this normalized value $\hat x$ as : $\gamma \hat x + \beta$.
		1. $\gamma, \beta$ are learnable parameters.
		2. Normalization gets the value centered at zero and of fixed variance. Affine transform helps represent distribution with different mean and variation.


----
# Practical notes

## Transformations
Applying transformations makes the model robust to different kinds of variations.  

### Per-image whitening
Zero-center every pixel in an image by subtracting out the mean and normalizing the unit to 1 variance. Removes the potential differences between images.  

#### Data augmentation
Creating more data by cropping, rotating, flipping, modifying saturation, brightness, etc of the available image.  

----
# Special architectures
1. [AlexNet](./Special%20Architectures.md)
2. [VGGNet16](./Special%20Architectures.md)
3. [VGGNet19](./Special%20Architectures.md)
4. GoogLeNet for CIFAR-10
5. Artistic Style
