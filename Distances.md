# Distances

Let $\tau$, called space, be a set of points. Then the distance measure for two points $x$ and $y$ on this space is a function that taking these two points as arguments results in a real number output.

## Axioms of Distance Measure
1. $d(x,y)\ge0$, no negative distance.
1. $d(x,y)=0$, if and only if $x=y$.
1. $d(x,y)=d(y,x)$, is symmetric.
1. $d(x,y)\le d(x,z) + d(z,y)$, the triangle inequality.

# $L_r$-norm
For points $\large x=[x_1,x_2,...,x_n]^T$ and $\large y=[y_1,y_2,...,y_n]^T$ in Euclidean space $R^n$, $L_r$-Norm is defined as:  
$\large L_r -norm = (\sum_{i=1}^n|x_i-y_i|^r)^{1/r}$

# Manhattan Distance / $L_1$-norm
For points $\large x=[x_1,x_2,...,x_n]^T$ and $\large y=[y_1,y_2,...,y_n]^T$ in Euclidean space $R^n$, $L_1$-Norm or Manhattan distance is defined as:  
$\large L_1 -norm = \sum_{i=1}^n|x_i-y_i|$

- If the space be divided into blocks and we were allowed to travel only the sides, then this distance would be exact distance for travelling from $x$ to $y$ or vice-versa.
- The layout of Manhattan city inspired the name.

# Euclidean Distance / $L_2$-Norm
In $\R^n$, Euclidean distance is defined as:  
$\large d(x,y)=L_2 -norm = (\sum_{i=1}^n|x_i-y_i|^2)^{1/2}= \sqrt{\sum_{i=1}^n{(x_i -y_i)^2}}$  
where $\large x=[x_1,x_2,...,x_n]^T$ and $\large y=[y_1,y_2,...,y_n]^T$.

# $L_{\infin}$-norm
For points $\large x=[x_1,x_2,...,x_n]^T$ and $\large y=[y_1,y_2,...,y_n]^T$ in Euclidean space $R^n$, $L_{\infin}$-norm or Manhattan distance is defined as:  
$\large L_{\infin}=max(|x_i-y_i|) for\ 1\le i<n$
- Assumption: As $r$ gets large enough only the dimension with the largest difference matters.

# Jaccard Distance
**Jacard Similarity:** IOU(Intersection Over Union) = Ratio of cardinality of intersection and cardinality of union for given two **sets** $A$ and $B$ =$\large \frac{|A\cap B|}{|A\cup B|}$  
Jaccard distance for two given **sets** $x$ and $y$ is defined as,  
$\large d(x,y)=1-JSIM(x,y)$  
- Range of $JSIM(x,y) = [0,1]$
- Range of $JDIS(x,y) = [0,1]$
- As Jaccard similarity increases Jaccard Distance decreases and vice versa.
- Repetition is not allowed in a set.
## Distance Axioms:
1. $d(x,y)$ is non-negative because intersection of sets cannot exceed their union.  
> $Since, \frac{x\cap y}{x\cup y} \le1$  
> $\therefore d(x,y)=  1 - \frac{x\cap y}{x\cup y} \ge 0$
> $[Proved!]$
2.  $d(x,y)=0$ when $x=y$ else $d(x,y)>0$
> Case-I: When $x=y$,
>> $d(x,y)= 1 - \frac{x\cap y}{x\cup y}$ 
>> $d(x,y)= 1 - 1$
>> $d(x,y)= 0$  [Proved!]  
>
> Case-II: When $x\not=y$  
>> $Since, \frac{x\cap y}{x\cup y} <1$  
>> $\therefore d(x,y)=  1 - \frac{x\cap y}{x\cup y} \gt 0$
>> $[Proved!]$
<!-- #TODO: Check above render in github
#TODO: check latex for since -->
3. $d(x,y)=d(y,x)$, because union and intersection are symmetric.
> $d(x,y) = 1-\frac{x\cap y}{x\cup y} = 1- \frac{y\cap x}{y\cup x} = d(y,x) [Proved!]$
4. 
<!-- #TODO: Jaccard distance proof for 4th axiom -->

# Cosine Distance
Given two **vectors** $\large x=[x_1,x_2,...,x_n]^T$ and $\large y=[y_1,y_2,...,y_n]^T$,  
$\Large d(x,y)= \frac{Dot\ product\ of\ x\ and\ y}{Product\ of\ their\ L_2-norm}=\frac{x.y}{||x||\ ||y||}$  
$\Large = \frac{\sum_{i=1}^n{x_i*y_i}}{\sum_{i=1}^n{x_i^2}*\sum_{i=1}^n{y_i^2}}$ 
- There is no difference between a vector and its multiple.
- Angle between two vectors is the smaller angle between them, range=$[0\degree,180\degree]$.
# Hamming Distance
