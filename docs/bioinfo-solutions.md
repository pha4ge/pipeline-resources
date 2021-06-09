# **Bioinformatics Solutions for SARS-CoV-2 Genomic Analysis**

PHA4GE Bioinformatics Pipelines &amp; Visualizations Working Group <br/>
Libuit KG, Park D, van Heusden P, Neher R, Kapsak CJ, Southgate J, Bridges D, Mboowa G, Lunn S, Langhorst B

# Overview

Genomic analysis of SARS-CoV-2 (SC2) samples is an increasingly critical function to public health laboratories around the world. Integration of the appropriate bioinformatics solutions to support these works, however, can be an overwhelming challenge.

 In an attempt to assist this integration process, the bioinformatics pipeline and visualization working group of the Public Health Alliance for Genomic Epidemiology (PHA4GE) has drafted this living document to help define the major bioinformatics challenges for SC2 genomic analysis and suggest various open-source and freely available bioinformatics resources to address them.

Please note that the bioinformatics resources listed in this document are simply an attempt to highlight the most accessible solutions **as per the opinions of our working group** and in no way represent a comprehensive list of all available SC2 bioinformatics resources. If this document fails to include a valuable public health resource or in some way mischaracterizes a resource mentioned, we encourage community collaboration through pull-requests and/or raised GitHub issues.

# Bioinformatics Challenges for Public Health

The PHA4GE bioinformatics pipeline and visualization working group has defined four key public health bioinformatics challenges for genomic analysis of SC2 samples:

1. **Generating consensus assemblies from PCR tiling NGS data:** Tiled amplicon sequencing--through the Artic V3 protocol, for example--is the most commonly adopted method for generating SC2 sequencing data. These sequencing experiments generate thousands of amplicon reads that represent fragments of the original SC2 genome present in a sample. As a result, one of the first bioinformatics challenges laboratories run into is the assembly of PCR tiling NGS data into a contiguous SC2 genome from which powerful public health insights can be derived, such as lineage typing and genomic epidemiology studies that help inform public-health decision making.

2. **Submitting raw sequence data (fastq), consensus assemblies (fasta), and relevant sample metadata to internationally-accessible databases:** Sharing of sample read and assembly data through internationally accessible databases allows insights to be drawn about how the virus is spreading and mutating across the globe; the more freely available these data are to international researchers and public health scientists, the stronger our decision making can be.

3. **Screening sequenced SC2 samples for variants of concern:** The detection of certain genetic variants of the SARS-CoV-2 virus may have a significant impact on the decisions of public health officials. Thus, an ability to accurately and reliably screen for variants of interest and variants of concern, such as B.1.1.7 or B.1.617, is a critical component to the bioinformatics analysis of SC2 genomes.

4. **Performing phylogenetic analysis of SC2 datasets:** Genetic relatedness as inferred through phylogenetic analysis of SC2 datasets can be a powerful proxy for epidemiological associations that help resolve transmission networks, enable real-time surveillance, provide insights of the variance-over-time of SC2 samples, and support local outbreak investigations

# Community Resources

## 1. Generating consensus assemblies from PCR tiling NGS data

