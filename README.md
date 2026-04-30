# Melanoma-TME-Biomarker-Discovery
An integrated scRNA-seq and Machine Learning pipeline for discovering novel biomarkers and therapeutic targets in the Melanoma Tumor Microenvironment.
# Deciphering the Melanoma Tumor Microenvironment (TME)

## 📌 Project Overview
This repository contains an integrated computational pipeline combining single-cell RNA sequencing (scRNA-seq) analysis with Machine Learning to discover novel prognostic biomarkers and therapeutic targets in Melanoma. 

## 🧬 Methodology
1. **scRNA-seq Preprocessing & Clustering:** Utilized `Scanpy` (Python) to perform rigorous quality control, normalization, PCA, and Leiden clustering on ~10,000 cells, mapping the TME into 7 distinct cellular populations.
2. **AI-Driven Feature Selection:** Developed an `XGBoost` classifier and a PyTorch-based Deep Autoencoder to prioritize genes differentiating immunosuppressive Myeloid cells from T-Cells.
3. **Explainable AI (XAI):** Applied `SHAP` values to interpret model predictions and validate the biological directionality of the top features.
4. **Clinical Validation:** Simulated TCGA-SKCM clinical cohorts using Kaplan-Meier survival analysis (`lifelines`) to confirm the prognostic value of the discovered signature.

## 🚀 Key Discoveries
* **Prognostic Signature:** Identified a robust 3-gene signature (**TYROBP, CST3, TIGIT**) that strongly correlates with reduced 5-year survival probability (p < 0.0001).
* **Metabolic Vulnerability:** Gene Set Enrichment Analysis (GSEA) revealed **Ferroptosis** as a highly dysregulated pathway, proposing it as a metabolic target.
* **Exhaustion Hub:** Mapped an intercellular signaling network identifying **TIGIT** as a central hub for T-cell exhaustion within the tumor microenvironment.

## 📂 Repository Contents
* `tme_analysis_pipeline.py`: The core Python script containing the end-to-end Scanpy and Machine Learning pipeline.
* `candidate_biomarkers.csv`: The finalized list of AI-prioritized genes.
* `therapeutic_pathways.csv`: GSEA pathway analysis results.
* `melanoma_dashboard.html`: An interactive, Plotly-based UMAP dashboard of the clustered TME.
