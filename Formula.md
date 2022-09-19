# Counting
## Permutations
- Permutation of $r$ out of $n$ unique items
    - $\large ^nP_r = \frac{n!}{(n-r)!}$ 
- Permutation $n$ unique items
    - $\large ^nP_n=n!$
- Permutation of $n$ items where $n_1,n_2,...,n_k$ duplicates present
    - $\large \frac{n!}{n_1!n_2!...n_k!}$
    - here $n_1+n_2+...+n_k+remaining\ unique\ items=n$
### Circular Permutations
- $\large Circular\ permutation\ of\ n\ things= (n-1)!$
## Combinations
- ways of taking subset of $r$ items from set of $n$ unique items
    - $\large ^nC_r = \frac{^nP_r}{r!} = \frac{n!}{r!(n-r)!}$


# Probability
## Random Variable
### Univariate
#### Expectation - $\mu$
- $E[X] = \sum xf(x)\ or\ \int^\infin_{-\infin}{xf(x)dx}$
- $E[a]=a$
- $E[aX]=aE[X]$
- $E[a\pm X]=a\pm E[X]$
- $E[X\pm Y]= E[X]\pm E[Y]$
- $E[XY]=E[X]E[Y]+Cov(X,Y)$

#### Variance - $\sigma^2$
- $Var(X)=E[(X-E[X])^2]=E[X^2]-(E[X])^2$
- $Var(X)=\frac{1}{n-1}\sum (x_i-\bar x);\ \ (n-1)\ for\ sample\ n\ for\ population.$
- $Var(a)=0$
- $Var(aX)=a^2Var(X)$
- $Var(a+X) = Var(X)$
- $Var(aX\pm bY)=a^2Var(X)+b^2Var(Y)\mp 2abCov(X,Y)$

#### Covariance
- $Cov(X,Y)=\frac{1}{n-1} \sum((x_i-\bar x)(y_i-\bar y));\  \ (n-1)(for\ sample)\ with\ n\ for\ population;.$
- $Cov(X,Y)=E[XY]+E[X]E[Y]$
- $Cov(X,X)=Var(X)$
- $Cov(X,a)=0$
- $Cov(X,Y)=Cov(Y,X)$
- $Cov(aX,bY)=abCov(X,Y)$
- $Cov(X+a, Y+a)=Cov(X,Y)$
- $Cov(aX+bY,cW+dZ)=abCov(X,Y)+acCov(X,W)+bcCov(Y,W)+bdCov(Y,Z)$
- $Cov(X,Y)=0\ if\ independent$

#### Correlation - $\rho$
- $\large \rho_{X,Y}=\frac{Cov(X,Y)}{\sqrt{Var(X)*Var(Y)}}$
- $\large \rho_{X,Y}=\frac{\sum((x_i-\bar x)(y_i-\bar y))}{\sqrt{(\sum(x_i-\bar x)^2)(\sum(y_i-\bar y)^2)}}$
- $-1\le\rho\lt1$