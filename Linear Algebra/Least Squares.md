$Ax=b$ may not have solution every time, in such cases maybe we can find the closest solution. Least squares helps us in that.  

Finds $x$ such that $Ax-b=E=error$ is minimum.  

We work with squares of errors because:
1. then negative and positive errors wont cancel out
2. will still be differentiable.

$ax=b$ solution doesnt exist because $a$ and $b$ are independent.  
Instead we can find $a\hat x=P$, such that $P$ is the projection of $b$ on $a$, this $\hat x$ is the closest solution we can find.  

### Normal equation
$e =$ error must be $\perp$ to $A\hat x-b$ or $b-A \hat x$.  
$\implies A^Te=0 \implies A^T(b-A \hat x)=0$  
$\large \implies A^TA\hat x = A^Tb$   

LS solution: $\hat x = (A^TA)^{-1}A^Tb$,  
Projection matrix: $A(A^TA)^{-1}A^T$  
Projection: $p=A\hat x$  

Projection matrix properties:
1. $P^2 = P$
2. $P^T=P$

#TODO 


