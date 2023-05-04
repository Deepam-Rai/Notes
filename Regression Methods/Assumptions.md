----
## CLRM
CLRM(Classical Linear Regression Models) has 3 sets of assumptions:
1. regarding formulation of Population Regression Equation(PRE)
2. regarding statistical properties of error term and the dependent variable
3. regarding properties of sample data.

----
### 1. Formulation of PRE

> A1: PRE(Population Regression Equation) takes the form:  
> $Y=\beta_0 + \beta_1 X +u$
- $\beta_0 + \beta_1 X$ is called PRF(Population Regression Function)
- $u$ is random error term / stochastic error term.
	- It accounts for other factors that we are not able to capture in this relationship.
- regressand / dependent variable = Y  
- regressor / independent variable = X  
- $\beta$ are regression coefficients

This assumption in itself has assumptions:
1. Random error terms enters PRE additively.
2. PRE is linear in regression coefficients.
3. Regression coefficients do not vary across observations.

----
### 2. Properties of Random Error Term

> A2: The error has zero conditional mean.  
> $E[u|X]=0$ or $E[u_i|X_i]=0,\forall X_i$
- It means that the error is same for all population values of $X \implies$ error is not dependent on $X$. 

Implications:
1. Unconditional mean of random error term equals 0. $E[u]=0$
2. The population values of $X$ and $u$ are uncorrelated. $Cov(X,u)=0$
3. $X$ and $u$ have zero correlation. $\rho (X,u)=0$
4. $E[Y|X]=PRF=\beta_0 + \beta_1 X$

> A3: The assumption of Constant Error Variances/Homoskedastic Errors/Homoskedacity.  
> The conditional variances of random error $u$ is identical for all observations and equal the same finite positive constant $\sigma^2$.  
> $Var(u|X)=\sigma^2$

Implications:
1. Unconditional variance $Var(u)=\sigma^2$.
2. $Var(Y|X)=\sigma^2$.

> A4: The assumption of zero error covariances/non-autoregressive errors/non-autocorrelated errors.  
> $Cov(u_i,u_j|X_i,X_j)=0$

Implications:
1. $Cov(Y_i,Y_j|X_i,X_j)=0$

----
### 3. Properties of Sample Data

> A5: Random sampling or independent random sampling.

Implications:
1. Observations $X$ are statistically independent.
2. Errors $u$ are statistically independent.
3. Dependent variables $Y$ are statistically independent.

> A6: Number of sample observations $n$ is greater than the number of unknown parameters $k$.

> A7: Non-constant regressor. The regressors $X$ are not same/constant.

> A7: No perfect multi-collinearity between regressors.

----
