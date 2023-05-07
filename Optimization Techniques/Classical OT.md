
----
# Unconstrained Functions
## Of One Variable
Let $f$ be a continuous function $f:I=(a,b) \to \mathbb{R}$.  

### Extremas: Minima and Maxima

> **Global/absolute minimum** of $f$ is said to be at $x_1 \in I$ if $$f(x_1) \le f(x) \forall x \in I$$

> **Global/absolute maximum** of $f$ is said to be at $x_1$ if $$f(x_1) \ge f(x) \forall x \in I$$

> **Local/relative minimum** of $f$ is said to be at $x_1 \in I$ if $\exists$ a real number $\delta \gt 0$ such that, $$f(x_1) \le f(x) \forall x \in (x-\delta, x+\delta)$$

> **Local/relative maximum** of $f$ is said to be at $x_1\in I$ if $\exists$ a real number $\delta \gt 0$ such that, $$f(x_1) \ge f(x) \forall x \in (x-\delta, x+\delta)$$

> **Stationary/critical** of $f$ is said to be at $x_1 \in I$ if $f$ is differentiable at $x_1$ and $f'(x_1)=0$.

- The function at stationary/critical point is neither increasing or decreasing.

Necessary condition for Local Extrema:  
If $f:I \to \mathbb{R}$ is differentiable at $x_1$, and the $f$ has local extremum at $x_1$ then $f'(x_1)=0$.  

#### Sufficient Condition for Local Extrema:  
> If $f^{(k)}(x_1)=0, k=1,2,...,n$ and $f^{(n+1)}(x_1) \not = 0$, and $f^{(n+1)}(x_1)$ is continuous in the neighbourhood of $x_1$, then $f$ has local extremum at $x_1$ iff $(n+1)$ is even. Further, $f$ has a local maxima at $x_1$ if $f^{(n+1)}(x_1) \lt 0$ and minima at $x_1$ if $f^{(n+1)}(x_1) \gt 0$.  

#TODO why?

----
### Newton Raphson Method
- Computes stationary point of a function iteratively.
- Leverages Taylor's Theorem.
- The method may or may not converge.
- Manually need to determine how many stationary points are present and suitable starting points for them.

Taylor's Theorem #TODO  move to separate misc concepts note
 If $f^k$ is continuous in $[x,x+h]$ and $f^{(k+1)}$ exists on $(x,x+h)$, then for some $\theta, 0 \lt \theta \lt 1$  $$\large f(x+h) = f(x) + hf'(x) + \frac{h^2}{2}f''(x)+...+\frac{h^{k+1}}{(k+1)!}f^{(k+1)}(\theta x + (1-\theta)(x+h))$$

Steps:
1. Take an arbitrary starting point $x_0$.
2. Until $|x_k - x_{k+1}| \lt \text{tolerance}$
	1. $\large x_{k+1} = x_k - \frac{f(x_k)}{f'(x_k)}$
3. $x_{k+1}$ is an stationary point.

----
## Of Several Variables
Let $f$ be a function $f:S \to \mathbb{R}$ where $S \subset \mathbb{R}^n$ is a region.  
$X \in S$ is n-dimensional vector $[x_1,x_2,...,x_n]^T$.  


### Necessary and Sufficient Condition for Local Extrema
> If $\large \frac{\partial f(X)}{\partial x_j}$ exists for all $X \in S$ and for all $j=1,2,...,n$ and if $f$ has a local extremum at $X'$ in the interior of $S$, then  
 

$$\large \nabla f(X')=\frac{\partial f(X')}{\partial x_j}=0, j=1,2,...,n$$


### Hessian Matrix
#TODO move to separate misc concepts note
It is a square matrix of second-order partial derivatives of scalar valued function.  
It gives information like local curvature of a function at a particular point thus immensely helpful in finding maxima/minima.  

Hessian matrix is defined as:  

$$\Large H(X)=\begin{bmatrix}
\frac{\partial ^2 f}{\partial x_1^2} & \frac{\partial^2 f}{\partial x_1 \partial x_2} & ... & \frac{\partial^2 f}{\partial x_1 \partial x_n} \\
\frac{\partial^2 f}{\partial x_2 \partial x_1} & \frac{\partial ^2 f}{\partial x_2^2} & ... & \frac{\partial^2 f}{\partial x_2 \partial x_n} \\
. & . &  & .\\
. &  & . & .\\
\frac{\partial^2 f}{\partial x_n \partial x_1} & \frac{\partial ^2 f}{\partial x_n \partial x_2} & ... & \frac{\partial^2 f}{\partial x_n^2}
\end{bmatrix}$$

