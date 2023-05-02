$$PA=LDU'$$

$A =$ the matrix that is to be decomposed,  
$P =$ permutation matrix denoting row swapping,  
$L =$ lower triangular matrix formed from elementary matrices of Gaussian elimination,  
$D =$ diagonal matrix just used to make $U$ look better,  
$U' =$ Upper triangular matrix such that row-echelon form of $A=U=DU'$.
This note explains how we come to above expression.

----
# Elementary matrices
Elementary matrices are lower triangular matrices that pre-multiply matrix $A$ such that the end result is elementary row operation on $A$.
- They are lower triangular matrices.
- Product of lower triangular matrices are always lower triangular
	- Easy to see using pre-multiplication of B by A.
- Inverse of lower triangular matrix is also lower triangular.
	- Else $EE^{-1}$ doesn't give $I$.

----
# LU Factorization
1. We can use elementary row operations on a matrix $A$ to get its row-echelon form which is upper triangular.
2. And these elementary row operations can be denoted using product of elementary matrices.
	1. The elementary  matrices are all lower triangular.
	2. Product of lower triangular matrices is also lower triangular.

Thus, let  
$A =$ a matrix,  
$U =$ reduced row echelon form of $A$,  #TODO reduced?
$E = E_l...E_3E_2E_1 =$ product of elementary matrices that converts $A$ to $U$,  

$$\begin{aligned}
\therefore EA &= U \\
A &= E^{-1}U \\
A &= LU
\end{aligned}$$  
where $L$ and $U$ are lower and upper triangular matrices respectively.  
Form of $L$ and $U$:

$$L=\begin{bmatrix}
1 & 0 & 0 \\
* & 1 & 0 \\
* & * & 1
\end{bmatrix}$$

$$U=\begin{bmatrix}
* & * & * \\
0 & * & * \\
0 & 0 & *
\end{bmatrix}$$


----
## Solving Linear Equations
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

Once $c$ is calculated we can use it for other $b$ directly without new $LU$ factorization.  

----
# A=LDU'
$U$ can be further decomposed into $D$ and $U'$ such that:  

$$D=\begin{bmatrix}
* & 0 & 0 \\
0 & * & 0 \\
0 & 0 & *
\end{bmatrix}$$

$$U'=\begin{bmatrix}
1 & * & * \\
0 & 1 & * \\
0 & 0 & 1
\end{bmatrix}$$

Thus we get $A=LDU'$.

----
# Permutation matrices
If the Gaussian elimination of $A$ needs swapping of rows to get $U$ then because of this swapping of rows there are changes in $E$ thus  in $L$. Therefore blindly applying $A=LU$ will not work.  
To account for this swapping of rows we use permutation matrices.    

Permutation matrices pre-multiply $A$ to swap it's rows.  
Properties:
1. $P$ has same rows as $I$(just swapped).
2. Product of $P_1,P_2$ gives $P_3$.
3. $P^{-1}=P^T$.
4. $n!$ = Number of permutation matrices for  $A$ with $n$ rows.

Thus we get:

$$PA=LDU'$$

----
