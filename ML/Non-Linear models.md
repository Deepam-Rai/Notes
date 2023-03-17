Represents target variable as non-linear function of feature variables.  

Let,  
$n=$ number of observations/datapoints,  
$k$ = number of features,  
$\mathbb{X}= [X_1  X_2  ... X_k]$ = feature matrix,  
$X_i=$ i'th feature vector,
$$\large \mathbb{X} = \begin{bmatrix}
1 & x_{11} & x_{12} & ... & x_{1k} \\
1 & x_{21} & x_{22} & ... & x_{2k} \\
.\\
.\\
1 & x_{n1} & x_{n2} & ... & x_{nk} \\
\end{bmatrix}$$  
Prediction = $$\large Y = \begin{bmatrix}
y_1 \\ y_2 \\ .\\.\\.\\ y_n
\end{bmatrix}$$  
Weights = $$\large W = [w_0, w_1, w_2,..., w_k]$$

Basis functions = 
$$\large \phi = [\phi_0,\phi_1, \phi_2,...,\phi_k]$$


Then non-linear model is given as,  
$$\Large \begin{aligned} Y &= w_0\phi_0(X_0) + w_1\phi_1(X_1) + w_2\phi_2(X_2) + ... + w_k\phi_k(X_k) \\
&= \sum_{i=0}^k{w_i \phi_i(X_i)}
\end{aligned}$$
---
# Common basis functions
They map the input features to new space.
- Mapped features might be easier to manipulate/understand.
- Interpretability decreases drastically. 

## Linear models
$$\phi(X)=X$$

## Polynomial models
$$\phi(X)= X^p$$

## Gaussian models
$$\large \phi(X) = exp\left[ -\frac{1}{2} \left( \frac{X- \mu_X}{s_X} \right)^2 \right]$$

----
