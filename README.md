
# CAPI: A Retrieval-Augmented LLM Chatbot for Informatics Academic Consultation

This repository contains the **replication package** accompanying the paper:

> **Evaluating a Retrieval-Augmented LLM Chatbot for Academic Consultation: Configuration, Correctness, and Quality-in-Use**

The repository provides the source code, experimental datasets, analysis notebooks, and supporting materials required to reproduce the experiments and statistical analyses reported in the paper.

---

## Repository Structure

```text
.
├── 01_Knowledge_Base/      Sample knowledge base
├── 02_Ablation_Test/       Ablation experiment notebooks
├── 03_Data/                Experimental datasets
├── 04_CAPI_System/         Gradio-based chatbot implementation
├── 05_Analysis/            Statistical analysis notebooks
├── LICENSE
├── CITATION.cff
└── README.md
```

Each folder includes a dedicated `README.md` describing its contents and usage.

---

## Research Questions

The experiments reported in the paper address the following research questions:

**RQ1.** How does the response-generation configuration (LLM-only, LLM+RAG, or LLM+RAG+Prompt Adaptation at varying retrieval depths) affect the correctness and relevance of CAPI's responses to informatics-domain queries?

**RQ2.** To what extent do automatic evaluation metrics (BERTScore and ROUGE-L) agree with human judgments of response quality across these configurations?

**RQ3.** How do real users of CAPI perceive its overall software quality, as measured across the nine quality aspects drawn from the ISO/IEC 25010 Quality in Use and Product Quality models?

---

## Repository Contents

### 01_Knowledge_Base

Contains a **sample** of the knowledge base used by CAPI.

The complete knowledge base consists of **291 curated question–answer (QA) pairs** compiled from:

* Informatics Study Program curriculum documents;
* University academic regulations and guidelines; and
* Relevant regulations issued by the Government of Indonesia.

Only a representative subset is included in this repository due to copyright and institutional data-sharing restrictions.

### 02_Ablation_Test

Contains Jupyter notebooks used to generate chatbot responses under the five response-generation configurations evaluated in this study.

### 03_Data

Contains the datasets required to reproduce the experimental analyses, including:

* Human evaluation scores from two independent raters;
* Ground-truth answers;
* BERTScore evaluation results;
* ROUGE-L evaluation results; and
* ISO/IEC 25010 user evaluation responses.

All released datasets have been anonymized, and personally identifiable information has been removed.

### 04_CAPI_System

Contains the implementation of the CAPI chatbot, including the Gradio-based web interface used during the user evaluation.

### 05_Analysis

Contains Jupyter notebooks for reproducing the statistical analyses reported in the paper, including:

* Quadratic Weighted Cohen's Kappa;
* BERTScore;
* ROUGE-L;
* Quality Satisfaction analysis;
* Statistical analyses for RQ1–RQ3; and
* Figures and tables presented in the manuscript.

---

## Software Requirements

The notebooks were developed using **Google Colab** and are compatible with:

* Google Colab
* Jupyter Notebook
* JupyterLab

The primary Python dependencies include:

* transformers
* sentence-transformers
* torch
* gradio
* jsonlines
* pandas
* numpy
* scikit-learn

---

## Reproducibility

This repository enables researchers to reproduce the experiments reported in the paper, including:

* Response generation under five ablation configurations;
* Automatic evaluation using BERTScore and ROUGE-L;
* Human evaluation and inter-rater agreement using Quadratic Weighted Cohen's Kappa;
* Statistical analyses addressing RQ1–RQ3; and
* Quality Satisfaction analysis based on the ISO/IEC 25010 quality model.

---

## Replication Package

The archived replication package is permanently available on **Zenodo**:

**DOI:** https://doi.org/10.5281/zenodo.21395509

The GitHub repository hosts the latest development version, while the Zenodo archive preserves the version associated with the published experiments. Zenodo assigns persistent version-specific DOIs to support reproducibility.

---

## Citation

If you use this repository in your research, please cite the accompanying paper and the archived replication package.

Citation metadata are provided in the `CITATION.cff` file.

---

## License

* **Source code:** Apache License 2.0
* Other materials are distributed according to the licenses specified within the repository.

---

## Contact

**Luh Gede Surya Kartika**

Universitas Hindu Negeri I Gusti Bagus Sugriwa Denpasar

Email: [suryakartika@uhnsugriwa.ac.id](mailto:suryakartika@uhnsugriwa.ac.id)

ORCID: https://orcid.org/0000-0001-9895-1418

