# Global Transcriptomic Profiling of Aortic Aneurysms

**Title**: Global Transcriptomic Profiling Identifies Differential Gene Expression Signatures between Inflammatory and Non-inflammatory Aortic Aneurysms  
**DOI**: DOI: 10.1002/art.42138  
**Authors**: Benjamin Hur, Matthew J. Koster, Jin Sung Jang, Cornelia M. Weyand, Kenneth J. Warrington, and Jaeyun Sung  
**Contact**: hur.benjamin@mayo.edu  
**Corresponding Author**: sung.jaeyun@mayo.edu  

---

## Overview

This repository contains the analysis pipeline and associated resources used in the transcriptomic profiling of **inflammatory vs. non-inflammatory aortic aneurysms**.

Key components:
- Differential gene expression (DEG) analysis
- Gene set enrichment
- Pharmacogenomic network construction
- PCA and confounding factor analysis
- FASTQ trimming and alignment

---

## 🔬 Differential Expression & Gene Set Analysis

Location: `analysis_with3Meta/gene_set/`

- `01_run_deseq_multi_level.sh` – Run DESeq2 for DEG analysis  
- `02_geneset.sh` – Gene set enrichment analysis  
- `03_draw_vocano.sh` – Generate volcano plots  

> **Note**: DESeq2 v1.26.0 was used. DEG results may differ from newer versions (e.g., v1.30+).

---

## 🧬 Pharmacogenomic Network Construction

Location: `analysis_with3Meta/network/`

- `01_run.sh` – Initialize network generation  
- `02_parse_subnetwork.sh` – Extract subnetworks  
- `03_create_pharmacogenomic_network.sh` – Build final network

---

## 📊 Additional Analyses

- **PCA**  
  `src/statistics/PCA_whole_data.ipynb`

- **Confounding Variable Assessment**  
  `src/statistics/linear_model_variable_significance.ipynb`

- **PANTHER Pie Chart Visualization**  
  `src/statistics/panther_pie_chart.ipynb`

---

## 🧪 Data Preprocessing (FASTQ → Alignment)

Location: `/Users/m221138/Aortitis_Public/preprocess/`

- `01_trim_rawdata.sh` – Adapter trimming  
- `02_run_alignmnet.sh` – STAR alignment  

---

## 📁 Data Files

- `data/aortitis.tsv` – Raw read counts (50 samples × 26,475 genes, STAR)  
- `data/tpm_profile.log2.tsv` – Log2-transformed TPM (50 samples × 26,475 genes, RSEM)  

> **Note**: Raw `.fastq` files are available upon request.

