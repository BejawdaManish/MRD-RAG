# 🧠 MRD-RAG: Multi-Round Diagnostic Retrieval-Augmented Generation

> **Enhancing Medical Diagnosis through Multi-Round Dialogue and Knowledge Retrieval**

## 📘 Overview

**MRD-RAG** (Multi-Round Diagnostic Retrieval-Augmented Generation) is a framework that mimics the diagnostic reasoning of real doctors by enabling **multi-round interactive diagnosis**.  
It enhances Large Language Models (LLMs) in medical diagnosis by integrating **retrieval-augmented generation (RAG)** with a **tree-structured medical knowledge base**.

Unlike traditional single-round RAG systems, MRD-RAG can analyze interconnections between diseases, proactively ask follow-up questions, and make more precise diagnostic decisions.

---

## 🚀 Key Features

- 🩺 **Doctor-like Dialogue** — Engages in multi-turn consultations to simulate real medical interviews.  
- 🌳 **DI-Tree Knowledge Base** — Tree-structured medical knowledge for 746 Modern Medicine (MM) and 130 Traditional Chinese Medicine (TCM) diseases.  
- 🧩 **Pseudo Medical History Alignment** — Bridges the semantic gap between patient utterances and disease data for more accurate retrieval.  
- ⚙️ **Modular Architecture** — Comprises three core modules:
  - **Retriever:** Fetches potential candidate diseases.
  - **Analyzer:** Evaluates inter-disease connections and reasoning.
  - **Doctor:** Generates responses, questions, or diagnoses.  
- 🧠 **LLM-Agnostic Design** — Compatible with general and medical LLMs (e.g., GPT, Qwen, Baichuan, HuatuoGPT).

---

## 🏗️ Architecture

```plaintext
Patient ↔ MRD-RAG System
           ├── Retriever → Retrieves disease info from DI-Tree
           ├── Analyzer  → Compares diseases & reasoning
           └── Doctor    → Generates medical inquiry or diagnosis
```

The **DI-Tree Knowledge Base** contains diagnosis-related details such as symptoms, clinical signs, and tests, structured for easy retrieval.

---

## 📊 Experimental Results

- 📈 MRD-RAG improves diagnostic accuracy by:
  - **+9.4%** over non-RAG LLMs  
  - **+6%** over single-round RAG  
- 👨‍⚕️ Human doctors rated MRD-RAG dialogues **21.75% more accurate** than baseline methods.
- 🧮 Works effectively across **Modern Medicine** and **Traditional Chinese Medicine** datasets.

---

## 🧬 Datasets

| Dataset | Type | Cases | Diseases | Description |
|----------|------|--------|-----------|--------------|
| CMB-Clin | MM | 74 | 66 | Complex Chinese medical benchmark |
| MM-Cases | MM | 609 | 609 | Synthesized modern medical cases |
| TCM-SD-100 | TCM | 100 | 33 | Public TCM benchmark subset |
| TCM-Cases | TCM | 130 | 130 | Synthesized traditional medicine cases |

---

## ⚙️ Installation & Usage

```bash
# Clone the repository
git clone https://github.com/<your-username>/MRD-RAG.git
cd MRD-RAG

# (Optional) Create and activate a virtual environment
python -m venv venv
source venv/bin/activate  # or venv\Scripts\activate on Windows

# Install dependencies
pip install -r requirements.txt
```

### Running the Framework

```bash
python mrd_rag_main.py --config configs/mrd_rag_config.json
```

(Adjust the script and config filenames according to your implementation.)

---

## 🧪 Evaluation Metrics

- **Diagnosis Accuracy** (GPT & Human Evaluation)
- **BLEU / ROUGE / METEOR** for text quality
- **MRR / Hits@n** for retrieval precision

---

## 📚 Reference

If you use this work, please cite:

> **MRD-RAG: Enhancing Medical Diagnosis with Multi-Round Retrieval-Augmented Generation**  
> Yixiang Chen, Penglei Sun, Xiang Li, Xiaowen Chu  
> *The Hong Kong University of Science and Technology (Guangzhou), 2025.*

[📄 Paper Link (arXiv:2504.07724)](https://arxiv.org/abs/2504.07724)

---

## 🧩 License

This project is released under the **MIT License**.

