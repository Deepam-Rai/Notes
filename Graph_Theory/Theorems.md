----
> **Theorem 2.1 (The First Theorem of Graph Theory)  
> If G is a graph of size $m$ then,**  
> $$\large \sum_{v\in V(G)}{deg(v_i)}=2m$$

**Proof:**
Since, each edge is incident on two vertices.  
each edge adds 2 to sum of degrees.  
$\therefore$ For $m$ edges we have sum of degrees = $2m$
$$[Proved!]$$



> **Corollary 2.3
> Every graph has an even number of odd vertices.**

**Proof:**
Let, $V(G)=V(G_1)\cup V(G_2)$, where  
$G_1$= set of even vertices  and let $\sum_{v\in V(G_1)}{deg(v_i)}=2l$  
$G_2$= set of odd vertices.  

$$\large \therefore \sum_{v\in V(G_1)}{deg(v_i)} + \sum_{v\in V(G_2)}{ deg(v_i)}= \sum_{v\in V(G)}{deg(v_i)}$$

$$\large 2l + \sum_{v\in V(G_2)}{deg(v_i)} = 2m$$

$$\large \sum_{v\in V(G_2)}{deg(v_i)} = 2(m-l) = even\ number$$

$$\implies \text{Sum of degrees in $G_2$ should be an even number}$$

$$Since, \text{every vertex in $G_2$ has odd degree}$$

$$\implies \text{There should be even number of vertex in $G_2$}$$

$$\text{[Since for only even count of odd numbers,the sum is even.]}$$

$$[Proved!]$$

----
> **Theorem 2.4
> Let G be a graph of order $n$. If  
> $$\large deg(u)+deg(v)\ge n-1$$
> for every two nonadjacent vertices  $u$ and $v$ of G. Then G is connected and $diam(G)\lt2$.**

**Proof:**  
**Claim-I:** G is connected.  
	Case-I: If $u$ and $v$ are adjacent then its anyway connected.  
	Case-II: If $u$ and $v$ are not adjacent then:  
		$deg(u)+deg(v)\ge n-1 \implies$ $u$ and $v$ has at-least one common vertex,  
		because G is a simple graph(no parallel edges).
$\therefore$ G is connceted.  

**Claim-II:** $diam(G)<2$  
$\because$ Every non-adjacent vertices have a common neighbouring vertex.  
$\implies$ Max distance between any two vertices = 2.  
$\therefore diam(G)=2$
$$[Proved!]$$

> **Corollary 2.5
> If G is graph of order $n$ with $\delta(G)\ge\frac{n-1}{2}$ then G is connected.**

**Proof:**  
For any two given vertices $u$ and $v$,  
$$deg(u)+deg(v)= \frac{n-1}{2} + \frac{n-1}{2} =  n-1$$
$\therefore$ By Theorem G is connected.  
$$[Proved!]$$

----
> **Theorem 2.6:
> Let $r$ and $n$ be integers with $0\le r \le n-1$. There exists an r-regular graph of order $n$ iff one of $r$ or $n$ is even.**

**Proof:**  
**Claim-I:** If there exists r-regular graph of order n then at least one of $r$ or $n$ is even.  
Proof by contradiction: Suppose both $r$ and $n$ are odd.  
Then, it would contradict The First Theorem of Graph Theory.  
Thus at least one of them need to be even.  

**Claim-II:** If at least one of $r$ or $n$ is even then there exists a r-regular graph of order $n$.
Proof by Construction:   
We construct $H_{r,n}$ r-regular Harary graph with $V(H_{r,n})=\{v_1,v_2,...,v_n\}$  
Case-I: $r$ is even.  
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
> **Theorem 2.7
> For every graph $G$ with $r \ge \Delta(G), \exists$ r-regular graph $H$ containing $G$ as an induced subgraph.**  

