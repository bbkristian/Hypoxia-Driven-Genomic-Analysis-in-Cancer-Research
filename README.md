# Hypoxia-Driven-Genomic-Analysis-in-Cancer-Research
Cancer genomic research focusing on the role of hypoxia in tumor cell behavior, utilizing Single-cell RNA sequencing techniques.

# Cancer and Genomic Research: A Deep Dive into Hypoxia and its Role in Cancer Recognition

## Introduction

Tumorigenesis is a complex, multi-stage process wherein normal cells transform into malignant tumors through a cascade of gene mutations. These mutations accumulate progressively, leading to a diverse array of cancer sub-types. The proliferation and division of these mutated cells result in significant phenotypic changes influenced by their microenvironment. This genomic heterogeneity poses substantial challenges for both medical research and clinical treatment.

## Hypoxia and its Role in Cancer Recognition

A defining characteristic of a tumour's microenvironment is hypoxia, a condition marked by low oxygen availability. This arises due to increased oxygen consumption and impaired oxygen delivery. While many cells find hypoxia lethal, tumour cells adapt their metabolism to thrive in such conditions. These cells also develop resistance to treatments like chemo/radiotherapy. Moreover, hypoxic cells, which survive in an apoptosis state, become more aggressive, invasive, and are associated with a poor prognosis for cancer patients.

## Research Objective

Our research leverages Single-cell RNA sequencing (scRNA-seq) to explore the molecular mechanisms underpinning tumor development under hypoxic conditions. By analyzing the transcriptomes of individual cells, we aim to elucidate the impact of hypoxia on gene expression within tumors. We employ two scRNA-seq techniques, Smart-Seq2 and Drop-Seq, to train predictive models that classify cells as hypoxic (1% oxygen) or normoxic (20% oxygen). This classification enhances our understanding of hypoxia-induced genetic mutations.

## Preamble: Overview of Data

Our dataset comprises information on two cell lines:

- **HCC1086**: Derived from a human breast cancer patient.
- **MCF7**: A human breast cancer cell line known for high estrogen and progesterone receptor expression.

Metadata files provide detailed snapshots of these cell lines, grown under hypoxic or normoxic conditions and sequenced at specific intervals (24 hours for HCC1806 and 72 hours for MCF7). The metadata includes positional data, plate/lane information, and filenames summarizing cell features.

## Steps of our Analysis

1. **Exploratory Data Analysis**: Visualization and statistical analysis to understand data distribution and detect anomalies.
2. **Data Cleaning and Quality Control**: Filtering low-quality reads and removing potential batch effects.
3. **Normalisation and Scaling**: Standardize data to make it suitable for analysis.
4. **Feature Analysis**: Identifying highly variable genes to reduce dimensionality.
5. **Unsupervised Learning**: Clustering and dimensionality reduction to identify patterns and structures.
6. **Model Training**: Developing predictive models using supervised learning algorithms.

## Conclusions

Our research provided insights into three main areas:

1. **Data Processing Efficacy**: Effective preprocessing of the HCC1806_Unfiltered dataset was demonstrated by the LinearSVM model achieving a perfect accuracy score of 1.0, highlighting the robustness of our preprocessing pipeline.
2. **Model Performance Evaluation**: Comparative analysis showed slightly better results on Smart-Seq2 compared to Drop-Seq, with an average improvement of 2-3%, likely due to reduced dimensionality or superior sequencing technology.
3. **Genetic Profiles of Cell Lines**: The HCC1806 and MCF7 cell lines have unique genetic profiles. The most impactful genes, which determine the cell lines' functional characteristics, vary significantly between them.

**Top Genes for HCC1806**:
- CA9 (Carbonic Anhydrase IX)
- ANGPTL4 (Angiopoietin-like protein 4)
- NDRG1 (N-myc downstream regulated gene 1)
- EGLN3 (EGLN family prolyl hydroxylase)
- BNIP3P1 (BCL2/adenovirus E1B interacting protein 3 pseudogene 1)

**Top Genes for MCF7**:
- CYP1B1 (Cytochrome P450 1B1 gene)
- CYP1B1-AS1 (Enhancer RNA (eRNA))
- CYP1A1 (Member of the cytochrome P450 family)
- NDRG1 (N-myc downstream regulated gene 1)
- DDIT4 (DNA-damage-inducible transcript 4)

The primary genes for both cell lines differ, except for NDRG1. This indicates that the genes predictive of a hypoxic condition are closely tied with the cell line's microenvironment.

## Model Details 
- **LinearSVM**: Achieved high accuracy in classifying hypoxic vs. normoxic cells, demonstrating the effectiveness of our feature selection and preprocessing steps.
- **Random Forest**: Provided robust feature importance metrics, helping identify key genes associated with hypoxia.
- **XGBoost**: Delivered competitive performance with efficient handling of large datasets, proving useful for model interpretability.
- **Neural Networks (MLP)**: Explored complex, non-linear relationships within the data, offering deep insights into hypoxia-induced genetic expression.

## Bibliography

[Tutorial: guidelines for the computational analysis of single-cell RNA sequencing data](https://www.nature.com/articles/s41596-020-00409-w)

[Best practices for single-cell analysis across modalities](https://www.nature.com/articles/s41576-023-00586-w)

[Current best practices in single-cell RNA-seq analysis: a tutorial](https://www.embopress.org/doi/full/10.15252/msb.20188746)

[The role of carbonic anhydrase IX in cancer development: links to hypoxia, acidosis, and beyond](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6647366/)

[Hypoxia-induced angiopoietin-like protein 4 as a clinical biomarker and treatment target for human prostate cancer](https://pubmed.ncbi.nlm.nih.gov/28560449/)

[N-myc downstream regulated gene 1 (ndrg1) functions as a molecular switch for cellular adaptation to hypoxia](https://pubmed.ncbi.nlm.nih.gov/36214665/)

[The multifaceted role of EGLN family prolyl hydroxylases in cancer: going beyond HIF regulation](https://www.nature.com/articles/s41388-022-02378-8)

[Hypoxia-induced autophagy is mediated through hypoxia-inducible factor induction of BNIP3 and BNIP3L via their BH3 domains](https://pubmed.ncbi.nlm.nih.gov/19273585/)

[Effect of hypoxia on cytochrome P450 activity and expression](https://pubmed.ncbi.nlm.nih.gov/15180495/)

[CYP1B1-AS1 Is a Novel Biomarker in Glioblastoma by Comprehensive Analysis](https://www.hindawi.com/journals/dm/2021/8565943/)

[Upregulation of CYP1B1 by hypoxia is mediated by $ER\alpha$ activation in breast cancer cells](https://pubmed.ncbi.nlm.nih.gov/35812067/)

[The zero-inflation controversy about scRNA-seq data](https://genomebiology.biomedcentral.com/articles/10.1186/s13059-022-02601-5)

[Hypoxia responsive gene expression is mediated by various subsets of transcription factors and miRNAs that are determined by the actual oxygen availability](https://www.iris.sssup.it/bitstream/11382/326566/1/New%20Phytol%202011.pdf)
