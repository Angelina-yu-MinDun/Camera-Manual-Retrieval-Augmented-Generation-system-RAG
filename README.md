# Camera Manual RAG System

A retrieval-augmented generation (RAG) system for answering natural-language questions about Olympus / OM System camera operation manuals.

## Project Overview

Camera manuals are long, technical, and difficult to search when users need a specific operation quickly. This project builds an end-to-end RAG assistant that retrieves relevant passages from camera manuals and generates grounded answers for user questions such as enabling silent shooting, using Face Priority AF, connecting Wi-Fi, formatting memory cards, and finding ISO or self-timer settings.

## Key Features

- Parses camera manuals from PDF files using `unstructured` high-resolution PDF partitioning.
- Extracts both text and image-based content with OCR via `pytesseract`.
- Applies semantic sentence-based chunking to preserve context quality.
- Creates dense embeddings with `intfloat/e5-base-v2`.
- Stores manual chunks in a Chroma vector database.
- Combines BM25 keyword retrieval with vector retrieval using a hybrid retriever.
- Uses HyDE-style hypothetical document embeddings to improve retrieval.
- Applies Cohere reranking to prioritize the most relevant contexts.
- Generates final answers with Gemini 2.0 Flash.
- Evaluates the RAG pipeline using RAGAS metrics.

## Tech Stack

- Python
- Google Colab
- LangChain
- ChromaDB
- Hugging Face sentence-transformers
- BM25 / rank_bm25
- Cohere Rerank
- Gemini API
- OpenAI API for RAGAS evaluation
- RAGAS
- unstructured
- pytesseract / OCR

## Repository Structure

```text
camera-manual-rag-system/
├── README.md
├── requirements.txt
├── .gitignore
├── notebooks/
│   ├── camera_manual_rag_clean.ipynb
│   └── camera_manual_rag_with_results.ipynb
├── data/
│   └── README.md
├── outputs/
│   └── evaluation_summary.md
└── docs/
    ├── github_publish_checklist.md
    ├── github_repository_setup.md
    └── notion_portfolio_copy.md
```

## Notebook Versions

- `camera_manual_rag_clean.ipynb`: GitHub-friendly version with outputs and execution counts removed.
- `camera_manual_rag_with_results.ipynb`: portfolio version that keeps key outputs, including generated answers and RAGAS evaluation results, while removing installation logs and long download widgets.

## Evaluation Results

The RAG system was evaluated with RAGAS on 13 camera-operation questions.

| Metric | Score | Interpretation |
|---|---:|---|
| Context Precision | 0.8510 | Strong retrieval of relevant manual passages. |
| Answer Relevancy | 0.8499 | Generated answers were highly relevant to user questions. |
| Faithfulness | 0.7614 | Most answers were grounded in retrieved manual content, with room for improvement. |

## Important Notes Before Publishing

This portfolio copy does not include the generated Chroma vector database because it is large and can be rebuilt from the notebook. The original manual PDFs should only be published if their redistribution rights are confirmed. A safer GitHub approach is to describe the data source and provide instructions for users to place manuals in a local `data/raw/` folder.

API keys should never be committed. Use environment variables or Colab secrets for `GEMINI_API_KEY`, `COHERE_API_KEY`, and `OPENAI_API_KEY`.

## Portfolio Summary

Built an end-to-end RAG pipeline for technical camera manuals, combining OCR, semantic chunking, dense vector search, BM25 retrieval, HyDE query expansion, reranking, Gemini answer generation, and RAGAS evaluation. The system achieved strong retrieval and answer relevance while surfacing key limitations around visual symbols and multimodal manual understanding.
