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

$$\large \therefore \sum_{v\in V(G_1)}{deg(v_i)} + \sum_{v\in V(G_2)}{ deg(v_i)}=\sum_{v\in V(G)}{deg(v_i)}$$
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
