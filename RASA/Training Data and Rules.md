- user generated + conversational patterns.

## Stories
Interactive learning: `rasa interactive`  

```yaml
example:
stories:
- story: happy path
  steps:
    - intent: greet
    - action: utter_greet
    - intent: mood_great
    - action: utter_happy
    - or:
	    - intent: affirm
	    - intent: thanks
	- action: action_signup_newsletter
```
- `or` statements available.
- `checkpoint` available.

## Rules
Type of training data to train assistant's dialogue management model.  
Pieces of conversations that should always go the same way.  
```yaml
rules:
	- rule: Greeting Rule
	  steps:
	      - intent: greet
	      - action: utter_greet
```

## Intents
In `nlu.yml` file.
```yaml
nlu:
	- intent: greet_smalltalk
	  examples: |
	      - hi
	      - hello
	      - howdy
	      - hey
```

