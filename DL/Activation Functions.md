----
# Linear/Identity
$\large a(x)=x$

----
# Binary Step
$\large a(x)=\cases{1, x\ge \theta \\0, x \lt \theta}$

----
# ReLU (Rectified Linear Unit)
$\large a(x)= max\{0,x\} = \cases{x, x\gt 0 \\0, x\le 0}$

----
# LeakyReLU
$\large a(x)= max\{\alpha x, x\} = \cases{x, x\gt 0 \\ \alpha x, x\le 0}$


----
# Exponential Linear Unit
$\large a(x) = \cases{\alpha(e^x-1), x\lt 0   \\x, x\ge 0}$


----
# SELU
$\Large a(x) = \cases{\lambda x, x\ge 0   \\ \lambda \alpha (e^x-1), x\lt 0}$

----
# Sigmoid
$\Large \sigma(x) = \frac{1}{1+e^{-x}}$

----
# tanh
$\Large tanh(x) = 2\sigma(2x)-1 = \frac{e^x - e^{-x} }{ e^x + e^{-x}}$



----
# Softmax
$\LARGE a(x_i) = \frac{e^{x_i}}{\sum _{j=1}^n e^{x_j}}$

----
# Swish
$\Large a(x) = \frac{x}{1+e^{-x}}$
