# 📘 MedInSight-RAG  
### Retrieval-Augmented Biomedical Question Answering  
**A Comparative Study of BioGPT, Flan-T5, and Phi-2**

---

## 🧬 Overview

**MedInSight-RAG** is a biomedical Retrieval-Augmented Generation (RAG) system designed to improve factual accuracy, reduce hallucinations, and enhance reasoning in biomedical question answering.  

This project compares three LLMs:

- **BioGPT**
- **Flan-T5**
- **Phi-2**

The system integrates:

- BioBERT embeddings  
- FAISS dense retrieval  
- Top-k evidence extraction  
- Structured RAG prompting  
- Biomedical evaluation metrics  

MedInSight-RAG demonstrates how retrieval-grounded reasoning substantially improves LLM behavior in the biomedical domain.

---

## 🧠 Motivation

Biomedical QA requires:

- factual correctness  
- domain-aware reasoning  
- evidence-grounded responses  

However, general-purpose LLMs often:

- hallucinate biological mechanisms  
- misinterpret complex pathways  
- generate unsupported scientific claims  

RAG provides a principled solution:  
**retrieve first → reason with evidence → generate controlled answers**.

---

## 🧱 System Architecture

### 📐 Architecture Diagram (GitHub-Compatible Mermaid)

```mermaid
flowchart TD

A[User Question] --> B[BioBERT Embeddings]

B --> C[10k-Passage\nBiomedical Corpus]
C --> D[FAISS Dense\nRetrieval]
D --> E[Top-k Evidence\nRetrieval]

E --> F[RAG Prompt\nConstruction]
F --> G[LLM Answer Generation\nBioGPT / Flan-T5 / Phi-2]

G --> H[Evaluation Framework\nSemantic Similarity\nFactual Accuracy\nHallucination Analysis]




Dataset

The system uses a curated version of the PubMedQA biomedical dataset.

Dataset Components

1,000+ biomedical QA pairs

10,000 cleaned and preprocessed evidence passages

Removed:

citation noise

PubMed metadata

non-semantic identifiers

Why PubMedQA?

It emphasizes factual biomedical reasoning, making it an ideal benchmark for RAG systems requiring:

domain fidelity

controlled hallucination

evidence grounding

🧪 Evaluation Framework

Our evaluation pipeline is structured around quantitative and qualitative biomedical metrics.

🔢 1. Quantitative Metrics
BERTScore F1

Evaluates semantic similarity

Better suited to biomedical semantics than BLEU/ROUGE

Factuality Scoring (Flan-T5)

Evaluates correctness of biomedical claims

Trained to verify scientific statements

🔬 2. Qualitative Metrics
Evidence Attribution

Evaluates whether generated answers correctly use retrieved passages.

Biomedical Plausibility

Assesses:

mechanistic correctness

domain terminology integrity

reasoning validity

Hallucination Severity

Categories:

factual misinterpretation

mechanistic hallucination

fabricated biological claims

📊 Results Summary
Model Comparison Table
Model	Semantic Similarity	Factual Accuracy	Composite Score
BioGPT	0.81	0.72	0.765
Flan-T5	0.87	0.83	0.85
Phi-2	0.78	0.69	0.735
🔍 Key Insights
⭐ Flan-T5 — Best Overall

Strongest evidence grounding

Best factual accuracy

Lowest hallucination rate

⭐ BioGPT — Most Fluent, Least Reliable

Generates domain-sounding text

But prone to mechanistic hallucination

⭐ Phi-2 — Lightweight but Limited

Efficient

Reasonable performance on simple questions

Struggles with biomedical depth

🔮 Future Work

The project identifies several opportunities for expanded research:

1️⃣ Hybrid Retrieval Systems

Combine:

FAISS dense retrieval

BM25 sparse retrieval
for higher recall and precision.

2️⃣ Cross-Encoder Reranking

Use biomedical cross-encoders to refine top-k passages.

3️⃣ Fine-Tuning LLMs

Training BioGPT/Flan-T5/Phi-2 on:

biomedical reasoning chains

citation-aligned datasets

PubMed-scale corpora

4️⃣ Extended Corpora

Beyond PubMedQA:

full PubMed abstracts

clinical notes

NIH trial summaries

5️⃣ Evidence-Linked Explanations

Generate answers with explicit citation mapping:
“Evidence from Passage 3 suggests that…”

👥 Contributors

Muralidhar Kolimali — Embeddings, FAISS retrieval, model integration

Sunaina Makkena — Dataset preparation, evaluation design

Spandana Dammanagari — LLM experiments, qualitative analysis
