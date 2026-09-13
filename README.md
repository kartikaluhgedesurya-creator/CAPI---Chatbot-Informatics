# CAPI: A Retrieval-Augmented LLM Chatbot for Informatics Academic Consultation

This repository contains the **replication package** accompanying the paper:

> **Evaluating a Retrieval-Augmented LLM Chatbot for Academic Consultation: Configuration, Correctness, and Quality-in-Use**

The replication package provides the source code, experimental datasets, analysis notebooks, and supporting materials required to reproduce the experiments and statistical analyses reported in the paper.

## Repository Structure

The replication package is organized into the following folders:

```text
.
├── 01_Knowledge Base/       Knowledge-base materials
├── 02_System/               CAPI system implementation
├── 03_Data/                 Experimental datasets
├── 04_Generation/           Response-generation experiments
├── 05_Analysis/             Statistical analysis notebooks
├── LICENSE
├── CITATION.cff
└── README.md
```

Each folder contains a dedicated `README.md` describing its contents and, where applicable, the steps required to run the associated notebooks or scripts.

> **Important:** Keep the replication-package folder structure unchanged. Several notebooks and scripts use relative paths to access files in other folders.

## Getting Started

The replication package is designed to be used with **Google Drive and Google Colab**. To avoid path-related errors, place the extracted replication-package folder directly in the root of your Google Drive (`My Drive`), rather than inside another folder.

### Step 1. Download the replication package

Download the complete replication package as a ZIP archive from the archived repository.

Do not download individual folders or files separately.

### Step 2. Upload the ZIP file to Google Drive

1. Open **Google Drive**.
2. Go to **My Drive** (the root level of your Google Drive).
3. Upload the complete replication-package ZIP file.
4. **Do not place the ZIP file inside another folder.**

The ZIP archive should therefore be located directly under `My Drive`.

### Step 3. Extract the replication package

Extract the ZIP archive directly in the root of `My Drive`.

After extraction, the replication package should have a structure similar to:

```text
My Drive/
└── <Replication-Package>/
    ├── 01_Knowledge Base/
    ├── 02_System/
    ├── 03_Data/
    ├── 04_Generation/
    ├── 05_Analysis/
    ├── LICENSE
    ├── CITATION.cff
    └── README.md
```

**Do not create another parent folder around the extracted replication package.** In particular, avoid structures such as:

```text
My Drive/
└── SomeOtherFolder/
    └── <Replication-Package>/
```

The relative folder structure inside the replication package should remain unchanged.

### Step 4. Open Google Colab

Open **Google Colab** and sign in with the Google account associated with the Google Drive containing the replication package.

The notebooks in this package were developed using Google Colab and are also compatible with Jupyter Notebook and JupyterLab.

### Step 5. Connect Google Drive to Colab

In Google Colab, mount your Google Drive so that the notebooks can access the replication package and its data.

The replication package should then be accessible from the mounted `My Drive` directory.

### Step 6. Select the analysis or experiment to reproduce

The replication package is divided into five main folders:

- **`01_Knowledge Base`** — contains knowledge-base materials used by CAPI.
- **`02_System`** — contains the CAPI chatbot implementation.
- **`03_Data`** — contains the experimental datasets and evaluation data.
- **`04_Generation`** — contains notebooks for generating chatbot responses under the experimental configurations.
- **`05_Analysis`** — contains notebooks for reproducing the statistical analyses and figures reported in the paper.

Open the `README.md` inside the relevant folder before running its notebooks.

### Step 7. Run the notebooks

Run the notebooks in the relevant folder using Google Colab.

Unless otherwise stated in a folder-specific `README.md`, run the notebook cells **in their original order and name**. Do not rename, move, or delete files that are referenced by the notebooks.

Some experiments may require a GPU runtime and additional Python packages. The required dependencies are described in the relevant folder or notebook.

### Step 8. Reproduce the reported analyses

