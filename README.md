# 📘 MedInSight-RAG  
### Retrieval-Augmented Biomedical Question Answering  
*A Comparative Study of BioGPT, Flan-T5, and Phi-2*

---

## 🧬 Overview

**MedInSight-RAG** is a biomedical Retrieval-Augmented Generation (RAG) system designed to improve factual accuracy, reduce hallucinations, and enhance reasoning in biomedical question answering.

This project evaluates three Large Language Models:

- **BioGPT**
- **Flan-T5**
- **Phi-2**

The pipeline integrates:

- BioBERT embeddings  
- FAISS dense retrieval  
- Top-k evidence extraction  
- Structured RAG prompting  
- Biomedical evaluation metrics  

This ensures answers are grounded, scientifically valid, and more reliable compared to vanilla LLM generation.

---

## 🏥 Why Biomedical RAG?

Biomedical information is **high-stakes**, requiring precision and evidence.  
Traditional LLMs often:

- Hallucinate mechanisms  
- Misinterpret biological pathways  
- Produce unsupported claims  

To mitigate this, MedInSight-RAG retrieves real **PubMed** evidence and grounds model outputs, significantly reducing hallucinations and improving factual accuracy.

---

## 📚 Dataset

The system uses a curated subset of **PubMedQA**, consisting of:

- 1,000+ biomedical questions  
- A 10k-passage evidence corpus  
- Cleaned abstracts (no citation clutter or metadata noise)  
- Yes / No / Maybe reasoning labels  

PubMedQA is ideal because it emphasizes **fact-based biomedical reasoning**, not open-ended generation.

---

## 🧪 Evaluation Metrics

### **Quantitative Metrics**
- **BERTScore F1** → Semantic similarity between generated and gold answers  
- **Factuality scoring (Flan-T5 classifier)** → Checks biomedical accuracy  

### **Qualitative Metrics**
- Biomedical plausibility  
- Evidence usage  
- Hallucination severity  

---

## 📊 Results Summary

| Model   | Similarity | Accuracy | Composite |
|---------|------------|----------|-----------|
| BioGPT  | 0.81       | 0.72     | 0.765     |
| **Flan-T5** | **0.87** | **0.83** | **0.85**  |
| Phi-2   | 0.78       | 0.69     | 0.735     |

### 🔍 Key Insights

- **Flan-T5** → Best factual grounding + best overall performance  
- **BioGPT** → Highly fluent but more hallucinations  
- **Phi-2** → Efficient but limited biomedical specificity  

---

## 🔮 Future Work

- Hybrid retrieval (dense + sparse)  
- Cross-encoder reranking  
- Fine-tuning LLMs on biomedical evidence chains  
- Scaling beyond PubMedQA to full PubMed  

---

## 👥 Contributors

- **Muralidhar Kolimali** — Embeddings, FAISS retrieval, model integration  
- **Sunaina Makkena** — Dataset processing, evaluation  
- **Spandana Dammanagari** — Model experimentation, qualitative analysis  

---

## 📖 Citation

