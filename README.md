# 🤖 AI-Powered Chatbot with Context & Logging

This is an intelligent chatbot built using Hugging Face's `DialoGPT` and Gradio. It supports:

- ✅ Contextual conversations (remembers chat history)
- 📝 Logs all user-bot interactions to CSV
- ⚙️ Built in Python using `transformers`, `torch`, and `gradio`
- 🌐 Deployable via Colab or Hugging Face Spaces

## 🚀 Try It on Google Colab

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1P_V-daVPk7NASLKuHwlvd6AFNBJVoqdq?usp=sharing)

Or click this link to open directly:  
🔗 https://colab.research.google.com/drive/1P_V-daVPk7NASLKuHwlvd6AFNBJVoqdq?usp=sharing

---

## 🧠 How It Works

- Loads the `DialoGPT-medium` model
- Uses token history to generate context-aware replies
- Stores every chat interaction in `chat_log.csv`
- Supports `reset` command to clear memory mid-chat

## 🛠 Technologies

- Python
- Hugging Face Transformers (`DialoGPT-medium`)
- PyTorch
- Gradio for web UI
- CSV for lightweight logging

## 📁 Folder Structure

