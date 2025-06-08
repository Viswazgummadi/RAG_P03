# Civil Engineering RAG System

A Retrieval Augmented Generation (RAG) system for querying civil engineering documents using LLMs.

## Features

- Extracts text and tables from PDFs
- Stores embeddings in ChromaDB
- Uses Google Gemini for Q&A
- Built with LangChain + LangGraph
- CLI/Streamlit interface (optional)

## Tech Stack

- Python 3.10+
- LangChain, LangGraph
- Google Gemini API
- ChromaDB
- unstructured (for parsing)
- Sentence Transformers

## Setup

```bash
git clone <your-repo-url>
cd civil_eng_rag
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate
pip install -r requirements.txt
```

## .env Example

```env
GOOGLE_API_KEY="your_gemini_key"
GOOGLE_APPLICATION_CREDENTIALS="/path/to/service-account.json"
```

## Ingest Documents

```bash
python -m ingestion.run_ingestion --source_dir "path/to/pdf_documents"
```

## Run App

```bash
python -m rag_pipeline.app      # CLI
# or
streamlit run rag_pipeline/app.py  # UI
```

## Project Structure

```
civil_eng_rag/
├── ingestion/
│   └── run_ingestion.py
├── rag_pipeline/
│   └── app.py
├── requirements.txt
├── .env
└── README.md
```

## Dependencies Example

```txt
langchain
langchain-google-genai
langgraph
chromadb
sentence-transformers
unstructured[local-inference,gcp]
pypdf
python-dotenv
streamlit
```

## Notes

- Install poppler & tesseract for PDF parsing
- Enable billing for higher Gemini API limits