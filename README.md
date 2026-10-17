# RAG: Baseline Retrieval vs. Cross-Encoder Re-Ranking

LMA Assignment 1. I compare two retrieval pipelines over the same chunked copy of
**NIST SP 800-63B-4 (Digital Identity Guidelines: Authentication and Authenticator Management)**:

1. **Baseline** – bi-encoder (`all-MiniLM-L6-v2`) + FAISS, top 10 by cosine, top 3 go to the LLM.
2. **Re-ranking** – the same top 10 are re-scored by a cross-encoder
   (`cross-encoder/ms-marco-MiniLM-L-6-v2`), and the new top 3 go to the LLM with the same prompt.

Answers are generated with the Gemini API.

## How to run

```bash
pip install -r requirements.txt
# set your key first, e.g. on Windows PowerShell:  $env:GEMINI_API_KEY="..."
jupyter notebook rag_baseline_vs_rerank.ipynb
```

## Files

- `rag_baseline_vs_rerank.ipynb` – all the code, with outputs (pipelines, failure queries, latency)
- `NIST.SP.800-63B-4.pdf` – the document used as the corpus
- `report/report.pdf` – the written report
