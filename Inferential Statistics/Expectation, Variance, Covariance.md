
----
# Expectation
Like finding the center of mass for the distribution.  

**Discrete:**
$$\large \mu = E[X] = \sum_x{xf(x)}$$
where $f(x)$ is a discrete probability function.

**Continuous:**
Let $X$ is continuous random variable with p.d.f f(x).  
$$\large \mu = E[X] = \int_{-\infty}^{+\infty}{xf(x)dx}$$

Everything below applies in continuous case too.

- $E[g(X)] = \sum_x{g(x)f(x)}$
- $E[X+Y] = E[X] + E[Y]$
- $E[a]=a$, where $a$ is a constant.
- $E[aX+b] = aE[X] + b$
- $E[XY] = E[X]E[Y]$ if $X$ and $Y$ are independent.
- Conditional Expectation:
	- $E[X|Y=y] = \sum_x xf_{X|Y}(x|y)$
		- Expectation of $X$ when $Y$ is fixed at $y$.
	- $E[X|Y]$
		- Its a random variable, with randomness inherited from $Y$.
- Law of Total Expectation:
	- Total average is the average of case by case average.
	- $E[X] = E_Y(E[X|Y])$
		- $E_Y =$ Expectation computed over the distribution of $Y$.


----
# Variance
Indicates the spread of values from the expected value.  

$$\large \begin{aligned}
Var(x) = \sigma^2 
&= E[(X-\mu)^2] \\
&= E[X^2] - (E[X])^2
\end{aligned}$$
- $Var(a)=0$
- $Var(aX)=a^2Var(X)$
- $Var(aX+bY)= \begin{cases} a^2Var(X) + b^2Var(Y) +2abCov(X,Y) &\text{if dependent} \\ a^2Var(X) + b^2Var(Y) &\text{if independent}\end{cases}$
- Conditional Variance:
	- $Var(X|Y=y)$
		- Variance of $X$ keeping $Y$ as fixed $y$.
		- Its a number.
	- $\large Var(X|Y) = E\{ (X - \mu_{X|Y})^2|Y\} = E[X^2|Y] - (E[X|Y])^2$
		- Its a random variable with randomness inherited from $Y$.
- Law of Total Variance:
	- $Var(X) = E_Y[Var(X|Y)] + Var_Y(E[X|Y])$
	- $Var_Y =$ Variance over $Y$.
	- #TODO intuitive meaning

# Covariance
Indicates association or dependence between two variables.

$$\large \begin{aligned}
cov(X,Y) &= E\{ (X-\mu_x)(Y-\mu_y)\} \\
&= E[XY] - E[X]E[Y]
\end{aligned}$$

$$\large cov(X,Y) = \begin{cases}
positive &\text{large values of occurs together and same for small} \\
0 &\text{independent} \\
negative &\text{large X values occurs with small Y values and vice-versa} \\
\end{cases}$$

----
# Correlation Coefficient
Indicates linear association.

$$\large corr(X,Y) = \frac{Cov(X,Y)}{\sqrt{ Var(X)Var(Y)}}$$


$$\large corr(X,Y) = \begin{cases}
positive &\text{both increase/decrease together.} \\
0 &\text{does not imply independence.} \\
negative &\text{one increases as another decreases.} \\
+1, -1 &\text{perfect linear relationship.}
\end{cases}$$

- $Corr(X,Y) \in [-1,+1]$
- $X$ and $Y$ are independent $\implies corr(X,Y)=0$; but converse may not be True.

----
