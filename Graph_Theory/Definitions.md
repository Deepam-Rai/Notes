# ONLY SIMPLE GRAPHS
----
### Graphs
A graph G is an ordered pair of vertex nonempty set V and edge set E, denoted as G(V,E),   where  
	V is a finite non-empty set of objects.  
	E is a two element subset of V.  

This is a simple graph.
- Undirected
- No Parallel Edges
- No Loops

#### Order
Number of vertices in a graph.
#### Size
Number of edges in a graph.
#### Diameter
Max of distances between all vertex pairs in the graph.
- Undefined in disconnected graphs.

----
## **Common terms**
### Degree of vertex
The number of edges incident to the vertex
- Outdegree: The number of vertices **to** which this vertex is adjacent.
- Indegree: Number of vertices **from** which this vertex is adjacent.
- Loop contributes 2 degree to a vertex.

### Joined
If $uv\in E$ then vertices u and v are said to be joined by edge uv.

### Neighbours
Vertices $u,v\in V$ are said to be neighbours if they are joined by some edge.

### Connected vertices
If there exists a path between them.

### Adjacent vertices
Vertices $u,v\in V$ are said to be adjacent to each other if edge  $uv\in E$. 
#### In digraphs
For $a,b\in V(D)$,  "a is adjacent to b" or "b is adjacent from a" if $(a,b)\in E(G)$.

### Eccentricity of the vertex
Eccentricity of vertex $u=max\set{length(Path(u,v)) \forall v\in V(G)\ and\ u\not = v}$

### Incident
If an edge $e\in E$ pairs vertex $v\in V$ with some other vertex then e and v are said to be incident with each other.

### Adjacent edges
Edges that are incident on a common vertex are called ajacent edges.

### Parallel edges
Edges that joins same pair of vertices.

### Loop
An edge that connects a vertex to itself.
- A loop contributes two degrees(1 out and 1 in) for degree count of the vertex.

### Distance $d_G(u,v)$
The **length of** shortest path between $u$ and $v$ in G.

### Bridge
An edge $e$ is called a bridge if $k(G-e)=k(G)+1$. (k(G)=Number of components in G)  
- A bridge never lies on a cycle.

----
## **Sequences**

### Degree Sequence
The degrees of the vertices in G listed in a sequence.
#### Graphical sequence
A finite sequence of non-negative intergers is called graphical if it is a degree sequence of some graph.
- Havel-Hakimi theorem helps to verify graphical sequence.

### Vertex Sequence
### Walk
Sequence of vertices W such that consecutive vertices in the sequence are adjacent.  
It can be expressed as: $W=\set{u=v_0,v_1,v_2,...,v_k=v}$ which is a u-v walk.

#### length of a walk
Number of edges in a walk.
#### Equality
Two u-v walks are equal if as sequences they are equal term by term.
#### Trivial walk
If the length of walk is 0.
#### Closed walk
If the first and the last vertices of walk are same, then it is a closed walk.
#### Open walk
If the first and the last vertices of walk are not same, then it is an open walk.

### Trail
A walk where edges doesn't repeat.

### Path
A walk where vertices doesn't repeat.
- Distance $d_G(u,v)$ is the **length of shortest path** between them in G.
#### Geodesic
A u-v path of length $d_G(u,v)$ in G is called u-v geodesic.
- If $d(u,v)=diam(G)$ and $w\not =u\ and\ v$, then no u-w geodesic can contain v as that would imply $d(u,w)>d(u,v)=diam(G)$ which is impossible.

### Circuit
A closed trail.
- Begins and ends at the same vertex.
- In a simple graph it will have $length\geq3$


### Cycle
A circuit where no vertex repeats except the first and the last.
#### Length of a cycle
Number of edges in the cycle.
#### k-cycle
A cycle of length k.
#### Triangle
A 3-cycle.
#### Odd cycle
A cycle of odd length.
#### Even cycle
A cycle of even length.

