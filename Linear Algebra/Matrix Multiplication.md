
$\large A_{m\times n} . B_{n\times p} = C_{m\times p}$


----
# Regular way - Dot Product
$$\large \begin{align}C_{ij} =
(\text{i'th row of A}) . (\text{j'th column of B}) =
\sum_{k=1}^nA_{ik}B_{kj}
\end{align}$$ 

----
# Post-multiply A by B
$j$'th column of $C$ is the linear combination of column vectors of $A$ with components of $j$'th column of $A$ as scalars.  
 
 
$\text{j'th column of C}$
$$\begin{aligned}
&= C_{*j} \\
&=\text{(Col 1 of A)$\times B_{j1}$ + (Col 2 of A)$\times B_{j2}$ + ... + (Col n of A)$\times B_{jn}$} \\ 
&=\sum_{k=1}^n\text{(Col k of A)}\times B_{jk}
\end{aligned}$$

- This can be used for elementary column operations.

----
# Pre-multiply B by A
$i$'th row of $C$ is the linear combination of row vectors of $B$ with components of $i$'th row of $A$ as scalars.  


$\text{i'th row of C}$
$$\large \begin{aligned}
&= A_{i1}\text{(Row 1 of B)} + A_{i2}\text{(Row 2 of B)} + ... +A_{in}\text{(Row n of B)} \\
&= \sum_{k=1}^n A_{ik}\text{(Row k of B)}
\end{aligned}$$  

- This can be used for elementary row operations.

----
