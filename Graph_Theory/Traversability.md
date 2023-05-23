
# Eulerian graphs

> **Eulerian trail:** A trail that contains all edges of the graph.

>**Eulerian circuit:** A circuit that contains all edges of the graph.

>**Eulerian graph:** A graph that contains eulerian circuit.
- [Theorem:](./Theorems.md) A connected graph G is Eulerian iff every vertex has even degree.
- $G$ conatins Eulerian circuit iff every vertex has even degrees.
- if exactly two vertices has odd degree then it has Eulerian trail.
- $P_n$ for $n\ge 2$ contains Eulerian trail.
- $C_n$ for $n \ge 3$ contains Eulerian circuit.
- $K_n$ for $n\ge 3$ is Eulerian iff $n$ is odd.
- $K_{s,t}$ is Eulerian iff both $s,t$ are even.

# Hamiltonian Graphs

>**Hamiltonian path:** A path that contains every vertex of $G$.

>**Hamiltonian cycle:** A cycle that contains every vertex of $G$.
- It's a spanning cycle.

>**Hamiltonian graph:** Graph that contains Hamiltonian cycle.
- Peterson's graph is not Hamiltonian.
- If $G$ contains a cut-vertex, then its not Hamiltonian.
- $G$ is Hamiltonian if sum of degrees of every non-adjacent pair is greater than it's order.

>**Closure $C(G)$:** of a graph $G$ is obtained by joining non-adjacent vertices of $G$ whose degree sum is at least $n$ in that stage, until no such pair remains.
- A graph is hamiltonian iff it's closure is Hamiltonian

