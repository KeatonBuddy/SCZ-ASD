# Identification of Shared Differentially Expressed Genes in Schizophrenia and Autism Spectrum Disorder
## Project Summary
This study explores common transcriptomic alterations between two major neuropsychiatric conditions—Schizophrenia (SCZ) and Autism Spectrum Disorder (ASD)—with the goal of uncovering shared molecular pathways that may underlie their overlapping symptomatology. By directly comparing RNA‑seq data from post‑mortem amygdala samples of SCZ patients and frontal‑cortex samples of ASD patients against matched healthy controls, we aimed to pinpoint genes whose expression is similarly dysregulated in both disorders.

*This work was conducted to fulfill the MDSC 519 course requirement at the University of Calgary*

## Key Objectives

### Data Curation & Harmonization

- Gather publicly available paired-end RNA‑seq datasets: 22 SCZ + 24 controls (amygdala) and 12 ASD + 12 controls (frontal cortex).

- Randomly select a balanced subset (3 SCZ, 3 ASD, 4 control samples) to minimize study‑specific biases.

### Quality Control & Alignment

- Perform read‑level QC with FastQC/MultiQC.

- Quantify transcript abundance against GRCh38 using the pseudoaligner Kallisto.

- Validate alignment profiles across samples.

### Clustering & Exploratory Analysis

- Run principal component analyses (PCA) on TPM and scaled‑reads matrices to visualize sample grouping and assess batch/tissue effects.

###Differential Expression & Filtering

- Use Sleuth to identify genes differentially expressed in SCZ vs. control and ASD vs. control.

- Apply two successive filters:

  - Filter 1: retain genes whose SCZ/control and ASD/control fold‑changes lie outside ±1, then FDR ≤ 0.10.

  - Filter 2: stricter FDR ≤ 0.05 in both comparisons.

### Candidate Gene Annotation

- Annotate the final gene sets for known neurological associations and functional pathways.

## Major Findings

- Batch & Tissue Effects: PCA revealed that control samples from each study cluster more closely with their originating disorder, reflecting amygdala vs. frontal‑cortex expression differences.

- Shared Hits: After stringent FDR filtering, a small number of genes (e.g., GJB1, AMOTL2, ARRDC4) emerged as consistently dysregulated in both SCZ and ASD relative to controls.

- Functional Insights: Among these, GJB1 (a gap‑junction protein) has established roles in neural connectivity, suggesting a convergent mechanism affecting intercellular communication in both disorders.

## Conclusions & Next Steps
Although limited by small sample size and differing tissue origins, this pilot analysis highlights a handful of promising candidate genes for deeper investigation. Future work should leverage larger, multi‑region cohorts (e.g., CommonMind Consortium) and validate these candidates via independent datasets or functional assays. Ultimately, identifying robust, shared biomarkers could illuminate novel targets for therapeutic intervention across these complex mental illnesses.
---
*All analysis code (read‑level QC with FastQC/MultiQC, transcript pseudoalignment via Kallisto, differential expression testing in Sleuth, and PCA/clustering visualizations) was written in R (run in RStudio with auxiliary Bash pipelines); figures and the full write‑up appear in the submitted project document, and the original scripts are unfortunately no longer available.*
