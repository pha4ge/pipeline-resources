# **Bioinformatics Solutions for Mpox Genomic Analysis**

PHA4GE Bioinformatics Pipelines &amp; Visualization Working Group <br/>
Libuit KG, Southgate J, Ünal G, Maguire F, Smith E, Kapsak S, van Heusden P, Wright S, Neher R, Diallo A

<details>
 <summary> Document Changelog</summary>
 
- 2022-10-10:
  - First draft published
- 2022-11-28:
  - Nomenclature update: Monkeypox -> Mpox
- 2023-03-09:
  - Add changelog
</details>


# Overview

Genomic analysis of Mpox virus (MPXV) samples by public health laboratories is a critical component in understanding the global outbreak. The integration and awareness of appropriate bioinformatics tools to support these endeavours are potential challenges.

 In an attempt to assist this integration process, the Bioinformatics Pipelines and Visualization Working Group of the [Public Health Alliance for Genomic Epidemiology (PHA4GE)](https://www.pha4ge.org) has drafted this living document to help define the major bioinformatics challenges for MPXV genomic analysis and suggest various open-source and freely available bioinformatics resources to address them.

Please note that the bioinformatics resources listed in this document are simply an attempt to highlight the most accessible solutions **as per the opinions of our working group** and in no way represent a comprehensive list of all available MPXV bioinformatics resources. If this document fails to include a valuable public health resource or in some way mischaracterizes a resource mentioned, we encourage community collaboration through pull-requests and/or raised GitHub issues.


# Background

Mpox is a viral zoonosis which belongs to genus Orthopoxvirus in the family Poxviridae. The virus can be transmitted to humans from animals. After the eradication of smallpox in 1980, mpox emerged and became the most important orthopoxvirus for public health aspects. The virus is an enveloped double-stranded DNA virus and has two distinct genetic clades: the central African (Congo Basin) clade and the west African clades. Historically known as the Congo Basin can cause more severe disease and more transmissible [WHO](https://www.who.int/news-room/fact-sheets/detail/monkeypox). The clinical presentation of this virus is similar to smallpox but some vaccination with smallpox can help individuals for cross-immunity. Lethality rate varies %1-10 and transmission between humans mainly occurs either direct contact or body fluids and via droplets [Berthet, N. et al.](https://rdcu.be/cTOiG). 

MPXV is a linear DNA genome of ≈197 kb. Like other orthopoxviruses, the central coding region sequence (CRS) at MPXV is between ≈56000–120000 and is highly conserved. The genes in the terminal end of MPXV genome responsible for immunomodulation, host range and pathogenicity and also contains at least 4 ORF in the ITR region [Kugelman, JR et al.](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3901482/).  


# Public Mpox Case Databases

This [repository](https://github.com/globaldothealth/monkeypox) contains dated records of curated Mpox cases from the 2022 outbreak (April - ), a data dictionary, and a script used to pull contents from a spreadsheet into JSON and CSV files.

The downloadable [data file](https://www.ecdc.europa.eu/en/publications-data/data-monkeypox-cases-eueea) contains information on the number of mpox cases reported by EU/EEA countries or collected throughout epidemiologic intelligence at ECDC. Each row contains the corresponding data for a country, day of reporting, number of cases and source of information (data are in long format). The file is updated twice a week. You may use the data in line with ECDC’s copyright and data usage policy.

This [report](https://monkeypoxreport.ecdc.europa.eu/) provides an overview of the total number of cases of mpox identified by ECDC and the WHO Regional Office for Europe through IHR mechanisms and official public resources and case-based data through The European Surveillance System (TESSy) up to 9 August 2022. The first summary table and maps (first two tabs) describe the number of cases identified through the different platforms. The following figures and tables describe national case-based data for surveillance of mpox reported in TESSy from all the countries and areas of the WHO European Region, including the 24 countries of the European Union (EU) and the additional three countries of the European Economic Area (EEA).


# Bioinformatics Challenges for Public Health

The PHA4GE Bioinformatics Pipeline and Visualization Working Group has defined four key public health bioinformatics challenges for genomic analysis of SC2 samples:

1. **Generating consensus assemblies** 

2. **Submission of sequence data to international accessible databases** 

3. **Screening for Variants of Concern** 

4. **Performing Phylogenetic analysis of MPXV datasets** 

# Open-Access/Source Bioinformatics Solutions & Resources

## Video resources

- [BV-BRC Mpox and Orthopoxvirus Mini Symposium Playlist](https://youtube.com/playlist?list=PLWfOyhOW_OavOhvmuyUf19nsYASClMnXU)

## Sequencing resources

- [PrimalSeq amplicon scheme and protocol](https://www.protocols.io/view/monkeypox-virus-multiplexed-pcr-amplicon-sequencin-cd8ds9s6)
- [Yale tiled-amplicon protocol](https://www.protocols.io/view/monkeypox-virus-multiplexed-pcr-amplicon-sequencin-5qpvob1nbl4o/v2)


## Generating consensus assemblies
- [TheiaCoV workflows (for Illumina SE/PE, ONT, and fasta files) with MPXV input variables](https://www.protocols.io/view/monkeypox-virus-multiplexed-pcr-amplicon-sequencin-cd8ds9s6)
    - Supports amplicon and metagenomic data
- [GalaxyProject MPXV analysis effort](https://galaxyproject.org/projects/mpxv/)
    - Only supports Illumina PE metagenomic data
- [Nextflow workflow from the Utah PHL](https://github.com/UPHL-BioNGS/Cecret#monkeypox)
    - Supports amplicon and metagenomic data
- [Epi2Me](https://labs.epi2me.io/basic-monkeypox-workflow/)
    - Only supports metagenomic data
-[Viral-Recon](https://github.com/nf-core/viralrecon):
    - Workflow for raw read quality control, de-hosting, assembly, variant calling, and consensus generation for illumina and nanopore monkeypox data. Currently does not include pre-built support for monkeypox (e.g., reference genome, reference annotations, nextclade dataset, and amplicon schemes) but these can be user-supplied on the command line and should be appropriate to the sequencing method (e.g., for amplicon sequencing using the reference used to create the amplicon scheme and for metagenomic sequencing, to be consistent with Nextstrain, you can use NC_063383.1.fasta, NC_063383.1.gff, with the nextclade dataset nextclade_hMPXV_B1_pseudo_ON563414_XXXXXXX).

## Submission of sequence data to international accessible databases
- [Sample Metadata Specifications](https://sprcdn-assets.sprinklr.com/1652/133486a8-9b49-4461-a0d7-211c140947cc-562840094.pdf)
- Preparation and/or Submission of Samples
    - Terra_2_NCBI workflow (only SRA/BioSample at the moment) for programmatic submission of raw read data analysed on Terra to SRA and BioSample
    - [NCBI guide to submit consensus sequences using BankIt](https://www.ncbi.nlm.nih.gov/genbank/monkeypox_submission/)
- Assess Data Quality Prior to Submission


## Screening for Variants of Concern

- [Nextclade](https://clades.nextstrain.org/)
    - assignment of consensus sequences to Nextstrain clades, quality control, and mutation effect annotation.  References pre-built for inferred ancestral monkeypox, the human monkeypox clade, and the specific B.1 human monkeypox clade. 


## Performing Phylogenetic analysis of MPXV datasets

- [Augur](https://docs.nextstrain.org/projects/augur/en/stable/index.html)
    - A bioinformatics toolkit for phylogenetic analysis which constructs phylogenetic trees that can be visualised in NextStrain 

- [Nextstrain Mpox build workflow](https://github.com/nextstrain/monkeypox)
    - Workflow to perform contextualised phylogenetic analysis of monkeypox consensus sequences (by default using the human monkeypox reference genome NC_063383.1)

- [Taxonium](https://taxonium.org/?treeUrl=https%3A%2F%2Fns-proxy.vercel.app%2Fapi%2Fcharon%2FgetDataset%3Fprefix%3Dmonkeypox%2Fhmpxv1&ladderizeTree=true&treeType=nextstrain&color=%7B%22field%22%3A%22meta_country%22%7D)
    - Tool for exploring large phylogenetic trees - Mpox sequences from GenBank

## Publicly available data
To help getting started with phylogenetic analysis, Nextstrain provides MPXV data available on NCBI in aggregated form:
- [Sequences](https://data.nextstrain.org/files/workflows/monkeypox/sequences.fasta.xz)
- [Metadata](https://data.nextstrain.org/files/workflows/monkeypox/metadata.tsv.gz)

Pairwise alignments with [Nextclade](https://clades.nextstrain.org/) against the [reference sequence MPXV-M5312_HM12_Rivers](https://www.ncbi.nlm.nih.gov/nuccore/NC_063383), insertions relative to the reference, and translated ORFs are available:

- [Alignment](https://data.nextstrain.org/files/workflows/monkeypox/alignment.fasta.xz)
- [Insertions](https://data.nextstrain.org/files/workflows/monkeypox/insertions.csv.gz)
- [Translations](data.nextstrain.org/files/workflows/monkeypox/translations.zip)

