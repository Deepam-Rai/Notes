- $X =$ a continuous/discrete random variable.  
- $f(x|\theta) =$ probability density function for distribution of $X$.  
- $X_1,X_2,...,X_n =$ samples taken of $X$.  
- $d = d(X_1,X_2,...,X_n) =$ decision function that estimates parameter $\theta$ given $X_1,X_2,...X_n$. Its called estimator function. (loosely called estimate also.)  
- $\text{estimate of }\theta =$ numerical value(s) obtained from estimator $d$ after inserting observational values $X_1,X_2,...,X_n$ in it.  ($\theta$ can be a vector)  

Its impossible to find an estimator that is best for all values of $\theta$ in most cases.    
- Use minimax or Bayes decision function.
	- Difficult to find.
	- It ignores $d$ that is good for most of the $\theta$ but has large maximum.
	- It can be biased.

----
# Unbiased estimates
> **Unbiased Estimator:** An estimator $d = d(X_1,X_2,...,X_n)$ is an unbiased estimator if 
> $$E[d(X_1,X_2,...,X_n)]=\theta$$  
> for all values of $\theta$.
> 

If we use mean squared error then, $E[(d-\theta)^2] = Var(d)$ since $E[d]=\theta$.  
Then comparing estimators is equivalent to comparing their variances.  

> **Best unbiased estimator:** Unbiased estimator that possesses minimum variance among all unbiased estimators.

# Efficiency
> **Efficiency:** If $d^*$ is best unbiased estimator and $d$ is the estimator that interests us, then efficiency of $d$ as estimator of $theta$ 
> $$\frac{Var(d^*)}{Var(d)}$$

> **Efficient estimator:** If $efficienfy(d)=1.0$ or $100\%$.

Problem:
- There is no defined method for finding $d^*$.
- There is no guarantee that $d^*$ even exists.

Somewhat solution:
- Under certain conditions, the lower bound for magnitude of variance of any unbiased estimator can be found.
- For this $f(x|\theta)$ should satisfy certain regularity conditions w.r.t. differentiation and integration, and must possess a variance.
- An unbiased estimator with variance equal to this lower bound is best unbiased estimator in this class of estimators. It would also be efficient estimator.

Replace $V(d^*)$ by lower bound $B(\theta)$ in efficiency, since we have $B$ while $d^*$ may not be.

## Cramer-Frechet-Rao bound
For random samples of size $n$ the lower bound was found by them as:  
$$\Large B(\theta) = \frac{1}{n E\left[ \left( \frac{\partial \log{ f(X|\theta)}}{\partial \theta} \right)^2 \right] }$$

> $\therefore$ Efficiency of unbiased estimator $\delta$ with this lower bound is given as: 
> $$\Large e(\delta) = \frac{1}{Var(\delta) n E\left[ \left( \frac{\partial \log{ f(X|\theta)}}{\partial \theta} \right)^2 \right] }$$

These methods
- Considers only unbiased estimators; we might miss estimators with smaller risk.

## Asymptotic efficiency
#TODO 


# MLE (Maximum Likelihood Estimation)

> $X_1,X_2,...,X_n =$ random variables,  
> $x_1, x_2, ...,x_3 =$ observations(some values) of above random variables,  
> $\theta =$ parameter(s) of the distribution function that we want to find,  
> $f(x|\theta) =$ distribution/density function of $X_i$,  
> $L(\theta) =$ Likelihood function; the likelihood of getting the samples that we got  ,  
> $$\large L(\theta) = \prod_{i=1}^n{f(x_i|\theta)}$$  
> $\hat \theta  = \theta$ that maximizes $L(\theta)$  

- $\log(L(\theta))$ is maximized rather than $L(\theta)$ because it's easier and both are max for same $\theta$.
- $\hat \theta$ is parameter such that if it were to be real parameters of the underlying population, then there would be maximum likelihood of us getting samples $x_1,x_2,...,x_n$ that we have got.  
	- Calculated using usual calculus:
		- diff $\log(L(\theta))$ w.r.t. $\theta$.
		- Equate to $0$; solve $\theta$ values.
		- Double differentiate and determine whether maxima, minima or saddle point.

#TODO verify aboves

Properties satisfied by MLE estimators:
1. If there exists an efficient unbiased estimator, then when certain regularity conditions are satisfied, the MLE will produce it.
2. Under certain regularity conditions, MLE estimators are asymptotically efficient. #TODO asymptotic part.