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

### Why Gauss-Jordan method works?  
$\because A=LU \implies U^{-1}L^{-1}=A^{-1}$.  

First to transform $A$ to $U$ we indirectly/unknowingly/via some other method multiplied it with $L^{-1}$ thus we multiplied augmented $I$ also with $L^{-1}$.  
$\therefore$ we get $[A|I] \to [U|L^{-1}]$.  

Now to get $I$ from $U$ we indirectly/unknowingly/via some other method multiplied it with $U^{-1}$ thus we multiplied augmented part also with $U^{-1}$.  
$\therefore$ we get $[U|L^{-1}] \to [I|U^{-1}L^{-1}]$.  
Thus augmented part is transformed to $A^{-1}$.  

## LU vs Gauss Jordan
| | LU | Gauss-Jordan |
|--|--|--|
| Time complexity: | $O(n^3)$ | $O(n^3)$ |
| Parallelization: | Easily. | Difficult. |
| Practicality: | Faster than GS due to parallelization. | Comparatively slower. |
| Uses: | Can be used to solve for other linear systems. | Finds only inverse. |


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
# Pseudo Inverse

Let $A =m \times n$ matrix.  
$I_k = k \times k$ identity matrix.  

> **Left Inverse:** Matrix $B$ such that $BA=I_n$

> **Right Inverse:** Matrix $C$ such that $AC=I_m$
- $A^T(AA^T)^{-1}$

Let $m \le n$ and $A$ be full row rank
$\implies A$ need not be full column rank
But  $C(A)$ covers entire $\mathbb{R}^m$.  
$\implies Ax=b$, solution exists for all possible $b \in \mathbb{R}^m$,  
$\because n \ge m$ there can be multiple solutions also,  
$\implies$ There is guarantee of EXISTENCE of AT LEAST ONE solution for $Ax=b$.  
$\implies$ In such case we can find C such that $AC=I_m$,  
$\implies$ right inverse(or inverses) exists for $A$.  

Let $n \le m$ and $r=n$ meaning $A$ is full column rank,  
$\implies$ there are $r=n$ independent rows,  
$\implies C(A)$ is subspace of $\mathbb{R}^m$,  
and $n$ independent columns forms basis of $C(A)$,  
$\implies Ax=b$, solution exists for only $b \in C(A)$,  
But if solution exists then it is UNIQUE.  

> A rectangular matrix cannot have both EXISTENCE and UNIQUENESS guarantee.

Similarly for left inverse:  
Now, $\because r=n$ rows are independent,  
$C(A^T)$, row space, covers entire $\mathbb{R}^n$,  (not $\mathbb{R}^m$)  
$\implies x^TA=b$ solution exists for any $b \in \mathbb{R}^n$,  
$\because m \ge n$, there can be multiple solutions too,  
$\implies BA=I_n$ solution exists $\implies$ left inverse exists and there can be multiple.  

----
# Determinant
$detA$ tells about the volume of the box formed by row vectors.  

Properties:
1. $det(I)=1$
2. $det(B)=-det(A)$ if $B$ is obtained by one row exchange of $A$
	1. row exchange changes the determinant sign
3. it depends linearly on first row
	1. $det(kA) \not = k\ det(A)$ but $k$ just multiplies first row.
4. $det(A+B) \not = det(A)+det(B)$
	1. only first rows we can separate like this.
5. If two rows are equal then det is 0.
6. If row of zeroes exist, then det is 0
7. If $A$ is triangular, $det(A)=$ product of its diagonal elements
8. If $A$ is singular, $det(A)-0$
9. $det(AB)=det(A)det(B)$
10. $det(A^T)=det(A)$
11. $det(A_k)=det(D_k)=d_1d_2...d_k$ (Use A=LDU)
12. 

$$det(A) = \sum_{i=1}^n a_{ij}C_{ij}$$

where $C_{ij} = (-1)^{i+j}det(M_{ij})$ = cofactor of $a_{ij}$,  
where $M_{ij} =$ minor of $a_ij$.  

#TODO write with more clarity

### Finding inverse

$$A^{-1}=\frac{C^T}{detA}$$

### Cramer's rule
$Ax=b$  

$$\large x_j = \frac{B_j}{detA}$$

where $B_j =$ same as $A$ but j'th column replaced with $b$.  


### Finding pivots

$$\large d_k = \frac{detA_k}{detA_{k-1}}$$

where $d_k =$ k'th pivot.  

----
