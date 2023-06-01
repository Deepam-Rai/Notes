> **Cut vertex:** A vertex $v \in V(G)$ is said to be a cut vertex of $G$ if $k(G-v) \gt k(G)$. 
- Bridge exists $\implies$ cut vertex exists, but not vice versa.
- [Theorem](./Theorems.md): v incident to a bridge is cut vertex iff $deg(v)\ge 2$.
- [Theorem](./Theorems.md): v cannot be the farthest vertex from any other vertex.
- [Theorem](./Theorems.md):Every nontrivial connected graph contains at least two non-cut-vertices.

>**Nonseparable graph:** A non-trivial connected graph with no cut vertices.
- [Theorem](./Theorems.md): Every two vertices lie on a common cycle.

>**Block:** A maximal nonseparable subgraph. A nonseparable subgraph of $G$ that is not a proper subgraph of any other nonseparable subgraph in $G$.
- Blocks are joined by cut vertices.

>**Vertex cut:** A set $U$ of vertices of graph $G$, such that $G-U$ is disconnected or trivial graph.
- **Minimum vertex-cut:** A vertex-cut of minimum cardinality.
- A connected graph contains a vertex-cut iff it's not complete.

>**Vertex-connectivity $\kappa(G)$:** Cardinality of minimum vertex cut of $G$.
- $0 \le \kappa(G) \le n-1$
	- 0 for disconnected $G$.
	- $\kappa(G) = n-1$ for $G=K_n$.

>**k-connected:** If $\kappa(G)\ge k$.
- Removal of fewer than $k$ vertices does not result in disconnected or trivial graph.
- k-connected is also l-connected for all $0\le l \le k$.

>**Edge-cut:** Set of edges $X$ of graph $G$ such that $G-X$ is either disconnected or trivial graph.
- **minimal edge-cut:** An edge-cut whose no proper subset is edge cut.
- **minimum edge cut:** edge-cut of minimum cardinality.
	- All minimal edge cut are minimum edge cut, but converse is not true.

>**Edge connectivity $\lambda(G)$:** of a nontrivial graph $G$ is the cardinality of a minimum edge cut.
- $\lambda(G)=0$ iff $G$ is disconnected or trivial.
- $0 \le \lambda(G) \le n-1$

>**k-edge connected:** $\lambda(G) \ge k$.
- Every k-edge connected is also l-edge connected for $0\le l \le k$.
- 2-edge connected graph has no bridges.
- [Theorem:](./Theorems.md) $\lambda(K_n)=n-1$

Relationships:
1. [Theorem:](./Theorems.md) $\kappa(G) \le \lambda(G) \le \delta(G)$
2. [Theorem:](./Theorems.md) $\kappa(G) = \lambda(G)$ for cubic graphs.

>**Harary graphs $H_{r,n}$:** A graph, for integers $2 \le r \lt n$, with order $n$, is *nearly* r-regular, has size $m$ and $\large \kappa(H_{r,n}) = r = \floor{\frac{2m}{n}}$.  

>**k'th power:** A graph $G^k$ is said to be $k'th$ power of $G$ with $V(G^k)=V(G)$, such that $uv \in E(G^k)$ if $1\le d_G(u,v) \le k$.
- $G^2, G^3$ are called square and cube of G, respectively.
- [Theorem:](./Theorems.md) If $G$ of order $n \ge 3$ is connected, then $G^2$ is 2-connected.
- 