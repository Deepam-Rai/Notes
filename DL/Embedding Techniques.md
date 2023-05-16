
Embedding techniques:
1. One-hot encoding
2. PCA
3. [Autoencoders](./Autoencoders.md): Encoder can be used for embedding.
4. word2vec
5. Glove
6. BERT

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
