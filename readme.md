🔗 Smart URL Answer Bot

An AI-powered Retrieval-Augmented Generation (RAG) application that allows users to ask questions based on content extracted from web URLs.

Built with Streamlit + LangChain + Groq + HuggingFace + ChromaDB.

🚀 Features

🌐 Extracts content from multiple URLs

🧠 Uses RAG pipeline for accurate answers

🔎 Semantic search using vector embeddings

⚡ Fast LLM responses via Groq

📚 Displays answer sources

🎯 Simple Streamlit UI

🏗️ Project Architecture
User URLs → Web Scraping → Text Chunking → Embeddings →
Chroma Vector DB → Retriever → Groq LLM → Answer + Sources
📂 Project Structure
├── main.py          # Streamlit frontend
├── rag.py           # RAG pipeline logic
├── resources/
│   └── vector_store # Persistent Chroma DB
├── .env             # API keys
└── README.md
⚙️ Tech Stack

Frontend: Streamlit

LLM: Groq (Llama 3.3 70B)

Embeddings: HuggingFace GTE Base

Vector DB: ChromaDB

Framework: LangChain

Loader: UnstructuredURLLoader

🔧 Installation
1️⃣ Clone the repository
git clone https://github.com/your-username/smart-url-answer-bot.git
cd smart-url-answer-bot
2️⃣ Create virtual environment
python -m venv venv
source venv/bin/activate   # Linux/Mac
venv\Scripts\activate      # Windows
3️⃣ Install dependencies
pip install -r requirements.txt
4️⃣ Setup environment variables

Create a .env file:

HUGGINGFACEHUB_API_TOKEN=your_huggingface_token
GROQ_API_KEY=your_groq_api_key

⚠️ Required because the app authenticates HuggingFace before loading embeddings. 

rag

▶️ Run the Application
streamlit run main.py

The app will open in your browser.

🧪 How to Use
Step 1: Enter URLs

Add up to 3 URLs in the sidebar

Click 🚀 Process URLs

The system will:

Initialize components

Scrape web pages

Split into chunks

Store in vector database

(This workflow is implemented in process_urls().) 

rag

Step 2: Ask Questions

Type your question

Press Enter

Get AI-generated answer + sources

The Streamlit UI handles the interaction and displays results. 

main

🧠 How It Works (Technical Flow)
1. URL Loading

Uses:

UnstructuredURLLoader

to scrape webpage content.

2. Text Chunking

Uses recursive splitter:

Chunk size: 1000

Multiple separators

3. Embeddings

Model used:

Alibaba-NLP/gte-base-en-v1.5
4. Vector Storage

Database: Chroma

Persistent storage enabled

Collection name: real_estate

5. Retrieval + Generation

Pipeline:

Retriever → RetrievalQAWithSourcesChain → Groq LLM

Model:

llama-3.3-70b-versatile
📌 Requirements

Typical dependencies:

streamlit
langchain
langchain-community
langchain-groq
langchain-chroma
langchain-huggingface
huggingface_hub
python-dotenv
chromadb
unstructured
⚠️ Important Notes

You must process URLs first before asking questions.

HuggingFace token is mandatory.

Internet connection required for scraping.

Large pages may take time to embed.

🔮 Future Improvements

 Support more than 3 URLs

 Add PDF support

 Add caching

 Improve UI styling

 Add chat history

 Deploy on Streamlit Cloud

👨‍💻 Author

Prajwal Poojary

⭐ If You Like This Project

Give it a star on GitHub and share it!