**Proof by Construction:**  (Konig's construction)  
Let $\large V(G)=\{v_1, v_2,...,v_n\}$  
Create $G's$ shadow graph $G'$ whose each vertex $v_i'$ corresponds to $v_i$ in $G$.  
For every $v_i$ with degree $\lt r$  
it's counterpart $v_i'$ also has degree $\lt r$.  
Add edge $v_iv_i'$ .  

Now, if there still exists vertices with degree < $r$.  
 Again create a shadow copy of the whole graph and add edges as in previous step.  

Repeat this until all vertices have degree $r$.  

Thus doing so for every graph gives us graph $H$ whose all vertices have degree $r$.  
And $G$ is induced subgraph of r-regular graph $H$.  
$$[Proved!]$$

----
>**Theorem 2.10 (Havel-Hakimi Theorem)  
> A non-decreasing sequence $\large s: d_1, d_2, d_3,...,d_n$ of non-negative integers is graphical iff $\large s_1: d_2-1,d_3-1,...,d_{d_1+1}-1, d_{d_1+2},...,d_n$ is graphical.**

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
Then $G-v_1$ has degree sequence $s_1$, thus $s_1$ is graphical.

Case-II: If $v_1$ is not adjacent to one of these $\large v_2, v_3,...,v_{d_1+1}$   
$\implies v_1$ is adjacent to say $\large v_s, s>d_1+1$ and say $v_1$ is not adjacent to $\large v_r, r\le d_1+1$.  
Now, $\large \because deg(v_r)>deg(v_s) \implies \exists v_t$ such that $v_r$ is adjacent to $v_t$ but $v_s$ is not adjacent to $v_t$.  
$\therefore$ The confirmed edges we are having are: $\large v_1v_s, v_rv_t$  
Now, remove $\large v_1v_s, v_rv_t$ and add edges $\large v_1v_r, v_sv_t$.  
The resultant graph $G_1$ still remains graphical.  
Following same manner we can make $v_1$ adjacent to $v_i, i\le 2 \le d_1+1$ in graph $G_1$.  
$\therefore G_1$ will have degree sequence $s_1$.
$\implies s_1$ is graphical.

$$[Proved!]$$

----
> **Theorem 3.1**
> $$G\cong H \iff \bar G \cong \bar H$$

**Proof:**   
$\exists \phi:V(G) \to V(H)$  
**Claim-I:** $G\cong H \implies \bar G \cong \bar H$  
Let, $u,v \in V(G)$, then  
$uv \in E(G) \iff \phi(u)\phi(v) \in E(H)$  and $uv \notin E(G) \iff \phi(u)\phi(v) \notin E(H)$  
$\therefore uv \notin E(\bar G) \iff \phi(u)\phi(v) \notin E(\bar H)$  and $uv \in E(\bar G) \iff \phi(u)\phi(\bar v) \in E(\bar H)$  
$\implies \phi: V(\bar G) \to V(\bar H)$  
$\implies \bar G \cong \bar H$  

**Claim-II:** $\bar G\cong \bar H \implies G \cong H$  
Similar to case-I.  
$$[Proved!]$$

----
> **Theorem 3.2
> $G \cong H \implies$ degrees of the vertices of G are the same as the degrees of the vertices of H.**

**Proof:**  
Let, $u \in V(G)$ and $v=\phi(u) \in V(H)$  
If $u$ is adjacent to $x_1, x_2,...,x_k$ and not adjacent to $w_1, w_2,...,w_l$ such that $|V(G)|=k+l+1$.  
$\implies deg(u)=k$  
$\therefore v$ is adjacent to $\phi(x_1), \phi(x_2),...,\phi(x_k)$ and not adjacent to $\phi(w_1), \phi(w_2),...,\phi(w_l)$ such that $|V(H)|=k+l+1$.   
$\implies deg(v)=k$  
$\therefore deg(u)=deg(v)$  
$$[Proved!]$$

----
> **Theorem 3.5  
>  Let $G \cong H$, then  
> (a) G is bipartite $\iff$ H is bipartite  
> (b) G is connected $\iff$ H is connected.**


**Proves:**  
Let $\phi:V(G) \to V(H)$  

(a)
**Proof:**  
Claim-I: $G$ is bipartite $\implies$ $H$ is bipartite.  
$\because G$ is bipartite let $V(G)=V_1(G)\cup V_2(G)$, such that  
$V_1(G) \cap V_2(G) = \emptyset$  

First we show that there is corresponding vertex partition for $H$ too.  
Let, $W_1(H) = \{\phi(u) \ such\ that\ u \in V_1(G)\}$  
$W_2(H) = \{\phi(v) \ such\ that\ v \in V_2(G)\}$  
Now, for any $a \in W(H) \exists u \in V(G)$ such that $u \in V_1(G) \ or \ V_2(G)$ but not both.  
$\implies a \in W_1(H) \ or \ W_2(H)$ but not both.  
$\implies W_1(H) \cup W_2(H) = W(H)$ and $W_1(H) \cap W_2(H) = \emptyset$  

Now we show that any edge in E(H) joins vertices between these two vertex partitions only, and not within a partition.  
Let, $ab = e \in E(H)$ where $a,b\in W(H)$  
Now, $\exists u,v \in V(G)$ such that $a=\phi(u)$ and $b=\phi(v)$.  
$\because G$ is bipartite $u$ and $v$ belongs to different partite $V_1(G)$ and $V_2(G)$.  
$\implies \phi(u),\phi(v)=a,b$ also belongs to different vertex sets $W_1(H)$ and $W_2(H)$.  
$\implies e$ always joins vertices of two different vertex sets $W_1(H)$ and $W_2(H)$.  
$\implies H$ is also bipartite.

Claim-II: If $H$ is bipartite, then $G$ is bipartite.
$\because \phi^{-1}$ exists, as $\phi$ is a bijective function.  
Proof similar to claim-I follows.  
$$[Proved!]$$

(b)
**Proof:**  
Let, $u,v \in V(G)$  
If $u-v$ path exists in $G$, then $\phi(u)-\phi(v)$ path exists in $H$.  
$\implies$ If all vertices in $G$ are connected by a path, then corresponding vertices in $H$ are also connected.  
$\implies$ If G is connected H is also connected.

Now, $\exists \phi^{-1}: V(H) \to V(G)$, since  $\phi$ is a bijective function.  
Similaryly, we can show that  
If $H$ is connected, then $G$ is also connected.  
$$[Proved!]$$

----
> **Theorem 3.6:  
> Isomorphism is an equivalence relation on the set of all graphs.**

**Proof:**  
**Reflexive:**  
Let, $\phi$ be an identity function , $\phi: V(G) \to V(G)$  
$\therefore uv \in E(G) \iff \phi(u)\phi(v) \in E(G)$  
$\therefore G \cong G$  
$\phi$ an isomorphism is reflexive.  

**Symmetric:**  
Let, $\phi: V(G_1) \to V(G_2)$  
$\because \phi$ is bijective.  
$\exists \phi^{-1}:V(G_2) \to V(G_1)$  such that  
$uv \in V(G_2) \implies \phi^{-1}(u)\phi^{-1}(v) \in V(G_1)$  
and $uv \notin V(G_2) \implies \phi^{-1}(u)\phi^{-1}(v) \notin V(G_1)$  
$\therefore uv \in V(G_2) \iff \phi^{-1}(u)\phi^{-1}(v) \in V(G_1)$  
Thus $\phi^{-1}$ is an isomorphism: $V(G_2) \to V(G_1)$  
$\therefore G_1 \cong G_2 \implies G_2 \cong G_1$  
$\therefore$ Isomorphism is symmetric.  

**Transitive:**  
Let,  
$\alpha: V(G_1) \to V(G_2) \implies G_1 \cong G_2$  
$\beta: V(G_2) \to V(G_3) \implies G_2 \cong G_3$  
Now,  
$uv \in E(G_1) \iff \alpha(u)\alpha(v) \in E(G_2)$  
and $\alpha(u)\alpha(v) \in E(G_2) \iff \beta(\alpha(u))\beta(\alpha(v)) \in E(G_2)$  
or $\alpha(u)\alpha(v) \in E(G_2) \iff (\beta \circ \alpha)(u)(\beta\circ\alpha)(v) \in E(G_2)$  
But $\because \alpha \ and \ \beta$ are bijective $\implies (\beta \circ \alpha)$ is also bijective.  
$\therefore uv \in E(G_1) \iff (\beta \circ \alpha)(u)(\beta\circ\alpha)(v) \in E(G_2)$  
$\therefore G_1 \cong G_2$  
$\therefore$ isomorphism is transitive.  
$$\therefore \text{Isomorphism is an equivalence relation}.$$

$$[Proved!]$$

----
> **Theorem 4.1:
> An edge $e$ of graph $G$ is a bridge iff $e$ lies on no cycle of G.**

**Proof:**  
**Claim-I:** If $e$ is a bridge, then $e$ lies on no cycle of G.  
Proof by contradiction: Let $e$ be a bridge that lies on cycle of G.  
Let, $e=uv$, thus $e$ joins vertices $u,v \in V(G)$  
We show that $G-e$ is still connected.  
$\because uv$ lies in a cycle $\implies in\ G-e, \exists u-v$ path say $P$.
Take $x,y \in V(G)$.  
Case-I: $e$ didnt lie in $x-y$ path in $G$.  
$\implies$ $e$ doesnt lie in $x-y$ path in $G-e \implies x,y$ is still connected in $G-e$.  
Case-II: $e$ lie in $x-y$ path in $G$.  
In $G-e$ take walk $W(x,y)=Path(x,u) + P + Path(v,y)$.  
$\because$ Walk $W(x,y)$ exists in $G-e \implies Path(x,y)$ exists in $G-e$.  
$\therefore x,y$ is still connected.  

$\therefore G-e$ is connected $\implies e$ is not a bridge (by definition).  
$\therefore$ If $e$ is a bridge, then it wont lie on any cycle of $G$.  

**Claim-II:** If $e$ lies on no cycle of $G$, then $e$ is a bridge.  
Proof by contrapositive( $(p \implies q) \cong (\neg q \implies \neg p)$ ): If $e$ is not a bridge, then $e$ lies on cycle of $G$.   
Let, $e = uv \in E(G)$.  
$\because e$ is not a bridge.   
$\implies G-e$ contains a $Path(u,v)$.  
$\implies G$ also contains $Path(u,v)$ that is distinct from $e$.  
Now, joining $Path(u,v)$ and $e$ will form a cycle containing $e$.  
$\therefore e$ lies in a cycle in G.  

Thus, combining claim-I and claim-II,  
$$[Proved!]$$

----

