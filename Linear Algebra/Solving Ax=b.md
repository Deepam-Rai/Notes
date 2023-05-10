----
## Column Space View
$Ax=b$  
$b$ is linear combination of column vectors of $A$ with elements of $x$ as multiplying scalars.
Thus, it is solvable if $b$ lies in the column space of $b$.  

Q. Let $M = \set{x | Ax=b}$. Is $M$ subspace of $\mathbb{R}^n$?  
Not necessarily.

----
## Least Squares
[Least Squares](./Least%20Squares.md)

----
## LU factorization
[LU Factorization](./LU%20Factorization.md)
We can use $LU$ factorization to solve simultaneous linear equations.
$$\large \begin{aligned}
Ax &= b \\
or\ LUx &= b \\
or\ Lc &= b \\
\end{aligned}$$

where $c=Ux$.

Steps:
1. LU Factorize A using Gaussian elimination. Thus get $A=LU$.
2. Solve for $c$ using $Lc=b$. Forward substitution can be used.
3. Solve for $x$ using $Ux=c$. Backward substitution can be used.
Time complexity $O(n^2)$. ($n^2$ each for forward and backward substitution).

Once $LU$ factorization is done we can discard $A$ and use same $LU$ for other $b$ directly without new $LU$ factorization.  

----
## Rectangular Matrices
[Rectangular matrices](./Rectangular%20Matrices.md)
$A=$ rectangular matrix.
1. Convert $A$ to upper triangular.(all operations are applied on RHS $b$ also)
2. Do backward substitution to solve for $x$.
$Ax=b \to Ux=c$  

- Non-pivot columns are free variables, we can choose any value for them.

Further we can:  
$Ax=b \to Ux=c \to Rx=d$    
Using non-pivot columns of $R$ we can get complete solution and using $d$ we can get particular solution.
#TODO how.
- particular solution: choose all free variables as 0.
- Special solutions: Put one free variable as 1 and rest 0, for all free variables one at a time.
- complete solution = N(A) = linear combination of special solutions. #TODO
