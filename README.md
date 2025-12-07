# 📘 MedInSight-RAG  
### Retrieval-Augmented Biomedical Question Answering  
**A Comparative Study of BioGPT, Flan-T5, and Phi-2**

---

## 🧬 Overview

**MedInSight-RAG** is a biomedical Retrieval-Augmented Generation (RAG) system designed to enhance factual accuracy, evidence usage, and scientific reliability in biomedical question answering.  
This project compares three widely used LLMs:

- **BioGPT**
- **Flan-T5**
- **Phi-2**

By grounding model outputs in **domain-validated PubMed evidence**, MedInSight-RAG significantly reduces hallucinations and improves biomedical reasoning.

---

## 🧠 Academic Motivation

Biomedical question answering is a **high-stakes, evidence-sensitive** domain.  
Conventional LLMs frequently:

- invent biological mechanisms  
- misinterpret molecular pathways  
- produce unsupported clinical/biomedical claims  

RAG offers a principled solution by retrieving domain-specific evidence before generation, enabling:

- increased factual grounding  
- reduced hallucination rates  
- improved semantic alignment with gold biomedical answers  
- greater trustworthiness in real-world biomedical contexts  

---

## 🧱 System Architecture

The MedInSight-RAG architecture integrates embedding-based retrieval and multi-model answer generation.  
This pipeline mirrors modern RAG systems used in biomedical NLP research.

### 📐 **Architecture Diagram (Mermaid)**  
*(This will render automatically on GitHub)*

```mermaid
flowchart TD

A[User Question] --> B[BioBERT Embeddings]

B --> C[10k-Passage Biomedical Corpus]
C --> D[FAISS Dense Retrieval]
D --> E[Top-k Evidence Retrieval]

E --> F[RAG Prompt Construction]
F --> G[LLM Answer Generation<br>(BioGPT / Flan-T5 / Phi-2)]

G --> H[Evaluation Framework<br>• BERTScore Similarity<br>• Factual Accuracy<br>• Hallucination Severity]
