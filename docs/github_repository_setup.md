# Repository Setup Notes

Suggested GitHub repository name:

```text
camera-manual-rag-system
```

Suggested description:

```text
RAG system for answering Olympus / OM System camera manual questions using OCR, hybrid retrieval, reranking, Gemini generation, and RAGAS evaluation.
```

Recommended visibility:

```text
Public, after confirming PDF manual redistribution rights and excluding raw manuals/vector database files.
```

## Files To Include

Include these files in the GitHub repository:

```text
README.md
requirements.txt
.env.example
.gitignore
data/README.md
docs/github_publish_checklist.md
docs/notion_portfolio_copy.md
outputs/evaluation_summary.md
notebooks/camera_manual_rag_clean.ipynb
notebooks/camera_manual_rag_with_results.ipynb
```

Do not include these by default:

```text
notebooks/camera_manual_rag_original.ipynb
data/raw/
rag_project/
*.pkl
*.pickle
*.sqlite3
*.bin
*_vector_db/
```

## Command-Line Steps If Git Is Installed Later

```bash
git init
git add README.md requirements.txt .env.example .gitignore data/README.md docs outputs notebooks/camera_manual_rag_clean.ipynb notebooks/camera_manual_rag_with_results.ipynb
git commit -m "Create camera manual RAG portfolio project"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/camera-manual-rag-system.git
git push -u origin main
```