The package supports reproduction of the main experimental and statistical analyses reported in the paper, including:

- Response generation under the five experimental configurations;
- Automatic evaluation using BERTScore and ROUGE-L;
- Human evaluation and inter-rater agreement using Quadratic Weighted Cohen's Kappa;
- Statistical analyses addressing RQ1–RQ3; and
- Quality-in-use analysis based on the ISO/IEC 25010 quality model.

## Research Questions

The experiments reported in the paper address the following research questions:

**RQ1.** How does the response-generation configuration (LLM-only, LLM+RAG, or LLM+RAG+Prompt Adaptation at varying retrieval depths) affect the correctness and relevance of CAPI's responses to informatics-domain queries?

**RQ2.** To what extent do automatic evaluation metrics (BERTScore and ROUGE-L) agree with human judgments of response quality across these configurations?

**RQ3.** How do real users of CAPI perceive its overall software quality, as measured across the nine quality aspects drawn from the ISO/IEC 25010 Quality in Use and Product Quality models?

## Repository Contents

### 01_Knowledge Base

Contains a **sample** of the knowledge base used by CAPI.

The complete knowledge base consists of **291 curated question–answer (QA) pairs** compiled from:

- Informatics Study Program curriculum documents;
- University academic regulations and guidelines; and
- Relevant regulations issued by the Government of Indonesia.

Only a representative subset is included in this repository due to copyright and institutional data-sharing restrictions.

### 02_System

Contains the implementation of the CAPI chatbot, including the Gradio-based web interface used during the user evaluation.

### 03_Data

Contains the datasets required to reproduce the experimental analyses, including:

- Human evaluation scores from two independent raters;
- Ground-truth answers;
- BERTScore evaluation results;
- ROUGE-L evaluation results; and
- ISO/IEC 25010 user evaluation responses.

All released datasets have been anonymized, and personally identifiable information has been removed.

### 04_Generation

Contains Jupyter notebooks used to generate chatbot responses under the five response-generation configurations evaluated in this study.

### 05_Analysis

Contains Jupyter notebooks for reproducing the statistical analyses reported in the paper, including:

- Quadratic Weighted Cohen's Kappa;
- BERTScore;
- ROUGE-L;
- Quality Satisfaction analysis;
- Statistical analyses for RQ1–RQ3; and
- Figures and tables presented in the manuscript.

## Software Requirements

The notebooks were developed using **Google Colab** and are compatible with:

- Google Colab
- Jupyter Notebook
- JupyterLab

The primary Python dependencies include:

- `transformers`
- `sentence-transformers`
- `torch`
- `gradio`
- `jsonlines`
- `pandas`
- `numpy`
- `scikit-learn`

## Reproducibility

This replication package enables researchers to reproduce the experiments reported in the paper, including:

- Response generation under five experimental configurations;
- Automatic evaluation using BERTScore and ROUGE-L;
- Human evaluation and inter-rater agreement using Quadratic Weighted Cohen's Kappa;
- Statistical analyses addressing RQ1–RQ3; and
- Quality-in-use analysis based on the ISO/IEC 25010 quality model.

## Replication Package

The archived replication package is permanently available on **Zenodo**:

**DOI:** https://doi.org/10.5281/zenodo.22732052

The GitHub repository hosts the latest development version, while the Zenodo archive preserves the version associated with the published experiments. Zenodo assigns persistent version-specific DOIs to support reproducibility.

## Citation

If you use this replication package in your research, please cite the accompanying paper and the archived replication package.

Citation metadata are provided in the `CITATION.cff` file.

## License

- **Source code:** Apache License 2.0
- Other materials are distributed according to the licenses specified within the repository.

## Contact

**Luh Gede Surya Kartika**

Universitas Hindu Negeri I Gusti Bagus Sugriwa Denpasar

Email: suryakartika@uhnsugriwa.ac.id

ORCID: https://orcid.org/0000-0001-9895-1418