Usage:  
If $f$ has local extremum at $X^*$, then
1. $f$ has local maximum at $X^*$ if $H(X^*)$ is negative definite.
	1. All eigen values are negative.
2. $f$ has local minimum at $X^*$ if $H(X^*)$ is positive definite.
	1. All eigen values are positive.
	2. All upper $k \times k$ sub-determinants are positive.
	3. $x^TH(X^*)x \gt 0$ for all vector $x \not = 0$.


### Jacobian Matrix
#TODO move to misc concepts
Let $f: \mathbb{R}^n \to \mathbb{R}^m$, then Jacobian of $f$.  

Jacobian matrix is a matrix of first-order partial dervatives of a vector-valued function with respect to its variables.  

$$\Large J=\begin{bmatrix}
\frac{\partial g_1}{\partial x_1} & \frac{\partial g_1}{\partial x_2} & ... & \frac{\partial g_1}{\partial x_n} \\
\frac{\partial g_2}{\partial x_1} & \frac{\partial g_2}{\partial x_2} & ... & \frac{\partial g_2}{\partial x_n} \\
. & . &  & .\\
. & . &  & .\\
\frac{\partial g_m}{\partial x_1} & \frac{\partial g_m}{\partial x_2} & ... & \frac{\partial g_m}{\partial x_n}
\end{bmatrix}_{m \times n}$$

### Newton Raphson Method
- Iterative method to find stationary point by solving $\nabla f(X)=0$.
- Leverages Taylor's Theorem for several variables.

Taylor's Theorem for several Variable:  
#TODO move to misc maths notes
If the second partial derivatives of $f$ are continuous and $X, X+h$ are two points in the domain of $f$, then for some $0 \lt \theta \lt 1$  $$f(X+h) = f(X) + \nabla f(X)^Th + \frac{1}{2}h^TH(\theta X+(1-\theta)(X+h))h$$

Steps:
1. Arbitrarily initiate $X_0$.
2. Until $|X_{k+1} - X_k| \lt \text{tolerance}$
	1. $\large X_{k+1} = X_k - J^{-1} A_k$
3. $X_{k+1}$ is a stationary point.

where 
$$A_k = \begin{bmatrix}
g_1(X_k) \\
g_2(X_k) \\
.\\
.\\
g_m(X_k)
\end{bmatrix}$$


----
# Convex and Concave functions
#TODO move to misc concepts.

>**Convex function**: A function $f$ defined on a simply connected region $S \subset \mathbb{R}^n$ is said to be convex on $S$ if $\forall \alpha \in [0,1]$ and $X_1, X_2 \in S$ 
>$$f(\alpha X_1 +(1-\alpha)X_2) \le \alpha f(X_1) + (1-\alpha)f(X_2)$$

Intuitive understanding:
1. Take two points $X_1$ and $X_2$.
2. Draw line joining them.
3. For all the points between these two points (here controlled by $\alpha$), the graph of the function will always lie below or at equal height ($\le$) than the line drawn.

> **Concave function**: A function $f$ is said to be a concave function if $\forall \alpha \in [0,1]$ and $X_1, X_2  \in S$
> $$f(\alpha X_1 + (1-\alpha)X_2) \ge \alpha f(X_1) + (1-\alpha)f(X_2)$$

Intuitive understanding:
1. Take two points $X_1$ and $X_2$.
2. Draw line joining them.
3. For all the points between these two points (here controlled by $\alpha$), the graph of the function will always lie above or at equal height ($\ge$) than the line drawn.

Convex/concave function has only one minimum/maximum, means finding local minima/maxima is equivalent to finding global minima/maxima.  

## Determining convexity
For a single variable function $f(x)$
1. We can see the graph :)
2. If $f(x)$ is twice differentiable on an interval $I$, then $f(x)$ is convex on $I$ iff $f''(x) \ge 0$ on $I$.

Similarly it can be extended to multi-variable functions.  
Owing to some theorem #TODO  we get:  
Let, $f:S \to \mathbb{R}$ be a twice continuously differentiable function on $S$ where $S \subset \mathbb{R}^n$, then
1. $f$ is convex on $S$ if Hessian matrix $H(X)$ of $f$ is positive semi-definite.
2. $f$ is strictly convex on $S$, if $H(A)$ of $f$ is positive definite.

----
# Constrained Functions

General optimization problem with constraints:  