The bioinformatics resources listed below are open-source pipelines that run on general-purpose, containerized workflow infrastructure to generate consensus SC2 assemblies from PCR tiling NGS data. While some parameters and modules may differ slightly, each pipeline will perform read mapping to the Wuhan-1 reference genome, remove primer regions from the mapped read data, and generate a consensus assembly based on conserved and variant positions identified in the resulting alignment. These resources have been organized into three categories: [Terra](app.terra.bio) and [Galaxy](https://galaxyproject.org/) Workflows, Web-Accessible Software as a Service (SaaS) Solutions, and Command-Line Interface (CLI) gools and are listed in no particular order.

<details>
 <summary>Terra and Galaxy Workflows</summary>

1. [Broad viral-ngs](https://dockstore.org/organizations/BroadInstitute/collections/pgs)
  - **Brief Description** : The viral-ngs workflow collection contains many tools for viral analysis. The consensus genome caller is called assemble\_refbased and should work for any low-diversity microbial genome and is appropriate for viruses stemming from a single point-source outbreak, such as SARS-CoV-2. Accepts Illumina paired, single, or mixed reads, as well as ONT reads. Accepts metagenomic or amplicon-based reads with primer trimming.
  - **Developed/supported by:** Broad Institute Viral Genomics 
  - **Documentation** : [Technical documentation (ReadTheDocs)](https://viral-ngs.readthedocs.io/en/latest/)
  - **User base:** [H3Africa](https://h3africa.org/index.php/consortium/genomic-characterization-and-surveillance-of-microbial-threats-in-west-africa/) West African sites ([RUN](http://acegid.org/), [KGH](https://vhfc.org/consortium/people/), [UCAD](https://www.ucad.sn/))
  - **Workflow language:** WDL
    - **Web/Cloud GUI Platforms:** Terra, DNAnexus,
    - **CLI Platforms:** Cromwell (local HPC, cloud), miniWDL
2. [Titan Workflows for Genomic Characterization](https://dockstore.org/organizations/Theiagen/collections/PublicHealthViralGenomics)
  - **Brief Description** : The Titan Series includes four separate WDL workflows (Titan\_Illumina\_PE, Titan\_Illumina\_SE, Titan\_ClearLabs, and Titan\_ONT) that process NGS read data from four different sequencing approaches: Illumina paired-end, Illumina single-end, Clear Labs, and Oxford Nanopore Technology (ONT)) to generate consensus assemblies, produce relevant quality-control metrics for both the input read data and the generated assembly, and assign samples with a lineage and clade designation using Pangolin and NextClade, respectively.
  - **Developed/supported by:** Theiagen Genomics
  - **Documentation:** [Technical documentation (ReadTheDocs)](https://public-health-viral-genomics-theiagen.readthedocs.io/en/latest/overview.html), [step-by-step protocols (Protocols.io)](https://www.protocols.io/file-manager/9EF18A27777511EBA1C60A58A9FEAC2A), and [video tutorials (YouTube Playlist)](https://www.youtube.com/watch?v=fy0Hm0lfIas&amp;list=PLU47xRg_MKJrtyoFwqGiywl7lQj6vq8Uz)
  - **User base:** US PHLs
  - **Workflow language:** WDL
    - **Web/Cloud GUI Platforms:** Terra\* (primary), DNAnexus,
    - **CLI Platforms:** Cromwell (local HPC, cloud), miniWDL
3. [COVID-19 Galaxy Workflows](https://covid19.galaxyproject.org/artic/)
  - **Brief Description** : Several Galaxy workflows for performing SC2 consensus genome assembly have been available including a Galaxy workflow for the analysis of Illumina paired-end sequenced ARTIC amplicon data and the SARS-CoV-2 RECoVERY pipeline hosted on the Galaxy instance ARIES; SARS-CoV-2 RECoVERY can generate SC2 consensus genomes from Illumina, Ion Torrent, and Nanopore read data.
  - **Developed/supported by:** usegalaxy.eu ([https://covid19.galaxyproject.org/artic/](https://covid19.galaxyproject.org/artic/))
  - **Documentation** : [https://covid19.galaxyproject.org/artic/](https://covid19.galaxyproject.org/artic/)
  - ARIES/Istituto Superiore di Sanità ([https://aries.iss.it/u/arnold-knijn/w/sars-cov-2recovery31](https://aries.iss.it/u/arnold-knijn/w/sars-cov-2recovery31))
  - **User base:** usegalaxy.\* (preprint in progress), ARIES ([https://www.biorxiv.org/content/10.1101/2021.01.16.425365v2](https://www.biorxiv.org/content/10.1101/2021.01.16.425365v2))
  - **Workflow language:** Galaxy
    - **Web/Cloud GUI Platforms:** GalaxyProject
</details>

<details>
 <summary>Web-Accessible SaaS Solutions</summary>
 
1. [IDSeq (CZ BioHub)](https://idseq.net/)
  - **Brief Description** : User-friendly software platform originally developed for metagenomics studies that has since been repurposed to include SC2 consensus assembly calling from paired-end Illumina data
  - **Developed/supported by:** CZI
  - **User base:** CZ BioHub &amp; partners
  - **User-interface** : Web application on BioHub-funded AWS
2. [EDGE COVID-19](https://edge-covid19.edgebioinformatics.org/)
  - **Brief Description** : EDGE COVID-19 is a derivative of the original EDGE Bioinformatics software (Li _et al._ 2017) that was developed to perform reference-based SC2 assemblies and quality assessment of Illumina or Nanopore read data.
  - **Developed/supported by:** Los Alamos National Laboratories
  - **User base:** LANL &amp; partners
  - **User-interface** : Web application on LANL hardware
</details>

<details>
 <summary>Command-line interface (CLI) Tools</summary>
 
 1. [SIGNAL (SARS-CoV-2 Illumina GeNome Assembly Line; CanCOGeN)](https://github.com/jaleezyy/covid-19-signal)
  - **Brief Description** : SnakeMake pipeline for generating SC2 consensus assemblies from Illumina read data; being utilized to support SC2 sequencing efforts throughout the state of California, USA through the COVID-Tracker initiative
  - **Developed/supported by:** Nassir, JA, _et al._
  - **Documentation** : [Technical Documentation (GitHub README)](https://github.com/jaleezyy/covid-19-signal)
  - **User base:** CA PHLs
  - **User-interface** : CLI (Snakemake)
2. [ARTIC nCOV19 (ARTIC Network; Connor-lab)](https://github.com/connor-lab/ncov2019-artic-nf)
  - **Brief Description** : Configured conda environment that enables access to Oxford Nanopore or Illumina consensus sequence assemblers: Medaka (ONT), NanoPolish (ONT) or BWA (Illumina)
  - **Developed/supported by:** COG UK / ARTIC
  - **Documentation** : [https://github.com/connor-lab/ncov2019-artic-nf](https://github.com/connor-lab/ncov2019-artic-nf)
  - **User base:** COG UK
  - **Workflow language:** Nextflow
    - **CLI Platforms:** Nextflow cli client, Nextflow Tower (local HPC, cloud, etc)
3. [StaPH-B ToolKit](https://github.com/StaPH-B/staphb_toolkit)
  - **Brief Description** : Two StaPH-B workflows for performing SC2 consensus genome assembly have been available, Cecret a pipeline developed for the analysis of single or paired-end Illumina reads and Monroe, a workflow with various subcommands that perform consensus genome assembly from Illumina and Nanopore read data.
  - **Developed/supported by:** StaPH-B
  - **Documentation** : [https://staph-b.github.io/staphb\_toolkit/](https://staph-b.github.io/staphb_toolkit/install/), [Python Package Index (PyPI)](https://pypi.org/project/staphb-toolkit/)
  - **User base:** US PHLs
  - **User-interface** : CLI (Python package)
 
</details>

## 2. Sharing raw sequence data (fastq) and consensus assemblies (fasta) through internationally-accessible databases (GISAID/NCBI)

Below is a list of resources developed to assist in the preparation and submission of raw NGS read data (fastq files), SC2 consensus assemblies (fasta files), and contextual sample metadata to internationally-accessible databases. We have also included a list of bioinformatics software designed to assess the quality of SC2 data; we recommend the use of such software prior to submission to avoid the inadvertent sharing of poor quality, contaminated, or otherwise misleading SC2 data. Additional information regarding the interpretation of read and assembly quality metrics for SC2 data will be made available as a separate document.

<details>
 <summary>Recommended SC2 Sample Metadata Specifications</summary>
 
- [PHA4GE Contextual Data Specifications](https://www.preprints.org/manuscript/202008.0220/v1)
  - **Database Target(s)**: GISAID, ENA, SRA, Genbank
  - **Brief Description** : A SARS-CoV-2 contextual data specification based on harmonisable, publicly available, community standards. The specification is implementable via a collection template, as well as an array of protocols and tools to support the harmonisation and submission of sequence data and contextual information to public repositories.
  - **Developed/supported by:** PHA4GE
  - **Documentation** : [Technical documentation (GitHub README)](https://github.com/pha4ge/SARS-CoV-2-Contextual-Data-Specification)
  - **User base:** Global public health community
 
</details>

<details>
 <summary>Bioinformatics Solutions to Prepare and/or Submit SC2 Sample Data</summary>
 
- [Broad viral-ngs](https://dockstore.org/organizations/BroadInstitute/collections/pgs) (described above)
  - **Database Target(s)**: SRA, GenBank, GISAID
  - **Brief Description** : The viral-ngs workflow collection contains workflows (sarscov2\_genbank, sarscov2\_sra\_to\_genbank, sarscov2\_illumina\_full) that prepare data for Genbank and GISAID submission (and SRA submission if starting from raw reads).
  - **Developed/supported by:** Broad Institute Viral Genomics
  - **Documentation** : [Technical documentation (ReadTheDocs)](https://viral-ngs.readthedocs.io/en/latest/)
  - **User base:** [H3Africa](https://h3africa.org/index.php/consortium/genomic-characterization-and-surveillance-of-microbial-threats-in-west-africa/) West African sites ([RUN](http://acegid.org/), [KGH](https://vhfc.org/consortium/people/), [UCAD](https://www.ucad.sn/))
  - **Workflow language:** WDL
    - **Web/Cloud GUI Platforms:** Terra, DNAnexus,
  - **CLI Platforms:** Cromwell (local HPC, cloud), miniWDL
- [Theiagen&#39;s Mercury Workflows](https://dockstore.org/organizations/Theiagen/collections/PublicHealthViralGenomics)
  - **Database Target(s)**: GenBank, GISAID (SRA submission prep in development)
  - **Brief Description** : The Mercury Series includes three separate WDL workflows (Mercury\_SE\_Prep, Mercury\_PE\_Prep, and Mercury\_Batch) that prepare SC2 consensus assemblies (fasta files) and contextual sample metadata sample for submission to GISAID and NCBI&#39;s GenBank database.
  - **Developed/supported by:** Theiagen Genomics
  - **Documentation:** [Technical documentation (ReadTheDocs)](https://public-health-viral-genomics-theiagen.readthedocs.io/en/latest/overview.html), [step-by-step protocols (Protocols.io)](https://www.protocols.io/file-manager/9EF18A27777511EBA1C60A58A9FEAC2A), and [video tutorials (YouTube Playlist)](https://www.youtube.com/watch?v=fy0Hm0lfIas&amp;list=PLU47xRg_MKJrtyoFwqGiywl7lQj6vq8Uz)
  - **User base:** US PHLs
  - **Workflow language:** WDL
    - **Web/Cloud GUI Platforms:** Terra\* (primary), DNAnexus,
    - **CLI Platforms:** Cromwell (local HPC, cloud), miniWDL
- [Galaxy ENA Submission Plugin](https://github.com/galaxyproject/tools-iuc/tree/master/tools/ena_upload)
  - **Database Target(s)**: ENA
  - **Brief Description** : Galaxy plugin for direct submission to the European Nucleotide Archive database
  - **Developed/supported by:** [Galaxy IUC (Intergalactic Utilities Commission)](https://galaxyproject.org/iuc/)
  - **Documentation**: [https://github.com/ELIXIR-Belgium/ena-upload-container](https://github.com/ELIXIR-Belgium/ena-upload-container)
  - **User base:** European PHLs
  - **Workflow language:** Galaxy
    - **Web/Cloud GUI Platforms:** GalaxyProject
 
</details>

<details>
 <summary>Bioinformatics Solutions to Assess Data Quality Prior to Submission</summary>
 
- [VADR - Viral Annotation DefineR](https://github.com/ncbi/vadr)
  - **Brief Description** : VADR is a suite of CLI tools for classifying and analyzing sequences homologous to a set of reference models of viral genomes or gene families. With regards to SC2, laboratories have utilized VADR to identify samples with potentially mis-assembled genomes that are likely to be rejected from an internationally-accessible database.
  - **Developed/supported by:** NCBI
  - **Documentation** : [Technical Documentation (GitHub Wiki)](https://github.com/ncbi/vadr/wiki/Coronavirus-annotation)
  - **User base:** NCBI GenBank & US PHLs
  - **Accessibility** : [Local install](https://github.com/ncbi/vadr/blob/master/documentation/install.md#top) or the [StaPH-B Docker Image](https://hub.docker.com/r/staphb/vadr/)
- [Broad viral-ngs](https://dockstore.org/organizations/BroadInstitute/collections/pgs) (Terra workflow described above; includes VADR)
- [Titan Workflows for Genomic Characterization](https://dockstore.org/organizations/Theiagen/collections/PublicHealthViralGenomics) (Terra workflow described above; includes VADR)
- [COVID-19 Galaxy Workflows](https://covid19.galaxyproject.org/artic/) (Galaxy resources described above)
- [IDSeq (CZ BioHub)](https://idseq.net/) (SaaS solution described above)
- [EDGE COVID-19](https://edge-covid19.edgebioinformatics.org/) (SaaS solution described above)
- [SIGNAL (SARS-CoV-2 Illumina GeNome Assembly Line; CanCOGeN)](https://github.com/jaleezyy/covid-19-signal) (CLI tool described above)
- [ARTIC nCOV19 (ARTIC Network; Connor-lab)](https://github.com/connor-lab/ncov2019-artic-nf) (CLI tool described above)
- [StaPH-B ToolKit](https://github.com/StaPH-B/staphb_toolkit) (CLI tool described above; VADR included in the Cecret workflow)
 
</details>
