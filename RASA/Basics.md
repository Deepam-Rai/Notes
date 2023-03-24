> https://learning.rasa.com/

- task oriented
- dialogue system: two way conversation

----
# Installation

```
python -m pip install rasa
```

```
pip install rasa
```


----
# Two Systems

## 1. NLU (Natural Language Understanding)
- Takes in raw data and gives out machine readable information
- Takes in **intent and entities**
- Can be rule based - regex, or neural network based.
	- DIET: NN architecture that sorts texts into intents and entities.

## 2. Dialogue Policies
- system that predicts next action to take.
- can be rule based or NN based.
	- TED: gives next best action.

> Conversation Driven Development: Correct errors that assistant makes in conversations, such that assistant can learn from it's mistakes.