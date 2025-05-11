# RAG Pipeline Implementation – Technical Test

This repository contains the implementation of a minimal Retrieval-Augmented Generation (RAG) pipeline as part of a technical assessment.

## 📄 Project Overview

The pipeline is designed to answer natural language questions using only one domain-specific document:
[A Survey on LLM-as-a-Judge (arXiv:2411.15594)](https://arxiv.org/abs/2411.15594).

It performs the following steps:

1. PDF to text extraction and cleaning (headers, footers, citations, references removed)
2. Chunking by logical document structure (e.g., 1, 2.1, 2.1.1)
3. Embedding of chunks using `all-MiniLM-L6-v2`
4. Indexing with FAISS for semantic search
5. Retrieval of top-k relevant chunks based on a user query
6. Prompt construction with context and question
7. Response generation using `TinyLlama/TinyLlama-1.1B-Chat-v1.0`
8. Cleaned final answer output with optional stop token trimming

---

## 💬 Example Test Question

> “What are the two main challenges that hinder the widespread application of the 'LLM-as-a-Judge' approach?”

---

## 🚀 Before running

### Install dependencies

```bash
pip install -r requirements.txt
```

---

## 🔧 Model Used

- Embedding: `sentence-transformers/all-MiniLM-L6-v2`
- Generation: `TinyLlama/TinyLlama-1.1B-Chat-v1.0`

No OpenAI key required. All models are open source and run locally.

---

## 📦 Files

- `rag_pipeline.ipynb` – main notebook with all steps
- `requirements.txt` – list of dependencies
- `publication_clean.txt` – cleaned version after manual processing
- `README.md` – project documentation

---
