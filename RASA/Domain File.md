`domain.yml` configuration of everything that the assistant knows.
Contains:
1. responses: Things assistants can say to users.
2. Intents: Categories of things users say.
3. Slots: Variables remembered over conversation.
4. Entities: Pieces of info extracted from incoming text.
5. Forms and actions: Adds application logic and extends what assistant can do.

## Responses
- Each response starts with `utter`. `utter_<thing>`.
- Also allows it to be dynamic `{slot_variable}`. Fills in  if slot value available.
- By default randomly selects one of the texts.
- Images and buttons available.
- Customized message for channels.
- Custom payloads possible for own channels.
```
example:
responses:
	utter_greet:
		- text: "Hey, there!"
		  image: "pathToImage.extension"
		- text: "Hey, {name"}. How are you?"
		  buttons:
		  - title: "great"
		    payload: "/mood_great"
```

## Intents
Intents that users can send to the assistant.
```
intents:
	- affirm
	- deny
	- greet
```
- training data for it available in `nlu.yml`.