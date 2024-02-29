# HIV Bioinformatics Solutions

Authors
=======

Amy Gaskin

Marc Niebel

Frank Ambrosio

Abbas Abel Anzaku

## Introduction


Human Immunodeficiency Virus (HIV), a highly contagious retrovirus, presents a formidable global public health challenge. According to the World Health Organization (WHO), HIV infections lead to severe immunodeficiency and acquired immunodeficiency syndrome (AIDS), causing millions of deaths annually. The virus primarily targets CD4+ T cells, compromising the immune system and necessitating effective treatment strategies. Given its high mutation rate, understanding the genomics of HIV is crucial for designing treatments, including antiretrovirals and vaccines.

In recent years, bioinformatics has played a pivotal role in HIV genomics research, offering insights into viral diversity, drug resistance, and transmission patterns. Applying bioinformatics to HIV research enhances public health initiatives by monitoring genetic variations, detecting mutations, supporting risk assessment, and refining vaccine development. Standardization holds the potential to make HIV genomics research more accessible across diverse global settings, as it enhances transparency, reproducibility, and reliability.

This paper serves as a guidance document, aiming to address existing challenges within the bioinformatics community related to standardization of HIV genomic analyses.  Here, we introduce guidance pathways, which can be likened to distinct themes of bioinformatic analysis specifically tailored to HIV research. These pathways include real-world public health case studies along with relevant HIV bioinformatics tools, making them an invaluable starting point for researchers familiar with microbial bioinformatics but seeking orientation in the world of HIV bioinformatics.

Therefore, this paper aims to contribute to a global network of knowledge-sharing, promoting equitable access to genomics for HIV -- empowering researchers and clinicians worldwide in pursuit of reducing the burden of disease. 

## Background Information for Bioinformaticians

Understanding the HIV genome, evolutionary dynamics, and subtypes are essential for designing bioinformatic processes. Here, we present a set of resources to help springboard researchers into the world of HIV bioinformatics! 

## Genomic Structure 

