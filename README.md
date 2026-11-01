# PDF Q&A RAG Chatbot

A Retrieval-Augmented Generation (RAG) pipeline that lets you ask natural language questions over any PDF document and get context-aware answers with source page references.

## What it does

- Upload any PDF
- Ask questions in plain English
- Get accurate answers grounded in the document content
- See exactly which pages the answer came from

## Tech Stack

- **LangChain** — pipeline orchestration
- **FAISS** — vector database for semantic search
- **Google Gemini Embeddings** — document and query embeddings (gemini-embedding-2-preview)
- **Google Gemini 2.5 Flash** — LLM for answer generation
- **PyPDF** — PDF loading and parsing
- **Python / Google Colab** — development environment

## How it works

1. PDF is loaded and split into 500-character overlapping chunks
2. Each chunk is converted to a vector using Google Gemini Embeddings
3. Vectors are stored in a FAISS index for fast similarity search
4. On each query, the top 3 most relevant chunks are retrieved
5. Retrieved chunks + question are sent to Gemini to generate an answer

## Setup

1. Open the notebook in Google Colab
2. Install dependencies (Cell 1)
3. Upload your PDF
4. Get a free Gemini API key at [aistudio.google.com](https://aistudio.google.com)
5. Run all cells and start asking questions

## Sample Usage
```python
ask("What is the main topic of this document?")
ask("Explain the key concepts in chapter 3")
ask("What are the types of JSP directives?")
```

## Author

Divya Sharma — [github.com/Sharma0408](https://github.com/Sharma0408) | [LinkedIn](https://www.linkedin.com/in/divya-sharma-aug)
