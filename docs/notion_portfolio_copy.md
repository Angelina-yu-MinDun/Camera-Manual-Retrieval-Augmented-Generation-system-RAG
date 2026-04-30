# Notion Portfolio Copy

## Project Name

Camera Manual RAG System

## Goal / Challenge

Camera manuals are long, technical, and difficult for users to search manually. This project built a RAG-based assistant that retrieves relevant manual sections and generates grounded answers to camera operation questions.

## What I Did

Built an end-to-end RAG pipeline using PDF parsing, OCR, semantic chunking, Hugging Face embeddings, Chroma vector storage, BM25 + vector hybrid retrieval, HyDE query expansion, Cohere reranking, Gemini answer generation, and RAGAS evaluation.

## Outcome / Impact

Achieved strong retrieval and answer quality, with RAGAS scores of Context Precision 0.8510, Answer Relevancy 0.8499, and Faithfulness 0.7614. The project also identified limitations around visual symbols and multimodal manual content.

## Tools

Python, LangChain, ChromaDB, Hugging Face Embeddings, BM25, Cohere Rerank, Gemini API, OpenAI API, RAGAS, OCR, Google Colab

## Suggested Tags

Data Analytics, Machine Learning, Generative AI, RAG, NLP, Information Retrieval, Evaluation