The diploid genome of HIV-1 consists of approximately 9700 nucleotides, and features nine genes which encode for fifteen proteins (Figure 1)[1](https://www.zotero.org/google-docs/?d63R6n) which interact with human proteins as part of the HIV-1 viral life cycle. Structural proteins, enzymes, and envelope proteins are encoded by three main genes: gag, pol, and env respectively. The remaining genes are responsible for coding regulatory (tat, rev) and accessory (vif, vpr, vpu/vpx, nef) proteins.

Figure 1: HIV-1 DNA genome structure[1](https://www.zotero.org/google-docs/?ELvnGh)

## Evolution

The HIV-1 population, despite having a relatively small genome (Figure 1), showcases extensive genomic diversity primarily due to its exceptionally high mutation rate. This rapid mutation occurs during replication, leading to an accumulation of genetic variations within the viral population. Furthermore, the virus exhibits a high proficiency in recombination[2](https://www.zotero.org/google-docs/?rsgo16), particularly notable due to the varying recombination event rates observed in different segments of the HIV genome, which contribute to the overall genomic diversity of the virus.

In turn, this high genomic diversity gives rise to minor variants that assume a critical role in the development of drug resistance. When exposed to selective pressures, such as antiretroviral drugs or the host immune system, the virus adapts by favouring the proliferation of specific minor variants carrying resistance mutations.

A comprehensive understanding of these evolutionary mechanisms is crucial, as they pose a significant challenge in the clinical and public health management of HIV-1 by significantly influencing treatment outcomes.

## Subtypes

HIV is classified into types, groups and subtypes according to its genetic diversity. [3](https://www.zotero.org/google-docs/?WdpgqI)

HIV-1 / Group M, N, O, P

Group M is the most widespread subtype, responsible for the majority of infections globally (Table  1). Groups N, O, and P are less common. These variations impact transmission, virulence, and treatment responses.

Table  1: Subtypes and main locations for group M

## HIV Bioinformatics Guidance Pathways 

Below, we outline key guidance pathways, which aim to capture  distinct themes of common types of bioinformatics analysis specifically tailored to HIV research. These pathways include real-world public health case studies along with relevant sequencing strategies and HIV bioinformatics tools.

### Genomic Characterisation/Subtyping

Subtyping of HIV-1 refers to the categorization of the genome into groups (M, N, O or P) and further into subtypes (A-J  & CRFs) or clades. Following the production of a consensus   sequence various different approaches (similarity, statistical or phylogenetic) can be used  to assign a probable subtype.

Sequencing strategy

-   Tiled amplicon WGS (gold standard)

-   Targeted amplicon sequencing (overlap with drug resistance prediction on pol region)

Analysis

-   Reference based mapping or de novo assembly methods

-   Consensus sequence generation

-   Assignment of subtype to queried sequence

Tools

-   minimap2, shiver, iva

-   Quasitools HyDRA, samtools, bcftools

-   Stanford HIVdb, REGA

Case Study: Benchmarking study of HIV-1 subtyping tools for clinical and surveillance purposes [4](https://www.zotero.org/google-docs/?TnxG7k)

Description: In this study HIV-1 pol sequences obtained from Los Alamos were subtyped using various automated subtyping tools which were compared to manual phylogenetic analysis.This concluded that most automated subtyping tools work well with pure subtypes especially A & C, however variability of sensitivity and  specificity in subtyping CRFs concluded that multiple tools should be used to confirm HIV-1 subtype.

Tools & databases used: Los Alamos HIV Sequence Database, REGA,COMET, jpHMM, STAR, Stanford HIVdb, NCBI and SCUEAL.

### Drug Resistance Surveillance

The goal of using bioinformatics in drug resistance surveillance is to comprehensively analyse and identify mutations that confer resistance to resistance to antiretoviral drugs, such as protease, reverse transcriptase and integrase inhibitors. Targeting the pol region of the genome is useful as this region is associated with genes coding for protease, reverse transcriptase, and integrase.

This guidance pathway can involve several commonly-used steps, including: aligning sequencing reads to a reference genome (e.g. HXB2: <https://www.ncbi.nlm.nih.gov/nuccore/K03455.1>), followed by de novo assembly methods to reconstruct the HIV genome.

Assembled contigs can be used to generate an optional consensus sequence, serving as a reference for variant identification.

Variant calling algorithms can either detect high-frequency genetic variations,  or perform more sensitive analysis for minor variant calling, which identifies low-frequency mutations. Both can be used to inform downstream clinical treatment.

Annotated variants are then cross-referenced with gold-standard databases and interpreted through the lens of literature on HIV drug resistance to assess their potential impact on drug susceptibility in human-readable formats. These results can then be bundled into tailored reports so clinicians can interpret these findings and tailor antiretroviral therapy appropriately, minimising treatment failure and optimising patient care.

Through this integrated approach, this guidance pathway facilitates proactive surveillance and management of HIV drug resistance, ultimately improving treatment efficacy and patient outcomes.

Sequencing Strategy

-   Targeted amplicon sequencing of pol (Table 2).

Analysis

-   Reference-based mapping or de novo assembly methods

-   Consensus sequence

-   Variant calling 

-   Minor variant calling

-   Database querying

Tools 

-   minimap2, iva, shiver

-   VarScan

-   Stanford Database (either for pipeline implementation - codon frequency file - or for API query from consensus sequence)

Case Study: Bioinformatic data processing pipelines in support of next-generation sequencing-based HIV drug resistance testing: the Winnipeg Consensus

Pipelines: 

Quasiflow: <https://academic.oup.com/bioinformaticsadvances/article/2/1/vbac089/6849543>

HIV-DRIVES:  <https://www.medrxiv.org/content/10.1101/2023.09.30.23296350v1>

### Drug Development and Resistance Prediction

Drug Target Identification: Understanding the genome aids in identifying potential drug targets, such as the Protease, Reverse Transcriptase, and Integrase enzymes. Bioinformatics tools predict inhibitors for these targets.

Drug Resistance Prediction: Analysing genomic sequences helps predict drug resistance mutations, informing clinicians about the efficacy of personalised highly active antiretroviral therapies (HAART).The treatment success of HIV infection is affected by development of viral drug resistance, thereby, complicating clinicians choice of selecting the right drugs for patients' treatment. This challenge has led to the development  of various bioinformatics software tools and databases for predicting drug resistance, and responses to combination therapy from viral genotypes [23](https://www.zotero.org/google-docs/?MPxock).

Phylogenetics

The study of HIV genetic variation and evolution using genomic data serves several important purposes in understanding and combating HIV/AIDS. It allows researchers to reconstruct the evolutionary history of HIV and track transmission dynamics within populations. By analyzing the genetic sequences of HIV strains obtained from infected individuals, researchers can infer relationships between viral lineages, identify transmission clusters, and trace the spread of the virus over time and geographical regions. This information is crucial for understanding patterns of HIV transmission, identifying high-risk populations, and implementing targeted prevention and intervention strategies.

In addition to understanding transmission dynamics, HIV phylogenomics can shed light on the emergence and spread of drug resistance mutations in the HIV genome. Antiretroviral therapy (ART) is a cornerstone of HIV treatment, but the emergence of drug-resistant strains poses a significant challenge to effective treatment and control efforts around the world. By analyzing the genetic sequences of HIV strains, researchers can identify mutations associated with drug resistance and monitor their prevalence and transmission patterns within communities. This information is essential for guiding treatment decisions, designing effective drug regimens, and developing strategies to prevent the spread of drug-resistant HIV strains.

Furthermore, HIV phylogenomics can provide valuable insights into the broader epidemiology of HIV/AIDS and inform public health responses to outbreaks and epidemics. By integrating genomic data with epidemiological information, researchers can identify sources of infection, map transmission networks, and assess the impact of prevention and control measures. This knowledge can help public health officials allocate resources more effectively, tailor interventions to specific populations, and ultimately reduce the burden of HIV/AIDS on affected communities. This type of analysis can be performed using whole genome sequencing (WGS) or by using one of the more stable regions of the HIV genome such as the pol, env or gag genes, as mutations in these genes will likely have occurred from the process of natural viral evolution, and not from recombinations or from insertions and deletions.

Sequencing Strategy

-   Tiled amplicon WGS (Table 2).

-   Targeted amplicon sequencing of pol (Table 2).

Analysis

-   Reference-based mapping assembly methods 

-   Consensus sequence

-   Variant calling 

-   Pairwise genomic distance computation

-   Phylogenetic tree inference

-   Phylogenetic tree visualization

Tools 

-   minimap2, iva, shiver

-   VarScan

-   HIV-TRACE

Protocol: https://www.researchgate.net/publication/376330219_An_NGS_amplicon_tiling_protocol_for_HIV-1_drug_resistance_detection_using_IlluminaR_COVIDSeq_Assay_Kit_v2

Pipelines: 

TheiaCoV: https://github.com/theiagen/public_health_bioinformatics/tree/main/workflows/theiacov

iVar: https://github.com/andersen-lab/ivar

### Genomic Epidemiology 

Genomic Epidemiology: Utilising bioinformatics for large-scale analysis of HIV sequence data aids in tracking the spread of viral variants and understanding transmission dynamics.

Network transmission analysis usually takes place just after phylogenetic tree construction, and these analyses are inherently related by the fact that each requires the investigator to determine the pairwise genomic distances between a set of samples. However, there is a distinction between the use of phylogenetic trees to visualize the genomic diversity and relationships between a set of samples, and the use of the pairwise genomic distances of a set of samples to generate a putative transmission network.

Genomic distance information can be used to infer which samples may be linked by a transmission event. One can construct a putative transmission network from a set of inferred transmission events. By using genomic similarity as a proxy for likelihood of a direct transmission event one can map the propagation of a pathogen through a population using high-resolution genomic sequencing data.

Connections between nodes in the network (edges) are based on genomic similarity falling below a threshold of genomic distance computed by assessing the distribution of genomic distances found within samples known to be associated with the outbreak by traditional epidemiological techniques such as contact tracing. The techniques and tools outlined in the above phylogenomics section will be useful in generating assemblies, distance matrices and phylogenetic trees which are the inputs for most genomic network construction tools.

Sequencing Strategy

-   Tiled amplicon WGS (Table 2).

-   Targeted amplicon sequencing of pol (Table 2).

Analysis

-   Reference-based mapping assembly methods 

-   Consensus sequence

-   Variant calling 

-   Pairwise genomic distance computation

-   Putative transmission network construction

-   Force-directed network layout visualization

Tools:

-   MicrobeTrace

-   GrapeTree

## Sequencing Strategies

The sequencing strategy (Table 2)  that you adopt is dependent on multiple factors but should be driven by the question that you are trying to answer. For example, targeted amplification of the Pol region has historically been used to assess drug resistance to antiretroviral therapy.

 Table 2: Potential sequencing  strategies for HIV-1

*Will not be able to subtype some circulating recombinant forms due to missing breakpoints (CRF_AE & CRF_BG)[5,6](https://www.zotero.org/google-docs/?AVqBsR)

A tiled amplicon sequencing primer scheme has been developed by the Association of Public Health Laboratories (APHL): <https://www.protocols.io/view/an-ngs-amplicon-tiling-protocol-for-hiv-1-drug-res-n92ldmq4ol5b/v2> (DOI:10.17504/protocols.io.n92ldmq4ol5b/v2)

## HIV-1 Bioinformatics Tools 

For researchers and clinicians alike, designing a bioinformatics analysis of HIV sequence data comes down to careful selection of bioinformatics tools. The effectiveness of analysis, accuracy of results, and subsequent genomic and epidemiological insights hinge on the appropriateness of the chosen tools. This decision encapsulates the essence of bioinformatics in HIV research, where precise tool selection aligns with the specific research objectives, ensuring that analytical methods harmonize with the intricacies of the virus. Below, we provide a categorised list of bioinformatics tools used in HIV research, distinguishing between general tools applicable to various contexts and those specifically designed for HIV-related analyses.

### Assembly

-   shiver: A tool for assembling HIV sequences, particularly focusing on improving de novo assembly by minimising biased information [7](https://www.zotero.org/google-docs/?sahTRG)

-   iva: Generating de novo assembly of RNA virus genomes [8](https://www.zotero.org/google-docs/?9jQ24S)

Subtyping

Various HIV-1 subtyping tools are available (Table 3) which have been benchmarked previously [4,14](https://www.zotero.org/google-docs/?qUlDzn)

Table 3: HIV-1  subtyping tools

Multiple considerations need to be taken into account when choosing a subtyping tool.

Although the gold standard for HIV-1 subtyping is full-genome, often only the pol region is available. This region will allow for subtyping for most group M subtypes but will not differentiate CRF_AE & CRF_BG from the pure parent subtype due to lacking the recombination breakpoint in this region.[5,6](https://www.zotero.org/google-docs/?O3urnG) The second is that an up-to-date alignment is desirable especially when considering treatment failures e.g. cabotegravir (integrase inhibitor) not working on HIV-1 subtypes A1/A6.[15](https://www.zotero.org/google-docs/?aM4QLV)

### Resistance detection

Resistance detection is mainly undertaken in reference to HXB2 (Accession Number:K03455)

-   Stanford University HIVdb (<https://hivdb.stanford.edu/>) : An online database and tool for identifying drug-resistant mutations in HIV-1 using consensus and next-generation sequencing data [16--18](https://www.zotero.org/google-docs/?SChQDb)

-   Quasitools HyDRA (no longer actively maintained): Command line tool to analyse next-generation sequencing data for cataloging drug resistance mutations using the Stanford University HIVdb [19](https://www.zotero.org/google-docs/?deyvXC)

-   SierraPy: Python client to query Stanford University HIVdb (<https://github.com/hivdb/sierra-client/blob/master/python/README.md>)

Other Stanford HIVdb resources which are useful to investigate especially for pipeline implementation:

-   Release Notes (<https://hivdb.stanford.edu/page/release-notes/>) 

-   Web Service (<https://hivdb.stanford.edu/page/webservice/>)

-   Github repository (<https://github.com/hivdb>)

### Transmission network analysis 

-   HIV-TRACE: A command line tool for identifying and visualizing HIV transmission clusters using molecular sequence data [20](https://www.zotero.org/google-docs/?JkPOE4)

-   Clusterpicker (no longer actively maintained): A command line tool for identifying clusters in a phylogenetic tree based on bootstrap support and pairwise genetic distance within clusters [21](https://www.zotero.org/google-docs/?Gk777r)

### Sequence Databases

-   NCBI HIV-1 Human Interaction Database

(<https://www.ncbi.nlm.nih.gov/genome/viruses/retroviruses/hiv-1/interactions> )[22](https://www.zotero.org/google-docs/?iOtiCG) :

An online database of HIV-1 sequence data and annotations, including drug resistance and subtype information

-   Los Alamos HIV Sequence Database <https://www.hiv.lanl.gov/content/sequence/HIV/mainpage.html>  : A web database which can be searched for HIV sequence data, including reference genomes, annotations, and geographic origins of subtypes

-   Stanford University HIVdb: In addition to being the most up-to-date resource for investigating HIV-1 drug resistance(see above) it also has a wealth of information on HIV-1 virus isolates,  published drug susceptibilities and archived treatment episodes (incorporates ARVs received, mutations detected and new regimen initiated with measured viral loads and CD4 counts longitudinally).

### Case Studies

#### Case Study: Tracking HIV Transmission Networks in a High-Incidence Area

**Description:** Using molecular epidemiology, this study identified transmission networks among individuals with acute HIV infection in a high-incidence region, providing insights into transmission dynamics and hotspots.

**Citation:** Wertheim JO, et al. (2014). "Social and Genetic Networks of HIV-1 Transmission in New York City." PLOS Pathogens, 10(7), e1004280.

**Tool(s) & databases used:** HIV-TRACE, Los Alamos

#### Case Study: Evolution of Drug Resistance Mutations in Long-Term ART Patients

**Description:** This study investigated the dynamics of drug resistance mutations in individuals on long-term therapy (ART), revealing the persistence of archived resistant variants and the importance of continuous monitoring.

**Citation:** Rhee SY, et al. (2006). "HIV-1 Protease and Reverse-Transcriptase Mutations: Correlations with Antiretroviral Therapy in Subtype B Isolates and Implications for Drug-Resistance Surveantiretroviral illance." Journal of Infectious Diseases, 194(4), 454-465.

**Tool(s) & databases used:** PAUP, MESQUITE, Stanford HIVdb

#### Case Study: Impact of Drug Resistance Mutations on Treatment Outcomes

**Description:** This study assessed the impact of specific drug resistance mutations on treatment response and virological outcomes, contributing to the optimization of treatment regimens for individuals with drug-resistant HIV.

**Citation:** Gupta RK, et al. (2009). "HIV-1 Drug Resistance before Initiation or Re-initiation of First-line Antiretroviral Therapy in Low-Income and Middle-Income Countries: A Systematic Review and Meta-Regression Analysis." The Lancet Infectious Diseases, 9(10), 711-718.

**Tool(s) & databases used:** Stanford HIVdb

#### Case Study: HIV Phylogenetics to Investigate Cross-Border Transmission

**Description:** Using phylogenetic analysis, this study traced cross-border transmission of HIV strains between neighboring countries, highlighting the need for coordinated prevention efforts in the region.

**Citation:** Novitsky V, et al. (2015). "Phylogenetic Relatedness of Circulating HIV-1C Strains in Mochudi, Botswana, and Implications for HIV Subtype Distribution in Botswana." AIDS Research and Human Retroviruses, 31(6), 631-638.

**Tool(s) & databases used:** Los Alamos

#### Case Study: Cross-clade simultaneous HIV drug resistance genotyping for reverse transcriptase, protease, and integrase inhibitor mutations by Illumina MiSeq

**Description:** This study created a universal Illumina MiSeq-based HIV drug resistance genotyping assay, which works across all major group M HIV-1 subtypes and identifies DRMs in the pol gene known to confer resistance to protease, reverse transcriptase, and integrase inhibitors.

**Citation:** Dudley, D. M., et al. (2014). "Cross-clade simultaneous HIV drug resistance genotyping for reverse transcriptase, protease, and integrase inhibitor mutations by Illumina MiSeq". Retrovirology, 11, 122. <https://doi.org/10.1186/s12977-014-0122-8> 

**Tool(s) & databases used:** Los Alamos

References
==========

[1.  Xiao, Q., Guo, D. & Chen, S. Application of CRISPR/Cas9-Based Gene Editing in HIV-1/AIDS Therapy. Front. Cell. Infect. Microbiol. 9, (2019).](https://www.zotero.org/google-docs/?OTPY9Q)

[2.  Olabode, A. S. et al. Evidence for a recombinant origin of HIV-1 Group M from genomic variation. Virus Evol. 5, vey039 (2019).](https://www.zotero.org/google-docs/?OTPY9Q)

[3.  Bbosa, N., Kaleebu, P. & Ssemwanga, D. HIV subtype diversity worldwide. Curr. Opin. HIV AIDS 14, 153--160 (2019).](https://www.zotero.org/google-docs/?OTPY9Q)

[4.  Pineda-Peña, A.-C. et al. Automated subtyping of HIV-1 genetic sequences for clinical and surveillance purposes: Performance evaluation of the new REGA version 3 and seven other tools. Infect. Genet. Evol. 19, 337--348 (2013).](https://www.zotero.org/google-docs/?OTPY9Q)

[5.  Delgado, E. et al. Identification of a Newly Characterized HIV-1 BG Intersubtype Circulating Recombinant Form in Galicia, Spain, Which Exhibits a Pseudotype-Like Virion Structure. JAIDS J. Acquir. Immune Defic. Syndr. 29, 536 (2002).](https://www.zotero.org/google-docs/?OTPY9Q)

[6.  Carr, J. K. et al. Full-length sequence and mosaic structure of a human immunodeficiency virus type 1 isolate from Thailand. J. Virol. 70, 5935--5943 (1996).](https://www.zotero.org/google-docs/?OTPY9Q)

[7.  Wymant, C. et al. Easy and accurate reconstruction of whole HIV genomes from short-read sequence data with shiver. Virus Evol. 4, vey007 (2018).](https://www.zotero.org/google-docs/?OTPY9Q)

[8.  Hunt, M. et al. IVA: accurate de novo assembly of RNA virus genomes. Bioinformatics 31, 2374--2376 (2015).](https://www.zotero.org/google-docs/?OTPY9Q)

[9.  Rozanov, M., Plikat, U., Chappey, C., Kochergin, A. & Tatusova, T. A web-based genotyping resource for viral sequences. Nucleic Acids Res. 32, W654-659 (2004).](https://www.zotero.org/google-docs/?OTPY9Q)

[10.  HIV Subtyping Program - HIV Drug Resistance Database. https://hivdb.stanford.edu/page/hiv-subtyper/.](https://www.zotero.org/google-docs/?OTPY9Q)

[11.  Struck, D., Lawyer, G., Ternes, A.-M., Schmit, J.-C. & Bercoff, D. P. COMET: adaptive context-based modeling for ultrafast HIV-1 subtype identification. Nucleic Acids Res. 42, e144 (2014).](https://www.zotero.org/google-docs/?OTPY9Q)

[12.  Zhang, M. et al. jpHMM at GOBICS: a web server to detect genomic recombinations in HIV-1. Nucleic Acids Res. 34, W463--W465 (2006).](https://www.zotero.org/google-docs/?OTPY9Q)

[13.  Pond, S. L. K. et al. An Evolutionary Model-Based Algorithm for Accurate Phylogenetic Breakpoint Mapping and Subtype Prediction in HIV-1. PLOS Comput. Biol. 5, e1000581 (2009).](https://www.zotero.org/google-docs/?OTPY9Q)

[14.  Fabeni, L. et al. Comparative Evaluation of Subtyping Tools for Surveillance of Newly Emerging HIV-1 Strains. J. Clin. Microbiol. 55, 2827--2837 (2017).](https://www.zotero.org/google-docs/?OTPY9Q)

[15.  Cutrell, A. G. et al. Exploring predictors of HIV-1 virologic failure to long-acting cabotegravir and rilpivirine: a multivariable analysis. AIDS Lond. Engl. 35, 1333--1342 (2021).](https://www.zotero.org/google-docs/?OTPY9Q)

[16.  Rhee, S.-Y. et al. Human immunodeficiency virus reverse transcriptase and protease sequence database. Nucleic Acids Res. 31, 298--303 (2003).](https://www.zotero.org/google-docs/?OTPY9Q)

[17.  Shafer, R. W. Rationale and Uses of a Public HIV Drug-Resistance Database. J. Infect. Dis. 194, S51--S58 (2006).](https://www.zotero.org/google-docs/?OTPY9Q)

[18.  Liu, T. F. & Shafer, R. W. Web Resources for HIV Type 1 Genotypic-Resistance Test Interpretation. Clin. Infect. Dis. Off. Publ. Infect. Dis. Soc. Am. 42, 1608--1618 (2006).](https://www.zotero.org/google-docs/?OTPY9Q)

[19.  Marinier, E. et al. quasitools: A Collection of Tools for Viral Quasispecies Analysis. 733238 Preprint at https://doi.org/10.1101/733238 (2019).](https://www.zotero.org/google-docs/?OTPY9Q)

[20.  Kosakovsky Pond, S. L., Weaver, S., Leigh Brown, A. J. & Wertheim, J. O. HIV-TRACE (TRAnsmission Cluster Engine): a Tool for Large Scale Molecular Epidemiology of HIV-1 and Other Rapidly Evolving Pathogens. Mol. Biol. Evol. 35, 1812--1819 (2018).](https://www.zotero.org/google-docs/?OTPY9Q)

[21.  Ragonnet-Cronin, M. et al. Automated analysis of phylogenetic clusters. BMC Bioinformatics 14, 317 (2013).](https://www.zotero.org/google-docs/?OTPY9Q)

[22.  Ako-Adjei, D. et al. HIV-1, human interaction database: current status and new features. Nucleic Acids Res. 43, D566-570 (2015).](https://www.zotero.org/google-docs/?OTPY9Q)

[23.  Mannu, J. & Mathur, P. P. Role of Bioinformatics in Drug Resistance Prediction for HIV/AIDS. in Current trends in Bioinformatics: An Insight (eds. Wadhwa, G., Shanmughavel, P., Singh, A. K. & Bellare, J. R.) 277--286 (Springer, Singapore, 2018). doi:10.1007/978-981-10-7483-7_16.](https://www.zotero.org/google-docs/?OTPY9Q)

Further Reading, Courses, and Training Materials
------------------------------------------------

-   Ji, H., Enns, E., Brumme, C. J., Parkin, N., Howison, M., Lee, E. R., Capina, R., Marinier, E., Avila-Rios, S., Sandstrom, P., Van Domselaar, G., Harrigan, R., Paredes, R., Kantor, R., & Noguera-Julian, M. (2018). Bioinformatic data processing pipelines in support of next-generation sequencing-based HIV drug resistance testing: the Winnipeg Consensus. Journal of the International AIDS Society, 21(10), e25193.

-   Kanyerezi, S., Sserwadda, I., Ssemaganda, A., Sseruyange, J., Ayitewala, A., Oundo, H., ... & Mboowa, G. (2023). HIV-DRIVES: HIV Drug Resistance Identification, Variant Evaluation, & Surveillance Pipeline. medRxiv, 2023-09.