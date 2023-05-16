#TODO add summary table on top
#TODO add plots

Points:
- Adds non-linearity to the network, hence they are the must for capturing non-linear relationship.
- Helps mapping the output to desired range.
- Also known as transfer functions.
- If the output range is limited, also called squashing function.
- Desired properties:
	- Non-Linear: Then Universal Approximation Theorem holds.
	- Continuously Differentiable: Suitable for gradient-based optimizations, although many dont posess this(subgradient technique used).
	- Monotonous: Either always increasing or always decreasing - suitable for gradient based optimizations.
	- Computationally efficient

----
# Linear/Identity/No Activation

$$\large a(x)=ax$$

where $a$ is some constant.  

- Doesnt add non-linearity.
- Derivative is constant($a$) everywhere, not influenced by input.
- Taking all activations as Linear makes the whole network just a linear regression model.

----
# Binary Step

$$\large a(x)=\cases{1, x\ge \theta \\0, x \lt \theta}$$

where $\theta=$ threshold value.

- Can be used for binary classification.
- Its not differentiable at all points, and wherever it is - the gradient is zero, thus hindring backpropagation.

----
# ReLU (Rectified Linear Unit)

$$\large a(x)= \max\{0,x\} = \cases{x, x\gt 0 \\0, x\le 0}$$

- Its not differentiable at 0.
- Dead Units/Dying ReLU problem: Perceptrons output 0 for $x<0$.
- For $x<0$ its gradient is 0, for $x\ge0$ its gradients is constant($1$).
- Comparatively its computationally inexpensive.

----
# ParametricReLU and LeakyReLU

$$\large a(x)= \max\{\alpha x, x\} = \cases{x, x\gt 0 \\ \alpha x, x\le 0}$$

LeakyReLU when $\alpha = 0.01$.
- Information is not lost for $x<0$.
- It mitigates vanishing gradient compared to ReLU, as now gradients exists for $x<0$ also.

----
# Exponential Linear Unit

$$\large a(x) = \cases{\alpha(e^x-1), x\lt 0   \\x, x\ge 0}$$

- Differentiable everywhere.
- Has exploding gradient problem.
----
# SELU

$$\large a(x) = \cases{\lambda x, x\ge 0   \\ \lambda \alpha (e^x-1), x\lt 0}$$

- Its self normalizing, thus helps in stability and faster convergence.

----
# Sigmoid/Logistic

$$\Large \sigma(x) = \frac{1}{1+e^{-x}}$$

where $\sigma (x) \in (0,1)$.  

- Output is a probabilistic value **between** 0 and 1.
- Useful for binay classification.
- Its not zero centered, unlike tanh.
- For large positive/negative values the output values are saturated ~0/1, where the gradients are also almost zero, prone to vanishing gradients.
- It behaves like linear when x->0.
- $\sigma'=\sigma(1-\sigma)$
- $\sigma(-x)=1-\sigma(x)$

----
# tanh/hyperbolic tangent

$$\tanh(x) = 2\sigma(2x)-1 =\Large \frac{e^x - e^{-x} }{ e^x + e^{-x}}$$

where $tanh(x)\in (-1,1)$.  

- Its outputs are zero centered.
- Its mathematically shifted sigmoid.
- Outputs linear if x->0.
- Saturation: The output is ~(1.0) for large positive values and ~(-1.0) for large negative values, where the gradients are 0, prone to vanishing gradients.
- $\tanh'(x)= 1- (\tanh(x))^2$
- $\tanh(-x)=-\tanh(x)$

----
# Softmax
Input: $X=[x_1,x_2,...,x_n]^T$   

$$a(x_i) =\LARGE \frac{e^{x_i}}{\sum _{j=1}^n e^{x_j}} = o_i$$

Output: $O=[o_1,o_2,...,o_n]^T$ such that $\sum _{i=1}^n o_i= 1.0$.  

- Useful in multiclass classification: it gives the probability of each target class over all target classes. 
- This is a layer-wise activation function/fold function: calculation of i'th value requires all n values of the layer as input.
- Doing just $\large \frac{x_i}{\sum_{j=1}^nx_j}$ gives linear graph.

----
# Swish

$$\Large a(x) = x\sigma (x) = \frac{x}{1+e^{-x}}$$


- Differentiable everywhere.
- It is non-monotonic.
----
# Used concepts

## Saturating functions
A function is said to be saturating if $\displaystyle \large \lim_{|x|->\infty} |(\nabla f(x))| \rightarrow 0$.
