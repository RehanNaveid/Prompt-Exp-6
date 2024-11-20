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
```
from transformers import pipeline

# Load GPT-Neo and GPT-2 models
generator_neo = pipeline('text-generation', model='EleutherAI/gpt-neo-1.3B')
generator_gpt2 = pipeline('text-generation', model='gpt2')

# Function to get answer from GPT-Neo
def get_gpt_neo_answer(question):
    generated_text = generator_neo(question, max_length=100, num_return_sequences=1)
    return generated_text[0]['generated_text']

# Function to get answer from GPT-2
def get_gpt2_answer(question):
    generated_text = generator_gpt2(question, max_length=100, num_return_sequences=1)
    return generated_text[0]['generated_text']

# Function to compare answers from both models
def compare_answers(question):
    answer_gpt_neo = get_gpt_neo_answer(question)
    answer_gpt2 = get_gpt2_answer(question)
    
    print("GPT-Neo Answer:", answer_gpt_neo)
    print("GPT-2 Answer:", answer_gpt2)
    
    if answer_gpt_neo == answer_gpt2:
        summary = "Both models provided the same answer."
    else:
        summary = "The answers are different."
    
    print("Summary:", summary)
    
    return {
        "question": question,
        "gpt_neo_answer": answer_gpt_neo,
        "gpt2_answer": answer_gpt2,
        "summary": summary
    }

# Run the comparison with a sample question
question = "What happens after humans die?"
result = compare_answers(question)
print("Comparison Result:", result)

```

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
