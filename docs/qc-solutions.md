# **QC Solutions for SARS-CoV-2 Genomic Analysis**

PHA4GE Bioinformatics Pipelines &amp; Visualization Working Group <br/>
Libuit KG, Lunn S, Carleton H, Khan W, Kanwar S, van Heusden P, Amrosio F, Southgate J 

# Overview

Next-generation sequencing (NGS) has expanded the approach of genomic analysis for pathogen surveillance systems. The demand for NGS continues to grow, with the need for high throughput, lower costs, and better quality of data. 

However, the quality of NGS sequencing data can be affected by library preparation and sequencing processes, systematic variation in quality scores across sequence reads, biases in sequencing due to base composition, and less-than optimal library fragment sizes and indexes. Such factors can negatively impact the quality of raw sequencing data for downstream analyses. 

In an attempt to assist with quality control (QC) measures, the bioinformatics pipeline and visualization working group of the Public Health Alliance for Genomic Epidemiology (PHA4GE) has drafted this living document to help define the QC challenges for SC2 genomic analysis and suggest a QC systems solutions to address them.

Please note that the QC guidelines in this document are simply an attempt to highlight the most accessible solutions **as per the opinions of our working group** and in no way represent a comprehensive system for QC guidance and bioinformatic solutions. If this document fails to include a valuable public health resource or in some way mischaracterizes a resource mentioned, we encourage community collaboration through pull-requests and/or raised GitHub issues. 

## Contents
- [Process Control For Bioinformatics QC Checkpoints](#process-control-for-bioinformatics-qc-checkpoints)
- [QC Metric Definitions](#qc-metric-definitions)
	- [Read QC Metrics](#read-qc-metrics)
	- [Alignment QC Metrics](#alignment-qc-metrics)
	- [Assembly QC Metrics](#assembly-qc-metrics)
	- [Educational resources](#educational-resources)
- [Community-Defined Guidance Thresholds](#community-defined-guidance-thresholds)
    - [PHA4GE Suggested Thresholds](#pha4ge-suggested-thresholds)
    - [US CDC Resources](#us-cdc-resources)

# Process Control For Bioinformatics QC Checkpoints

Quality Control checkpoints should be conducted at different stages of bioinformatics analysis, including QC of raw read data, pre-processing stages (trimming and filtering), and alignment/assembly.

# QC Metric Definitions

## Read QC Metrics

Different sequencing platforms use different technologies to determine the nucleotide sequence of the genetic material that they are processing, but all of these technologies converge on the fastq file format. For example, Illumina uses a sequencing-by-synthesis approach which involves assembling copies of each read using fluorescently tagged nucleotides and taking high resolution pictures of each read as each nucleotide is added to the read. These images are then captured in BCL files, and BCL files are converted into fastq files using the bcl2fastq program. On the other hand, Oxford Nanopore Technologies sequencing platforms run single strands of nucleic acids through nano-scale protein pores. An electric current is run across the pore, and the changes in current are detected as each nucleotide passes through the pore. The raw electric signal is captured in the fast5 file format and converted into fastq file format using the basecalling program guppy. Due to the nature of these sequencing platforms there are different considerations when assessing the quality of the raw sequence data (the fastq files).



## Alignment QC Metrics

## Assembly QC Metrics

## Educational resources

# Community-Defined Guidance Thresholds

## PHA4GE Suggested Thresholds

## US CDC Resources