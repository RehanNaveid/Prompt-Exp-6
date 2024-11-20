**EXP 6 : Development of Python Code Compatible with Multiple AI Tools Aim:**

To compare the responses of two open-source language models, **GPT-Neo** and **GPT-2**, to a given question, and analyze how different models generate text and handle natural language queries.

**Procedure:**

1. **Install Required Libraries**: 

Use the command below to install the necessary Python libraries: bash 

Copy code 

pip install transformers torch

2. **Load Models**: 
- Load two pre-trained language models from Hugging Face: 
- **GPT-Neo** (EleutherAI/gpt-neo-1.3B). 
- **GPT-2** (gpt2). 
3. **Define Functions**: 
- Define two functions to generate text from both models. 
- **GPT-Neo Function**: Generates text from the GPT-Neo model. 
- **GPT-2 Function**: Generates text from the GPT-2 model. 
4. **Generate Answers**: 
- Input the question “What are the benefits of renewable energy?” to both models and generate their responses. 
5. **Compare Answers**: 
   1. Compare the generated answers from both models to see if they match or differ. 
   1. Print the responses and a summary indicating whether the answers are the same or different. 
5. **Execute the Code**: 
- Run the code to generate and compare answers. 

**Code:**

from transformers import pipeline ![](Aspose.Words.8fae4571-5baf-4450-af56-6c7d0e93356e.001.png)

- Load GPT-Neo and GPT-2 models 

generator\_neo = pipeline('text-generation', model='EleutherAI/gpt-neo-1.3B') ![](Aspose.Words.8fae4571-5baf-4450-af56-6c7d0e93356e.002.png)generator\_gpt2 = pipeline('text-generation', model='gpt2') 

- Function to get answer from GPT-Neo 

def get\_gpt\_neo\_answer(question): 

`    `generated\_text = generator\_neo(question, max\_length=100, num\_return\_sequences=1) 

`    `return generated\_text[0]['generated\_text'] 

- Function to get answer from GPT-2 def get\_gpt2\_answer(question): 

  `    `generated\_text = generator\_gpt2(question, max\_length=100, ![](Aspose.Words.8fae4571-5baf-4450-af56-6c7d0e93356e.003.png)num\_return\_sequences=1) 

  `    `return generated\_text[0]['generated\_text'] 

- Function to compare answers from both models def compare\_answers(question): 

  `    `answer\_gpt\_neo = get\_gpt\_neo\_answer(question)     answer\_gpt2 = get\_gpt2\_answer(question) 

print("GPT-Neo Answer:", answer\_gpt\_neo) print("GPT-2 Answer:", answer\_gpt2) 

`    `if answer\_gpt\_neo == answer\_gpt2: 

`        `summary = "Both models provided the same answer."     else: 

`        `summary = "The answers are different." 

print("Summary:", summary) 

`    `return { 

`        `"question": question, 

`        `"gpt\_neo\_answer": answer\_gpt\_neo,         "gpt2\_answer": answer\_gpt2, 

`        `"summary": summary 

`    `} 

- Run the comparison with a sample question question = "What happens after humans die?" result = compare\_answers(question) print("Comparison Result:", result) 

  **Result: Output:** 

  **GPT-Neo Answer:** What happens after humans die? What happens to the soul? And, what happens to the physical body? If you have an answer to these questions, you are ready to try out the first of the most exciting and successful human experiments in history. 

  Here, in all their glory, we bring you the results of the first human experiment that has ever been performed on a human, and which has changed our world. The results may surprise you... 

  **GPT-2 Answer:** What happens after humans die? 

  A: The last person who makes the ultimate sacrifice of their own selves to save another is the creator of the universe — perhaps also of our species, and perhaps even of humanity itself. If you want to see what he's trying to hide, it's the final moment of the universe — the final gasp of the universe's evolution, the final moment that makes humanity the living species it is. That's how, or how it was until a thousand years 

  **Summary:** The answers are different. 

  **Comparison Result:** {'question': 'What happens after humans die?', 'gpt\_neo\_answer': 'What happens after humans die? What happens to the soul? And, what happens to the physical body? If you have an answer to these questions, you are ready to try out the first of the most exciting and successful human experiments in history. 

  Here, in all their glory, we bring you the results of the first human experiment that has ever been performed on a human, and which has changed our world. The results may surprise you. 

  gpt2\_answer': "What happens after humans die? 

  A: The last person who makes the ultimate sacrifice of their own selves to save another is the creator of the universe — perhaps also of our species, and perhaps even of humanity itself. If you want to see what he's trying to hide, it's the final moment of the universe — the final gasp of the universe's evolution, the final  moment that makes humanity the living species it is. That's how, or how it was until a thousand years", 'summary': 'The answers are different.'

  **Conclusion:**

  In this experiment, we compared the responses of two different language models, **GPT-Neo** and **GPT-2**, to the same input question. The results showed that the models provided different answers, which indicates that each model has its unique way of generating text based on its training data and architecture. 
