

----
# About
[deeplearning.ai](https://www.deeplearning.ai/) course  *LangChain for LLM Application Development*:  
https://learn.deeplearning.ai/courses/langchain/lesson/1/introduction


----
# Overview
> **LangChain:** is a opensource development framework for LLM applications.

- Packages available: Python, Javascript(Typescript)
- Focuses on modularity and composition

Developed by Harrison Chase and Ankush Gola(Co-Founder).  

---

1. Provides wrappers and utilities for giving prompt to LLM model and also for the output given by LLM.
3. [Typical flow here](./Models,%20prompts%20and%20parsers.md) for usual prompt and getting response from LLM.
4. Gives dedicated memory retaining mechanism for chatbots conversations [here](./Memory.md).
5. Combines prompt and LLMs to form building blocks, which can be joined in sequence and used as a chain.


----
# Models, prompts and parsers

> **Models:** LLM models.

>**Prompts:** Style of creating inputs to pass into the models.

> **Parsers:** Parsing of model outputs to more structured format.

Typical flow:
	1. Create a prompt template. Which can have variables - the text to be worked upon, output format instructions, etc, etc.
	2. Generate prompt:
		1. Fill in the variables in the prompt template.
	3. Instructions for output parsing:
		1. Define output schema using LangChain classes, instantiate schema objects.
		2. Create output parser, an object, using above schemas.
		3. Get format instructions(string) from output_parser.
	4. Create message to pass to LLM, by adding format instruction to the prompt. Message is an instance of class provided by LangChain.
	5. Pass the message to LLM model, the output would be as per the format instructions, but still as string type.
		1. Langchain has model/providers(e.g., OpenAI) wrappers that are built to work with the langchain input message, output parsers, etc classes.
	6. Pass LLM output(which is string) to output parser to get structured format output, json, xml, etc.


----
# Memory
## Types
1. Vector data memory
	1. Store text in vector database and retrieve the most relevant blocks of text.
2. Entity memory
	1. Remember details about specific entities.
3. ConversationBufferMemory:
	1. remember the conversation history.
4. ConversationBufferWindowMemory: 
	1. remember recent conversation history in window.
5. ConversationTokenBufferMemory: 
	1. remember recent conversation history as accomodated by the max token limit
6. ConversationSummaryMemory:
	1. Creates summary of conversation overtime.

## Adding memory in chatbots

**How:** The conversation between the user and AI is stored by langchain. When user inputs new message, a template containing the conversation history and new input is generated and sent to LLM as prompt. This gives LLM access to past history giving illusion of memory.

**Problem:** The conversation history can become long, meaning a long prompt for the LLM, which has several issues.  

**Mitigations:** (LangChain provides memory type for each of below)
1. Keep and use just recent conversation part, a window memory.
2. Create prompt according to token limit, for efficient use of tokens.
3. Instead of using exact conversation history, use its summary(use llm to generate summary) when the conversation history would exceed the max token limit.


----
# Chains
> **Chain:** combines LLMs with prompts, and these building blocks can be joined in a sequence.  

### Types
We can combine and use.
#### SimpleSequentialChain
Sequence of single input single output chains. 

#### RouterChain
Routes input to a chain depending upon the input.  

#### MultiPromptChain
Routes between multiple different prompt templates.

#### LLMRouterChain
Uses LLM to route between sub chains


----
# Question and Answer
**Problem:** LLM can only take limited number of tokens at a time. Thus, if our data is large how can LLM go over all of them and answer a question?  

**Solution:** Vector embeddings.  

1. During training
	1. When input arrive, if input is too large, divide into chunks.
	2. Create vector embedding of all chunks.
	3. Store embeddings in a vector database.
2. During inference
	1. When input arrive, embed the input.
	2. Find similarity against embedded vectors in vector database.
	3. Retrieve the most similar ones and pass them to the prompt.

### Processing Methods:
1. Stuff
	1. Put everything in prompt at once.
	2. Not good when the data is very large and varies widely in itself.
2. Map Reduce
	1. Able to handle when we are not able to put everything at once in a prompt.
	2. Work at chunks(not the same chunk as created for embedding process) parallelly. 
3. Refine
	1. Once chunk at a time.
	2. LLM is able to see whole of the data.
4. Map re-rank
	1. Variation of Map-Reduce.
	2. Assign LLMs to chunks of data. Parallel processing is possible.
	3. Instructs LLM to provide confidence score for its response, and the response with highest confidence score is taken.

![Methods](../Images/Lang%20Chain/LangChain_Q_A.png)

----

# Evaluation
## Using Chains to evaluate another chain
To evaluate a Question-&-Answer chain, we can make question answer pair for each document of the data. And check how well our it is doing on it.  
For large datasets we can make use of LLM chains themselves to create this question answer pairs.  LangChain provides utilities for this.  
But the answers generated by test-chain and the ones generated by the the question-answer pair generators may not be same sentence. They may be common in just meaning. Thus, to check if the answers mean the same or not, we can use another LLM.  LangChain provides utilities for all of these.  

Lang Chain evaluation platform: https://docs.smith.langchain.com/  

----
# Agent

Creating an agent able to handle multiple tasks. The core decision maker of the agent will be LLM, and tools like calculator, internet access,etc. is provided via lang chain library.  
Given a task, the LLM decides what tool to use and what operation to perform on it. We are able to see its thought process and the actions taken by the agent.  

## Giving our own tool to LangChain
By creating a function wrapper with tool decorator provided by LangChain.  

----
