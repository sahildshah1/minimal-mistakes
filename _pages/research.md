---
layout: single
permalink: /research/
author_profile: true
title: Statistical methods for the network-based analysis of genomic data 
---

The goals of analyzing omics data to generate insights for biology can be
broadly grouped into three categories: (1) ‘discovering molecular mechanisms’ ,
(2) ‘clustering samples’, and (3) ‘the prediction of an outcome, such as
survival or the efficacy of therapy'. Discovering molecular mechanisms can be
approached by either (1a) seeking to determine the mechanisms by which genomic
loci contribute to disease or (1b) seeking to understand the pathways that
contribute to disease. [See these [papers](https://paperpile.com/shared/VmFVX7)
for more information.]

The goal of our work in my thesis is (1b) to discover molecular mechanisms by
seeking to understand the pathways that contribute to disease:

<!--  In Chapter 2, we
review analysis techniques that identify pathways associated with a disease. In
Chapter 3, we present a novel analysis method to identify individual genes that
influence pathways associated with disease. In Chapter 4, we seek to identify
genes that are the sources of differences in the time courses of expression.
 -->

## 1. Evaluate: Network methods for pathway analysis of genomic data

We outline  a novel evaluation framework for pathway analysis methods. The key
idea is that analysis techniques that are finding true biological effects 
should find them across different datasets that are measuring the same 
underlying conditions. Therefore, we apply eight network-based pathway analysis
techniques to ten different ovarian cancer studies that have been curated to
ensure comparability and evaluate the methods by their cross-study concordance.
This approach allows us to evaluate the method with real (instead of 
artificial) data.


We presented a [poster of our work at the Chicago Area SIAM Student Conferencee](https://drive.google.com/file/d/0BwwWdkWAoHm0aWkyMHlnS09WckU/view?usp=sharing) and 
the work is currently in press at Computational and Structural Biotechnology Journal and  [available on the arXiv](https://arxiv.org/abs/1411.1993).



## 2. Develop: Network-based identification of disease genes in expression data

We present  a new analysis method that integrates expression data and network
information in a novel procedure to detect genes that appear to influence
nearby
genes with disease-associated dysregulation. Applying our algorithm to real
expression data we show that our method is able to identify biologically
relevant genes, integrate pathway and expression data, and yield more
reproducible results across multiple studies of the same phenotype than
competing methods.

We recently presented a [poster of our work at the ISMB 2018 conference.](https://drive.google.com/file/d/1HYteZfmJqg7YVqasT1YeP05SPnhVnsll/view?usp=sharing)
The work is currently under review at BMC Bioinformatics  and [available on the arXiv](https://arxiv.org/abs/1705.10922).


## 3. Apply: Analysis of expression and network data to identify dysregulated genes in mouse cell lines with a truncated GCSF receptor

This project  concerns original mouse cell line time-series expression data and
the statistical analysis of that data to study the development of acute myloeid
leukemia (AML) from severe congenital neutropenia (SCN). We first use this data
to find genes with significant differences in the time course of expression and
then, to take into account the role that a given gene has in signaling pathways,
apply our new analysis method to identify genes that are sources of
dysregulation on signaling networks.



<!-- My third paper is in progress and close to being submitted (The title is "Analysis of transcriptomic and network data to identify dysregulated genes in mouse cell lines with a truncated granulocyte colony stimulating factor (GCSF) receptor")

 -->