----
## **Graph Matrices**
$n$ = Order  
$m$ = Size  
$V(G)=[v_1,v_2,v_3,..., v_n]$  
$E(G) = [e_1, e_2,...,e_m]$  
$v_iv_j=$ edge between $v_i$ and $v_j$.

### Adjacency Matrix
Matrix $A$ of dimension $n\times n$ where  
$$\large A_{ij} = \cases{
1,  v_iv_j\in E(G) \\
0,   otherwise}$$
- Dependent upon vertex labelling.
- Symmetric for undirected graphs.
- Number of 1 in i'th row and j'th col = degree of $v_i$.
### Incidence Matrix
Matrix $B$ of dimension $n\times m$ where  
$$B_{ij} = \cases{
1, \text{ if $v_i$ is incident with $e_j$}  \\
0, \text{ otherwise}}$$
- Dependent upon vertex labelling.
- Number of 1 in i'th row = $deg(v_i)$.
- Exactly two 1 in a every col, because an edge is incident with exactly 2 vertices.

----
## **Types of Graph**

### Trivial graph
A graph with order 1.

### Non-Trivial graph
A graph with order greater than 1.


### Labelled graph
A graph with vertices labelled.
- Used when we are interested with just the structure of the graph.

### Unlabelled graph
A graph with no labelling.


### Subgraph of graph G
$H(V',E')$ such that $V'\subseteq V(G)\ and\ E'\subseteq E(G)$ 
- G contains H shown as $H\subseteq G$.
- Drop some vertices or edges to get H from G or let it be as it is.

#### Proper subgraph
A subgraph $H\subseteq G$ such that either $V(H)\subset V(G)$ or $E(H)\subset E(G)$.
- Drop some vertices or edges to get H from G.

#### Clique
Clique is a complete subgraph of $G$.
- **Clique number $\omega(G)$:** Order of the largest clique in $G$.

### Spanning subgraph of G
A subgraph $H\subseteq G$ such that $V(H)=V(G)$ and $E(H)\subset E(G)$.
- Drop some edges from G to get H.
- G is a spanning subgraph of G+e, for some new edge e.

### Induced subgraph of G
A subgraph $F\in G$ such that for vertices $u,v\in V(F)$ if $uv\in E(G)$ then $uv\in E(F)$.

#### Vertex induced subgraph of G
If S is a nonempty subset of V(G), then the induced subgraph of G by S is an induced subgraph with vertex set S and is denoted as G\[S] or $\lt S\gt _G$
- For $U\subseteq V(G)$, G-U is the induced subgraph of G, induced by V(G)-U.

#### Edge induced subgraph of G
If X is a nonempty subset of E(G) then induced subgraph of G denoted as G\[X] or $<X>_G$ will have $E( G[X])=X$ and V(G\[X]) consists of all vertices of G that are incident with at least one edge in X.
-  For $X\subseteq E(G)$ G-X = spanning subgraph of G induced by E(G)-X.


### Connected graph
If every two vertices of G are connected, or G contains a u-v path for every vertices pair {u,v} of V(G).

### Disconnected graph
Which is not connected.

### Component of G
A connected subgraph of G which is not a proper subset of any another connected subgraph of G.
- Number of components of G is denoted as k(G).
- Connected graph G has k(G)=1.
- Every graph is union of its components.

### Multigraph
A graph with parallel edges.

### Di-graph
A di-graph is an ordered pair of vertex set V and edge set E, denoted by D(V,E), where  
	V = finite non-empty set of objects  
	E $\subseteq V\times V$ , an ordered two element subset.

#### Oriented Graph
Digraph with no paralled edges.

### Pseudograph
Where loops are allowed.

### Weighted Graph
Where the edges and/or vertices are assigned numbers called cost/weight.

----
## **Common Classes of Graph**

### Path $P_n$
If the vertices $v_1, v_2, v_3,...,v_n$ in graph G can be labelled or relabelled so that its edges are $v_1v_2, v_2v_3,..., v_{n-1}v_n$ then G is called a path.

