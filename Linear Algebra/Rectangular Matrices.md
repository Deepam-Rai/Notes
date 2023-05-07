In Gaussian Elimination#TODO put link, for square matrix:  
$A \to U \to I$  
transformation takes place. for rectangular matrices following takes place:  
$A \to U\text{(row echelon form)} \to R\text{(reduced row echelon form)}$  

---
# Solving simultaneous system of equations
for rectangular matrix.
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
---

Let $A$ be $m \times n$ matrix.  
$r =$ rank of the matrix,  
$r =$ no. of pivot columns,  
$r =$ no. of pivot columns,  
$m-r =$ no. of zero rows,  
$m-r =$ no. of conditions to be satisfied,  
$n-r =$ no. of free variables,  
$n-r =$ no. of special solutions in $N(A)$,  


