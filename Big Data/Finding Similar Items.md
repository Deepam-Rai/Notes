
Applications of Near Neighbour Search
- Plagiarism
- Mirror sites
- Articles from the same source
- Collaborative filtering as Similar sets problem
    - Online purchases
    - Movie Ratings

## Problems
1. Too Large documents
    - Solution: Shingling, Minhashing
2. Too Many documents
    - Solution: Locality Sensitive Hashing.

----
## Jaccard Similarity of Sets
$\large JSIM(A,B)=\frac{|A\cap B|}{|A\cup B|} = IOU(Intersection\ Over\ Union)$
- Range: [0,1]
- Character level similarity not meaning.

#### Sets vs Bags
- **Set:** Collection of items with no duplicates allowed.
- **Bag:** Collection of items with duplicates allowed.
    - JSIM(Bag1, Bag2) has denominator Union as "bag of all elements of Bag1 and Bag2.
    - Range for JSIM will be $[0,\frac{1}{2}]$

----
## k-Shingles
**Definition:** Set of k-consecutive items.
- Items can by anything - characters, words, sentences, etc.
- Here we take character as an item.
- It can be bags instead of sets also.

For a document with $n$ items from universal set $U$ consisting of $m$ symbols.  
- |U| = $m$
- Range of $k$ = [1,n], n>0
- Count of, repetition allowed, k-shingles from document content = max count of k-shingles from document content = $n-k+1$
- Possible unique k shingles, of symbols= $n^k$ 

### Choosing k
- If to small then we might pick most occurring shingles.
- Avoid to choose the length of stopwords also.
- **Should choose such that the probability of any shingle occurring in any given document is low.**

### Hashing shingles
- Instead of using k-shingles directly hash them into buckets
    - $k-shingles \to buckets$
- Even larger shingles can be represented by the bucket-size, which might be smaller.
- Hashing larger sized shingles to small-sized buckets and working on them might be better than working directly on small sized shingles..

----
## Similarity preserving Summaries of sets
- Shingles take care of similarity.
- But k-shingle size for a document is large.
- So we take their **signature** sets, whose similarity must be statistically equal to similarity of true documents.

----
## Characteristic matrix
**Column:** Sets  
**Rows:** Elements of the Universal Set.  
**Entries:** 1 if the set(in the column) contains the element(in the row).

![Characteristic Matrix](Characteristic%20Matrix.png 'Characteristic Matrix')

- Better for visualization not storing.
- Is sparse matrix.

## Minhashing
A minhash is the permutation of rows of characteristic matrix where the sets are represented by columns.

#### Principle of minhashing

$$\large P(h(A)=h(B))=\frac{x}{x+y}=\frac{A\cap B}{A\cup B} = JSIM(A,B)$$

where
- x: number of X type rows (both 1)
- y: number of Y type rows (only one 1)
- z: number of Z type rows (both 0)

## Signature Matrix
If we take $n$ minhashes for characteristic matrix then,  
**columns:** sets  
**rows:** minhashes signatures  
![Signature Matrix](signature%20matrix.png 'Signature Matrix')

## Calculating Signature Matrix
Create minhashes as hash-functions that will permute the rows randomly.  

Algorithm:
<pre>  
Let,
    C=Characteristic matrix,
    S=Signature matrix

1. Initialize C<sub>ij</sub> to Infinity.
2. For each row i in C do:
    for each col j do:
        if C<sub>ij</sub> ==1
        then,
            for each minhash k:
                Set S<sub>kj</sub> = min{S<sub>kj</sub>, h<sub>k</sub>(r)}
</pre>

Till now:  
Documents ~ represented by shingles set $\to$ minhashed to short signature matrix

----
## Locality Sensitive Hashing
Also known as **Near Neighbour Search**.
Measuring similarity for every pair is herculent task, even for $n$ signature matrices we have $^nC_2$ comparisons.

1. Divide the signature matrix into $b$ bands with $r$ row each.
1. For each band, hash function to map 'each column vector' of dimension $r$ to a bucket.
1. Each band have different bucket array.

### Analysis
Note: Probability of minhash of two sets matching is equal to their Jaccard Similarity.

1. Probability that a row in a band matches in signatures= $s$
1. Probability that all row in a band matches in signatures = $s^r$
1. Probability that at least a row doesnt match in a band in signature = $1-s^r$
1. Probability that all row has at least one mismatch = $(1-s^r)^b$
1. Probability that at least one row has all matching rows = $1-(1-s^r)^b$  
- this has S-curve graph
- The threshold - value of similarity at which the probability of becoming candidate pair is 1/2 = $\large k = (\frac{1}{b})^\frac{1}{r}$  

----
## Distances
Refer to common notes [Distances](../Common/Distances.md).

----