### Cycle $C_n$
If the vertices of a graph with order>2 can be labelled or relabelled $v_1, v_2, v_3,..., v_n$ so that its edges are $v_1v_2, v_2v_3,..., v_{n-1}v_n, v_nv_1$, then G is called a cycle.

### Complete Graph $K_n$
Every two vertices of G are adjacent.
- Size of $K_n= (^n_2)$.
- $P_1=K_1,\ P_2=K_2,\ C_3=K_3$.

### Complement $\bar G$ of G
$\bar G$ is a graph with vertex set V(G) and edge set $E(\bar G)$ such that $uv\in E(\bar G) <=> uv\notin E(G)$.
- Let order of G be n and size be m, then size of $\bar G$ is $(^n_2)-m$.
- At least one of $G\ or\ \bar G$ must be connected.

### Empty Graph $\bar K_n$
A graph of order n with no edge.

### K-Regular graphs
All vertices have degree k.
- $\delta (G)= \Delta (G) = K$
- There can be no odd-regular graph with odd vertices.
#### 3-Regular graph
Also known as cubic graph.
#### Peterson Graph
3-Regular graph with 10 vertices.
#### $H_{r,n}$ Harary Graphs
r-regular graph with n vertices such that:
- we can arrange the nodes in a circle such that
	- for even n: each node is joined to $\frac{r}{2}$ nodes on each side.
	- for odd n: each node joined to $\frac{r-1}{2}$ on each side and to the node opposite to it.

### Irregular Graphs
With minimum order 2, and every distinct vertices having distinct degrees.
- No non-trivial graph is irregular. (see The Party Theorem)

### K-Partite Graph
If V(G) can be divided into k partites $V_1,V_2,...,V_k$ such that if $uv\in E(G)=>u,v$ belongs to different partites.

#### Bipartite Graph
If V(G) can be represented as the union of two vertex sets $V_1(G), V_2(G)$ called partite sets such that,  
$V(G) = V_1(G)\cup V_2(G)$, and  
$x,y\in V_i(G) \Leftrightarrow xy\notin E(G)$ for i=1,2.

#### Complete k-partite Graph $K_{n_1,n_2,...,n_k}$
If every two vertex in different partites are joined by an edge.  

### Star graph
If order of either U or V is 1.

### Isomorphic Graphs $G\cong H$
Labelled graphs $G\cong H$ iff $\exists$ one-to-one correspondence $\phi$ from V(G) to V(H) such that  $uv\in E(G) \iff \phi(u)\phi(v)\in E(H)$.
- Their complements are also isomorphic: $\bar G\cong \bar H$.
- G is called **self-isomorphic** if $G\cong \bar G$.
	- Size = $\frac{1}{2}(^n_2)=\frac{n(n-1)}{4} \implies 4|n\ or\ 4|(n-1)$.
- It is an equivalence relation on set of all graphs - creates equivalence classes.

### Planar graphs
If G can be drawn in a planse so that no two of it's edges cross each other.
- Nonplanar: Graph that is not planar.
- Plane graph: Graph that is drawn so that no two edges of it cross each other.
- Every cycle, path, star,tree are planar.
- **Regions**: The areas of the plane divided by the edges of the planar graphs.
	- Exterior region: The unbounded region that exists in every plane graph.
	- **Boundary of region:** The subgraph of plane graph whose vertices and edges are incident with the given region.
		- A boundary need not divide the region. Example a bridge of plane graph is boundary for exterior region.
		- A bridge is always on the boundary of exactly one region(not necessarily exterior region).
		- An edge that is not a bridge lies on the boundary of two regions.
	- Planar graph G can be drawn in many ways, but the region count doesnt change.
- **[Eular Identity](./Theorems.md):** If G is a connected plane graph of order n, size m and having r regions, then n-m+r=2.
- When $m\ge 3$, then boundary of every region has at least 3 edges. $2m \ge 3r$.
- $m \le 3n-6$ for $n \ge 3$.
- Every planar graph contains a vertex of degree 5 or less.
- $K_5$ is nonplanar.
- $K_{3,3}$ is nonplanar.

