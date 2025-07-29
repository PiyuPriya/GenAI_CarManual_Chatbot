# 📘 Multilingual GenAI Chatbot for Automotive Manuals (RAG-based)

This project is a Retrieval-Augmented Generation (RAG) chatbot designed to answer questions from **Audi A4 2025 Owner’s Manuals** (English and German). It combines semantic search using FAISS and HuggingFace embeddings with powerful LLM-based generation using OpenAI's GPT-4o-mini.

---

## 🚀 Features

- ✅ Multilingual support (English 🇬🇧 & German 🇩🇪)
- ✅ Vector search using `sentence-transformers/distiluse-base-multilingual-cased-v2`
- ✅ GPT-4o-mini for answer generation
- ✅ RAG chain built with LangChain
- ✅ Powered by Unity Catalog & Delta Lake on Databricks
- ✅ PDF chunking and preprocessing
- ✅ Return source documents for transparency

---

## 🗂 Project Structure

📁 project-root/

├── notebooks/

│ ├── 00_setup_environment.ipynb

│ ├── 01_Data_Loading_and_Chunking.ipynb

│ ├── 02_embed_and_store.py

│ └── 03_rag_chain.py

├── data/

│ ├── a4-2025-owners-manual.pdf

│ └── a4-2025-betriebsanleitung.pdf

├── README.md

└── requirements.txt


---

## 🔧 Setup

### 1. Install Dependencies


📄 Notebook/Script Details
00_setup_environment.ipynb
Installs required libraries.

Sets up cluster and Unity Catalog paths.

01_Data_Loading_and_Chunking.ipynb
Loads both English & German PDFs using PyPDF2.

Extracts clean text using .extract_text().

Splits the text using RecursiveCharacterTextSplitter.

Saves the structured chunks to Unity Catalog as Delta table.

02_embed_and_store.py
Loads saved text chunks.

Embeds using distiluse-base-multilingual-cased-v2 from HuggingFace.

Stores as FAISS index in Unity Catalog for retrieval.

03_rag_chain.py
Loads the FAISS index from Unity Catalog.

Sets up the OpenAI GPT-4o-mini model via LangChain's ChatOpenAI.

Wraps both into a RetrievalQA chain.

Accepts natural language questions and returns answers + sources.

💬 Sample Questions
English:

"What is Audi pre sense front and how does it work?"

"How do I activate the Audi adaptive cruise control?"

German:

"Wie funktioniert Audi pre sense front?"

"Wie aktiviere ich den adaptiven Tempomaten (Adaptive Cruise Control)?"

🧠 Model & Tools Used
Component	Details
Embedding Model	sentence-transformers/distiluse-base-multilingual-cased-v2 (HuggingFace)
Vector DB	FAISS (local, saved in Unity Catalog volume)
LLM	gpt-4o-mini via OpenAI
RAG Framework	LangChain
Chunking	RecursiveCharacterTextSplitter
Deployment Platform	Databricks + Unity Catalog

⚠️ Limitations
❌ Currently does not extract text from images or diagrams.

📷 OCR not integrated yet — image-based info is not searchable.

🔐 API key for OpenAI must be added manually or via secrets.

📌 To-Do / Future Improvements
 Add OCR support for extracting text from image-based diagrams.

 Add UI (Streamlit / Gradio).

 Extend support to additional languages.

 Enable audio/manual video Q&A (long-term).

📬 Contact
If you have questions or suggestions, feel free to reach out or raise an issue!


Would you like me to also generate the `requirements.txt` or a Streamlit frontend starter for the chatbot?


