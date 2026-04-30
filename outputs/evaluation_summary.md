# Evaluation Summary

The system was tested on 13 camera-operation questions across multiple camera models and evaluated with RAGAS.

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
