# Retrieval-Augmented Generation (RAG) Pipeline using LangChain, ChromaDB, and Gemini

## Overview

This project demonstrates a Retrieval-Augmented Generation (RAG) pipeline that enables Large Language Models (LLMs) to answer questions based on the content of a PDF document.

The application processes a PDF document on Quantum Computing, converts the document into vector embeddings, stores them in ChromaDB, retrieves relevant context based on user queries, and generates responses using Google's Gemini model.

---

## Architecture

```text
PDF Document
      │
      ▼
Document Loader
      │
      ▼
Text Splitting & Chunking
      │
      ▼
Embedding Generation
      │
      ▼
Chroma Vector Store
      │
      ▼
Similarity Search
      │
      ▼
Context Retrieval
      │
      ▼
Gemini LLM
      │
      ▼
Generated Response
```

---

## Technologies Used

| Component | Technology |
|------------|------------|
| Programming Language | Python |
| Framework | LangChain |
| Document Source | PDF on Quantum Computing |
| Text Splitter | RecursiveCharacterTextSplitter |
| Embeddings | HuggingFaceEmbeddings |
| Vector Store | ChromaDB |
| Similarity Search | L2 Euclidean Distance |
| LLM | Gemini Flash |
| Environment | Python Virtual Environment |

---

## Features

- Load and process PDF documents
- Split documents into meaningful chunks
- Generate embeddings using Hugging Face models
- Store embeddings in ChromaDB
- Perform semantic similarity search
- Retrieve context relevant to user queries
- Generate context-aware responses using Gemini
- End-to-end implementation of a RAG workflow

---

## Project Workflow

### 1. Document Loading

The PDF document is loaded and parsed into text using LangChain document loaders.

### 2. Text Splitting & Chunking

The extracted text is divided into smaller chunks using `RecursiveCharacterTextSplitter`.

Benefits:
- Improved retrieval accuracy
- Better context relevance
- Efficient embedding generation

### 3. Embedding Generation

Each chunk is converted into a vector representation using `HuggingFaceEmbeddings`.

These embeddings capture the semantic meaning of the text and enable similarity-based retrieval.

### 4. Vector Storage

The generated embeddings are stored in ChromaDB.

ChromaDB acts as a vector database that allows efficient searching of semantically similar content.

### 5. Similarity Search

When a user submits a query:

- The query is converted into an embedding
- ChromaDB compares the query vector with stored vectors
- Relevant document chunks are retrieved using L2 Euclidean Distance

### 6. Response Generation

The retrieved context is combined with the user's question and sent to Gemini Flash.

The LLM generates a response grounded in the retrieved document content.

---

## Example Query

### Question

```text
What is quantum entanglement?
```

### Process

1. Convert the query into an embedding
2. Retrieve relevant chunks from ChromaDB
3. Pass the retrieved context and query to Gemini
4. Generate the final response

---

## Project Structure

```text
RAG-Project/
│
├── data/
│   └── quantum_computing.pdf
│
├── notebooks/
│   └── rag_pipeline.ipynb
│
├── src/
│   ├── document_loader.py
│   ├── embeddings.py
│   ├── vector_store.py
│   └── retrieval.py
│
├── requirements.txt
├── README.md
└── .env
```

---

## Installation

### Clone the Repository

```bash
git clone https://github.com/your-username/rag-project.git
cd rag-project
```

### Create a Virtual Environment

```bash
python -m venv .venv
```

### Activate the Environment

#### Windows

```bash
.venv\Scripts\activate
```

#### Linux / macOS

```bash
source .venv/bin/activate
```

### Install Dependencies

```bash
pip install -r requirements.txt
```

---

## Configuration

Create a `.env` file in the project root:

```env
GOOGLE_API_KEY=your_api_key
```

---

## Running the Project

```bash
python app.py
```

or run the Jupyter Notebook:

```bash
jupyter notebook
```

---

## Skills Demonstrated

- Retrieval-Augmented Generation (RAG)
- LangChain
- ChromaDB
- Vector Embeddings
- Semantic Search
- Prompt Engineering
- Document Processing
- Context Retrieval
- Gemini Integration
- Python Development

---
