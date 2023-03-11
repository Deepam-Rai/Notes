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
