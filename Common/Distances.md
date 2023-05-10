# Distances

Let $\tau$, called space, be a set of points. Then the distance measure for two points $x$ and $y$ on this space is a function that taking these two points as arguments results in a real number output.

----
## Axioms of Distance Measure
1. Non-negativity: $d(x,y)\ge0$, no negative distance.
1. $d(x,y)=0$, if and only if $x=y$.
1. Symmetry: $d(x,y)=d(y,x)$
1. The triangle inequality: $d(x,y)\le d(x,z) + d(z,y)$

----
## $L_r$-norm
For points $\large x=[x_1,x_2,...,x_n]^T$ and $\large y=[y_1,y_2,...,y_n]^T$ in Euclidean space $R^n$, $L_r$-Norm is defined as:  

$$\large L_r -norm = (\sum_{i=1}^n|x_i-y_i|^r)^{1/r}$$

----
## Manhattan Distance / $L_1$-norm
For points $\large x=[x_1,x_2,...,x_n]^T$ and $\large y=[y_1,y_2,...,y_n]^T$ in Euclidean space $R^n$, $L_1$-Norm or Manhattan distance is defined as:  

$$\large L_1 -norm = \sum_{i=1}^n|x_i-y_i|$$

- If the space be divided into blocks and we were allowed to travel only the sides, then this distance would be exact distance for travelling from $x$ to $y$ or vice-versa.
- The layout of Manhattan city inspired the name.

----
## Euclidean Distance / $L_2$-Norm
In $\mathbb{R}^n$, Euclidean distance is defined as:  

$$\begin{aligned} d(x,y) &= \large(\sum_{i=1}^n|x_i-y_i|^2)^{1/2} \\
&= \sqrt{\sum_{i=1}^n{(x_i -y_i)^2}}
\end{aligned}$$

where $\large x=[x_1,x_2,...,x_n]^T$ and $\large y=[y_1,y_2,...,y_n]^T$.

#### Distance Axioms Proofs:
1. Non-negative distance
> Since, $(x_i-y_i)^2\ge0$  
> $\therefore d(x,y) = \sqrt{\sum_{i=1}^n{(x_i -y_i)^2}}\ge0$
2. Zero for same point else greater than 0.
> Case-I: When $x=y$,
>> $ d(x,x) = \sqrt{\sum_{i=1}^n{(x_i -x_i)^2}}=0$
>
> Case-II: When $x\not= y$  
>> Since, $(x_i-y_i)^2>0$  
> $\therefore d(x,y) = \sqrt{\sum_{i=1}^n{(x_i -y_i)^2}}>0$
3. Symmetric
>$\large d(x,y)= \sqrt{\sum_{i=1}^n{(x_i -y_i)^2}} = \sqrt{\sum_{i=1}^n{(y_i -x_i)^2}} = d(y,x)[Proved!]$  
4. #TODO:Triangle Law of Inequality


----
## $L_{\infty}$-norm
For points $\large x=[x_1,x_2,...,x_n]^T$ and $\large y=[y_1,y_2,...,y_n]^T$ in Euclidean space $R^n$, $L_{\infty}$-norm is defined as:  

$$\large L_{\infty}(x,y)=max(|x_i-y_i|) for\ 1\le i<n$$

- Assumption: As $r$ gets large enough only the dimension with the largest difference matters.

#### Distance Axioms Proofs:
1. Non-negative
> $Since, (|x_i-y_i|)\ge0, \therefore L_{\infty}(x,y)=max(|x_i-y_i|)\ge0$
2. Zero for same point else greater than 0.
> Case-I: When $x=y$
>> $L_{\infty}(x,y)=max(|x_i-x_i|)=0$
>
> Case-II: When $x\not=y$,
>>  $Since, (|x_i-y_i|)>0, \therefore L_{\infty}(x,y)=max(|x_i-y_i|)>0$
3. Symmetry
>  $ L_{\infin}(x,y)=max(|x_i-y_i|)=max(|y_i-x_i|)=L_{\infin}(y,x)$
4. #TODO:Triangle Law of Inequality


----
## Jaccard Distance
**Jacard Similarity:** IOU(Intersection Over Union) = Ratio of cardinality of intersection and cardinality of union for given two **sets** $A$ and $B$ =$\large \frac{|A\cap B|}{|A\cup B|}$  

Jaccard distance for two given **sets** $x$ and $y$ is defined as,  

$$\large d(x,y)=1-JSIM(x,y)$$

- Range of $JSIM(x,y) = [0,1]$
- Range of $JDIS(x,y) = [0,1]$
- As Jaccard similarity increases Jaccard Distance decreases and vice versa.
- Repetition is not allowed in a set.

#### Distance Axioms:
1. $d(x,y)$ is non-negative because intersection of sets cannot exceed their union.  
> $\because, \frac{x\cap y}{x\cup y} \le1$  
> $\therefore d(x,y)=  1 - \frac{x\cap y}{x\cup y} \ge 0$
> $[Proved!]$
2.  $d(x,y)=0$ when $x=y$ else $d(x,y)>0$
> Case-I: When $x=y$,
>> $d(x,y)= 1 - \frac{x\cap y}{x\cup y}$ 
>> $d(x,y)= 1 - 1=0$  [Proved!]  
>
> Case-II: When $x\not=y$  
>> $\because, \frac{x\cap y}{x\cup y} <1$  
>> $\therefore d(x,y)=  1 - \frac{x\cap y}{x\cup y} \gt 0$
>> $[Proved!]$
3. $d(x,y)=d(y,x)$, because union and intersection are symmetric.
> $d(x,y) = 1-\frac{x\cap y}{x\cup y} = 1- \frac{y\cap x}{y\cup x} = d(y,x) [Proved!]$
4. 
#TODO: Jaccard distance proof for 4th axiom


----
## Cosine Distance
Let,  
$\large x=[x_1,x_2,...,x_n]^T$,  
$\large y=[y_1,y_2,...,y_n]^T$
  
$$\begin{aligned} \Large d(x,y) &= \frac{Dot\ product\ of\ x\ and\ y}{Product\ of\ their\ L_2-norm}\\
&=\frac{x.y}{||x||\ ||y||} \\
&= \large\frac{\sum_{i=1}^n{x_i*y_i}}{\sum_{i=1}^n{x_i^2}*\sum_{i=1}^n{y_i^2}}
\end{aligned}$$

- There is no difference between a vector and its multiple.
- Angle between two vectors is the smaller angle between them, range=$[0\degree,180\degree]$.

----
## Hamming Distance
Let,  
$x=[x_1, x_2,..,x_n]$,  
$y=[y_1,y_2,...,y_n]$

$$d(x,y)= \text{Number of elements that differ between x and y}$$

----
