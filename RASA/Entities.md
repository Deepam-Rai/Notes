Any detail that can be used later in conversation. e.g., numbers, dates, names, etc.
- Can also detect entities within an utterance.
- is in `nlu.yml`.
- `synonym` feature available. Can put inline also.
- Entities can influence stories.

```yml
nlu:
	- intent: check_balance
	  examples: |
	      - I want to check my [savings account](account_type)
	      - Can you show me my [credit account](account_type)
	- synonym: credit
	  examples: |
	      - credit card account
	      - credit account
```
----
## Detecting Intents
- ML pipeline should be correctly configured.
### Pre-built models
- Provided by Duckling or Spacy.

### regex
```yaml
nlu:
	- regex: account_number
	  examples: |
	      - \d{10, 12}
	- lookup: country
	  examples: |
	        - Afghanistan
	        - Albania
	        - ...
	        - Zambia
	        - Zimbabwe
```

### ML models
- Base model DIET available.

## Roles and Groups
Added information to entitties.
