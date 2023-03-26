- specialized for processing sequence of values.
- can scale to variably long sequences.
- Uses parameter sharing - if we had separate parameters for each value of time index, we couldn't generalize it unseen time indexes.
- Alternative: Convolution across 1-D temporal sequence - but its shallow.
- RNNs can be built in many different ways. Much as almost any function can be considered to be a feedforward neural network.

>**Computational Graph:** Way to formalize the structure of set of computations, such as those involved in mapping inputs and parameters to outputs and loss.

----
# Unfolding Computational Graph

$t=$ time step,  
$h^{(t)} =$ hidden state at time step $t$,  
$x^{(t)} =$ input for hidden state $h^{(t)}$ at time step $t$,  
$\theta =$ parameters,
$$h^{(t)} = f(h^{(t-1)}, x^{(t)};\theta)$$
- $h^{(t)}$ acts as a kind of lossy summary.

# Important Design patterns
#TODO: put image

