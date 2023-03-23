> $P =$ Population of any distribution*,  
> $\mu =$ Population mean,  
> $\sigma^2 =$ **finite** population variance,  
> $n =$ Sample size = Number of observations we draw for a sample,  
> $\{ X_1, X_2,..., X_n \}=$ a sample drawn from $P$,  
> 	where $X_i =$ i.i.d random variable ~ an observation,  
> then if $\bar X =$ sample means distribution,  then  
> $$\large \lim_{n \to \infty} \bar X \sim N \left( \mu, \frac{\sigma}{\sqrt{n}}\right) $$

\*Assumptions:
1. $n \ge 30$, is an accepted sufficiently large $n$.
	- If $n$ is low sampling distribution follows almost population distribution.
1. 1st moment (mean) should exist for the population.
	- e.g., doesn't exist for Cauchy distribution.

- $\implies \sqrt{n}\left( \bar X - \mu \right) \sim N(0, \sigma^2)$
- $\Large \implies \left( \frac{\sqrt{n}(\bar X - \mu)}{\sigma} \right) = Z = N(0,1)$
- $n$ controls the deviation of $\bar X$
	- Greater $n \implies$ smaller deviation and vice-versa. 