---

layout: post
title: "Relative Quantification in qPCR Using the Delta-Delta Ct Method"
date: 2026-06-28
categories: qPCR
tags: [qPCR, relative-quantification, delta-delta-ct, gene-expression]
----------------------------------------------------------------------

# Relative Quantification in qPCR Using the Delta-Delta Ct Method

## Introduction

In this classwork assignment, I analyzed qPCR data using the relative quantification approach. Relative quantification is used to compare the expression level of target genes between different experimental groups. In this dataset, gene expression in the **inhibitor treatment** was compared with the **DMSO control**.

The method used for the analysis was the **Delta-Delta Ct method**, also known as the **2^-ΔΔCt method**. This method allows calculation of relative gene expression after normalization to a reference gene.

In this dataset, **Tubulin** was used as the reference gene.

---

## What Is Ct?

Ct stands for **cycle threshold**. It represents the PCR cycle at which the fluorescence signal crosses a defined threshold.

A lower Ct value usually indicates a higher amount of starting cDNA, meaning higher gene expression. A higher Ct value usually indicates a lower amount of starting cDNA, meaning lower gene expression.

---

## Step 1: Calculating ΔCt

The first step is to normalize each target gene to the reference gene.

The formula is:

ΔCt = Ct(target gene) - Ct(reference gene)

In this dataset, Tubulin was used as the reference gene. Therefore, for each target gene:

ΔCt = Ct(target gene) - Ct(Tubulin)

This step corrects for technical differences between samples, such as differences in starting RNA amount, cDNA synthesis efficiency, or total sample input.

---

## Step 2: Calculating ΔΔCt

After calculating ΔCt for each gene in both groups, the next step is to compare the inhibitor treatment to the DMSO control.

The formula is:

ΔΔCt = ΔCt(inhibitor treatment) - ΔCt(DMSO control)

The DMSO control is used as the baseline for comparison.

---

## Step 3: Calculating Relative Expression

The relative expression, or fold change, is calculated using:

Relative expression = 2^-ΔΔCt

This value shows how much the expression of each gene changed in the inhibitor treatment compared with the DMSO control.

A value of **1** means no change compared with the control.
A value **greater than 1** means the gene was upregulated.
A value **lower than 1** means the gene was downregulated.

---

## Results

The following table summarizes the calculated ΔΔCt and fold-change values for each target gene.

| Gene  |  ΔΔCt | Relative expression, 2^-ΔΔCt | Interpretation         |
| ----- | ----: | ---------------------------: | ---------------------- |
| ascs  | -0.59 |                         1.50 | Upregulated            |
| Delta | -0.43 |                         1.34 | Upregulated            |
| ets   | -0.28 |                         1.21 | Slightly upregulated   |
| foxA  | -0.64 |                         1.56 | Upregulated            |
| gcm   | -0.18 |                         1.13 | Slightly upregulated   |
| NGN   | -1.00 |                         2.00 | Upregulated            |
| opt   |  0.69 |                         0.62 | Downregulated          |
| pak3  | -0.11 |                         1.08 | Almost no change       |
| pak4  | -0.32 |                         1.25 | Slightly upregulated   |
| pitx  |  2.05 |                         0.24 | Strongly downregulated |
| SM30  |  0.80 |                         0.58 | Downregulated          |
| sm50  |  1.11 |                         0.46 | Downregulated          |
| soxC  | -0.74 |                         1.68 | Upregulated            |
| synB  | -0.07 |                         1.05 | Almost no change       |

---

##  Graph

![Relative gene expression graph](/Adi-Research-method-2026/assets/images/qpcr_fold_change_graph.png)

The graph shows the relative expression of each target gene in the inhibitor treatment compared with the DMSO control. The DMSO control is used as the baseline and is represented by a relative expression value of 1.

Genes with values above 1 showed increased expression in the inhibitor treatment, while genes with values below 1 showed decreased expression.

---



The graph shows that several genes were upregulated in the inhibitor treatment compared with the DMSO control. The strongest increase was observed for **NGN**, with a relative expression value of approximately **2.00**, meaning that its expression was about two times higher in the inhibitor treatment.

Other genes that showed increased expression included **soxC**, **foxA**, and **ascs**.

In contrast, some genes were downregulated in the inhibitor treatment. The strongest decrease was observed for **pitx**, with a relative expression value of approximately **0.24**, meaning that its expression was strongly reduced compared with the control.

Other downregulated genes included **sm50**, **SM30**, and **opt**.

Some genes showed only small changes in expression, such as **pak3** and **synB**, which had fold-change values close to 1. This suggests that their expression was relatively similar between the inhibitor treatment and the DMSO control.

---

## Biological aspect

The results suggest that the inhibitor treatment affected the expression of several genes. Some genes were activated, while others were reduced compared with the DMSO control.

The increase in expression of genes such as **NGN**, **soxC**, **foxA**, and **ascs** may suggest that the inhibitor treatment activated or maintained pathways associated with these genes.

In contrast, the strong decrease in **pitx**, **sm50**, and **SM30** suggests that the treatment may have suppressed pathways related to these genes.

Overall, the data indicate that the inhibitor treatment did not affect all genes equally. Instead, it caused gene-specific changes in expression.

---

## Important Note

This analysis is descriptive because the provided dataset includes one Ct value per condition for each gene. Without biological replicates, it is not possible to calculate reliable error bars or determine statistical significance.

Therefore, the results should be interpreted as relative expression trends rather than statistically confirmed differences.

---

## Conclusion

The Delta-Delta Ct method is a useful approach for analyzing relative gene expression in qPCR experiments. In this classwork dataset, Tubulin was used as the reference gene, and the DMSO control was used as the baseline.

The inhibitor treatment caused both upregulation and downregulation of different target genes. The most strongly upregulated gene was **NGN**, while the most strongly downregulated gene was **pitx**.

This analysis demonstrates how Ct values can be converted into biologically meaningful relative expression values using the 2^-ΔΔCt method.
