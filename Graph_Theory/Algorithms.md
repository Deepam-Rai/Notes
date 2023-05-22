----
## Kruskal's Algorithm
Finds Minimum Spanning Tree in a weighted connected graph.  
[Proof](./Theorems.md)

1. $G \gets$ weighted connected graph.
2. $n=$ order of $G$.
3. $S \gets$ a graph with $V(S)= V(G), E(S)=\emptyset$.
4. $L=\{\text{sequence of edges of G in non-decreasing weight order}\}$.
5. While $(|S_E| \lt n-1)$
	1. $e \gets$ edge with minimum weight from $L$ such that if $E(S) \gets E(S) \cup \set{e}$ no cycle is formed in $S$.
	2. $E(S) \gets E(S) \cup \set{e}$
	3. $L \gets L-\set{e}$
	4. Repeat.
6. $S$ is a MST of $G$.


----
## Prim's Algorithm
Finds Minimum Spanning Tree in a weighted connected graph.
[Proof](./Theorems.md)

1. $G \gets$ weighted connected graph.
2. $n \gets$ order of $G$.
3. $S \gets$ a graph such that $V(S)=\emptyset, E(S)=\emptyset$.
4. $V(S)={v} \text{ for arbitrary } v \in V(G)$.
5. While $(V(S) \not = V(G))$
	1. $L \gets \set{uv \in E(G) \text{ such that }u,v \in V(G); u \in V(S); v \notin V(S)}$, all outgoing edges from $V(S)$.
	2. $E(S)\gets E(S)\cup \set{uv}$ for $uv \in E(G); u \in V(S); v \notin V(S)$ is edge with minimum weight in $L$ such that  no cycle is formed in $S$.
	3. $V(S) \gets V(S) \cup \set{v}$
	4. Repeat.
6. $S$ is MST for $G$.

----