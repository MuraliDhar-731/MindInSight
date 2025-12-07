# 📘 MedInSight-RAG  
### Retrieval-Augmented Biomedical Question Answering  
**A Comparative Study of BioGPT, Flan-T5, and Phi-2**

---

## 🧬 Overview

**MedInSight-RAG** is a biomedical Retrieval-Augmented Generation (RAG) system designed to improve factual accuracy, reduce hallucinations, and enhance reasoning in biomedical question answering.

This project evaluates three LLMs:

- **BioGPT**
- **Flan-T5**
- **Phi-2**

The system integrates:

- BioBERT embeddings  
- FAISS dense retrieval  
- Top-k evidence extraction  
- Structured RAG prompting  
- Biomedical evaluation metrics  

---

## 🧠 Motivation

Biomedical literature is complex and high-stakes. General-purpose LLMs often:

- hallucinate biological mechanisms  
- misinterpret molecular pathways  
- produce unsupported biomedical claims  

MedInSight-RAG addresses this by grounding responses in **real PubMed evidence**, significantly improving factuality and reasoning quality.

---

## 🧱 System Architecture

Below is the **validated GitHub-compatible Mermaid architecture diagram**.

### 📐 Architecture Diagram

```mermaid
flowchart TD

A[User Question] --> B[BioBERT Embeddings]

B --> C[10k-Passage\nBiomedical Corpus]
C --> D[FAISS Dense\nRetrieval]
D --> E[Top-k Evidence\nRetrieval]

E --> F[RAG Prompt\nConstruction]
F --> G[LLM Answer Generation\nBioGPT / Flan-T5 / Phi-2]

G --> H[Evaluation Framework\nSemantic Similarity\nFactual Accuracy\nHallucination Analysis]
