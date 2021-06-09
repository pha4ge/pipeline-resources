# **Bioinformatics Solutions for SARS-CoV-2 Genomic Analysis**

PHA4GE Bioinformatics Pipelines &amp; Visualizations Working Group

 Libuit KG, Park D, van Heusden P, Neher R, Kapsak CJ, Southgate J, Bridges D, Mboowa G, Luun S, Langhorst B

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
