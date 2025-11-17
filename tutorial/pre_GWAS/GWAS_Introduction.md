# Introduction to Genome-Wide Association Studies (GWAS)

## What is GWAS?

A **Genome-Wide Association Study (GWAS)** is a statistical approach used to identify genetic variants (usually SNPs) associated with a trait or disease. Unlike traditional studies that examine one gene at a time, GWAS scans the **entire genome** to find regions where genetic variation correlates with differences in a phenotype.

GWAS is widely used to:

- Discover **risk variants for diseases**
- Understand **biological pathways**
- Predict disease risk using **polygenic risk scores**
- Identify potential **drug targets**

---

## Why Perform a GWAS?

GWAS helps answer:

> “Which genetic variants influence this trait?”

Key motivations:

- Identify SNPs that affect disease risk or trait variability
- Understand the genetic architecture of complex traits
- Enable personalized medicine approaches
- Generate hypotheses for further functional studies

---

## Required Data for GWAS

### 1. Genotype Data
- Millions of SNPs per individual, usually in **PLINK binary format** (`.bed`, `.bim`, `.fam`) or VCF.
- Example:

| SNP | Sample1 | Sample2 | Sample3 |
|-----|---------|---------|---------|
| rs1 | AA      | AG      | GG      |
| rs2 | CC      | CT      | TT      |

### 2. Phenotype Data
- **Binary traits**: case vs. control (0/1)  
- **Quantitative traits**: height, BMI, blood pressure  
- Format example:
FID IID PHENO
1 1 0
1 2 1
1 3 2.4

### 3. Covariates (Optional but Recommended)
- Age, sex, genotyping batch
- Principal components (PCs) to control for population structure
- Example:
FID IID SEX AGE PC1 PC2 PC3
1 1 1 34 -0.01 0.02 …


---

## How GWAS Works (Simplified)

For each SNP, GWAS tests:

> “Is the allele frequency different between phenotypes?”

- **Binary traits**: logistic regression or chi-square test  
- **Quantitative traits**: linear regression

This is repeated for **millions of SNPs**, producing a genome-wide association profile.

---

## Multiple Testing & Significance

Because millions of SNPs are tested, we apply **stringent significance thresholds** to reduce false positives:
p < 5 × 10⁻⁸


This is called **genome-wide significance**.

---

## GWAS Output

- **Association results**: SNP ID, p-value, beta, odds ratio  
- **Manhattan plot**: genomic overview of significant regions  
- **QQ plot**: checks for inflation and confounding  
- **Significant SNP list**: candidates for follow-up studies

---

## Limitations of GWAS

- Does **not prove causation**  
- Identifies regions, not specific causal genes  
- Can be influenced by population structure or relatedness  
- Requires large sample sizes for power  

---

## Summary

> **GWAS is a genome-wide scan for SNPs associated with a trait, allowing researchers to identify genetic regions that may influence phenotypes.**

This tutorial will guide you through **pre-GWAS preparation, GWAS analysis, and post-GWAS interpretation**, step by step.


