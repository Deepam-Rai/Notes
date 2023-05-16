
> **Hidden layers:** Layers between input layer and output layer.
- This is where the learning of model happens.
- Each layer can have different number of neurons.
- Not necessary to connect every neuron in a layer to every neuron in another layer.
- The input, output, all maths are done in vectorized representations.

----
## Notation
$n_k =$ number of neurons in k'th layer,  
$W^{(k)} \in \large\mathbb{R}^{n_k \times n_{k-1}} =$ Weight matrix connecting (k-1)'th layer with k'th layer,  
$w_{i,j}^{(k)}=$ weight connecting i'th neuron in k'th layer with j'th neuron in (k-1)'th layer,  
$b^{(k)} \in \large \mathbb{R}^{n_k} =$ bias vector of k'th layer,  
$a^{(k)} =$ pre activation at layer k,  
$g^{(k)}() =$ activation function of layer k,  
$h^{(k)} =$ after activation at layer k,  

$$\large a^{(k)} = W^{(k)}h^{(k-1)} + b^{(k)}$$

$$\large h^{(k)}= g^{(k)}(a^{(k)})$$

----
# Specialized models
Though feed-forward is a universal the parameters are too large and thus the space to find the optimal parameters is too vast. For specific tasks we can reduce this space drastically by changing the architecture such that it takes into consideration many nuances which now the model wont need to learn. Example in CNN by giving inputs as matrices we are setting assumption that the inputs will related to each other in a specific way, which now the model need not learn.  

List of some specialized model architectures are:
1. [Convolutional Neural Networks(CNN)](./CNN.md)
2. [Recurrent Neural Networks(RNN)](./RNN.md)
3. [Long-Short Term Memory(LSTM)](./LSTM.md)
4. [Memory Augmented Models](./Memory%20Augmented%20Models.md)
	1. [Neural Turing Machines(NTM)](./Memory%20Augmented%20Models.md)
	2. [Differentiable Neural Computers(DNC)](./Memory%20Augmented%20Models.md)
5. [Reinforcement Learning(RL)](./Reinforcement%20Learning.md)
