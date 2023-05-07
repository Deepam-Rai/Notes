> Orthogonality = perpendicular $\implies$ independent

- Linear independence $\centernot \implies$ orthogonality

> **Orthogonal vectors:** are mutually perpendicular set of vectors.

> **Orthonormal basis:** Basis set is a set of orthogonal vectors.

> **Orthogonal subspaces:** $V$ and $W$ are said to be orthogonal subspaces if $x^Ty=0, \forall x \in V, y \in W$.

Example: xy plane and xz plane, axes, x axis to yz plane, etc.
- $V=${zero vector} is a subspace orthogonal to every other subspace.
- If basis vectors are orthogonal, then vector spaces are orthogonal.

> **Orthogonal Complement:** Space of all vectors orthogonal to $V$, denoted as $V^\perp$.


Test of orthogonality: 
1. $v_1.v_2=0$
2. $v_1^Tv_2=0$

----
# Orthonormalization

Properties of orthonormal matrix $Q$
1. column vector have unit length
2. row vectors are also orthonormal
3. $Q^TQ=I$
4. $Q^T =Q^{-1}$ for square matrix $Q$
5. $Q^T$ = Left inverse for rectangular $Q$
6. transformation with $Q$ does not change length of vector
7. $Q$ preserves inner dot product and angles
8. 
Example: Permutation matrices.

## Gram-Schmidt process
Generating orthonormal basis from independent vectors.  

$a_1,a_2,...,a_n =$ independent vectors,  
$q_1, q_2,...,q_n =$ orthonormal vectors that we want,  

1. $\large q_1=\frac{a_1}{||a_1||}$
2. for $k=2,3,...,n$:
	1. $\large t_j = a_j - [(q_1^Ta_j)q_1 + (q_2^Ta_j)q_2 + ... + (q_{j-1}^Ta_j)q_{j-1}]$
	2. $\large q_j = \frac{t_j}{||t_j||}$

----
# QR decomposition

$$A=QR$$

where,  
$A =$ $m \times n$ matrix with rank $=n$ (all columns are independent),  
$a_j =$ j'th column vector of $A$,  
$Q =$ orthonormal basis spanning subspace of $\mathbb{R}^m$ constructed from independent column vectors,  
$q_i =$ i'th column vector of $Q$,  
$R =$ upper triangular matrix such that $R_{ij}=q_i^Ta_j$.  

We can get $Q$ and $R$ using Gram-Schmidt process from column vectors of $A$.

----
