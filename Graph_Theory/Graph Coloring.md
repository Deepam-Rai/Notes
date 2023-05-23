>**Dual of a map:**  A graph constructed with regions of the map as the vertices that are joined by an edge if corresponding regions are neighbouring region.  

>**Proper graph coloring:** Assigning a color to each vertex of the graph such that no two adjacent vertices get the same color.

> **k-colorable:** graph that can be colored using k colors.

>**Chromatic number $\chi(G)$:** Smallest number of colors needed to color a graph.
- **k chromatic:** $\chi(G)=k$.
- **Minimum coloring:** Every $\chi(G)$ coloring of $G$.
- $\chi(G)=1$ iff $G=\bar K_n$ for $n \ge 1$.
- $\chi(K_n)=n$
- $\chi(H) \le \chi(G)$ where $H$ is subgraph of $G$.

>**The Four Color Theorem:  
>The chromatic number of every planar graph is at most 4.**

> **Independent Set:** Set $S \subset V(G)$ such that no two vertices $\in S$ are adjacent.
- **Maximum independent set:** Independent set of max cardinality.
	- **Independence number $\alpha(G)$:** Cardinality of maximum independent set.
		- $\alpha(G)=k$ iff $\omega(\bar G)=k$, where $\omega()$ is [clique number](./Definitions.md).
- **Color classes:** $k$ independent sets $V_1,V_2,...,V_k$ of $G$ where $k=\chi(G)$ such that all elements of a set has same color and each set is assigned different color.

> **Theorem 10.2:  
> A graph $G$ has $\chi(G)=2$ iff $G$ is a nonempty bipartite set.**

- If $G$ contains odd-cycle $\chi(G)\ge 3$.
- If $G$ contains even-cycle $\chi(G)\ge 2$.
- $\chi(G) \ge \omega(G) \text{ and } \chi(G) \ge \frac{n}{\alpha(G)}$
- 

