
Two types of Large Language Models(LLMs):
1. Base LLM: Predicts next word based upon text training data.
2. Instruction tuned LLM: Tries to follow instructions.
	1. RLHF(Reinforcement Learning with Human Feedback): Refinement technique for  instruction tuned LLM.

----
## Guidelines for Prompting

Principles:
1. Write clear and specific instructions.
	1. clear $\not =$ short.
2. Give model time to think.
	1. If the model is rushing to incorrect conclusions for complex tasks, give prompt that makes the model arrive to conclusion step by step. Thus the model has chance to reason out it's solution.

Tactics:
1. Use delimiters
	1. Delimiters can be anything that indicates a separate section.
	2. Also helps in avoiding prompt injections.
3. Ask for structured output
	1. JSON, HTML.
	2. Easy to handle the data.
5. Ask the model to check whether the conditions are satisfied
	1. Kind if like if-else.
6. Few-shot prompting
	1. Give successful examples of completing tasks, then ask the model to perform the task.
7. Specify the steps required
8. Instruct the model to work out it's own solution before reaching to conclusion
	1. Instruct steps.
9. Ask for valid citations
	1. Helps in reducing hallucination.
10. Iterative prompt development
	1. Its more about the process through which we get a good prompt.

----
## Model limitations

1. Hallucinations
	1. Makes statements that sound plausible but are not true.

----
Jupyter notebook available as: I2-guidelines.ipynb

----
