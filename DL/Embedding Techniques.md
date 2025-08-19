
Embedding techniques:
1. One-hot encoding
2. PCA
3. [Autoencoders](./Autoencoders.md): Encoder can be used for embedding.
4. word2vec
5. Glove
6. BERT

----
## One-Hot Encoding

Each token/item/category/... is represented as unique binary vector.

Example:  
Tokens: cat, dog, mouse.
Possible one-Hot encoding:

| Token | One-Hot encoding |
| ----- | ---------------- |
| cat   | `1 0 0`          |
| dog   | `0 1 0`          |
| mouse | `0 0 1`          |


Pros:
1. Preserves nature of nominal encoding - no inherent ranking.
Cons:
3. High dimensionality: More tokens $\implies$ Larger embedding vector(with most value 0)

----
## Word2vec

### CBOW model
Continuous Bag Of Words predicts the word given context.  
Input: Context = $w_{i-t},w_{i-t+1},...,w_{i-1},w_{i+1},...,w_{i+t}$, where $t$ is the window width.  
Output: Predicted $w_i$.  

### skip-gram model
Given word predicts context.  

Input: word
Output: Context word related to word.
#TODO

----
