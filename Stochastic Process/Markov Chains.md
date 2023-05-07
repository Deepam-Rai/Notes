> **State space:** Finite or countably infinite set of space that a system can be in.

Let system be observed at discrete moments of time $n=0,1,2,...$ and $X_n$ denote the state of the system at time $n$.  

$X_n$ is a random variable, as we talk about non-deterministic systems.  

> **Markov property:** Given a present state, past states have no influence on the future.  

$$\large P(X_{n+1} = x_{n+1} | X_0=x_0,...,X_n=x_n) = P(X_{n+1}=x_{n+1} | X_n=x_n)$$

- It doesn't matter what were my previous state, only current state influence immediate next future state.
- Similarly my current state was determined by just immediate previous state.
- Suppose we can come to state $a$ in 3 ways and $a$ can lead to state $b$ or $c$. Now irrespective of which way(out of 3) we came to $a$, $a$ will lead to $b$ or $c$ with the same constant probability.

> **Transition probabilities:** The conditional probabilities that denote the transition from one state to next.  
> $P(X_{n+1}=y | X_n=x)$

> **Stationary transition probability**: Transition probabilities independent of $n$.

#TODO clarity.


> **Transition function $P(x,y)$:** $P(x,y)=P(X_1=y | X_0=x)$ for $x,y \in$ State Space.  
> Also known as *one-step transition probabilities* as no matter how system got to state $x$ it will go to state $y$ with probability $P(x,y)$.

Properties:
1. $P(x,y) \ge 0,$ for  $x,y \in$ State Space.
2. $\sum_{y}P(x,y)=1,$ for  $x\in$ State Space.
Since Markov chains has stationary probabilities: $P(X_{n+1}=y|X_n=x)=P(x,y)$  