#### Embeddings
A graph drawn on a surface such that no two edges cross each other.
- Non-planar graphs cannot be embedded on a plane.
- **Surface of genus k $S_k$:** A sphere with $k$ handles.
	- $S_0$: Sphere
	- $S_1$: Torus
- **Genus of $G$, $\gamma(G)$:** Smallest $k$ such that $G$ can be embedded on $S_k$.
	- $\gamma(G) \ge \large \frac{m}{6}-\frac{n}{2}+1$, general form for $m \le 3n-6$.
	- $\gamma(K_n) = \Large \ceil{ \frac{(n-1)(n-4)}{12}}$, for $n\ge 3$.
- **2-cell:** A region where any closed curve that is drawn on that region can be  continuously shrunk to a point.
	- **2-cell embedding:** An embedding, every region of which is a 2-cell.
		- $n-m+r=2 -2k$, $k=$genus.
		- $n-m+r = 2-2\gamma(G)$

### Subdivision
A graph $G'$ is called subdivision of graph $G$ if $G'=G$ or one or more vertices of degree 2 is inserted into one or more edges of $G$ to get $G'$.
- **[Kuratowski Theorem](./Theorems.md):** A graph $G$ is planar iff $G$ does not contain subdivision of $K_5$ or $K_{3,3}$ as subgraph.


----
## Trees
Acyclic connected graphs.  
- Every edge is a bridge.
- Every two vertices are connected by a unique path.
- Every non-trivial tree has at least two end-vertices.

### Terms
1. Root: The node from which all other nodes appears to be descendant of in a particular way of drawing the tree.
	- Any node can be chosen as root.
	- Its just the way we draw.
1. Leaves/End vertices: Vertices with degree 1.

### Spanning Tree
A spanning subgraph which is a tree.
- There can be multiple for a graph.
#### Minimal Spanning Tree
Spanning tree with minimum weight among all spanning tree.
- The sum of all edge weights added is minimum possible.
- Algorithms to find MST:
	- [Kruskal's algorithm](./Algorithms#Kruskal's-Algorithm)
		- Adding edges in increasing weights order, so that cycle is not formed, until connectivity established.
	- [Prim's Algorithm](./Algorithms#Prim's-Algorithm)
		- Including single arbitrary vertex first,then adding new vertices incident to outgoing edges from set of included vertices until all vertices are taken. 

### Other Special Trees
1. Trivial Tree
	- Tree with order 1.
2. Rooted tree
	- Tree that has root.
	- Every tree has root. :)
3. Double Star
	- Contains exactly two vertices that are not end-vertices and adjacent.
4. Caterpillar
	- Removing its end-vertices results in a path - called **spine.**
	- Every Path, Star(order>2), Double star is a caterpillar.
 

## Forest
Acyclic graphs.
- Consequently components of forest are trees - forest is collection of trees.
- Forest can be disconnected.

----
## Points
- V and E are also represented as V(G) and E(G) respectively.
- $V\not=\phi$  => Order of every graphs is at least 1.
- Graphs G and H are equal if $V(G)=V(H) and E(G)=E(H).
- Word graph of the Set of Words: is a graph model G whose vertices are the words and two words are adjacent if they can be transformed into each other by any of following rules:
	1.  Interchanging two letters.
	2. Replacing a letter by another letter.
-  $paths\subseteq trail \subseteq walk$.
-  $cycle\subseteq circuit\subseteq trail \subseteq walk$.
- The vertices and edges of trail, path, circuit or cycle in G forms a subgraph.
- Let $d_G(u,v)$ = $\{u=v_0,v_1,...,v_k=v\}$ be shortest path between u and v, then for $0\le i\le j \le k$, subsequence $v_i$ to $v_j$ is shortest path between $v_i$ and $v_j$.

