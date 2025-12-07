**MedInSight-RAG: Retrieval-Augmented Biomedical Question Answering**

**A Comparative Study of BioGPT, Flan-T5, and Phi-2**

**University of New Haven**

**Authors: Muralidhar Kolimali, Sunaina Makkena, Spandana Dammanagari**

**1.Overview**

MedInSight-RAG is a biomedical Retrieval-Augmented Generation (RAG) system designed to improve factual accuracy and reasoning in biomedical question answering.

Because biomedical information is sensitive and high-stakes, Large Language Models (LLMs) often hallucinate facts. This project evaluates how RAG improves reliability across three LLMs:

**BioGPT**

**Flan-T5**

**Phi-2**

The pipeline integrates:

BioBERT embeddings

FAISS dense retrieval

LLM generation using three different models

Biomedical evaluation metrics (semantic similarity, factual accuracy, hallucination)

**2.Motivation**

Biomedical text is complex. Traditional LLMs:

Invent mechanisms

Misinterpret pathways

Provide unsupported claims

RAG reduces hallucination by grounding model responses in retrieved PubMed literature.

**3.System Architecture**

The MedInSight-RAG pipeline consists of:

Biomedical text embeddings (BioBERT)

FAISS similarity search on a 10k-passage corpus

Top-k evidence retrieval

RAG prompt construction

Answer generation using BioGPT, Flan-T5, or Phi-2

Evaluation via semantic and factual metrics

**Architecture Flow:**

User Query

     ↓
     
BioBERT Embedding

     ↓
     
FAISS Similarity Search

     ↓
     
Top-k Biomedical Evidence

     ↓
     
RAG Prompt Builder

     ↓
     
LLM Generation (BioGPT / Flan-T5 / Phi-2)

     ↓
     
Final Biomedical Answer

**4.Dataset**

We use a processed subset of the PubMedQA dataset, containing:

Domain-validated biomedical Q&A pairs

Extracted 1,000+ biomedical questions

A 10k-passage evidence retrieval corpus

Cleaned passages free from citations, extraneous references, and metadata

PubMedQA focuses on yes/no/maybe reasoning and is well-suited for RAG evaluation.

**5.Evaluation**

**Quantitative Metrics**

1.BERTScore F1 → semantic similarity

2.Factuality scoring using Flan-T5

**Qualitative Metrics**

1.Evidence usage

2.Biomedical plausibility

3.Hallucination severity

**6.Results Summary**

| Model   | Similarity | Accuracy | Composite |
| ------- | ---------- | -------- | --------- |
| BioGPT  | 0.81       | 0.72     | 0.765     |
| Flan-T5 | **0.87**   | **0.83** | **0.85**  |
| Phi-2   | 0.78       | 0.69     | 0.735     |

**7.Key Observations**

**Flan-T5** → Best factuality & grounding

**BioGPT** → Most fluent but hallucinates more

**Phi-2** → Efficient but weakest biomedical specificity

**8.Future Work**

1.Hybrid retrieval (dense + sparse)

2.Reranking with cross-encoders

3.Fine-tuning LLMs on biomedical evidence chains

4.Larger corpus expansion beyond PubMedQA

**9.Contributors**

1.Muralidhar Kolimali – Embeddings, FAISS, model integration

2.Sunaina Makkena – Dataset processing, evaluation

3.Spandana Dammanagari – Model experimentation, analysis

**10.Reference**

All details are based on our paper:
