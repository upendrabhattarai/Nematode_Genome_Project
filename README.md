# Nematode_Genome_Project

This repository contains scripts used for the curation and annotation of Nematode genome.
It is presented in three parts:

1. Genome assembly pipeline
2. Repeat library preparation and repeat masking
3. Genome annotation pipeline
---
## 1. Genome Assembly pipeline

Genome is assembled using long reads from nanopore, linked reads from 10x chromium and RNA-seq (mRNA and total RNA) data. Long read assembly is used as a primary assembly which is then scaffolded and gap closed using long, link and RNA-seq reads. Schematic representation of the genome assembly pipeline is presented below. Black arrow represents the workflow and red dotted lines represents the external input at various stages.

![Alt text](Nematode_genome_assembly_pipeline.png?raw=true "Title")


For the ease of understanding Genome assembly pipeline is divided into six sections: 
1. Preprocessing of the long reads
2. Primary assembly and removal of haplotigs
3. Linked read assembly for scaffolding
4. Scaffolding and gapclosing
5. Contaminant removal
6. Final genome polishing
---
## 2. Repeat library preparation and repeat masking

A comprehensive denovo repeat library is prepared for the assembled genome. which was then used for repeat content analysis, repeat masking and as input for annotation pipeline.
Process is described in four stages, scripts used for each stage is given below:
1. De novo repeat identification:
      1. Repeatmoduler
      2. LTRharvest & LTRdigest
      3. TransposonPSI
      4. Mite-tracker
2. External repeat database
      1. Sine database
      2. Dfam database
      3. Repbase database
3. Contenating and classifying Repeat database
      1. RepeatClassifier
4. Repeat masking the genome
      1. RepeatMasker
---
## 3. Genome annotation pipeline
Maker2 pipeline is used for genome annotation. mRNA seq data is denovo assembled using Trinity and other relavant publicly available datasets were downloaded and used as input.

1. Denovo mRNA-seq assembly
      1. Trimmomatic
      2. Trinity
2. Downloading publicly available datasets
3. Configuring and running Maker2 pipeline
