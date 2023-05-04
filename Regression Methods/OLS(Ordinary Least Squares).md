Ordinary Least Squares is a method to estimate the parameters of linear regression models. There are other alternatives too like MLE(Maximum Likelihood Estimates).  

It aims to find parameters $\beta$ that minimizes squared difference between predicted $\hat Y$ and actual $Y$. Since, this difference is also called residual it is also said to minimize the sum of squared residuals.  

- It is basically minimizing the error/residual.
- Taking square:
	- avoid negative and positive errors cancelling each other.
	- maintains the differentiability of the function.

----
# 2 variable

$n =$ total number of observations,  
$\sigma^2 =$ variance of error.  
For simple two variable regression model, the OLS estimation criterion can be given as:  

$$\large \text{Min }RSS(\beta_0,\beta_1) = \sum_{i=1}^n u_i^2 = \sum_{i=1}^n{(Y_i - \hat Y_i)^2} = \sum_{i=1}^n{(Y_i - \hat\beta_0 - \hat\beta_1 X_i)^2}$$

We use usual first-order derivative method to solve for $\hat\beta_0$ and $\hat\beta_1$.  
Thus partially differentiate the above equation w.r.t. $\hat\beta_0$ and $\hat\beta_1$ to get:  

$$\begin{aligned}
\sum_{i=1}^n{(Y_i - \hat\beta_0 - \hat\beta_1 X_i)}=0 \\
\sum_{i=1}^n{X_i(Y_i - \hat\beta_0 - \hat\beta_1 X_i)}=0
\end{aligned}$$


Simplify to get **OLS Normal Equations**:  

$$\begin{aligned}
n\hat\beta_0 + \hat \beta_1 \sum_{i=1}^n X_i &= \sum_{i=1}^n Y_i \\
\hat\beta_0 \sum_{i=1}^n X_i + \hat\beta_1 \sum_{i=1}^n X_i^2 &= \sum_{i=1}^n X_iY_i
\end{aligned}$$

Then solve for $\hat\beta_0$ and $\hat\beta_1$,  

$$\large \begin{aligned}
\hat\beta_0 &= \bar Y - \hat\beta_1 \bar X \\
\hat \beta_1 &= \frac{\sum_{i=1}^n{X_iY_i} - n\bar X \bar Y}{\sum_{i=1}^n X_i^2 - n \bar X} = \frac{\sum_{i=1}^nY_i(X_i-\bar X)}{\sum_{i=1}^n(X_i-\bar X)^2} = \frac{S_{xy}}{S_{xx}}
\end{aligned}$$
----
### Statistical Properties of OLS estimators

Characteristics:  
OLS estimators $\hat \beta_0$ and $\hat \beta_1$:
- are functions of only observed sample values.
- are point estimators.

Statistical properties:  
1. **Unbiasedness of $\hat \beta_0$ and $\hat \beta_1$.**
	- $E[\hat \beta_0]=\beta_0$
	- $E[\hat \beta_1]=\beta_1$
2. Linearity of $\hat \beta_1$.
	1. It can be expressed as linear function of sample values $Y_i$.
3. Variance of $\large \hat \beta_1 = \frac{\sigma^2}{\sum_{i=1}^n(X_i-\bar X)^2} = \frac{\sigma^2}{TSS^2}$.
	1. Measures statistical precision of $\hat \beta_1$.
4. Variance of $\large \hat \beta_0 = \frac{\sigma^2 \sum_{i=1}^nX_i^2}{n\sum_{i=1}^n(X_i-\bar X)^2}$.
	1. Measures statistical precision of $\hat \beta_0$.
5. $\large Cov(\hat \beta_0, \hat \beta_1) = -\bar X\frac{\sigma^2}{\sum X_i}$

----
## Gauss Markov Theorem
> Under assumptions of CLRM, the OLS estimators of $\hat \beta_0$ and $\hat \beta_1$ are the minimum variance estimators of the regression coefficients $\beta_0$ and $\beta_1$ in the class of all linear unbiased estimators.

(CLRM Assumptions are stated in [Assumptions](./Assumptions.md) file.)

Means they are BLUE(Best Linear Unbiased Estimators), in terms of minimum variance. It means that they are statistically more precise than other linear unbiased estimators.

----
