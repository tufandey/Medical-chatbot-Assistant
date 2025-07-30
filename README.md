## 🩺 MediBot – Medical AI Chatbot using FastAPI, LangChain & Groq

**MediBot** is an intelligent medical chatbot designed to provide accurate and insightful responses to health-related questions by leveraging **Groq's high-speed LLMs**, **LangChain**, and **custom medical books as a knowledge base**. Ideal for students, researchers, and health enthusiasts looking for AI-driven medical explanations.

---

### 🚀 Features

* 🤖 AI-Powered Responses using **Groq’s LLaMA 3.3 / Mixtral**
* 📚 Ingests **custom medical books** (PDFs) into a **vector store**
* 🔍 Contextual question answering using **LangChain + Retrieval QA**
* 💬 Streamlit-based UI for natural interaction
* 🌐 FastAPI backend for easy API integration
* 🔐 `.env` for secure API key handling

---

### 🛠️ Tech Stack

| Layer      | Tools/Frameworks                           |
| ---------- | ------------------------------------------ |
| LLM        | [Groq](https://groq.com/), LangChain       |
| Vector DB  | FAISS (in-memory)                          |
| Backend    | [FastAPI](https://fastapi.tiangolo.com/)   |
| Frontend   | [Streamlit](https://streamlit.io/)         |
| Loader     | PyMuPDF / PyPDF for medical book ingestion |
| Deployment | Uvicorn (ASGI Server)                      |

---

### 📁 Folder Structure

```
.
├── medibot.py         # Main Streamlit app
├── backend.py         # FastAPI server for model response
├── ingest_books.py    # Script to ingest PDF books into vector DB
├── vectorstore/       # Stores FAISS index files
├── medical_books/     # Folder for your medical PDFs
├── .env               # Your API keys
├── requirements.txt   # Python dependencies
└── README.md          # This file
```

---

### 🔧 Setup Instructions

#### 1. Clone the Repository

```bash
git clone https://github.com/your-username/medibot-chatbot.git
cd medibot-chatbot
```

#### 2. Add Your Medical Books

Place your PDF medical books inside the `medical_books/` folder.

#### 3. Create `.env` File

```env
GROQ_API_KEY=your_groq_api_key
```

#### 4. Install Dependencies

```bash
pip install -r requirements.txt
```

#### 5. Ingest Books into Vector DB

```bash
python ingest_books.py
```

This will generate a FAISS vector index in the `vectorstore/` directory.

#### 6. Start the Backend Server

```bash
python backend.py
```

#### 7. Run the Chatbot Frontend

```bash
streamlit run medibot.py
```

---

### 🧪 How It Works

1. **PDF Loader** extracts text from medical books
2. **LangChain Embeddings** convert text into vectors
3. **FAISS** stores these vectors
4. **User Query** is matched against relevant chunks
5. **Groq LLM** generates an answer using matched context

---

### 💬 Sample Query

> *"What are the symptoms of acne?"*

🧠 MediBot searches all medical PDFs, finds relevant sections, and answers in simple language with reference-based accuracy.

---

### 🖼️ Demo

> ![MediBot Screenshot 1](https://github.com/user/screenshots/medibot1.png)
> ![MediBot Screenshot 2](https://github.com/user/screenshots/medibot2.png)

---

### 🛠️ API Endpoint

`POST /query`

```json
{
  "question": "What is diabetes?",
  "model_name": "llama3-70b-quantized",
  "system_prompt": "Act as a medical expert",
  "top_k": 5
}
```

---



### 🙌 Credits

* Developed by [Tufan Dey](https://github.com/tufandey)
* Powered by [LangChain](https://www.langchain.com/), [Groq](https://www.groq.com/), and [FastAPI](https://fastapi.tiangolo.com/)


