Long Short-Term Memory models
- improvement over RNN as it has Long-term memory also.

RNN's hidden state is divided into two parts:
1. Memory/Cell state: Long-term memory
2. Hidden state: short term memory
	1. The output itself is taken as hidden state.

LSTM unit architecture at tensor and operation level:  
![LSTM architecture](../Images/DL/LSTM_arch_tensor_and_ops.png)

**Memory cell:** Tensor represented by the bold inner loop above.  
- It is long-term memory.

**Keep gate:** Determines how much of previous memory to keep.  

**Write gate:** Determines how much of new input to write in memory.  
- tanh component: what information to write into the state.
- sigmoid component: further filters the informations that is to be wrote into state.

**Output gate:** Process the current time step input and memory content to create output.  

**Output:** The output of current time step. Also taken as short term memory for next time step.  

Keep gate:
![Keep gate](../Images/DL/LSTM_keep_gate.png)

Write gate:
![Write gate](../Images/DL/LSTM_write_gate.png)

Output gate:
![](../Images/DL/LSTM_output_gate.png)



Unrolled through time steps:
![](../Images/DL/LSTM_unrolled.png)

LSTM as stacked RNN:
![](../Images/DL/LSTM_stacked_RNN.png)

----
# Applications

## seq2seq with RNN
![](../Images/DL/RNN_seq2seq.png)


----
# Improvement
1. [Attention Mechanism](./Attention.md)
