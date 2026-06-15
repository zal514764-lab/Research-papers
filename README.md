BERT_vs_GPT:
1. BERT vs. GPT-4 for Information Retrieval
Description
Scholarly comparative analysis of BERT (bidirectional encoder) and GPT-4 (autoregressive decoder) for information retrieval tasks, examining architectural differences, pre-training objectives, and empirical performance on retrieval benchmarks.

Technologies
BERT (Base: 110M params, Large: 340M params)

GPT-4 (hundreds of billions of params)

Dense Passage Retrieval (DPR)

ColBERT (late interaction retrieval)

Retrieval-Augmented Generation (RAG)

FAISS (approximate nearest neighbor indexing)

Models Evaluated
BERT-based bi-encoders (DPR, SBERT)

BERT-based cross-encoders (MonoBERT, RocketQA)

GPT-4 as reranker (listwise setting)

GPT-4 as generator in RAG pipelines

Results
Model / System	Benchmark	Metric	Score
DPR (BERT-based)	Natural Questions	Top-20 accuracy	79.4%
BM25 (baseline)	Natural Questions	Top-20 accuracy	59.1%
RocketQA	Natural Questions	Top-1 accuracy	74.0%
MonoBERT (cross-encoder)	MS MARCO	MRR@10	>0.39
ColBERT	MS MARCO	Recall@1000	96.8%
Key Concepts
Bidirectional vs. autoregressive attention: BERT conditions on left+right context; GPT-4 uses causal (unidirectional) attention

Dense retrieval: Queries and documents encoded as vectors; similarity computed in embedding space

Retrieval-Augmented Generation (RAG): BERT retrieves passages; GPT-4 synthesizes answers

Cross-encoder reranking: BERT processes query-document pairs directly for high-precision relevance scoring

Generative retrieval (DSI): Model generates document identifiers directly (emerging paradigm)

Short Summary
BERT-class encoders retain a structural advantage for dense retrieval and semantic matching due to their bidirectional architecture and efficient offline indexing (sub-second latency on 21M passages). GPT-4 excels as a reader/synthesizer in RAG pipelines but is impractical as a first-stage retriever due to high inference cost. Empirical evidence shows BERT-based systems outperform BM25 by 20+ percentage points on open-domain QA, while GPT-4's strength lies in reasoning over retrieved context. The paper concludes the models are complementary, not competitive.

