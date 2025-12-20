# Bilingual-RAG-Chatbot-for-International-Students
This project implements a **Retrieval-Augmented Generation (RAG)** chatbot designed to help international students — particularly Spanish-speaking applicants — navigate complex topics related to U.S. university admissions, F-1 visas, scholarships, and life on campus. The system combines dense semantic search (via FAISS) with a fine-tuned **LLaMA 2 model** using **LoRA adapters** to produce context-aware answers in both **English and Spanish**.

## 🎯 Key Features

- ✅ **Multilingual Question Answering** (English/Spanish)
- 🔍 **FAISS-based vector search** for retrieving relevant context passages from a custom dataset
- 🧠 **RAG-style prompting**: context + question → answer
- 🤖 **Fine-tuned LLaMA 2 with LoRA adapters** for low-cost, domain-specific generation
- 📉 **Reduced time-to-answer**: students no longer need to jump between 10+ government/academic pages
- 🧪 Interactive testing environment via script or Gradio interface (optional)

---

## ⚙️ Architecture Overview

```bash
┌────────────┐      ┌─────────────────────┐      ┌────────────────────────┐
│  User Q&A  │ ──▶ │  Sentence-BERT Embed │ ──▶ │  FAISS Vector Search   │
└────────────┘      └─────────────────────┘      └────────────────────────┘
                                                           │
                                                           ▼
                                       ┌────────────────────────────────┐
                                       │ Retrieved Context + User Query │
                                       └────────────────────────────────┘
                                                           │
                                                           ▼
                                 ┌─────────────────────────────────────────┐
                                 │   LLaMA 2 + LoRA Adapter (Quantized)    │
                                 └─────────────────────────────────────────┘
                                                           │
                                                           ▼
                                                🧠 Generated Response
