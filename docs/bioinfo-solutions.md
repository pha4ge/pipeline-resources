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

# Open-Access/Source Bioinformatics Solutions & Resources

## 1. Generating consensus assemblies from PCR tiling NGS data

The bioinformatics resources listed below are open-source pipelines that run on general-purpose, containerized workflow infrastructure to generate consensus SC2 assemblies from PCR tiling NGS data. While some parameters and modules may differ slightly, each pipeline will perform read mapping to the Wuhan-1 reference genome, remove primer regions from the mapped read data, and generate a consensus assembly based on conserved and variant positions identified in the resulting alignment. These resources have been organized into three categories: [Terra](app.terra.bio) and [Galaxy](https://galaxyproject.org/) Workflows, Web-Accessible Software as a Service (SaaS) Solutions, and Command-Line Interface (CLI) tools and are listed in no particular order.

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
 
1. [IDSeq](https://idseq.net/)
  - **Brief Description** : User-friendly software platform originally developed for metagenomics studies that has since been repurposed to include SC2 consensus assembly from Oxford Nanopore or paired-end Illumina data
  - **Developed/supported by:** [Chan Zuckerberg Initiative (CZI)](https://chanzuckerberg.com/) 
  - **User base:** CZ Biohub &amp; partners; access available on request to other users
  - **User-interface** : Web application on CZI-funded AWS
2. [EDGE COVID-19](https://edge-covid19.edgebioinformatics.org/)
  - **Brief Description** : EDGE COVID-19 is a derivative of the original EDGE Bioinformatics software (Li _et al._ 2017) that was developed to perform reference-based SC2 assemblies and quality assessment of Illumina or Nanopore read data.
  - **Developed/supported by:** Los Alamos National Laboratories
  - **Documentation**: [EDGE COVID-19 User Guide](https://edge-covid19.edgebioinformatics.org/docs/EDGE_COVID-19_guide.pdf)
  - **User base:** LANL &amp; partners
  - **User-interface** : Web application on LANL hardware, [local instance using Docker](https://hub.docker.com/r/bioedge/edge-covid19
)
</details>

<details>
 <summary>Command-line interface (CLI) Tools</summary>
 
 1. [SIGNAL (SARS-CoV-2 Illumina GeNome Assembly Line; CanCOGeN/OnCOV)](https://github.com/jaleezyy/covid-19-signal)
  - **Brief Description**: Quality control, assembly, and analysis snakemake workflow for Illumina-based viral amplicon sequencing. Includes de-hosting via competitive mapping, freebayes variant and consensus generation, lineage assignment, interactive HTML run summaries, and integration with the [ncov-tools](https://github.com/jts/ncov-tools/) QC workflow.
  - **Developed/supported by:** [CARD/McArthur Lab](https://mcarthurbioinformatics.ca), lead maintainers: Jalees Nasir & Finlay Maguire 
  - **Documentation** : [Technical Documentation (GitHub README)](https://github.com/jaleezyy/covid-19-signal)
  - **User base:** CA PHLs & academic partners
  - **User-interface** : CLI (Snakemake)
2. [ARTIC nCOV19 (ARTIC Network; Connor-lab)](https://github.com/connor-lab/ncov2019-artic-nf)
  - **Brief Description** : Configured conda environment that enables access to Oxford Nanopore or Illumina consensus sequence assemblers: Medaka (ONT), NanoPolish (ONT) or BWA (Illumina)
  - **Developed/supported by:** COG UK / ARTIC
  - **Documentation** : [Technical Documentation (GitHub README)](https://github.com/connor-lab/ncov2019-artic-nf/blob/master/README.md)
  - **User base:** COG UK
  - **Workflow language:** Nextflow
    - **CLI Platforms:** Nextflow cli client, Nextflow Tower (local HPC, cloud, etc)
3. [StaPH-B ToolKit](https://github.com/StaPH-B/staphb_toolkit)
  - **Brief Description** : Two StaPH-B workflows for performing SC2 consensus genome assembly have been available: Cecret, a pipeline developed for the analysis of single or paired-end Illumina reads. and Monroe, a workflow with various subcommands that perform consensus genome assembly from either Illumina or Nanopore read data.
  - **Developed/supported by:** StaPH-B
  - **Documentation** : [https://staph-b.github.io/staphb\_toolkit/](https://staph-b.github.io/staphb_toolkit/install/), [Python Package Index (PyPI)](https://pypi.org/project/staphb-toolkit/)
  - **User base:** US PHLs
  - **User-interface** : CLI (Python package)
 
</details>

## 2. Submitting raw sequence data (fastq), consensus assemblies (fasta), and relevant sample metadata to internationally-accessible databases

Below is a list of resources developed to assist in the preparation and submission of raw NGS read data (fastq files), SC2 consensus assemblies (fasta files), and contextual sample metadata to internationally-accessible databases such as [NCBI](https://www.ncbi.nlm.nih.gov/sars-cov-2/), [ENA](https://www.ebi.ac.uk/ena/browser/home), and [GISAID](https://www.gisaid.org/). We have also included a list of bioinformatics software designed to assess the quality of SC2 data; we recommend the use of such software prior to submission to avoid the inadvertent sharing of poor quality, contaminated, or otherwise misleading SC2 data. Additional information regarding the interpretation of read and assembly quality metrics for SC2 data will be made available as a separate document.

<details>
 <summary>Recommended SC2 Sample Metadata Specifications</summary>
 
- [PHA4GE Contextual Data Specifications](https://www.preprints.org/manuscript/202008.0220/v1)
  - **Database Target(s)**: GISAID, ENA, SRA, Genbank
  - **Brief Description** : A SARS-CoV-2 contextual data specification based on harmonisable, publicly available, community standards. The specification is implementable via a collection template, as well as an array of protocols and tools to support the harmonisation and submission of sequence data and contextual information to public repositories.
  - **Developed/supported by:** PHA4GE
  - **Documentation** : [Technical documentation (GitHub README)](https://github.com/pha4ge/SARS-CoV-2-Contextual-Data-Specification)
  - **User base:** Global public health community
  - **Protocols:** [NCBI Submission](http://dx.doi.org/10.17504/protocols.io.bsypnfvn), [ENA Submission](http://dx.doi.org/10.17504/protocols.io.buqnnvve), & [GISAID Submission](http://dx.doi.org/10.17504/protocols.io.bumknu4w)
 
</details>

<details>
 <summary>Bioinformatics Solutions to Prepare and/or Submit SC2 Sample Data</summary>

- [Galaxy ENA Submission Plugin](https://github.com/galaxyproject/tools-iuc/tree/master/tools/ena_upload)
  - **Database Target(s)**: ENA
  - **Brief Description** : Galaxy plugin for direct submission to the European Nucleotide Archive database
  - **Developed/supported by:** [Galaxy IUC (Intergalactic Utilities Commission)](https://galaxyproject.org/iuc/)
  - **Documentation**: [https://github.com/ELIXIR-Belgium/ena-upload-container](https://github.com/ELIXIR-Belgium/ena-upload-container)
  - **User base:** European PHLs
  - **Workflow language:** Galaxy
    - **Web/Cloud GUI Platforms:** GalaxyProject  
- [Theiagen&#39;s Mercury Workflows](https://dockstore.org/organizations/Theiagen/collections/PublicHealthViralGenomics)
  - **Database Target(s)**: GenBank, GISAID (SRA submission prep in development)
  - **Brief Description** : The Mercury Series includes three separate WDL workflows (Mercury\_SE\_Prep, Mercury\_PE\_Prep, and Mercury\_Batch) that prepare SC2 consensus assemblies (fasta files) and contextual sample metadata sample for submission to GISAID and NCBI&#39;s GenBank database.
  - **Developed/supported by:** Theiagen Genomics
  - **Documentation:** [Technical documentation (ReadTheDocs)](https://public-health-viral-genomics-theiagen.readthedocs.io/en/latest/overview.html), [step-by-step protocols (Protocols.io)](https://www.protocols.io/file-manager/9EF18A27777511EBA1C60A58A9FEAC2A), and [video tutorials (YouTube Playlist)](https://www.youtube.com/watch?v=fy0Hm0lfIas&amp;list=PLU47xRg_MKJrtyoFwqGiywl7lQj6vq8Uz)
  - **User base:** US PHLs
  - **Workflow language:** WDL
    - **Web/Cloud GUI Platforms:** Terra\* (primary), DNAnexus,
    - **CLI Platforms:** Cromwell (local HPC, cloud), miniWDL
- [Broad viral-ngs](https://dockstore.org/organizations/BroadInstitute/collections/pgs) (Terra workflow described above)
   - **Database Target(s)**: GISAID, GenBank, & SRA
- [EDGE COVID-19](https://edge-covid19.edgebioinformatics.org/) (SaaS solution described above) 
    - **Database Target(s)**: GISAID, GenBank, & SRA


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

## 3. Screening sequenced SC2 samples for variants of concern &amp; general lineage typing

These tools either assign a clade or lineage descriptor to consensus sequences or provide databases for lookup of information on variants in the SARS-CoV-2 genome. As variants of concern are listed by their lineage descriptor (typically PANGO lineage or sometimes Nextclade clades) these tools help identify variants of concern.

<details>
 <summary>Bioinformatics tools for SC2 lineage or clade assignment</summary>

- [Pangolin (Phylogenetic Assignment of Named Global Outbreak LINeages)](https://cov-lineages.org/pangolin.html)
  - **Brief Description** : Tool developed to implement the dynamic nomenclature of SARS-CoV-2 lineages, known as the Pango nomenclature. It allows a user to assign a SARS-CoV-2 genome sequence the most likely lineage (PANGO lineage) to SARS-CoV-2 query sequences.
  - **Developed/supported by:** Pangolin Network
  - **Documentation** : [Technical Documentation (Pangolin Website)](https://cov-lineages.org/pangolin.html), [publication (Nature Microbiology)](https://www.nature.com/articles/s41564-020-0770-5)
  - **User base:** Global Public Health Community
  - **Accessibility** : [Web application](https://pangolin.cog-uk.io/) &amp; [CLI tool](https://github.com/cov-lineages/pangolin)
  - **Bioinformatics workflows that incorporate NextClade clade assignments:**
    - [Broad viral-ngs](https://dockstore.org/organizations/BroadInstitute/collections/pgs) (Terra workflow described above)
    - [Titan Workflows for Genomic Characterization](https://dockstore.org/organizations/Theiagen/collections/PublicHealthViralGenomics) (Terra workflow described above)
    - [COVID-19 Galaxy Workflows](https://covid19.galaxyproject.org/artic/) (Galaxy resources described above)
    - {IDSeq](https://idseq.net/) (SaaS solution described above)
    - [EDGE COVID-19](https://edge-covid19.edgebioinformatics.org/) (SaaS solution described above)
    - [SIGNAL (SARS-CoV-2 Illumina GeNome Assembly Line; CanCOGeN)](https://github.com/jaleezyy/covid-19-signal) (CLI tool described above)
    - [StaPH-B ToolKit](https://github.com/StaPH-B/staphb_toolkit) (CLI tool described above)
- [NextClade](https://clades.nextstrain.org/)
  - **Brief Description** : Tool that identifies differences between your sequences and a reference sequence used by Nextstrain, uses these differences to assign your sequences to clades, and reports potential sequence quality issues in your data
  - **User-interface** : [Web application](https://clades.nextstrain.org/) &amp; CLI tool
  - **Help/community/discussion** : [discussion.nextstrain.org](http://discussion.nextstrain.org/)
  - **Bioinformatics workflows that incorporate NextClade clade assignments:**
    - [Broad viral-ngs](https://dockstore.org/organizations/BroadInstitute/collections/pgs) (Terra workflow described above)
    - [Titan Workflows for Genomic Characterization](https://dockstore.org/organizations/Theiagen/collections/PublicHealthViralGenomics) (Terra workflow described above)
    - [COVID-19 Galaxy Workflows](https://covid19.galaxyproject.org/artic/) (Galaxy resources described above)
    - I[DSeq](https://idseq.net/) (SaaS solution described above)
    - [StaPH-B ToolKit](https://github.com/StaPH-B/staphb_toolkit) (CLI tool described above)

</details>


<details>
 <summary>Public Health Resources that Track &amp; Visualize SC2 Variants Over Time</summary>
 
  - [PANGO cov-lineages](https://cov-lineages.org/)
    - **Brief Description** : Track global prevalences of PANGO lineages
    - **Developed/supported by:** Pangolin Network
  - [Covariants](https://covariants.org/)
    - **Brief Description** : Track global prevalence of Nextclade-annotated lineages
    - **Developed/supported by:** NextStrain Team
  - [Outbreak.info](https://outbreak.info/)
    - **Brief Description** : Epidemiological info including PANGO lineage prevalence
    - **Developed/supported by:** [Su](http://sulab.org/), [Wu](http://wulab.io/), and [Andersen](https://andersen-lab.com/) labs at Scripps Research
  - [COV-GLUE](http://cov-glue.cvr.gla.ac.uk/)
    - **Brief Description** : CoV-GLUE contains a database of amino acid replacements, insertions and deletions which have been observed in GISAID hCoV-19 sequences sampled from the pandemic Epidemiological info including PANGO lineage prevalence
    - **Developed/supported by:** COG-UK
  - [2019nCoVR](https://bigd.big.ac.cn/ncov/)
    - **Brief Description** :2019nCoVR features comprehensive integration of genomic and proteomic sequences as well as their metadata information from the GISAID, NCBI, NMDC and CNCB/NGDC. It also incorporates a wide range of relevant information including scientific literatures, news, and popular articles for science dissemination, and provides visualization functionalities for genome variation analysis results based on all collected SARS-CoV-2 strains.
    - **Developed/supported by:** China National Center for Bioinformation (CNCB)
  - [CoVizu](https://filogeneti.ca/covizu/)
    - **Brief Description:** CoVizu is an [open source project](https://github.com/PoonLab/CoVizu) endeavouring to visualize the global diversity of SARS-CoV-2 genomes, which are provided by the [GISAID Initiative](https://gisaid.org/).
    - **Developed/supported by:** [Poon Laboratory](https://www.schulich.uwo.ca/pathol/people/bios/faculty/poon_art.html) of Western University
  - [Annotation of SARS-2 Coronavirus Genome (Observable)](https://observablehq.com/@delphine-l/annotation-of-sars-2-coronavirus-genome)
    - **Brief Description:** Annotation of variation in the genome with some notes on what is known about the various amino acids
    - **Developed/supported by:** Delphine Lariviere (Penn State University)

</details>

<details>
 <summary>Bioinformatics Tools to Track &amp; Visualize Your Own SC2 Variants Over Time </summary>
 
 - [KRISP R-scripts](https://github.com/krisp-kwazulu-natal/africa-covid19-genomics)
    - **Brief Description** : Open-source repository containing all the code, data and information needed to reproduce the analyses for the [African genomic epidemiology manuscript](https://www.nature.com/articles/s41591-021-01255-3).
    - **Developed/supported by:** Emmanuel James San (University of KwaZulu-Natal)
    - **Documentation** : [Technical Documentation (GitHub README)](https://github.com/krisp-kwazulu-natal/africa-covid19-genomics#readme), [publication (Nature Medicine)](https://www.nature.com/articles/s41591-021-01255-3)
    - **Accessibility** : [RCL-Scripts](https://github.com/krisp-kwazulu-natal/africa-covid19-genomics#readme)
  - [GISAID Processing](https://github.com/pvanheus/GISAID_processing)
    - **Brief Description** : Open-source repository containing python scripts to process GISIAD data into frequency graphs
    - **Developed/supported by:** Peter van Heusden (University of Western Cape)
    - **Documentation** : [Technical Documentation (GitHub README)](https://github.com/pvanheus/GISAID_processing/blob/main/README.md)
    - **Accessibility** : [Python-Scripts](https://github.com/krisp-kwazulu-natal/africa-covid19-genomics#readme)
 
 </details>
 
## 4. Performing phylogenetic analysis of SC2 datasets

_The tools listed below perform phylogenetic analyses of different complexity, ranging from web-apps to command-line tools that need to run on HPC facilities. The selected tools are integrated with visualization features that facilitate the interrogation of the results, but beware that such inferences might be uncertain and often require careful interpretation._


<details>
 <summary>Public Health Resources Performing Global SC2 Phylogenetic Analysis </summary>


- [NextStrain](https://nextstrain.org/)
  - **Brief Description** : Nextstrain is an open-source project to harness the scientific and public health potential of pathogen genome data.
  - **Developed/supported by:** Fred Hutch/Basel (Nextstrain team)
  - **User base:** USA based groups
  - **Documentation** : [docs](https://docs.nextstrain.org/en/latest/index.html)
  - **Help/community/discussion** : [discussion.nextstrain.org](http://discussion.nextstrain.org/)
  - Implementations for compute steps (&quot;augur&quot;):
    - [**nextstrain/ncov**](https://github.com/nextstrain/ncov) snakemake pipeline
      - **Description:** The authoritative implementation of the Nextstrain &quot;augur&quot; pipeline that takes genomes and metadata to trees and visualizations.
      - **Developed/supported by:** Fred Hutch/Basel (Nextstrain team)
      - **Workflow language:** Snakemake
    - [Broad viral-ngs](https://dockstore.org/organizations/BroadInstitute/collections/pgs) (Terra workflow described above)
    - [Theiagen&#39;s Public Health Viral Genomics WDL Workflows](https://dockstore.org/organizations/Theiagen/collections/PublicHealthViralGenomics) (Terra workflow described above)
- [Microreact](https://microreact.org/)
  - **Developed/supported by:** Centre for Genomic Pathogen Surveillance (CGPS)
  - **User base:** COG-UK, New Zealand, etc
  - **User-interface:** Web application / centrally hosted service

</details>

<details>
 <summary>Offlineable Browser-Based Web Applications</summary>

- [Auspice](https://auspice.us/)
  - **Developed/supported by:** Fred Hutch/Basel (Nextstrain team)
  - **Documentation** : [Technical documentation (GitHub README)](https://github.com/nextstrain/auspice#readme), [NextStrain discussion Forum](https://discussion.nextstrain.org/)
  - **User-interface:** offlineable browser-based web app
- [MicrobeTrace](https://microbetrace.cdc.gov/MicrobeTrace/)
  - **Developed/supported by:** US CDC
  - **Documentation** : https://github.com/CDCgov/MicrobeTrace
  - **User-interface:** offlineable browser-based web app
- [UShER](https://genome.ucsc.edu/cgi-bin/hgPhyloPlace)
  - **Developed/supported by:** UCSC
  - **User-interface:** offlineable browser-based web app
  - Places user provided sequences on very large reference trees, extracts the relevant subtree, and provides a visualization

</details>

<details>
 <summary>Command-line interface (CLI) Tools</summary>

- [Grinch](https://github.com/cov-lineages/grinch)
  - **Developed/supported by:** PANGO, cov-lineages
  - **User-interface:** command-line tool
  - Generates reports for the international distribution of PANGO lineages that can be viewed in a web browser.
  
</details>
