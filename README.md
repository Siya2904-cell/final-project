README: Pathogenicity Accessory Chromosome in Fusarium oxysporum f. sp. vasinfectum
Project Overview

This repository contains data and analysis code for investigating a pathogenicity accessory chromosome in Fusarium oxysporum f. sp. vasinfectum (Fov) strain 89-1A. The project includes:

Genome quality validation
Identification of virulence-associated genes
qPCR analysis of candidate genes
Pathogenicity assessment of chromosome-modified isolates
Directory Structure
Fov891A_pathogenicity_chromosome/
│
├── data/
│   ├── genomic/
│   │   ├── Fov891A.contigs.fasta          # Genome assembly
│   │   ├── augustus_Fov891A.gff           # Gene annotations
│   │   └── au_Fov891A.proteins.fa         # Predicted proteins
│   │
│   ├── qPCR/
│   │   ├── test one--qPCR primer efficiency.csv
│   │   ├── test two--qPCR primer efficiency.csv
│   │   └── RNA expression data.csv
│   │
│   └── virulence/
│       ├── gfp-tag isolates virulence test.csv
│       └── 3-17 chro-lost virulence test.csv
│
├── scripts/
│   ├── genome_processing.sh               # Genome quality control
│   ├── busco_analysis.sh                  # Annotation completeness
│   └── qPCR_analysis.R                    # Expression analysis
│
├── results/
│   ├── genome_quality/
│   │   └── busco_results/                 # BUSCO output files
│   │
│   ├── figures/
│   │   ├── busco_completeness.pdf         # Quality metrics
│   │   ├── qPCR_efficiency_plots.pdf      # Primer validation
│   │   └── virulence_assays.pdf           # Pathogenicity results
│   │
│   └── tables/
│       ├── candidate_genes.csv            # Virulence candidates
│       └── expression_results.csv         # qPCR analysis
│
├── manuscript/
│   ├── Fov_accessory_chromosome.Rmd       # Analysis manuscript
│   └── Fov_accessory_chromosome.pdf       # Compiled report
│
└── README.md                              # This file
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
