Every matrix is a Linear Transformation.  

Properties:
1. $T(cX+dY)=xT(X)+dT(Y)$
2. If T(X) is known for all basis vectors then its known for all vectors in that vector space.
3. Every linear transformation can be represented by matrix.

What transformations cannot do:
1. Move origin.

Typically
1. Choose transformation on each basis vector.
2. Transformation matrix is formed by taking these transformations as column vectors.

----
### Some transformations

Rotation by $90\degree$ CCW(counter-clockwise):  

$$\begin{bmatrix}
0 & -1\\
1 & 0
\end{bmatrix}$$

Rotation by $\theta$ CCW:

$$\begin{bmatrix}
cos\theta & cos(90+\theta) \\
sin\theta & sin(90+\theta)
\end{bmatrix} = 
\begin{bmatrix}
cos\theta & -sin\theta \\
sin\theta & cos\theta
\end{bmatrix}$$


Projection onto x-axis in $\mathbb{R}^2$:

$$\begin{bmatrix}
1 & 0 \\
0 & 0
\end{bmatrix}$$

Projection onto any line with angle $\theta\ in\ \mathbb{R}^2$:  

$$\begin{bmatrix}
cos^2\theta & sin\theta cos\theta \\
sin\theta cos\theta & sin^2\theta
\end{bmatrix}$$

Reflection along x-axis:  

$$\begin{bmatrix}
1 & 0 \\
0 & -1
\end{bmatrix}$$

Reflection along a line with angle $\theta$:  

$$\begin{bmatrix}
cos2\theta & sin2\theta \\
sin2\theta & -cos2\theta
\end{bmatrix}$$

----
### Polynomial operations
Representation of polynomial of degree $n$:  

$$\large \begin{bmatrix}
a_0 \\
a_1 \\
. \\
. \\
a_n
\end{bmatrix} = a_nt^n + a_{n-1}t^{n-1}+...+a_2t^2+a_1t_1+a_0t^0$$

Basis of polynomial of degree $n =$ basis of $\mathbb{R}^{n+1}$,  

$$\begin{bmatrix}
1 \\
0 \\
0 \\
. \\
. \\
0
\end{bmatrix},
\begin{bmatrix}
0 \\
1 \\
0 \\
. \\
. \\
0
\end{bmatrix},...,
\begin{bmatrix}
0 \\
0 \\
0 \\
. \\
. \\
1
\end{bmatrix}$$

where each of $n+1$ basis vectors($1,t^1,t^2,...,t^n$) $\in \mathbb{R}^{n+1}$.  

**Multiplication:** Transformation matrix to multiply a degree 3 polynomial by $t$:  

$$\begin{bmatrix}
0 & 0 & 0 \\
1 & 0 & 0\\
0 & 1 & 0\\
0 & 0 & 1
\end{bmatrix}$$ 
**Differentiation:** n-degree polynomial $\to$ n-1 degree.  
Transformation matrix to differentiate 3rd degree polynomial:  
$$\begin{bmatrix}
0 & 1 & 0 & 0\\
0 & 0 & 2 & 0\\
0 & 0 & 0 & 3
\end{bmatrix}$$

**Integration:**  
Transformation matrix to integrate 3rd degree polynomial:  

$$\large \begin{bmatrix}
0 & 0 & 0 \\
1 & 0 & 0 \\
0 & \frac{1}{2} & 0 \\
0 & 0 & \frac{1}{3} \\
\end{bmatrix}$$

