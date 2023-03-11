----
# The First Theorem of Graph Theory
> Theorem 2.1
> If G is a graph of size $m$ then,  
> $$\large \sum_{v\in V(G)}{deg(v_i)}=2m$$

**Proof:**
Since, each edge is incident on two vertices.  
each edge adds 2 to sum of degrees.  
$\therefore$ For $m$ edges we have sum of degrees = $2m$
\[Proved!\]



> Corollary 2.3
> Every graph has an even number of odd vertices.

**Proof:**
Let, $V(G)=V(G_1)\cup V(G_2)$, where  
$G_1$= set of even vertices  and let $\sum_{v\in V(G_1)}{deg(v_i)}=2l$  
$G_2$= set of odd vertices.  

$$\large \therefore \sum_{v\in V(G_1)}{deg(v_i)} + \sum_{v\in V(G_2)}{ deg(v_i)}= \sum_{v\in V(G)}{deg(v_i)}$$

$$\large \sum_{v\in V(G_1)}{deg(v_i)} + 2l = 2m$$

$$\large \sum_{v\in V(G_1)}{deg(v_i)} = 2(m-l) = even\ number$$

$$\implies \text{Sum of degrees in $G_2$ should be an even number}$$

$$Since, \text{every vertex in $G_2$ has odd degree}$$

$$\implies \text{There should be even number of vertex in $G_2$}$$

$$\text{[Since for only even count of odd numbers,the sum is even.]}$$

$$[Proved!]$$

----
> Theorem 2.4
> Let G be a graph of order $n$. If  
> $$deg(u)+deg(v)\ge n-1$$
> for **every** two **nonadjacent** vertices  $u$ and $v$ of G. Then G is connected and $diam(G)\lt2$.

**Proof:**  
Claim-I: G is connected.  
	Case-I: If $u$ and $v$ are adjacent then its anyway connected.  
	Case-II: If $u$ and $v$ are not adjacent then:  
		$deg(u)+deg(v)\ge n-1 \implies$ $u$ and $v$ has at-least one common vertex,  
		because G is a simple graph(no parallel edges).
$\therefore$ G is connceted.  

Claim-II: $diam(G)<2$  
$\because$ Every non-adjacent vertices have a common neighbouring vertex.  
$\implies$ Max distance between any two vertices = 2.  
$\therefore diam(G)=2$
$$[Proved!]$$

> Corollary 2.5
> If G is graph of order $n$ with $\delta(G)\ge\frac{n-1}{2}$ then G is connected.

**Proof:**  
For any two given vertices $u$ and $v$,  
$$deg(u)+deg(v)= \frac{n-1}{2} + \frac{n-1}{2} =  n-1$$
$\therefore$ By Theorem G is connected.  
$$[Proved!]$$

----
> Theorem 2.6:
> Let $r$ and $n$ be integers with $0\le r \le n-1$. There exists an r-regular graph of order $n$ iff one or $r$ or $n$ is even.

**Proof:**  
Claim-I: If there exists r-regular graph of order n then at least one of $r$ or $n$ is even.  
Proof by contradiction: Suppose both $r$ and $n$ are odd.  
Then, it would contradict The First Theorem of Graph Theory.  
Thus at least one of them need to be even.  

Claim-II: If at least one of $r$ or $n$ is even then there exists a r-regular graph of order $n$.
Proof by Construction:   
We construct $H_{r,n}$ r-regular Harary graph with $V(H_{r,n})=\{v_1,v_2,...,v_n\}$  
Case-I: $r$ is odd.  
Let $r=2k$.  
$\forall 1\le i\le n$ connect $v_i$ to $v_{i-k},...,v_{i-2},v_{i-1},v_{i+1},v_{i+2},...,v_{i+k}$  
Thus constructed graph is r-regular with order $n$.  

Case-II: $r$ is odd.  
Let $r=2k+1$.  
Follow case-I procedure to get (r-1)-regular graph.  
$\because\ r$ is odd $\implies\ n$ is even $\implies$ we can find opposite vertex for every vertex.  
Now join every $v_i$ with its opposite vertex $\large v_{(i+\frac{n}{2})mod(n)}$.  
Thus we get r-regular graph.

$$[Proved!]$$

----
> Theorem 2.7
> For every graph $G$ with $r \ge \Delta(G), \exists$ r-regular graph $H$ containing $G$ as an **induced** subgraph.  

**Proof by Construction:**  
Let $\large V(G)=\{v_1, v_2,...,v_n\}$  
Create $G's$ shadow graph $G'$ whose each vertex $v_i'$ corresponds to $v_i$ in $G$.  
Now for every $v_i$ with degree $\lt r$  
it's counterpart $v_i'$ also has degree $\lt r$.  
Add edge $v_iv_i'$ till both of their degree = r.  

Thus doing so for every graph gives us graph $H$ whose all vertices have degree $r$.  
And $G$ is induced subgraph of r-regular graph $H$.  
$$[Proved!]$$
>The graph formed need not be a simple graph.

----
> Theorem 2.10
> A non-decreasing sequence $\large s: d_1, d_2, d_3,...,d_n$ of non-negative integers is graphical iff $\large s_1: d_2-1,d_3-1,...,d_{d_1+1}-1, d_{d_1+2},...,d_n$ is graphical.

**Proof:**  
**Claim-I:** If $s1$ is graphical then $s$ is graphical.  
Let, graph $G_1$ correspond to $s_1$.  
Let, $V(G)=\{v_2,v_3,...,v_n\}$ such that  
$$\large deg(v_i) = \cases{d_i-1,  \ 2\le i\le d_1+1 \\ d_i, \ d_1+2\le i \le n}$$

Now construct graph $G$ by  adding a vertex $v$ to $G_1$ and edges $\large (vv_i) \forall 2\le i \le d_1+1$.
$\implies deg(v)=d_1$  
And $s$ is degree sequence of $G$.  
$\implies s$ is graphical.

**Claim-II:** If $s$ is graphical then $s_1$ is graphical.  
Let $G$ be graph with degree sequence $s$.  
Let, $V(G)=\{v_1, v_2,...,v_n\}$.  
Case-I: If $v_1$ is adjacent to $\large v_2, v_3,...,v_{d_1+1}$  
Then $H-v$ has degree sequence $s_1$, thus $s_1$ is graphical.

Case-II: If $v_1$ is not adjacent to one of these $\large v_2, v_3,...,v_{d_1+1}$   
$\implies v_1$ is adjacent to say $\large v_s, s>d_1+1$ and say $v_1$ is not adjacent to $\large v_r, r\le d_1+1$.  
Now, $\large \because deg(v_r)>deg(v_s) \implies \exists v_t$ such that $v_r$ is adjacent to $v_t$ but $v_s$ is not adjacent to $v_t$.  
$\therefore$ The edges we are having confirmed are: $\large v_1v_s, v_rv_t$  
Now, remove $\large v_1v_s, v_r,v_t$ and add edges $\large v_1v_r, v_sv_t$.  
The resultant graph $G_1$ still remains graphable.  
Following same manner we can make $v_1$ adjacent to $v_i, i\le 2 \le d_1+1$ in graph $G_1$.  
$\therefore G_1$ will have degree sequence $s_1$.
$\implies s-1$ is graphical.

$$[Proved!]$$