$$\begin{aligned}
\text{Maximize or Minimize } z &= f(x) \\
\text{ subject to } \\
g_i(X) &\le 0, i=1,2,...,r \\
g_i(X) &\ge 0, i=r+1,...,p \\
g_i(X) &=0, i=p+1,...,m
\end{aligned}$$

$z =$ objective function,  
$g() =$ constraints,  
$X =  [x_1,x_2,...,x_n]^T \in \mathbb{R}^n$,   
$m =$ total number of constraints.  

> **Feasible:** $X$ is said to be feasible if $X$ satisfies all constraints.

## Equality constraints
General optimization problem with just equality constraints:  

$$\begin{aligned}
\text{Maximize or Minimize } z &= f(x) \\
\text{ subject to } \\
g_i(X) &=0, i=1,2,...,m
\end{aligned}$$

### Substitution
Sometimes its possible to substitute the variable among constraints and objective function and reduce the variables. But often its not.  
By substituting we mean:
1. From constraint get a variable in terms of another variabe: like $x_i = f(x_j)$
2. substitute $x_i$ with $f(x_j$) at other places.
3. thus effective we have reduced a variable $x_i$.

### Jacobian Method
#TODO 

### Method of Lagrange
Preferred method.
- introduces additional variables: Lagrange's multipliers
- converts the problem to unconstrained optimization problem.

Steps:  
1. Get all constraints into form:

$$g_i(X)=0, i=1,2,...,m$$

2. Change objective function to Lagrangian function as:

$$\large L = f(X) + \lambda_1(g_1(X)) + \lambda_2(g_2(X))+ ...  + \lambda_m(g_m(X)) = f(X) + \sum_{i=1}^m\lambda_i(g_i(X))$$

3. Differentiate $L$ w.r.t. $x_1,x_2,...,x_n$ and $\lambda_1,\lambda_2,...,\lambda_m$ to get:

$$\large \begin{aligned}
\frac{\partial L}{\partial x_1} = 0 \\
\frac{\partial L}{\partial x_2} = 0 \\
. \\
. \\
\frac{\partial L}{\partial x_n} = 0 \\
\frac{\partial L}{\partial \lambda_1} = 0 \\
\frac{\partial L}{\partial \lambda_2} = 0 \\
. \\
. \\
\frac{\partial L}{\partial \lambda_m} = 0
\end{aligned}$$


4. Solve above equations to get $X$ and $\lambda$s.
5. Check it's optimality using Hessian matrix $H(X)$ of $f$.
	1. If $H(X)$ is positive definite, then $X$ is strictly local minimum.
	2. If $H(X)$ is positive semi-definite, then $X$ is local minimum but not strictly.
		1. There may exist other local minimum points in neighborhood.
	3. If $H(X)$ is indefinite then we need more information to determine whether it is local maxima or minima or saddle point.
	4. If $H(X)$ is negative definite, then $X$ is strictly local maximum.
	5. If $H(X)$ is negative semi-definite, then $X$ is local maximum but not strictly.
		1. There may exist other local maxima in neighborhood.

Lagrange's method can be taken as special case of KKT method that deals with inequality constraints too.

## Inequality Constraints

### Karush-Kuhn-Tucker (KKT) method
It develops upon Lagrange's method, for inequality it adds slacks or subtracts surplus as necessary.  

General form of optimization problem:  

$$\begin{aligned}
\text{Maximize or Minimize } z &= f(x) \\
\text{ subject to } \\
g_i(X) &\le 0, i=1,2,...,r \\
g_i(X) &\ge 0, i=r+1,...,p \\
g_i(X) &=0, i=p+1,...,m
\end{aligned}$$

1. Convert all constraints to "=" type.  

$$\begin{aligned}
\text{Maximize or Minimize } z &= f(x) \\
\text{ subject to } \\
g_i(X) + s_i &= 0, i=1,2,...,r \\
g_i(X) - s_i &= 0, i=r+1,...,p \\
g_i(X) &=0, i=p+1,...,m
\end{aligned}$$

2. Follow normal Method of Lagrange. Construct Lagrangean function.

$$L(X,S,\lambda)=f(X)- \sum_{i=1}^r\lambda_i[g_i(X)+s_i] - \sum_{i=r+1}^p\lambda_i[g_i(X)-s_i] - \sum_{i=p+1}^m\lambda_ig_i(X)$$

$\lambda =$ generalized Lagrange multipliers,  
modified constraints = KKT conditions.

3. Follow normal method of Lagrange.

----
