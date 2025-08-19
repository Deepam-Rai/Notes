>**Markov chains:** Are mathematical model used to represent statistical process where the future step of the system depends only on the current step of the system and not on the sequence of events that preceded it.

## Representations

1. Directed graph:
	1. Nodes: represents the system state
	2. Edges: represent the transition from one state to another
2. Transition matrix

![Markov chain representations](Images/DL/markov_chains_representation.png)

----
## Usage in generative AI
1. Text generation
2. Music generation
3. Next step prediction in chess, etc.

----
## Advantages and Limitations

Advantages:
1. Simplicity
2. Relatively less compute intensive
3. Scalable

Limitations:
1. Memoryless: Model does not consider past history.
2. Stationary assumptions: Assumes that transition probabilities between states are constant overtime, which may not hold true in all cases.

----

## Tutorial

- https://www.kdnuggets.com/2019/11/markov-chains-train-text-generation.html

----
