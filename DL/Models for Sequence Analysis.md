Sequence analysis with feed forward:
1. If the sequence length is equal to input size, then performs good.
2. If sequence length is lesser, then we can pad.
3. If sequence length is greater, then feed forward fails. As it cant remember the past input sequences.


**seq2seq problems:** transforming an input sequence into a corresponding output sequence.  
Example: POS tagging, translation, summarization, etc.  

## Neural N-Grams
Logic: To know about the i'th element, instead of whole sequence maybe n-elements before it is sufficient.  

**Context window:** $i-n+1, i=n+2,...,i$ inputs, that is used to get the output for i'th input.  

## Syntaxnet
**arc-standard system:** technique used by SyntaxNet to generate dependency parsing tree.  

## Beam search
Instead of greedily selecting the most probable prediction at each step, maintain a beam of most likely hypothesis(up to a fixed beam size b) for the sequence of the first k actions and their associated probabilities.  

1. Expansion
2. Pruning

----
## Stateful DL Models
1. [RNN](./RNN.md)
2. [LSTM](./LSTM.md)