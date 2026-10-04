
TAGS: #Artificial_Intelligence #Agentic_Intelligence 
BUILT-ON: 
ENABLES: 
PREREQUSITIES:

---
# ChatGPT Prompt Engineering for Developers
## Prompt Engineering
LLMs are generally of two types:
- Base LLMs:
	- Trained to predict the next word based on the text training data.
- Instruction-tuned LLMs:
	- Fine-tuned to follow instructions by using the Base LLMs.
	- Often Instruction-tuned LLMs are further refined (after fine-tuning) using RLHF[^1]

Principles for writing efficient prompt:
- Write clear and specific instructions
	- Use Delimiters for specific content/context.
		- Triple quotes
		- Triple Backticks
		- Triple Dashes
		- Angle Brackets
		- XML Tags
	- Set output structure/format (Json, Html, Sectioned-data, Templates)  
	- One-Shot/Few-Shot Prompting
- Give model time to think
	- Specify the steps to complete a task
	- Instruct the model to work its own solution 

---
# LangChain for LLM Application Development
## LLM Parameters 
#### Temperature
The degree of exploration or randomness of the model.

## OpenAI API Call
#### Parameters
- Messages Format
  ```py
  messages = [{
	  "role": "user",
	  "content": PROMPT 
  }]
  
							   CHATBOT INTERFACES
  messages = [
	  { "role": "system", "content": PROMPT },  SETS BEHAVIOUR OF ASSISTANT
	  (
		  { "role": "user", "content": USER_REQUEST }, 
		  { "role": "assistant", "content": ASSISTANT_RESPONSE },
	  ) * N
  ]
  ```

































---
### FOOTNOTES


[^1]: Reinforcement Learning with Human Feedback
	- Helps flag harmful, unhelpful and dishonest outputs
