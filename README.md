README: Pathogenicity Accessory Chromosome in Fusarium oxysporum f. sp. vasinfectum
Project Overview

This repository contains data and analysis code for investigating a pathogenicity accessory chromosome in Fusarium oxysporum f. sp. vasinfectum (Fov) strain 89-1A. The project includes:

Genome quality validation
Identification of virulence-associated genes
qPCR analysis of candidate genes
Pathogenicity assessment of chromosome-modified isolates
Directory Structure
Fov891A_pathogenicity_chromosome/
# A Pathogenicity Accessory Chromosome in *Fusarium oxysporum* f. sp. *vasinfectum*

**Author:** Lihui Xiang  
**Date:** 2025-04-20  

---

## Abstract

This study identifies a unique accessory chromosome in *Fusarium oxysporum* f. sp. *vasinfectum* strain 89-1A, which carries a virulence-associated lactamase gene cluster. Through GFP tagging and chromosome loss assays, we confirmed its role in pathogenicity. Among eight candidate genes on this chromosome, **FUN_000082** and **FUN_001597** were highly upregulated during early infection of cotton. This work provides insight into host-specific pathogenic mechanisms and opens avenues for disease resistance strategies.

---

## Project Directory Structure

```text
Fov891A_pathogenicity_chromosome/
├── data/                          # Experimental raw data
│   ├── genomic/                  # Genome and annotation files
│   │   ├── Fov891A.contigs.fasta           # Genome assembly
│   │   ├── augustus_Fov891A.gff           # Gene annotation file
│   │   └── au_Fov891A.proteins.fa         # Predicted proteins
│   ├── qPCR/                     # qPCR primer efficiency & expression data
│   │   ├── test one--qPCR primer efficiency.csv
│   │   ├── test two--qPCR primer efficiency.csv
│   │   └── RNA expression data.csv
│   └── virulence/               # Virulence assay results
│       ├── gfp-tag isolates virulence test.csv
│       └── 3-17 chro-lost virulence test.csv
│
├── scripts/                      # Analysis scripts
│   ├── genome_processing.sh               # Protein/CDS extraction
│   ├── busco_analysis.sh                  # BUSCO run script
│   └── qPCR_analysis.R                    # qPCR data processing
│
├── results/                      # Analysis outputs
│   ├── busco_results/                     # BUSCO result folder
│   ├── figures/                          # Figures and plots
│   │   ├── busco_completeness.pdf        # BUSCO visualization
│   │   └── qPCR_efficiency_plots.pdf     # Primer efficiency plots
│   ├── virulence_assays.pdf              # Summary of virulence data
│   ├── candidate_genes.csv               # Selected gene cluster
│   └── expression_results.csv            # qPCR results for 8 genes
│
├── manuscript/                  # Report and manuscript
│   └── Fov_accessory_chromosome.Rmd       # R Markdown report source
│
└── README.md                    # This file
Key Findings

1. Genome Quality Validation

BUSCO analysis showed 98.8% completeness (C:97.9% single-copy, 0.9% duplicated)
High-quality gene predictions suitable for downstream analysis
2. Candidate Gene Identification

8 genes of interest identified on accessory chromosome:
FUN_000082 (200× upregulation at 15hpi)
FUN_001597 (60× upregulation at 15hpi)
6 additional genes with virulence-related domains
3. Pathogenicity Assessment

GFP-tagged chromosome isolates retained full virulence
Chromosome-loss isolates showed significant virulence reduction (p<0.01)
How to Reproduce Analysis

Dependencies

R (v4.2+)
Bioconductor packages
BUSCO (v5.4.3)
gffread
Workflow

Genome processing:
cd scripts/
./genome_processing.sh
./busco_analysis.sh
Rscript qPCR_analysis.R
