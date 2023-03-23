- non-parametric
- supervised

[ Its very disorganized.]: #

----
# Terms
<dl>
	<dt>Root</dt>
	<dd>The starting node to which whole dataset is assigned.</dd>

	<dt>Decision Nodes</dt>
	<dd>The inner nodes where during construction splitting is done and during prediction split conditions are tested to traverse the tree. </dd>

	<dt>Leaf Nodes</dt>
	<dd>The terminal nodes where prediction is done.</dd>
	
	<dt>Split Attribute</dt>
	<dd>The attribute chosen from the dataset associated to the node, upon which the splitting is done.</dd>

	<dt>Pure Split</dt>
	<dd>When all the data in the node belongs to one class.</dd>

	<dt>Horizon Effect</dt>
	<dd>Problem in AI where the models can only feasibly search small portion of possible states, this limit is called its horizon. By searching till horizon model might predict something detrimental confidently. This is because they are not able to see beyond their horizon.</dd>
</dl>

----
# Splitting Criterion/Metrics

## Entropy
Measures the level of disorder in data.  

$S =$ dataset whose entropy is calculated,  
$C =$ classes in $S$,  
$\Large p(c) = \frac{|C|}{|S|} =\frac{\text{No. of datapoints in C}}{\text{Total datapoints in S}}$   
$$\Large Entropy(S) = -\sum_{c\in C} {p(c)log_2{(c)}}$$

- - Entropy $\in [0,log_2(\text{No. of classes})]$
	- High Order: $0$ when all datapoints belongs to a class.
	- High Disorder: $1$ when all datapoints are present in equal proportion.
- Lesser the entropy the better.

## Information Gain
Represents difference between parent node Entropy and weighted Entropy of descendant nodes if split was done on a specific attribute.  

$a =$ a specific attribute or class label,  
$v =$ the unique values in $a$,  
$S_v =$ the datapoints whose attribute $a$'s value is $v$,  
$$\Large\begin{aligned}
\text{Information gain if we split on a} 
&= InformationGain(S,a) \\
&= Entropy(S) - \sum_{v\in a}{\frac{|S_v|}{|S|}Entropy(S_v)}
\end{aligned}$$


- Split on the attribute with highest Information Gain.
- **Shortcoming: If there is large number of distinct value for an attribute,  it has large Information Gain.**

## Gain Ratio
An attribute with large number of unique values separates the dataset into many small splits. Often there is only one data instance in a split, thus leading to less entropy often times. Consequently Information Gain is high for such attributes. e.g., date. But they are poor predictor over unseen instances.  Gain Ratio covers this shortcoming of Information Gain.

$$\Large\begin{aligned}
\text{Gain Ratio(S,a)} &= \frac{Gain(S,a)}{SplitInformation(S,a)},\\
\end{aligned}$$
where $$\large\begin{aligned}
SplitInformation(S,a) 
&= \text{Enrtopy of S with respect to values of attribute a} \\
&= -\sum_{v\in a}{\frac{|S_v|}{|S|}log_2{\frac{|S_v|}{|S|}}}
\end{aligned}$$

- If attribute $a$  many values $\implies a$ has high entropy $\implies SplitInformation(S,a)$ is high $\implies GainRatio(S,a)$ is low.
- Problem: If $a$ has too few unique values $\implies GainRatio(S,a)$ is very large or undefined. 

## Gini Index
Probability of misclassifying a randomly chosen datapoint from the dataset if it were labelled randomly according to the distribution of the dataset.
- Lower it is, the better.  

$C=$ classes in dataset $S$,  
$\large p(c)=\frac{|c|}{|S|}$ for $c\in C$.   

$$\large \text{Gini Impurity(S)} = 1 - \sum_{c\in C}({p(c)})^2$$


----
# Decision Tree Algorithms

## 1. ID3(Iterative Dichotomiser)
Generalized version:
```
S = datapoints in this node,  
T = Target attribute,
X = Other attributes.

ID3(S, T, X)
1. Root <- Root node for the tree.
2. If all datapoints in S belongs to same class:
	1. Label <- the common class
	3. Tree <- This single-node Root with label 'Label'
	4. Return Tree
3. If X is empty:
	1. Label <- most common class in S
	3. Tree <- This single-node Root with label 'Label'
	2. Return Tree
4. Otherwise Begin:
	1. A <- split attribute, attribute that best* classifies S
	2. For each possible value v of A:
		1. Add new tree branch below Root
		2. Let Sv = subset of S where A=v
		3. If Sv is empty:
			1. In this new branch add leaf node with label = most common value in S
		4. Else:
			1. In this new branch add subtree  ID3(Sv, T, X-{T})
5. Return Root.

*Best attribute is the one with highest information gain.
```

- Does not guarantee optimal solution.
- It can overfit the data.
- Produces a small tree, but not smallest possible tree.
- Its Hypothesis space is complete space of finite discrete valued functions, relative to available attributes.
- It cannot determine alternative decision trees.
- precursor to C4.5.

## 2. C4.5
- Handles both continuous and discrete attributes.
	- Continuous attributes: divides values using a threshold.
- Handles missing attributes
	- They are simply not used in gain and entropy calculations.
- Handles attributes with differing costs. #TODO ??
- Prunes trees after creation.
	- Prunes useless branch and replaces with leaf node.


## 3. CART (Classification And Regression Trees)


----
# Pruning
Replacing non-critical, redundant branch nodes with leaf node.
- Reduces complexity - tree becomes smaller.

## 1. Pre pruning
Inhibits building of branches during tree construction itself.

### Max depth
No more branching after max depth.

### Minimum Metric
Branching is not done if the metric isn't crossing a threshold. Example: Information Gain not crossing minimum required gain.


## 2. Post pruning
Build entire tree, or as big as possible, then prune the branches post construction.

## Bottom-up approach
Start from the leaf nodes and traverse upwards. If the node is not relevant then replace it by a leaf node.

### Reduced Error Pruning
Let, $\epsilon=$ accepted error difference during pruning.
$e_1=$ prediction error with current branch.  
$e_2=$ prediction error when branch is pruned.  
If $e_1 - e_2 \lt \epsilon$, then prune the branch else don't.
- $\epsilon$ represents the trade-off between complexity and accuracy of the tree.

### Minimum Cost Complexity Pruning/ Minimum Error Pruning
Build a full tree. Let it be $T_m$ with $m$ leaves.  
Let, $T_1, ...,T_m$ be pruned trees such that $T_i$ has only $i$ leaves.   $T_1$ is just root node.
1. The error decreases as $i$ increases. Let it be measured by function $error(T_i)$.
2. The complexity increases as $i$ increases. Let it be measured by function $complexity(T_i)$.
Find a function $TreeScore( error(T_i), complexity(T_i))$, that finds balance between error and complexity. Choose appropriate tree $T_i$ based upon this function. We may need to approximate some hyperparameters in $TreeScore()$ using cross validation.


## Top-Down approach
Start at root node and recurse downwards. If the node is not relevant, replace with leaf node. 

----

# Pros and Cons of Decision Trees

Advantages:
1. High interpretability.
2. No extensive data preparation required.
3. Can be used for regression and classification both.
4. Insensitive to underlying attributes relationship - e.g., correlation.

Disadvantages:
1. High variance estimators: small variance in input data can produce different tree structure.
2. Prone to overfitting - even when training data is noise free, owing to coincidental regularities and assigning small number of datapoints to leaf nodes.
3. Suffers from horizon effect.