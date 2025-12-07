# 📘 MedInSight-RAG  
### Retrieval-Augmented Biomedical Question Answering  
*A Comparative Study of BioGPT, Flan-T5, and Phi-2*

---

## 🧬 Overview

**MedInSight-RAG** is a biomedical Retrieval-Augmented Generation (RAG) system designed to improve factual accuracy, reduce hallucinations, and enhance reasoning in biomedical question answering.

The project evaluates three Large Language Models:

- **BioGPT**  
- **Flan-T5**  
- **Phi-2**

All models are grounded using:

- **BioBERT embeddings**  
- **FAISS dense retrieval**  
- **Top-k PubMed passages**  
- **RAG-style prompt construction**

This ensures that generated answers are evidence-based, scientifically plausible, and more reliable for biomedical use cases.

---

## 🏥 Why RAG for Biomedical QA?

Biomedical text is high-stakes and highly specialized.  
Traditional LLMs often:

- Hallucinate biological mechanisms  
- Misinterpret pathways  
- Generate unsupported claims  
- Confuse similar medical terminology  

**RAG mitigates these issues** by grounding model outputs in retrieved biomedical literature, improving both factual accuracy and reasoning.

---

## 🏗️ System Architecture

The MedInSight-RAG pipeline includes:

1. **BioBERT** → Convert passages into dense biomedical embeddings  
2. **FAISS** → Perform similarity search over a 10k-passage PubMed corpus  
3. **Top-k Retrieval** → Select evidence passages  
4. **RAG Prompting** → Insert evidence into model prompt  
5. **LLM Answer Generation** → BioGPT / Flan-T5 / Phi-2  
6. **Evaluation** → Semantic similarity + factuality scoring  

**Architecture Flow**

![Architecture](https://github.com/user-attachments/assets/c498ccc2-a5c2-4c0d-b3d6-6d08af033c00)

---

## 📚 Dataset

We use a curated subset of **PubMedQA**, containing:

- 1,000+ biomedical questions  
- Cleaned abstracts free of citation clutter  
- A 10k-passage retrieval corpus  
- Yes / No / Maybe reasoning labels  

PubMedQA is ideal for RAG because it emphasizes **fact-based biomedical reasoning**.

---

## 📊 Evaluation Metrics

### **Quantitative**
- **BERTScore F1** – Semantic similarity  
- **Factuality scoring (Flan-T5 classifier)**  

### **Qualitative**
- Evidence usage  
- Biomedical plausibility  
- Hallucination severity  

---

## 🧪 Results Summary

| Model   | Similarity | Accuracy | Composite |
|--------|------------|----------|-----------|
| BioGPT | 0.81       | 0.72     | 0.765     |
| **Flan-T5** | **0.87** | **0.83** | **0.85**  |
| Phi-2   | 0.78       | 0.69     | 0.735     |

### Key Findings

- **Flan-T5** → Best overall factual grounding  
- **BioGPT** → Highly fluent but more hallucinations  
- **Phi-2** → Lightweight but lowest biomedical specificity  

---

## 🔮 Future Work

- Hybrid retrieval (dense + sparse)  
- Cross-encoder reranking  
- Fine-tuning models on biomedical evidence chains  
- Expansion to full PubMed corpus  

---

## 👥 Contributors

- **Muralidhar Kolimali** – Embeddings, FAISS, model integration  
- **Sunaina Makkena** – Dataset processing, evaluation  
- **Spandana Dammanagari** – Model experimentation, qualitative analysis  

---

## 📖 Citation

