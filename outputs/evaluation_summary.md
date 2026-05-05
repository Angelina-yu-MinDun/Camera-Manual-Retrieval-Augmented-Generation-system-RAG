# Evaluation Summary

The system was tested on 13 camera-operation questions across multiple camera models and evaluated with RAGAS. This evaluation used a reference-free setup: each record contained the user question, retrieved manual contexts, and generated response, but no ground-truth reference answer.

## RAGAS Metric Definitions

- **Faithfulness:** Measures whether the generated answer is supported by the retrieved contexts. A lower score suggests that parts of the answer may not be fully grounded in the manual excerpts.
- **Answer Relevancy:** Measures how well the generated answer addresses the user's question. A high score means the response is on-topic and useful for the query.
- **Context Precision Without Reference:** Measures whether the retrieved contexts are relevant to the user's question without requiring a ground-truth answer. This is suitable when there is no manually written reference answer for each question.

## Overall RAGAS Scores

| Metric | Score |
|---|---:|
| Faithfulness | 0.7614 |
| Answer Relevancy | 0.8499 |
| Context Precision Without Reference | 0.8510 |

## Interpretation

- Context precision was strong, suggesting the retriever usually surfaced relevant manual passages.
- Answer relevancy was strong, likely supported by query rewriting and hybrid retrieval.
- Faithfulness was solid but lower than the other metrics, reflecting occasional weaknesses where retrieved context did not fully support generated responses.

## Known Limitations

- Visual symbols and UI icons in camera manuals were difficult to interpret with a text-focused RAG pipeline.
- Repeated manual sections across camera modes sometimes introduced retrieval noise.
- Multimodal RAG could improve symbol recognition and diagram understanding, but was out of scope due to compute constraints.
