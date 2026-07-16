# Analysis

This folder contains four Jupyter notebooks (`.ipynb`), developed in **Google Colab** (or any compatible Jupyter Notebook environment), for reproducing the analyses presented in this study.

## Contents

| Notebook | Description |
|----------|-------------|
| **Kappa+Quality.ipynb** | Computes the **Quadratic Weighted Cohen's Kappa** for inter-rater agreement.|
| **ROUGE+BERTSCORE.ipynb** | Computes the automatic evaluation metrics **ROUGE-L** and **BERTScore** for all response-generation configurations. |
| **RQ1_and_RQ2.ipynb** | Performs the statistical analyses for **RQ1** and **RQ2**, including descriptive statistics and Correctnes |
| **RQ3_ISO.ipynb** | Analyzes the user evaluation data to answer **RQ3**, including descriptive statistics, reliability analysis (Cronbach's alpha), and Quality Satisfaction across the nine ISO/IEC 25010 quality aspects. |

## Research Questions

- **RQ1:** *How does the response-generation configuration (LLM-only, LLM+RAG, or LLM+RAG+PA at varying retrieval depths) affect the correctness and relevance of CAPI's responses to informatics-domain queries?*

- **RQ2:** *To what extent do automatic evaluation metrics (BERTScore and ROUGE-L) agree with human judgments of response quality across these configurations?*

- **RQ3:** *How do real users of CAPI perceive its overall software quality, as measured across the nine quality aspects drawn from the ISO/IEC 25010 Quality in Use and Product Quality models?*

## Requirements

The notebooks can be executed using:

- Google Colab
- Jupyter Notebook
- JupyterLab

Before running the notebooks, ensure that the required datasets are available in the corresponding data directory and that all required Python dependencies are installed.

## Reproducibility

These notebooks reproduce the analyses and statistical results reported in the paper, including:

- Quadratic Weighted Cohen's Kappa for inter-rater agreement.
- ROUGE-L and BERTScore automatic evaluation metrics.
- Statistical analyses for RQ1 and RQ2.
- Quality Satisfaction and reliability analysis (Cronbach's alpha) for RQ3.
- Tables and figures presented in the manuscript.
