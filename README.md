# MedInSight-RAG  
### Retrieval-Augmented Biomedical Question Answering  
**A Comparative Study of BioGPT, Flan-T5, and Phi-2**

---

## Abstract

Biomedical question answering requires precise, evidence-grounded reasoning. Large Language Models (LLMs) often hallucinate unsupported claims—especially in biomedical contexts where factual accuracy is critical. **MedInSight-RAG** introduces a retrieval-augmented pipeline combining BioBERT embeddings, FAISS dense retrieval, and top-k biomedical evidence integration to improve LLM reliability. We evaluate three models—**BioGPT**, **Flan-T5**, and **Phi-2**—across semantic similarity, factual correctness, and hallucination severity using a curated subset of the PubMedQA dataset. Results demonstrate that RAG significantly enhances factual grounding, with **Flan-T5 achieving the strongest overall performance**.

---

## 1. Introduction

LLMs excel at generating text but struggle in specialized, high-stakes biomedical domains. Common failure modes include hallucinated biological mechanisms, incorrect clinical claims, and misuse of terminology. Retrieval-Augmented Generation (RAG) mitigates these issues by grounding answers in domain-specific literature. **MedInSight-RAG** implements a complete retrieval → grounding → generation pipeline for biomedical QA.

---

## 2. System Architecture

MedInSight-RAG includes:

1. **BioBERT embeddings** for query and passage representation  
2. **FAISS dense retrieval** over a 10k-passage biomedical corpus  
3. **Top-k evidence selection**  
4. **RAG prompt construction**  
5. **LLM answer generation** (BioGPT, Flan-T5, Phi-2)  
6. **Evaluation metrics for semantic similarity, factuality, and hallucination severity**

---

## 3. Dataset

We use a curated subset of **PubMedQA**, containing:

- 1,000+ biomedical questions  
- 10,000 cleaned PubMed passages  
- Yes/No/Maybe reasoning labels  
- Cleaned text without citation or metadata noise  

---

## 4. Evaluation

### Quantitative Metrics
- **BERTScore F1** for semantic similarity  
- **Factuality scoring (Flan-T5 classifier)** for biomedical correctness  

### Qualitative Metrics
- Evidence usage  
- Biomedical plausibility  
- Hallucination severity  

---

## 5. Results

| Model   | Similarity | Accuracy | Composite |
|--------|------------|----------|-----------|
| BioGPT | 0.81       | 0.72     | 0.765     |
| **Flan-T5** | **0.87** | **0.83** | **0.85**  |
| Phi-2   | 0.78       | 0.69     | 0.735     |

---

## 6. Future Work

- Hybrid retrieval (dense + sparse)  
- Cross-encoder reranking  
- Fine-tuning LLMs on biomedical reasoning  
- Scaling beyond PubMedQA  

---

## 7. Contributors

- **Muralidhar Kolimali**  
- **Sunaina Makkena**  
- **Spandana Dammanagari**

---

## Citation

Kolimali M., Makkena S., Dammanagari S.  
MedInSight-RAG: Retrieval-Augmented Biomedical Question Answering.  
University of New Haven, 2025.
