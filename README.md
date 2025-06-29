# Ai-chat_box_in-collab
This project is a conversational AI chatbot built with:

- 🤖 Microsoft DialoGPT
- 🧠 Hugging Face Transformers
- 💬 Gradio
- 🧪 Google Colab

## 🚀 How to Use

1. Open the notebook: `AI_Chatbot.ipynb`
2. Run all cells in order
3. A Gradio chat interface will launch

## 🧠 Example Code

```python
from transformers import AutoModelForCausalLM, AutoTokenizer
import gradio as gr

tokenizer = AutoTokenizer.from_pretrained("microsoft/DialoGPT-medium")
model = AutoModelForCausalLM.from_pretrained("microsoft/DialoGPT-medium")

def chat(user_input):
    input_ids = tokenizer.encode(user_input + tokenizer.eos_token, return_tensors='pt')
    output_ids = model.generate(input_ids, max_length=1000, pad_token_id=tokenizer.eos_token_id)
    return tokenizer.decode(output_ids[:, input_ids.shape[-1]:][0], skip_special_tokens=True)

gr.Interface(fn=chat, inputs="text", outputs="text").launch()
