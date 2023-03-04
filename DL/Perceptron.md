# McCulloch and Pitts Neuron

Inputs: $X = x_1, x_2,...,x_n$ where $x_i \in \{0,1\}$
  
Aggregation: $g(X) = \sum_{i=1}^n x_i$
  
Activation Function: $a(z)=\cases{1, z \geq \theta \\0,z\lt \theta}$

Prediction: $\hat y = a(g(X), \theta)$
where $\hat y \in \{0,1\}$

## Basic gates using MP Neuron

### AND

$\theta = n$
| $x_1$ | $x_2$ |...| $x_{n-1}$ | $x_n$ | $\sum X$ | $\hat y$ |
|----|---|---|----|---- |-----|---|
| 0 | 0 |... | 0  | 0  | 0    | 0 |
| 0 | 1 |... | 0  | 1  | 1    | 0 |
| ..|..| ..  | .. | .. | ..   | .. |
| 1 | 1 |... | 1  | 0   | n-1 | 0 |
| 1 | 1 |... | 1  | 1   | n  | 1  |

### OR
$\theta = 1$
| $x_1$ | $x_2$ |...| $x_{n-1}$ | $x_n$ | $\sum X$ | $\hat y$ |
|----|---|---|----|---- |-----|---|
| 0 | 0 |... | 0  | 0  | 0    | 0 |
| 0 | 1 |... | 0  | 1  | 1    | 1 |
| ..|..| ..  | .. | .. | ..   | .. |
| 1 | 1 |... | 1  | 0   | n-1 | 1 |
| 1 | 1 |... | 1  | 1   | n  | 1  |




# Perceptron

Inputs: $X \in \mathbb{R}^n$  

Weights: $W\in \mathbb{R}^n$  

Let $w_0=-\theta$ and $x_0 = 1$  
$\therefore X=[1,x_1,x_2,x_3,...,x_n]^T, W=[-\theta, w_1, w_2, ..., w_n]^T$

Aggregation: $g(X) = \sum_{i=0}^n w_i *x_i$
  
Activation Function: $a(z)=\cases{1, z \geq 0 \\0,z\lt 0}$

Prediction: $\hat y = a(g(X), \theta)=\cases{1, W.X \geq 0 \\0,W.X\lt 0}$
where $\hat y \in \mathbb{R}$


# Perceptron Algorithm

1. Let, $P\gets$ Inputs with label 1.
2. Let, $N\gets$ Inputs with label 0.
3. Weights $W_0\gets$ Randomly initialized.
4. while( not convergence ):
	1. Pick arbitrary $x\in P\cup U$
	2. if( $x\in P$ and $W.X\lt 0$ )
		1. $W\gets W+X$
	3. if( $x\in N$ and $W.X\ge 0$ )
		1. $W\gets W-X$
#TODO mathematical intuition

## Basic gates using Perceptron

### AND
| $w_0=-\theta$ | $w_1$ | $w_2$ | $x_0$ |
|---|----|---|----|
|-2 | 1 | 1 | 1 | 1 |

| $x_0$ | $x_1$ | $x_2$ | $W.X$ | $\hat y$ |
|----|----|----|------|---|
| 1 | 0 | 0 | -2 | 0 |
| 1 | 0 | 1 | -1 | 0 |
| 1 | 1 | 0 | -1 | 0 |
| 1 | 1 | 1 | 0 | 1 |

### OR
| $w_0=-\theta$ | $w_1$ | $w_2$ | $x_0$ |
|---|----|---|----|
|-1 | 1 | 1 | 1 | 1 |

| $x_0$ | $x_1$ | $x_2$ | $W.X$ | $\hat y$ |
|----|----|----|------|---|
| 1 | 0 | 0 | -1 | 0 |
| 1 | 0 | 1 | 0 | 1 |
| 1 | 1 | 0 | 0 | 1 |
| 1 | 1 | 1 | 1 | 1 |

### NOT
| $w_0 =-\theta$ | $w_1$ |  $x_0$ |
|---|---| --- |
| 0 | -1 | 1 |

| $x_0$ | $x_1$ | $W.X$ | $\hat y$ |
| -- | -- | --- | -- |
| 1 | 0 | 0 | 1 |
| 1 | 1 |-1 | 0 |

### NAND
| $w_0=-\theta$ | $w_1$ | $w_2$ | $x_0$ |
|---|----|---|----|
|1 |-1 |-1 | 1 |

| $x_0$ | $x_1$ | $x_2$ | $W.X$ | $\hat y$ |
|----|----|----|------|---|
| 1 | 0 | 0 | 1 | 1 |
| 1 | 0 | 1 | 0 | 1 |
| 1 | 1 | 0 | 0 | 1 |
| 1 | 1 | 1 |-1 | 0 |

### NOR
| $w_0=-\theta$ | $w_1$ | $w_2$ | $x_0$ |
|---|----|---|----|
| 1 | -1 | -1 | 1 |

| $x_0$ | $x_1$ | $x_2$ | $W.X$ | $\hat y$ |
|----|----|----|------|---|
| 1 | 0 | 0 | 1 | 1 |
| 1 | 0 | 1 | 0 | 1 |
| 1 | 1 | 0 | 0 | 1 |
| 1 | 1 | 1 | -1 | 0 |

### XOR, XAND, XNOR
Not linearly separable.

# MP Neuron vs Perceptron

| | MP Neuron | Perceptron |
|--|--|--|
|Inputs: | Inputs are binary. | Inputs can be real numbers. |
|Weights: | Inputs are not weighted. | Inputs are weighted. |
|Decision Boundary: | Creates linear decision boundary. | Creates linear decision boundary, but can learn more complex than MP Neuron. |
|Basic Gates: | Models AND, OR. Cannot model XOR, XAND, etc. | Models AND, OR, NOT. Cannot model XOR, XAND, etc. (but can with multiple layers.) |
| Parameters: | Cannot be learned. #TODO verify | Can be learned. |



----

# Multi-layer Perceptron
> Any boolean function of $n$ inputs can be modelled **exactly** by a multi-layer perceptron with 1 hidden layer of 2<sup>n</sup> perceptron and output layer with 1 perceptron.


# Universal Approximation theorem
> A multilayer network of sigmoid neurons with a single hidden layer can **approximate** any continuous function to any desired precision.

