# Hypoxia-Driven-Genomic-Analysis-in-Cancer-Research
Cancer genomic research focusing on the role of hypoxia in tumor cell behavior, utilizing Single-cell RNA sequencing techniques.
# Cancer and Genomic Research: A Deep Dive into Hypoxia and its Role in Cancer Recognition

## Table of Contents
- [Introduction](#introduction)
- [Hypoxia and its Role in Cancer Recognition](#hypoxia-and-its-role-in-cancer-recognition)
- [Target of this Research](#target-of-this-research)
- [Preamble: Overview of Data](#preamble-overview-of-data)
- [Steps of our Analysis](#steps-of-our-analysis)
- [Conclusions](#conclusions)

## Introduction

Tumour development is a multi-stage process where healthy cells transform into malignant tumours due to a series of gene mutations. These mutations accumulate in cells, causing broad cancer types to branch into various sub-types. As cells proliferate and divide, significant gene mutations in tissues lead to changes in cell phenotypes. Consequently, tumour cells evolve based on their microenvironments.

Every individual's genomic profile is closely tied with the genetic mutations of their cancer tissues. This tumour heterogeneity is a primary reason why cancer remains a significant challenge in both medical research and clinical treatment.

## Hypoxia and its Role in Cancer Recognition

A defining characteristic of a tumour's microenvironment is hypoxia, a condition marked by low oxygen availability. This arises due to increased oxygen consumption and impaired oxygen delivery. While many cells find hypoxia lethal, tumour cells adapt their metabolism to thrive in such conditions. These cells also develop resistance to treatments like chemo/radiotherapy. Moreover, hypoxic cells, which survive in an apoptosis state, become more aggressive, invasive, and are associated with a poor prognosis for cancer patients.

## Target of this Research

The intricate relationship between an individual's DNA and tumour genetic expression emphasizes the importance of Single-cell RNA sequencing. This technology analyzes the transcriptomes of complex tissues at the single-cell level, offering insights into the molecular mechanisms behind tumour occurrence. 

Using two scRNA techniques, Smart-Sequencing and Drop-Sequencing, our goal is to train a predictor that can determine if a cell is in a hypoxic (1% on average) or normoxic (typically 20% in labs) condition. By understanding Hypoxic cells better, we can identify genes responsible for genetic mutations.

## Preamble: Overview of Data

Our dataset comprises information on two cell lines:

- **HCC1086**: Derived from a human breast cancer patient.
- **MCF7**: A human breast cancer cell line known for high estrogen and progesterone receptor expression.

The Metadata.tsv files provide a snapshot of these cell lines. Both cell lines are grown in either hypoxic or normoxic conditions and sequenced after specific durations (24 hours for HCC1806 and 72 hours for MCF7). Additional details like position, plate/lane, and filenames summarizing their features are also provided.

## Steps of our Analysis

1. **Exploratory Data Analysis**: Understand the data's structure, distribution, and potential anomalies.
2. **Data Cleaning and Quality Control**: Ensure data integrity by removing noise and irrelevant information.
3. **Normalisation and Scaling**: Standardize data to make it suitable for analysis.
4. **Unsupervised Learning**: Identify patterns and structures within the data.
5. **Model Training**: Train predictive models using the curated data.

## Conclusions

Our research provided insights into three main areas:

1. **Data Processing Efficacy**: Our data processing techniques applied to the HCC1806_Unfiltered dataset proved effective. The LinearSVM model's perfect accuracy score of 1.0 highlights the robustness of our preprocessing mechanism.
2. **Model Performance Evaluation**: Comparative analysis showed slightly better results on SmartSeq compared to DropSeq, with an average improvement of 2-3%. This could be due to SmartSeq's reduced dimensionality or its superior sequencing technique.
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
