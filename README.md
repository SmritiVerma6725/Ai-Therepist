AI Therapist
AI Therapist is an intelligent mental health chatbot designed to provide compassionate and thoughtful responses to users seeking emotional support. It leverages advanced language models and vector databases to understand and answer user queries based on mental health-related documents.

Features
Utilizes the Groq-powered LLaMA 3 model (llama3-8b-8192) for natural language understanding and generation.

Loads and processes PDF documents containing mental health information to build a knowledge base.

Employs vector embeddings and Chroma vector store for efficient document retrieval.

Implements a RetrievalQA chain to answer user questions with context-aware responses.

Interactive command-line interface for chatting with the AI therapist.

Optional Gradio-based web interface for easy user interaction.

Supports persistent storage of vector database for faster startup.

Installation
Clone the repository:

bash
git clone https://github.com/yourusername/AI-Therapist.git
cd AI-Therapist
Create and activate a Python virtual environment (recommended):

bash
python3 -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
Install the required packages:

bash
pip install -r requirements.txt
Alternatively, install key dependencies manually:

bash
pip install langchain langchain_groq langchain_community chromadb sentence-transformers pypdf gradio python-dotenv
Setup
Obtain a Groq API key by registering at Groq's platform.

Create a .env file in the project root with the following content:

text
GROQ_API_KEY=your_groq_api_key_here
Prepare your mental health PDF documents and place them in the Data folder inside the project directory.

Usage
Running the Chatbot (Command Line)
Run the main script:

bash
python main.py
The chatbot will initialize the model and vector database.

Type your queries to interact.

Type exit to quit.

Example:

text
Human: I feel anxious lately.
Chatbot: I'm sorry to hear that. Would you like to talk about what's causing your anxiety?
Running with Gradio Web Interface
You can launch a web UI using Gradio for easier interaction (code snippet included in the project).

How It Works
Document Loading: PDF files are loaded from the specified directory and split into chunks.

Embedding: Text chunks are converted into vector embeddings using HuggingFace's all-MiniLM-L6-v2 model.

Vector Store: Chroma stores these embeddings for fast similarity search.

Model: The Groq-powered LLaMA 3 model answers questions based on retrieved document context.

QA Chain: A RetrievalQA chain combines retrieval and generation with a custom prompt for empathetic responses.

Project Structure
text
AI-Therapist/
├── Data/                   # PDF documents for knowledge base
├── main.py                 # Main chatbot script
├── requirements.txt        # Python dependencies
├── .env                    # Environment variables (not committed)
├── README.md               # This file
└── GradioApp/              # Optional Gradio web app code
Dependencies
Python 3.11+

langchain, langchain_groq, langchain_community

chromadb

sentence-transformers

pypdf

gradio

python-dotenv

Notes
The chatbot is designed to provide supportive conversation but is not a substitute for professional mental health care.

Ensure your Groq API key is kept secure and not shared publicly.

The vector database persists locally to speed up subsequent runs.

License
MIT License
