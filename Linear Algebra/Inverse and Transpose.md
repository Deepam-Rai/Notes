# Inverse
> For matrix $A$ a matrix $B$ is said to be it's inverse of $A$ if $BA=I=AB$.

- There can be at most one inverse.
- Inverse may not exist at all.
- If inverse exists then $A$ is said to be invertible.

Properties:
1. $(AB...Z)^{-1}=Z^{-1}...B^{-1}A^{-1}$
2. $A$ is invertible iff $A$ has $n$ pivots.

----
## Finding Inverse

### LU factorization
Let $A^{-1}=X$,  

$$\therefore AX=I$$

This can be seen as multiple systems of equations to be solved.
1. $A$ multiplied with a column of $X$ to get a column of $I$. At a time.

We can use [LU factorization](../LU%20Factorization).  
1. Factorize $A=LU$.
2. For every i'th column $b$ of $I$ get i'th column $x$ of $X$ as:
	1. Solve $Lc=b$
	2. Solve $Ux=c$

## Gauss-Jordan Method
Applying row operations simultaneously to rows of $A$ along with rows of $I$.  
Finally $A$ becomes $I$ and $I$ becomes $A^{-1}$.  

Steps:
1. For ease augment $I$ to $A$.
2. Perform row operation to convert:
	1. $A \to U$. Row echelon form.
	2. $U \to I$. Identity matrix.
3. The transformed columns of augmented $I$ is $A^{-1}$.

### Why this method works?  
$\because A=LU \implies U^{-1}L^{-1}=A^{-1}$.  

First to transform $A$ to $U$ we indirectly/unknowingly/via some other method multiplied it with $L^{-1}$ thus we multiplied augmented $I$ also with $L^{-1}$.  
$\therefore$ we get $[A|I] \to [U|L^{-1}]$.  

Now to get $I$ from $U$ we indirectly/unknowingly/via some other method multiplied it with $U^{-1}$ thus we multiplied augmented part also with $U^{-1}$.  
$\therefore$ we get $[U|L^{-1}] \to [I|U^{-1}L^{-1}]$.  
Thus augmented part is transformed to $A^{-1}$.  

----
# Transpose
Rows swapped columns and vice versa.  

$$\large A^T_{ij}=A_{ji}$$

Properties:
1. $(A+B)^T = A^T + B^T$
2. $(AB...Z)^T=Z^T...B^TA^T$
3. $(A^{-1})^T=(A^T)^{-1}$
4. $AA^T$ is always symmetric.

For symmetric matrix:
1. $A^T=A$
2. If $A^{-1}$ exists then it is also symmetric.
3. If invertible then $A=LDU' \to A=LDL^T$.

----

