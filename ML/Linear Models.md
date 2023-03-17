# Definitions

Represents **target** variable as **linear combination** of **feature** variables.

Let,  
$n=$ number of observations/datapoints,  
$k$ = number of features,  
$\mathbb{X}= [X_1  X_2  ... X_k]$ = feature matrix,  
$X_i=$ i'th feature vector,
$$\large \mathbb{X} = \begin{bmatrix}
x_{11} & x_{12} & x_{13} & ... & x_{1k} \\
x_{21} & x_{22} & x_{23} & ... & x_{2k} \\
.\\
.\\

x_{n1} & x_{n2} & x_{n3} & ... & x_{nk} \\
\end{bmatrix}$$  
Prediction = $$\large Y = \begin{bmatrix}
y_1 \\ y_2 \\ .\\.\\.\\ y_n
\end{bmatrix}$$  
Weights = $$\large W = [w_0, w_1, w_2,..., w_k]$$


Then linear model is given as,  
$$\large Y= w_0 + w_1X_1 + w_2X_2 + ... + w_kX_k$$

Its a special case of non-linear models where basis function $\phi(X)=X$.

----
# Linear Regression



## Estimating weights

### MLE (Maximum Likelihood Estimation)

### Least Square Estimation
hat matrix

### Gradient Descent

----
# Overfitting

## To overcome
1. k-fold validation
2. Regularization
3. Early-stop

## Bias-variance tradeoff

#TODO everything