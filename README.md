# Single-cell Chromatin Accessibility Genotyping Pipeline Based on GoT-ChA

## Overview

This repository contains a customized analysis pipeline built upon the GoT-ChA (Genotyping of Targeted loci with single-cell Chromatin Accessibility) technology. GoT-ChA integrates targeted genotyping with single-cell ATAC-seq data to simultaneously profile genetic variants and chromatin accessibility at single-cell resolution.

Using the GoT-ChA R package as the foundation, I developed this pipeline to analyze my own sequencing data, with personalized modifications and optimizations tailored to my research goals.

## Why GoT-ChA?

- Leverages genomic DNA for genotyping instead of relying on gene expression, overcoming limitations of scRNA-seq-based methods.  
- Captures both genotype and chromatin accessibility from the same single cells using 10x Genomics scATAC-seq platform.  
- Enables high-throughput and scalable single-cell genotyping, compatible with common single-cell analysis frameworks such as ArchR.

## Pipeline Description

1. **Data Preprocessing**  
   Utilize GoT-ChA functions for base quality filtering and splitting fastq files to facilitate parallel processing.

2. **Mutation Calling and Genotyping**  
   Perform targeted mutation calling by pattern matching primers and assigning reads to wildtype or mutant alleles.  
   Apply noise correction methods based on empty droplets or clustering to accurately assign genotypes per cell barcode.

3. **Downstream Analysis**  
   Integrate genotype calls with single-cell ATAC-seq metadata for differential accessibility analysis, co-accessibility calculations, and genome track visualization.

4. **Custom Modifications**  
   - Design and validate primers tailored to my regions of interest.  
   - Adjust noise correction thresholds and genotyping parameters based on experimental data characteristics.  
   - Extend functionality for downstream biological interpretation in my specific study context.

## Installation

The pipeline depends on the [Gotcha R package](https://github.com/landau-lab/Gotcha), which can be installed via:

```r
devtools::install_github("landau-lab/Gotcha")

