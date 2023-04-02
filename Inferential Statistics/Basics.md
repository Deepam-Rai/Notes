# Terms
>**Prior Distribution of X:** Distribution of random variable X, which is known beforehand.


# Introduction

> **Problem of statistical inference:**  
$X =$ a random variable, that models the data.  
$\text{Distribution of X is assumed to belong to certain family of distribution, particular member is specified when we know }\theta$.  
$\theta =$ parameter(can be a vector) which when known, we will know distribution of $X$.  
$\pi(\theta) =$ prior distribution of $\theta$, when it is treated as random variable.    
$f(x|\theta) =$ conditional distribution of $x$ for fixed $\theta$.  
$f(x,\theta) =$ joint distribution of $x$ and $\theta$.
**Problem:** Infer something about $\theta$ based upon data $X$.  

**Need of Probability:** Probability addresses the external/uncontrolled factors not included in the feature variables when studying a variable.  

> **Decision Function:** Function of random variable $X=x_1,x_2,...,x_n$, used for making inference of $\theta$, $$d(x_1,x_2,...,x_n)$$
- Its nature depends upon the kind of inference we want to make of $\theta$.

According to type of problems decision function also changes.
Types of problems:
1. Hypothesis testing
	- Testing value of $\theta$ against a specific value $\theta_0$.
	- Only two actions possible:
		1. Hypothesis is true.
		2. Hypothesis is false.
1. Multiple decision problem
	- $\theta$ can take multiple discrete values.
2. Estimation problems
	- $\theta$ can take infinite continuous values.

> **Loss function:** Numerically measures the penalty that arises when decision taken is $d(X)$ but true value is $\theta$, $$L(\theta, d(x_1,x_2,...,x_n))$$
- It evaluates how good is a decision function, for an individual decision.

A single experiment wont give good measure, thus we need to make multiple experiments.  
$X =$ denotes an experiment.  
$X_i =$ i'th potential observation value for $X$, $1 \le i \le n$.  

> **Risk function:** Expected loss for a fixed $\theta$, 
> $$\begin{aligned}
 R(\theta,d) &= E_{\theta}[L(\theta,d)] \\
 &= \int{L(\theta,d(x))f(x|\theta)}dx
 \end{aligned}$$
 Substitute $\int$ with $\sum$ for discrete $X$.

But when we evaluate decision functions using risk function, it may happen that for some value of $\theta$ one function has lesser values while for some $\theta$ another has lesser values.  
To break this ambiguity we take the max of risk function for all decision functions and then take the decision function with lowest max value - and is called minimax decision function.  
- The comparison is successfully converted to comparison of real values.
> **minimax decision function:** The function $d_0$ is called minimax decision function in the class $D$ of decision functions if it satisfies  
> $$max_{\theta} \ R(\theta, d_0) = min_{d\in D}\ max_{\theta}\  R(\theta, d)$$


Above $\theta$ had a fixed value.  
But when $\theta$ also becomes a random variable, we need the evaluation over all possible values of $\theta$ too.  
> **Mean Risk/Bayes Risk:** If $\theta$ is a continuous random variable having density $\pi(\theta)$, mean risk is given as:
> $$r(\pi,d) = E[R(\theta,d)] = \int{R(\theta,d)\pi(\theta)d\theta}$$
> Replace $\int$ by $\sum$ if $\theta$ is a discrete random variable.
- It is a real number for a given decision function and prior distribution of $\theta$.

> **Bayes Decision function:** A decision function $d_0$ is called Bayes decision function with respect to prior distribution $\pi(\theta)$ and class $D$ of decision functions if, 
> $$r(\pi, d_0) = min_{d \in D} \ r(\pi, d)$$
> 
- Similar to minimax decision function but w.r.t. risk function.

Choice of loss functions - depends upon nature of problem - some sample examples:
- $c(a-\theta)^2$: when large errors have significant impact.
- $c|a-\theta|$: when loss is proportional to size of errors
- $c(\theta)|a-\theta|^b$: generalization of the above two.
- For testing of hypothesis: $L(\theta,d) = \begin{cases} 0 \text{ if correct decision is made.} \\ 1 \text{ if  incorrect decision is made.}\end{cases}$
- For estimation: quadratic/squared error loss: $(d-\theta)^2$
