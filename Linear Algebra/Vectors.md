A quantity that has **magnitude** and **direction**.  
A vector $v$ in $\mathbb{R}^n$  is denoted as $v=[v_1, v_2,...,v_n]^T$

# Magnitude
$||V||=\sqrt{\sum _{i=1}^n v_i^2}$

- Unit vector: $||V||=1$

# Direction
Reference angle for the direction of vector = $\large \theta = tan^{-1}(\frac{y}{x})$  
- direction = $\theta$ = angle from x-axis.
- slope = $tan(\theta)$ = change in y for unit change in x

# Shadow
Length of shadow of $\vec a$ on $\vec b = ||s|| = ||\vec a||cos(\theta)$
- = $||\vec a||$ if $\theta=0\degree$ = parallel = length of $\vec a$ on itself
- = $0$ if $\theta = 90\degree$  - perpendicular
$\theta=$ shortest angle between $\vec a\ and\ \vec b$.
- $\theta \in [0\degree, 180\degree]$

# Dot Product
Let $\vec a,\vec b \in \mathbb{R}^n$.
- $\vec a . \vec b = ||\vec a||\ ||\vec b||cos(\theta) = \sum_{i=1}^n a_i b_i$  
- $\vec a . \vec b = \vec b . \vec a$
- $\large \theta =  cos^{-1}(\frac{\vec a . \vec b}{||a||\ ||b||})$
- $\vec a . \vec b = 0$ if perpendicular.
- Zero vector is perpendicular to any vector.
- $\vec a . \vec a = ||a||^2$
- 

---
# Linear Combination
Let, $V_1,V_2,...V_k$ be $k$ vectors $\in \mathbb{R}^n$,such that  
$V_i = \begin{pmatrix}v_{i,1} \\ v_{i,2} \\ ... \\ v_{i,n}\end{pmatrix}$

Their linear combination is given as,  
$Y = a_1V_1 + a_2V_2 + ... + a_kV_k$ where $a_1, a_2, ..., a_k \in \mathbb{R}$   

## Pictures: Visual representations
Let,  
$X,Y,Z,V \in \mathbb{R}^n$ and $a,b,c \in \mathbb{R}$  
$aX + bY + cZ = V$ can be geometrically viewed in following ways:

### Column picture
$$ \newcommand\mycolv[1]{\begin{bmatrix}#1\end{bmatrix}}

a\mycolv{x_1 \\ x_2 \\.\\.\\.\\x_n} + 
b\mycolv{y_1 \\ y_2 \\.\\.\\.\\y_n} + 
c\mycolv{z_1 \\ z_2 \\.\\.\\.\\z_n} 
= \mycolv{v_1 \\ v_2 \\.\\.\\.\\v_n}$$
Where we can view vectors $X,Y,Z$ as column vectors scaled by $a,b,c$ in $\mathbb{R}^n$ to get resultant vector $V$, in vector space graph.

### Row picture
$$\begin{aligned}
\large ax_1 + by_1 + cz_1 = v_1 \\
\large ax_2 + by_2 + cz_2 = v_2 \\
. \\
. \\
\large ax_n + by_n + cz_n = v_n \\
\end{aligned}$$
Which we can view as $n$ planes in $\mathbb{R}^3$ euclidean space graph.

- We get set of equations where each equation is a hyperplane, and intersection(if exists) of them gives the solution.
- Its easy to see if system is inconsistent(has no solution) or undertermined(has infinitely many solutions)
- Row picture is more cluttered than column picture visually.

----
## Linear Independence
Let,  
$[0]$ be a zero vector in $\mathbb{R}^n$,  
$V_1,V_2,...V_k$ be $k$ vectors $\in \mathbb{R}^n$,  are said to be linearly independent iff  
$a_1V_1 + a_2V_2 + ... + a_kV_k=[0]$  can only be satisfied by $a_i=0$.

- No vector in the set can be represented by linear combination of others.
- Property of set of vectors.

If we take all $V's$ as a column vector and form a matrix $A$, then checking linear independence is alike to checking $N(A)$, such that  
$N(A) = \set{x | Ax=0}$  
They are linearly independent if $N(A)$ contains only zero vector else they are linearly dependent.

## Linear dependence
If there exists $a_1, a_2,...,a_n \in \mathbb{R}$ such that  $a_1V_1 + a_2V_2 + ... + a_kV_k=[0]$  and there is at least one non-zero $a_i$.  

- At least one vector in the set can be represented as linear combination of others.
- Zero vector is linearly dependent on any set of vectors.
----

