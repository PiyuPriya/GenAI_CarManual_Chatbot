# 🤖 GenAI Car Manual Chatbot (Audi A4)

This project demonstrates how to build a **Retrieval-Augmented Generation (RAG)** chatbot that answers user questions based on the **Audi A4 Owner's Manual** in English and German.  
It is developed using **Databricks**, **Unity Catalog**, **LangChain**, **FAISS**, and **HuggingFace embeddings**.

---

## 📌 Project Overview

- 💬 **RAG pipeline** with LangChain and HuggingFace
- 📄 Parses multilingual Audi A4 manuals (English & German)
- 🔍 Chunks and embeds content using `sentence-transformers`
- 📦 Stores embeddings in a local FAISS vectorstore
- 🧠 Answers questions via OpenAI (or other LLMs)

---

## 🛠️ Tech Stack

- **Databricks (with Unity Catalog)**
- **LangChain**
- **HuggingFace Transformers**
- **FAISS** (local vector DB)
- **PyPDF / PyPDF2**
- **OpenAI GPT (optional for LLM)**

---

## 📁 Project Structure
genai-car-manual-chatbot/

│
├── data/

│ ├── audi_manual_en.pdf # English Audi A4 manual

│ └── audi_manual_de.pdf # German Audi A4 manual
│

├── notebooks/

│ ├── 00_setup_environment.ipynb # Install and configure dependencies

│ ├── 01_create_vectorstore.ipynb # Chunk text, generate embeddings, save FAISS index

│ ├── 02_build_rag_pipeline.ipynb # Load vectorstore, setup LLM, build QA chain

│ ├── 03_query_examples.ipynb # Sample user questions and responses


├── requirements.txt 

├── README.md 

└── LICENSE 




