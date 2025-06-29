# Ai-chat_box_in-collab
This project is a conversational AI chatbot built with:

- 🤖 Microsoft DialoGPT
- 🧠 Hugging Face Transformers
- 💬 Gradio
- 🧪 Google Colab

## 🚀 How to Use

1. Open the notebook: `AI_Chatbot.ipynb`
   # 🤖 AI Chatbot in Google Colab

# 🤖 AI Chatbot in Google Colab

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1_Vmu7_-LLO526gteIp9gjd0E4nEEIrgG?usp=sharing)

This is an AI-powered chatbot built using **Microsoft DialoGPT**, **Hugging Face Transformers**, and **Gradio**. It runs entirely in **Google Colab**, requires no setup, and provides a simple conversational interface.

---

## 🧠 Features

- Built with `transformers` and `gradio`
- Uses `DialoGPT-medium` for natural, human-like responses
- Gradio interface for easy chatting
- Supports chat history (multi-turn memory)
- "reset" keyword clears the conversation context

---

## 🚀 How to Use

1. Click the **"Open in Colab"** badge above ⬆️
2. Run all cells from top to bottom
3. Use the chatbox UI that appears
4. Type `reset` to clear the chat memory anytime

---

## 💬 Sample Conversation



This is a chatbot built using DialoGPT and Gradio in Google Colab.
3. Run all cells in order
4. A Gradio chat interface will launch

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
