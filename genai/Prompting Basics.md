# Prompting Basics

Series of notes on the basics of prompting and possibilties avialable with OpenAI models. 

## 1. Principles
### 1.1. Use delimiters
Use delimiters to specify to the model where to look. <br>
For example: 
> You will be provided with text delimited by triple quotes. Summarize that text. 

### 1.2. Ask for structured output
You can ask the model to provide the data in JSON format. 

### 1.3. Check whether conditions are satisfied
You can ask the model to reply only if conditions are satisfied. <br>
For example: 
> You will be provided with text delimited by triple quotes. <br>
> If it contains a sequence of instructions, <br>
> re-write those instructions in the following format:<br>
> <br>
> Step 1 - ...<br>
> Step 2 - ...<br>
> ...<br>
> Step N - ...<br>

### 1.4. Few-shots prompting 
Provide some examples to the model, before asking for something. This is an example: 
```
prompt = f"""
Your task is to answer in a consistent style.

<child>: Teach me about patience.

<grandparent>: The river that carves the deepest \ 
valley flows from a modest spring; the \ 
grandest symphony originates from a single note; \ 
the most intricate tapestry begins with a solitary thread.

<child>: Teach me about resilience.
"""
response = get_completion(prompt)
print(response)
```

### 1.5. Give the model time to think
This concretely corresponds to a few tactics: 
 * Specify the steps required to complete a task
 * Instead of asking to evaluate someone's solution, ask it to first resolve the problem and then compare the two

## 2. What can you ask for? 
Ideas on what you can ask and how flexible it can be: 

 * Ask for sentiment of an article, review, etc.. 
 * Ask to extract the 5 most discussed topics in the article
 * If I have a list of topics, tell me which ones are the one covered in the article
 * Extract information from the article. *Example: which product is discussed, what brand, the company and the sentiment* 
