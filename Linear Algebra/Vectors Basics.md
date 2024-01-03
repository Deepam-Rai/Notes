>**Definition:** A quantity that has both **magnitude** and **direction**.

----
### Direction Cosines
Are the cosines of the angle between the vector and positive coordinate axes.  

Let,  
$\vec v$ be a vector,  
$\alpha, \beta, \gamma$ be the angle it subtends at axes $x,y,z$ respectively,  
then it's direction cosines are given as:  

$$\begin{aligned}
l &= \cos{\alpha} \\
m &= \cos{\beta} \\
n &= \cos{\gamma} \\
\end{aligned}$$  
- Is a way of describing a vector using it's angles wrt the axes.
- $l^2 + m^2 + n^2 = 1$

### Direction ratio
Are constants $a,b,c$ such that  

$$\begin{aligned}
\frac{l}{a} = \frac{m}{b} = \frac{n}{c}
\end{aligned}$$

where $l,m,n$ are the direction cosines.  Thus,  

$$\begin{aligned}
l &= \frac{a}{\sqrt{a^2 + b^2 + c^2}} \\
m &= \frac{b}{\sqrt{a^2 + b^2 + c^2}} \\
n &= \frac{c}{\sqrt{a^2 + b^2 + c^2}} \\
\end{aligned}$$


----
## Types

### Equal
Equal magnitude and same direction.

### Unit
Magnitude is of unit length = 1.

### Zero
Magnitude is zero.

### Parallel
Vectors having the same direction?

### Collinear
Vectors that along the same line.

----
### Position vector of a point
Is an Euclidean vector that represents the position of a vector $P$ in space in relation to an arbitrary reference point $O$.  

### Negative of a vector
Vector that has opposite direction.  

### Components of vector
Are the scalar values associated with each axis that denotes distance of the vector from origin in that respective axis.  

## Properties

### Addition
Components are added.  

$$\begin{bmatrix}
a_1 \\
a_2 \\
. \\
. \\
\end{bmatrix} + 
\begin{bmatrix}
b_1 \\
b_2 \\
. \\
. \\
\end{bmatrix} = 
\begin{bmatrix}
a_1 + b_1 \\
a_2 + b_2 \\
. \\
. \\
\end{bmatrix}$$

### Multiplication
Vector by scalar:  Scalar gets multiplied to each component.  

$$c \begin{bmatrix}
a_1  \\
a_2 \\
. \\
. \\
\end{bmatrix} = 
\begin{bmatrix}
c a_1 \\
c a_2 \\
. \\
. \\
\end{bmatrix}$$


----
## Position vector of a point that divides  a line segment
Let,  
$\vec{OP}, \vec{OQ}$ be two vectors and  
$\vec{OR}$ divide line segment $\bar{PQ}$  in raion $m:n$ internally.  
Then,  
### Divides Internally

$$
\vec{OR} = \frac{m\vec{OP} + n\vec{OQ}}{m+n}
$$Derivation:
![Internal divide](../Images/Linear%20Algebra/divide_internal_section_vector.png)   

### Externally

$$
\vec{OR} = \frac{m\vec{OP} - n\vec{OQ}}{m-n}
$$ 
----
