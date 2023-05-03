# Inverse
> For matrix $A$ a matrix $B$ is said to be it's inverse of $A$ if $BA=I=AB$.

- There can be at most one inverse.
- Inverse may not exist at all.
- If inverse exists then $A$ is said to be invertible.

Properties:
1. $(AB...Z)^{-1}=Z^{-1}...B^{-1}A^{-1}$
2. $A$ is invertible iff $A$ has $n$ pivots.
3. $(A^2)^{-1}=B \implies A^{-1}=AB$
4. $A^T$ is invertible $\implies A$ is invertible.
5. $A$ is invertible is $N(A)$ contains zero vector alone.
	- This means that all the column vectors are independent $\implies$ $n$ pivots exists.
6. A column/rows of zeroes exists $\implies$ matrix is not invertible.

Square matrices:
1. Left inverse = Right inverse.

Permutation matrices:
1. $P^{-1}=P^T$

----
## Finding Inverse

### LU factorization
Let $A^{-1}=X$,  

$$\therefore AX=I$$

This can be seen as multiple systems of equations to be solved.
1. $A$ multiplied with a column of $X$ to get a column of $I$. At a time.

We can use [LU factorization](./LU%20Factorization.md).  
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

For square matrix:
1. $A+A^T$ is always symmetric.
2. $A-A^T$ is always skew symmetric.

For symmetric matrix:
1. $A^T=A$
2. If $A^{-1}$ exists then it is also symmetric.
3. If invertible then $A=LDU' \to A=LDL^T$.

----

