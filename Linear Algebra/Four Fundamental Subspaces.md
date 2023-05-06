Prerequisite notes:
1. [Vector Space](./Vector%20Space.md)
2. [Orthogonality](./Orthogonality.md)

----
Let $A = m\times n$ dimensional matrix.  

$C(A) =$ Column space of A,  
$C(A^T) =$ Row space of A,  
$N(A) =$ Null space of A,  
$N(A^T) =$ Null space of $A^T$,  
$r =$ no. of pivot elements in $A$, $r \le m, r \le n$,

$\therefore$  
$r =$ no. of pivot cols = no. of pivot rows,  
$r$ pivot columns forms basis of $C(A)$,  
$r$ pivot rows forms basis of $C(A^T)$,  
$C(A) = r$ dimensional subspace of $\mathbb{R}^m$,  
$C(A^T) = r$ dimensional subspace of $\mathbb{R}^n$,  
$N(A) = n-r$ dimensional subspace of $\mathbb{R}^n$,  
$N(A^T) = m-r$ dimensional subspace of $\mathbb{R}^m$,  
$\mathbb{R}^n$ is split into $C(A^T)$ of dim $r$ and $N(A)$ of dim $n-r$,  
$\mathbb{R}^m$ is split into $C(A)$ of dim $r$ and $N(A^T)$ of dim $m-r$,  

$R =$ row echelon form of $A$,  
$U =$ upper dimensional form of $A$,  
then,  
$N(R)=N(U)=N(R)$ as row operations maintains linear systems,   

$C(A^T) = C(U^T) = C(R^T)$ as row operations transforms rows using linear combination of other rows,    
$C(A), C(U), C(R)$ need not be same as row operations breaks columns,  


$C(A) \perp N(A)$ (orthogonal),  
$C(A^T) \perp N(A^T)$,  
$C(A) = (N(A))^\perp$ (orthogonal complement),  
$C(A^T) = (N(A^T))^\perp$,  

$Ax=b$, solution exists only if $b \in C(A) \implies$ only if $b \perp N(A^T)$,  

$v=v_r + v_n$ for any $v \in \mathbb{R}^n, v_r \in C(A^T), v_n \in N(A)$,  
$v=v_r + v_m$ for any $v \in \mathbb{R}^m, v_r \in C(A), v_n \in N(A^T)$,  


![Four Fundamental Subspaces](../Images/Linear%20Algebra/fundamental_subspaces.png)

#TODO clarity on those arrows and one-to-one mapping therein/invertibility.

