
<img src="images/PHA4GE%20Logo%20landscape%20rgb.png"
     alt="PHA4GE"
     width="340"
     align="left">

<h1>Sepsis Genomics Guidance</h1>

<br clear="all">


**Lead authors:** Dejenie Shiferaw, Mary Maranga

**Contributors:** Adolf Oyesigye Mukama, Arjun Prasad, Osasona Oluwadamilola Gideon, Patricia Nabisubi, Bruke Gezhagene, Oliver De Sousa, Ndahafa Frans, Dominique Anderson, Gustavo Ybazeta, Nozipho Magagula, Olusola Afuwape, Maindiguel Djimalabye, Shiza Naz, Tholwana Pelokgosi, Rekha Sathyan, Henry Njoku, Rajiha Abubeker Ibrahim, Jupiter Marina Kabahita, Godwin Tusabe Wenka, Justice Ohene Amofa, Ayorinde Afolayan, Syahidiah Syed Abu Thahir, Sola Afuwape, Palesa, Arthur Kasambula, Fabian Achangwi, Folami Balogun, Desye Melese, Melese Hailu, Tracey Calvert-Joshua

# Overview

Sepsis remains a major global health burden with substantial morbidity and mortality, especially in low- and middle-income countries (LMICs). The global burden of disease analysis estimated 48.9 million sepsis cases and 11.0 million sepsis-related deaths in 2017 and accounts for approximately 20% of deaths (Singer et al., 2016; Rudd et al., 2020). The leading causative agents of sepsis include bacterial pathogens such as *Escherichia coli, Klebsiella pneumoniae, Staphylococcus aureus, Pseudomonas aeruginosa,* and *Acinetobacter baumannii*, as well as fungal pathogens of the *Candida* species. Viral pathogens, including herpes simplex virus, have also been reported as causes of sepsis, although less frequently. Despite advances in diagnostics and clinical care, sepsis remains a major threat to public health, and the growing burden of antimicrobial resistance (AMR) is making effective treatment difficult.

Advances in whole-genome sequencing (WGS) have improved pathogen characterization in both research and public health settings. Genomic data provides a vast amount of information at high resolution, supporting pathogen subtyping, identification of serotypes or pathotypes, and surveillance of the emergence and spread of AMR, supporting the basis of genomic epidemiology. When combined with conventional phenotypic methods, genomic data can inform timely policy development and support the creation of rapid diagnostic tools, ultimately improving disease management.

This document aims to provide practical guidance on how to analyze and interpret whole-genome sequencing data for WHO priority sepsis-causing pathogens. It is intended to support the use of genomic data to strengthen antimicrobial resistance surveillance, outbreak investigation, and understanding of pathogen transmission.

# Purpose and intended use 

![Figure 1. Overview of document scope.](images/sepsis/PHA4GE%20Sepsis%20Genomics%20Guidance%20Infographic.png)

**Figure 1:** Overview of document scope.

This document provides a framework for characterizing pathogens associated with sepsis in public health settings (Figure 1). It brings together the key components of the genomic workflow, bioinformatics analysis, and interpretation of genomic data. <span class="mark">We also provide example case studies, examinations of published work</span> in outbreak investigation, and transmission analysis. Additionally, we provide guidance on minimum metadata and reporting standards.

This guidance is intended for use by public health laboratories, clinical microbiology laboratories, and national or regional surveillance programs. It is designed to accommodate a range of expertise levels and infrastructure, from settings with limited bioinformatics capacity to advanced centers with established genomic pipelines. Recommendations are structured to support stepwise adoption, enabling users to select appropriate tools and workflows based on available resources.

By consolidating recommendations on metadata standards, bioinformatics workflows and tools, and data sharing, this guidance aims to facilitate consistent and context-appropriate implementation across diverse settings. Overall, the guidance contributes to strengthening the integration of genomics into routine microbiology and public health practice, in alignment with broader international efforts to standardize genomic epidemiology.

# Pathogen scope

The document focuses on WHO priority pathogens: *Klebsiella pneumoniae*, *Escherichia coli*, *Acinetobacter baumannii*, *Pseudomonas* species, *Staphylococcus aureus*, and *Enterococcus* species. These organisms are prioritized because of the global burden of the disease and the increasing resistance to multiple antimicrobial classes. The five priority bacteria are among the six leading pathogens responsible for deaths associated with resistance (*E. coli*, followed by *S. aureus*, *K. pneumoniae*, *A. baumannii*, and *P. aeruginosa*). In 2019, they accounted for about 929 000 deaths attributable to AMR and about 3.57 million deaths associated with AMR (Murray et al., 2022).

# Table of Contents

[**Overview 1**](#_heading=)

[***Purpose and intended use 1***](#purpose-and-intended-use)

[***Pathogen scope 2***](#pathogen-scope)

[**Table of Contents 2**](#table-of-contents)

[***1. Public Health Applications of Genomics for Sepsis Pathogens 6***](#public-health-applications-of-genomics-for-sepsis-pathogens)

> [**1.1 Outbreak Investigation 6**](#outbreak-investigation)
>
> [**1.2 Routine Genomic Surveillance 7**](#routine-genomic-surveillance)
>
> [**1.3 AMR Mechanism Detection and Monitoring 8**](#amr-mechanism-detection-and-monitoring)
>
> [**1.4 Detection of High-Risk Clones and Population Structure 8**](#detection-of-high-risk-clones-and-population-structure)
>
> [**1.5 Genomics as a Complementary Tool: Interpretation and Uncertainty 9**](#genomics-as-a-complementary-tool-interpretation-and-uncertainty)

[***2. Surveillance Strategies Study Design 9***](#surveillance-strategies-study-design)

> [**2.1 Framework: Surveillance Objective Determines Study Design 9**](#framework-surveillance-objective-determines-study-design)
>
> [**2.2 Core Use Cases and Sampling Strategies 12**](#core-use-cases-and-sampling-strategies)
>
> [2.2.1 Outbreak Investigation 12](#outbreak-investigation-1)
>
> [2.2.2 Routine Genomic Surveillance 13](#routine-genomic-surveillance-1)
>
> [2.2.3 AMR Mechanism Detection and Monitoring 13](#amr-mechanism-detection-and-monitoring-1)
>
> [2.2.4 Population Structure and High-Risk Clone Detection 14](#population-structure-and-high-risk-clone-detection)
>
> [**2.3 Specimen Types, Collection, and Handling 14**](#specimen-types-collection-and-handling)
>
> [**2.4 Retrospective and Prospective Study Designs 15**](#retrospective-and-prospective-study-designs)
>
> [**2.5 Implementation of genomic surveillance 16**](#implementation-of-genomic-surveillance)

[***3. Metadata standards 17***](#metadata-standards)

> [**The PHA4GE Community Metadata Standards for Sepsis Pathogens 18**](#the-pha4ge-community-metadata-standards-for-sepsis-pathogens)

[***4. Ethical, Legal and Data Governance 24***](#ethical-legal-and-data-governance)

[***5. Laboratory and Sequencing Best Practices 26***](#laboratory-and-sequencing-best-practices)

> [**5.1 Pre-sequencing Pathogen Confirmation (Species Identification) 26**](#pre-sequencing-pathogen-confirmation-species-identification)
>
> [**5.2 Antimicrobial Susceptibility Testing (AST) 26**](#antimicrobial-susceptibility-testing-ast)
>
> [**5.3 Pure Isolate Culture, Storage, and DNA Extraction 28**](#pure-isolate-culture-storage-and-dna-extraction)
>
> [5.3.1 Pure Isolate Confirmation and Subculture 28](#pure-isolate-confirmation-and-subculture)
>
> [5.3.2 Isolate Storage for Genomic Archives 28](#isolate-storage-for-genomic-archives)
>
> [5.3.3 DNA Extraction 29](#dna-extraction)
>
> [**5.4 Sequencing Library Preparation and Platform Choice 30**](#sequencing-library-preparation-and-platform-choice)
>
> [**5.5 Quality Control Before Sequencing and Pre-analytical Documentation 31**](#quality-control-before-sequencing-and-pre-analytical-documentation)

[***6. Standard bioinformatics data analysis workflow - core bioinformatics steps 32***](#standard-bioinformatics-data-analysis-workflow---core-bioinformatics-steps)

> [**6.1 Base calling Nanopore data 33**](#base-calling-nanopore-data)
>
> [**6.2 Raw data quality control 33**](#raw-data-quality-control)
>
> [**6.3 Read trimming and filtering: preprocessing of reads 34**](#read-trimming-and-filtering-preprocessing-of-reads)
>
> [**6.4 Species confirmation or taxonomic classification 35**](#species-confirmation-or-taxonomic-classification)
>
> [**6.5 Genome assembly 36**](#genome-assembly)
>
> [**6.6 Reference-based mapping and variant calling 37**](#reference-based-mapping-and-variant-calling)
>
> [**6.7 Assembly quality control 38**](#assembly-quality-control)
>
> [**6.8 Detection of key features 40**](#detection-of-key-features)
>
> [6.8.1 AMR gene and mutation detection 40](#amr-gene-and-mutation-detection)
>
> [6.8.2 Virulence factor profiling 44](#virulence-factor-profiling)
>
> [6.8.3 Plasmid and mobile genetic element analysis 45](#plasmid-and-mobile-genetic-element-analysis)
>
> [6.8.4 MLST and Core Genome MLST 45](#mlst-and-core-genome-mlst)
>
> [Integrated Analysis Platforms 46](#integrated-analysis-platforms)
>
> [**6.9 Phylogenetic and epidemiological analysis 46**](#phylogenetic-and-epidemiological-analysis)
>
> [6.9.1 SNP and cgMLST thresholds for outbreak cluster definition 46](#snp-and-cgmlst-thresholds-for-outbreak-cluster-definition)
>
> [6.9.2 Pathogen-specific outbreak thresholds from the literature 47](#pathogen-specific-outbreak-thresholds-from-the-literature)
>
> [6.9.3 Recombination filtering 47](#recombination-filtering)
>
> [6.9.4 Variant discovery and core SNP Alignment strategies: Snippy vs. kSNP4 48](#variant-discovery-and-core-snp-alignment-strategies-snippy-vs.-ksnp4)
>
> [6.9.5 When to use which tool: Snippy vs. kSNP4 48](#when-to-use-which-tool-snippy-vs.-ksnp4)
>
> [6.9.6 Phylogenetic tree construction tools 49](#phylogenetic-tree-construction-tools)
>
> [**6.10 All-in-One Pipelines and Web-Based Analysis Platforms 49**](#all-in-one-pipelines-and-web-based-analysis-platforms)

[***7. Data Management, Reproducibility & Infrastructure 50***](#data-management-reproducibility-infrastructure)

> [**7.1 Data storage, sharing, and repositories 50**](#data-storage-sharing-and-repositories)
>
> [The Global Repository Ecosystem and Platforms 50](#the-global-repository-ecosystem-and-platforms)
>
> [7.1.1 The INSDC: Global Archival Infrastructure 50](#the-insdc-global-archival-infrastructure)
>
> [7.1.2 Specialized Public Health Platforms 51](#specialized-public-health-platforms)
>
> [**7.2 Workflow Reproducibility & Infrastructure 52**](#workflow-reproducibility-infrastructure)
>
> [7.2.1 The PHA4GE Ten Best Practices for Public Health Bioinformatics Pipelines 53](#the-pha4ge-ten-best-practices-for-public-health-bioinformatics-pipelines)
>
> [7.2.2 Workflow Management Systems 55](#workflow-management-systems)
>
> [7.2.3 Containerization and Software Packaging 57](#containerization-and-software-packaging)
>
> [7.2.4 Version Control and Documentation 58](#version-control-and-documentation)
>
> [7.2.5 Computing Infrastructure Options 59](#computing-infrastructure-options)

[***8. Pathogen-specific guidance 60***](#pathogen-specific-guidance)

> [***8.1 Klebsiella pneumoniae and the Klebsiella pneumoniae species complex (KpSC) 60***](#klebsiella-pneumoniae-and-the-klebsiella-pneumoniae-species-complex-kpsc)
>
> [Key genomic features for typing K. pneumoniae 61](#key-genomic-features-for-typing-k.-pneumoniae)
>
> [**8.1.1 Pathogenicity factors 61**](#pathogenicity-factors)
>
> [8.1.1.1 K antigen and locus 61](#k-antigen-and-locus)
>
> [8.1.1.2 O antigen and locus 61](#o-antigen-and-locus)
>
> [**8.1.2 Virulence factors 62**](#virulence-factors)
>
> [8.1.3 MLST, cgMLST and LIN codes 63](#mlst-cgmlst-and-lin-codes)
>
> [8.1.4 AMR mechanisms 64](#amr-mechanisms)
>
> [8.1.4.2 Acquired resistance 65](#acquired-resistance)
>
> [***8.1.6 Klebsiella genomics analysis 66***](#klebsiella-genomics-analysis)
>
> [<span class="mark">8.1.7 Transmission analysis using whole-genome sequencing 68</span>](#transmission-analysis-using-whole-genome-sequencing)
>
> [**8.1.8 Caveats in K. pneumonia WGS data analysis. 70**](#caveats-in-k.-pneumonia-wgs-data-analysis.)
>
> [***8.1.9 K. Pneumoniae case study examples 72***](#k.-pneumoniae-case-study-examples)

[***8.2 Escherichia coli 84***](#escherichia-coli)

> [**Key Genomic Features of E. coli 84**](#key-genomic-features-of-e.-coli)
>
> [**8.2.1 E. coli Population Structure and Phylogroups 84**](#e.-coli-population-structure-and-phylogroups)
>
> [**8.2.2 E. coli Virulence Factors 85**](#e.-coli-virulence-factors)
>
> [**8.2.3 O (Lipopolysaccharide) and H (Flagellar) Antigens of E. coli 85**](#o-lipopolysaccharide-and-h-flagellar-antigens-of-e.-coli)
>
> [**8.2.4 Antimicrobial Resistance (AMR) Mechanisms 86**](#antimicrobial-resistance-amr-mechanisms)
>
> [**8.2.5 Pathogen-Specific Analysis and Interpretation 88**](#pathogen-specific-analysis-and-interpretation)
>
> [8.2.5.1. Phylogenetic Grouping (Phylogrouping) 88](#phylogenetic-grouping-phylogrouping)
>
> [8.2.5.2 In Silico Serotyping (O and H Antigens) 89](#in-silico-serotyping-o-and-h-antigens)
>
> [8.2.5.3 Virulence Factor Detection 90](#virulence-factor-detection)
>
> [8.2.5.4 Integrated Genomic Platforms 90](#integrated-genomic-platforms)
>
> [**8.2.6 E. coli case study examples 96**](#e.-coli-case-study-examples)

[***8.3 Acinetobacter baumannii 105***](#acinetobacter-baumannii)

> [8.3.1 Background and Public Health Relevance 105](#background-and-public-health-relevance)
>
> [8.3.3 Pathogen-Specific Analysis and Interpretation 108](#pathogen-specific-analysis-and-interpretation-1)
>
> [8.3.4 Case Studies for A. baumannii 110](#case-studies-for-a.-baumannii)
>
> [**8.4 Pseudomonas aeruginosa 123**](#pseudomonas-aeruginosa)
>
> [8.4.1 Background and Public Health Relevance 123](#background-and-public-health-relevance-1)
>
> [8.4.2 Key Genomic Features 123](#key-genomic-features)
>
> [8.4.3 Pathogen-Specific Analysis and Interpretation 129](#pathogen-specific-analysis-and-interpretation-2)
>
> [8.4.4 Case Study for P. aeruginosa 133](#case-study-for-p.-aeruginosa)
>
> [**8.5 Staphylococcus aureus 145**](#staphylococcus-aureus)
>
> [**8.5.1 Background and Public Health Relevance 145**](#background-and-public-health-relevance-2)
>
> [**8.5.2 Key Genomic Features 146**](#key-genomic-features-1)
>
> [8.5.2.1 Species Complex and Taxonomic Differentiation 146](#species-complex-and-taxonomic-differentiation)
>
> [8.5.2.2 Population Structure and Major Lineages 147](#population-structure-and-major-lineages)
>
> [8.5.2.3 Genotyping 148](#genotyping)
>
> [8.5.2.4 Mechanisms of Resistance 148](#mechanisms-of-resistance)
>
> [Mobile Genetic Elements and Horizontal Gene Transfer 149](#mobile-genetic-elements-and-horizontal-gene-transfer)
>
> [8.5.2.5 Virulence Profiling and Toxins 150](#virulence-profiling-and-toxins)
>
> [**8.5.3 Pathogen-Specific Analysis and Interpretation 151**](#pathogen-specific-analysis-and-interpretation-3)
>
> [**8.5.4 Case Study for S. aureus 153**](#case-study-for-s.-aureus)

[***8.6 Enterococcus Species (Enterococcus faecium and Enterococcus faecalis) 159***](#enterococcus-species-enterococcus-faecium-and-enterococcus-faecalis)

> [**8.6.1 Background and Public Health Relevance 159**](#background-and-public-health-relevance-3)
>
> [**8.6.2 Key Genomic Features 159**](#key-genomic-features-2)
>
> [8.6.2.1 Population Structure and Major Lineages 159](#population-structure-and-major-lineages-1)
>
> [8.6.2.2 MLST Schemes 160](#mlst-schemes)
>
> [8.6.2.3 cgMLST and Hierarchical Clustering 160](#cgmlst-and-hierarchical-clustering)
>
> [8.6.2.4 Mechanisms of Resistance 161](#mechanisms-of-resistance-1)
>
> [8.6.2.5 Virulence Factors 162](#virulence-factors-3)
>
> [**8.6.3 Pathogen-Specific Analysis and Interpretation 163**](#pathogen-specific-analysis-and-interpretation-4)

[***9. Reporting, Interpretation, and Public Health Action 178***](#reporting-interpretation-and-public-health-action)

> [**9.1 Purpose and Guiding Principles 178**](#purpose-and-guiding-principles)
>
> [**9.2 Audience-Tailored Reporting 179**](#audience-tailored-reporting)
>
> [**9.3 Minimum Content and Structure of Public Health Genomic Reports 180**](#minimum-content-and-structure-of-public-health-genomic-reports)
>
> [**9.4 Reporting Timelines 183**](#reporting-timelines)

[***10. Future Directions 185***](#future-directions)

[***References 186***](#references)

[***Appendix 195***](#appendix)

> [**Genome resources for sepsis 200**](#genome-resources-for-sepsis)
>
> [**AMR data resources 200**](#amr-data-resources)
>
> [**Data Submission Workflow 200**](#data-submission-workflow)

# 

# 1. Public Health Applications of Genomics for Sepsis Pathogens 

For sepsis-associated bacterial or other pathogens, whole-genome sequencing (WGS) facilitates a variety of public health initiatives, such as routine surveillance, outbreak investigation, analysis of AMR mechanisms, and monitoring of high-risk lineages. Genomic data are most informative when combined with other contextual data, such as laboratory data, phenotypic test findings, and epidemiological metadata across all applications. Genomic evidence alone is rarely sufficient for definitive public health conclusions; its primary value lies in complementing and strengthening, rather than replacing, conventional microbiological and epidemiological approaches. The principles of open standards, reproducible bioinformatics, FAIR data practices, and responsible data sharing apply equally across all applications described in this chapter (Wilkinson et al., 2016).

**Guiding principles**

- Genomic data are a complementary line of evidence and should be interpreted alongside epidemiological, microbiological, clinical, and phenotypic data. Genomics does not replace phenotypic AST, clinical assessment, or epidemiological investigation.

- Genomic thresholds, such as SNP and cgMLST thresholds, should be viewed as empirical, probabilistic indicators rather than strict biological absolutes. Their interpretation varies depending on factors like the organism, lineage, background diversity, sampling completeness, analysis pipeline, and outbreak context.

- Phenotypic AST remains essential for routine public health AMR interpretation, and genomic AMR results should complement, not replace, phenotypic testing.

- Metadata quality, reproducibility, and responsible data governance are fundamental aspects of public health, not just technical details.

## 1.1 Outbreak Investigation

Healthcare-associated outbreaks involving sepsis pathogens can cause substantial morbidity and mortality, particularly in high-risk settings such as neonatal intensive care units (NICUs), adult intensive care units (ICUs), hematology-oncology wards, surgical wards, and transplant units. WGS provides substantially higher resolution than conventional typing methods, enabling discrimination between genetically related and unrelated isolates and supporting determination of whether a cluster of infections likely represents a genuine outbreak or reflects co-incident, epidemiologically unrelated cases (Gilchrist et al., 2015; Price et al., 2022).

Sampling for outbreak investigation should, where feasible, include all isolates that meet the outbreak case definition; colonization-screening isolates when programs are in place; historical isolates that may clarify the outbreak's origins; and environmental isolates guided by pathogen-specific biology and epidemiological findings. Environmental sampling may be particularly informative for organisms known to persist in healthcare environments, such as *A. baumannii*, or in water systems, such as *P. aeruginosa*, but it is not necessary in all investigations. Temporal representation of isolates collected before, during, and after the outbreak can improve understanding of outbreak dynamics and support the evaluation of IPC interventions.

WGS analysis may include species confirmation, multilocus sequence typing (MLST), core genome MLST (cgMLST), single-nucleotide polymorphism (SNP)-based analyses, plasmid analysis, AMR and virulence profiling, and phylogenetic reconstruction. No single SNP or allele threshold should be applied universally; thresholds reported in the literature are organism- and context-specific and must be interpreted cautiously. The findings from genomic analysis must be integrated with epidemiological data. Genetic similarity supports a hypothesis of epidemiological linkage but does not independently demonstrate direct transmission; combined interpretation of genomic and epidemiological evidence provides substantially stronger evidence for public health action than either data source alone (Price et al., 2022; Odih et al., 2026).

## 1.2 Routine Genomic Surveillance

Routine genomic surveillance of sepsis-associated bacterial pathogens enables monitoring of circulating lineages, detection of emerging AMR mechanisms, identification of high-risk clones, and longitudinal assessment of pathogen population structure (WHO, 2020; WHO, 2022a; Matsumura et al., 2025). Unlike outbreak investigation, routine surveillance is proactive, population-oriented, and inherently longitudinal.

Surveillance programs should be designed according to clearly defined public health objectives, available resources, and local pathogen epidemiology. Sampling approaches may include sentinel surveillance, systematic sampling of a defined proportion of isolates for each pathogen and time period, or targeted surveillance focused on specific populations, resistance phenotypes, or settings; no single approach is universally applicable. Genomic analyses typically include MLST, cgMLST, AMR determinant detection, virulence profiling, and population structure and phylogenetic analyses. A key analytical objective is distinguishing clonal expansion (a single lineage spreading within or across settings) from horizontal gene transfer (in which mobile genetic elements disseminate resistance determinants among diverse lineages); this distinction directly informs IPC and antimicrobial stewardship responses.

## 1.3 AMR Mechanism Detection and Monitoring

WGS complements phenotypic AMR surveillance by enabling characterization of AMR genes, resistance-associated chromosomal mutations, plasmids, and other mobile genetic elements associated with AMR genes (Matsumura et al., 2025). Key public health applications include monitoring temporal and geographic trends in resistance mechanisms; early detection of priority threats such as carbapenemase-producing Enterobacterales (CRE), carbapenem-resistant *A. baumannii* (CRAB), methicillin-resistant *S. aureus* (MRSA), and vancomycin-resistant enterococci (VRE); and determining whether resistant isolates are spreading through clonal dissemination, horizontal gene transfer, or both. This understanding can empower our efforts to identify spread mechanisms and enhance response strategies.

Commonly used software and databases for identifying AMR genes and mutations from genomic sequences include AMRFinderPlus, ResFinder, the Comprehensive Antibiotic Resistance Database Resistance Gene Identifier (CARD-RGI), and PointFinder. Results may differ due to variation in curation, nomenclature, interpretation criteria, algorithm, and update frequency. Laboratories should document software and database versions, update schedules, and analytical parameters to ensure reproducibility and comparability. Surveillance programs should periodically evaluate concordance between genotypic resistance predictions and phenotypic antimicrobial susceptibility testing (AST) results to validate prediction pipelines and detect novel or poorly characterized resistance mechanisms. Phenotypic AST remains essential; genomic AMR characterization should complement, not replace, it (Cosgrove, 2006; Matsumura et al., 2025).

## 1.4 Detection of High-Risk Clones and Population Structure

Genomic surveillance aims to determine whether rising antimicrobial resistance (AMR) results primarily from the clonal spread of specific resistant clones, which calls for targeted patient isolation and containment (triggering localized interventions like strict patient isolation and targeted equipment disinfection to contain the specific organism), or from horizontal gene transfer (HGT) of mobile genes among unrelated strains, which necessitates broader antibiotic stewardship and multi-species surveillance. As these mechanisms require different public health and infection control strategies, it is essential to integrate population structure analyses with AMR determinant profiles, plasmid data, phylogenetics, and epidemiological information to inform effective interventions. Certain bacterial lineages are disproportionately associated with AMR, healthcare-associated transmission, persistence in clinical environments, or widespread geographic dissemination. A high-risk clone may be defined as a lineage associated with characteristics that elevate public health concern, including multidrug resistance, enhanced transmission potential, geographic spread, increased virulence, or repeated involvement in outbreaks.

Genomic approaches for population structure analysis include MLST, cgMLST, phylogenetic reconstruction, and comparative genomics, applicable at local, regional, or international scales. Emerging clones continue to arise and may differ across regions. Internationally recognized examples include *E. coli* ST131, *K. pneumoniae* ST258, ST11, ST14, and ST147, *A. baumannii* International Clone 2 (IC2/ST2), and hospital-adapted *E. faecium* clade A1 lineages. Surveillance programs should monitor for indicators warranting heightened attention, including rapid increases in lineage frequency, acquisition of clinically important resistance or virulence determinants, association with outbreaks, and multi-facility or multi-regional dissemination. Identification of a recognized high-risk clone does not independently confirm ongoing transmission or active outbreak; genomic findings must be interpreted alongside epidemiological data, resistance profiles, clinical outcomes, and longitudinal surveillance trends. Harmonized typing schemes, standardized metadata, and FAIR data sharing are essential for consistent cross-jurisdictional monitoring and early detection of emerging lineages (WHO, 2022b; Wilkinson et al., 2016).

## 1.5 Genomics as a Complementary Tool: Interpretation and Uncertainty

Across all applications, genomic analyses are subject to inherent limitations, including incomplete sampling, missing or inaccurate metadata, laboratory and sequencing biases, pathogen-specific evolutionary characteristics, and undetected transmission events. Public health reports should clearly communicate analytical methods, assumptions, limitations, and uncertainties, and conclusions should be proportionate to the strength of the available evidence. The strongest public health inferences are typically derived from integration of genomic findings with epidemiological investigation, clinical information, microbiological testing, AST results, and environmental data; no single data source should be interpreted in isolation. Effective implementation of genomics for public health decision-making depends on high-quality metadata, reproducible workflows, transparent reporting, and responsible data stewardship and is supported by open standards and interoperable data practices across laboratories and surveillance programs (WHO, 2022a). The PHA4GE community standards, through its metadata standards, data harmonization tools, QC tags, and data-sharing principles, are designed to facilitate this integration, ensuring that genomic data are not generated in isolation but are embedded within a broader public health framework that maximizes their impact on patient outcomes and population health.

# 2. Surveillance Strategies Study Design

## 2.1 Framework: Surveillance Objective Determines Study Design

A public health laboratory that seeks to establish a genomic surveillance initiative must initiate the process with accurately articulated public health objectives prior to the collection of specimens, the delineation of laboratory workflows, or the selection of analytical methodologies. Decisions pertaining to sampling strategies, metadata prerequisites, sequencing volumes, bioinformatics evaluations, and reporting formats ought to be dictated by the specific public health questions that the program is intended to address. A frequently encountered challenge in subsequent implementation is the premature adoption of sequencing capabilities before the surveillance objectives have been clearly defined, which leads to the generation of data that cannot be reliably interpreted or acted upon (Armstrong et al., 2019; WHO, 2022a).

For bacterial pathogens associated with sepsis, a genomic surveillance program may be designed to address one or more of the following questions:

- Are cases in a ward, facility, or network likely to belong to the same transmission cluster?

- Which lineages and resistance mechanisms are circulating over time?

- Is resistance increasing due to clonal expansion, horizontal dissemination of mobile genetic elements, repeated introductions, or a combination of these processes?

- Are high-risk clones, unusual resistance determinants, or resistance–virulence convergence emerging locally or regionally?

- What public health actions should be guided by the genomic and epidemiological evidence?

If these questions are not pre-defined, programs may produce genomic data that are technically accurate but challenging to interpret or utilize in practice. WHO’s guidance on WGS for AMR surveillance and the overall WHO genomic surveillance strategy both highlight that the design of surveillance should start with its purpose rather than choosing the platform first (WHO, 2020, 2022a).

Before initiating a program, a public health laboratory should define the public health problem to be addressed, the intended users and anticipated actions, available laboratory, bioinformatics, and sequencing capacity, and sustainability requirements. The surveillance workflow should be conceived as a coordinated, sequential process.

A useful operational logic chain is:

Misalignment between design and analysis often leads to misinterpretation, since each stage must inform the next. Metadata requirements are driven by surveillance goals, and key elements such as collection date, specimen type, ward, and patient demographic information that cannot be reconstructed later must be recorded at the source.

This section of the guidance outlines four main applications of bacterial pathogen genomics in sepsis surveillance, each calling for specific sampling, metadata, and analysis methods (see Table 1). All use cases must follow open standards, use reproducible workflows, adhere to FAIR data principles, and employ interoperable metadata formats (WHO, 2020; WHO, 2022a; Wilkinson et al., 2016).

Table 1. Summary of Surveillance Use Cases Framework

| **Use Case**                                       | **Primary Objective**                              | **Sampling Strategy**                     | **Key Metadata Requirements**                       | **Typical Analyses**                                        | **Reporting Timeframe** |
|----------------------------------------------------|----------------------------------------------------|-------------------------------------------|-----------------------------------------------------|-------------------------------------------------------------|-------------------------|
| Outbreak investigation                             | Confirm genetic relatedness; support IPC action    | All isolates meeting case definition      | Temporal, spatial, ward movement, exposure history  | SNP analysis, cgMLST, phylogenetics                         | Real-time               |
| Routine genomic surveillance                       | Monitor population trends; detect emerging threats | Sentinel or systematic sampling           | Demographic, facility, surveillance identifiers     | MLST, AMR profiling, lineage analysis                       | Monthly/Quarterly       |
| AMR mechanism detection                            | Characterize and track resistance determinants     | Systematic plus targeted phenotype-guided | AST results, MIC values, AST standard (CLSI/EUCAST) | AMR gene/mutation detection, genotype–phenotype concordance | Monthly/Quarterly       |
| Population structure and high-risk clone detection | Characterize lineage diversity and dissemination   | Stratified representative sampling        | Geographic, clinical, epidemiological variables     | Phylogenetics, population genomics, diversity analysis      | Annual/Periodic         |

## 2.2 Core Use Cases and Sampling Strategies

This guidance describes four key genomic surveillance use cases and sampling strategies for sepsis-associated bacterial pathogens. While these use cases can overlap in practice, each has unique design considerations. Sampling strategy is one of the most important determinants of surveillance value. Poor sampling design cannot be fully corrected later by bioinformatics. Programs should therefore explicitly define the sampling frame, inclusion and exclusion criteria, and target population before analysis begins (WHO, 2020, 2022a).

### 2.2.1 Outbreak Investigation

In outbreak investigation, the primary objective is to determine whether cases are genetically linked within a shared transmission network and to gather evidence supporting infection prevention and control (IPC) strategies. It is recommended to sequence all isolates that fit the outbreak case definition whenever feasible. Case definitions should specify details such as the pathogen, resistance phenotype, healthcare setting, patient population, specimen type, and time frame, with any modifications during the investigation being documented. Sampling should include colonization screening isolates, if available; historical samples to trace outbreak origins; and environmental isolates if epidemiological data suggest a reservoir. Environmental sampling is particularly important for pathogens that persist in healthcare environments, like A. baumannii, P. aeruginosa, and VRE, and should be guided by epidemiological hypotheses rather than routine procedures (Gilchrist et al., 2015; Price et al., 2022). Background isolates from the same or nearby facilities are essential to determine if a suspected outbreak strain is new, endemic, or regionally circulating, especially for globally spread pathogens such as *K. pneumoniae*, *E. coli*, and *E. faecium*. For large-scale investigations involving more than 50-100 isolates, phased or representative sampling is acceptable if well-documented and justified. During outbreak analysis, there is no universal SNP or allele threshold for all species or settings; thresholds vary based on the organism and context and should be interpreted in conjunction with epidemiological, clinical, and temporal data. Genomic similarity indicates a potential transmission link but does not alone confirm direct transmission (Price et al., 2022; Odih et al., 2026).

### 2.2.2 Routine Genomic Surveillance

Routine surveillance is proactive, population-focused, and ongoing, aiming to monitor circulating lineages, identify new antimicrobial resistance (AMR) mechanisms, and track changes in pathogen populations over time (WHO, 2020; WHO, 2022a; Matsumura et al., 2025). Sampling should be systematic and predefined; sentinel surveillance, which involves selecting sites that represent key geographic regions, healthcare levels, and patient groups, is usually the most sustainable approach. Consistency in case definitions, laboratory methods, sequencing workflows, and analytical pipelines is crucial for accurate long-term trend analysis; any modifications should be thoroughly documented to ensure comparability across different surveillance periods. For example, the program might sequence approximately 10-20 isolates per pathogen per sentinel site each month, resources permitting. However, this is not a strict minimum and should be tailored based on local goals and resources. Sample sizes should be tied to surveillance objectives, expected prevalence, diversity, and laboratory throughput. Typical genomic analyses in this surveillance include MLST, cgMLST, detection of AMR genes, virulence profiling, and phylogenetic studies, with reporting focusing on population-wide trends in the case of large-scale surveillance and local investigation and upstream reporting in the case of hospital or site surveillance (Armstrong et al., 2019; WHO, 2022a).

### 2.2.3 AMR Mechanism Detection and Monitoring

Genomic AMR surveillance characterizes resistance genes, resistance-associated chromosomal mutations, mobile genetic elements, and plasmid structures and may support determination of whether resistance is spreading through clonal expansion, horizontal gene transfer, or both - a distinction with direct implications for IPC and antimicrobial stewardship (Matsumura et al., 2025). Effective programs combine systematic baseline surveillance of population-level AMR trends with targeted phenotype-guided surveillance for priority resistance threats, including CRE, CRAB, MRSA, and VRE. For this, commonly used AMR screening software and databases include AMRFinderPlus (Feldgarden et al., 2021), ResFinder (Bortolaia et al., 2020), and CARD-RGI (Alcock et al., 2020); results may differ across tools due to variation in algorithms, curation, and nomenclature; software database versions and analytical parameters must be documented for reproducibility. Phenotypic AST remains essential in most cases: genomic AMR prediction should complement, not replace, phenotypic testing, as gene presence does not guarantee expression and novel mechanisms may not be represented in reference databases. Periodic genotype–phenotype concordance evaluation is recommended to validate prediction pipelines and detect emerging resistance mechanisms.

### 2.2.4 Population Structure and High-Risk Clone Detection

Public health laboratories conduct population structure surveillance to analyze genetic diversity and geographic distribution, monitor known epidemic lineages, and detect emerging high-risk clones early (Wyres et al., 2020; WHO, 2022a). To obtain representative data, sampling should include diverse regions, healthcare environments, and patient groups through stratified methods. Relying solely on samples from outbreaks, referral centers, or highly resistant isolates may bias estimates of lineage prevalence and lead to invalid conclusions about true prevalence and genetic diversity. Although there are limitations of existing sampling strategies, sample size determination for population structure in genomic surveillance depends primarily on the primary objective, the expected prevalence of the variant(s) of interest, and the genetic diversity of the target population. Given the significant variation in pathogen diversity across settings, it is generally preferable to avoid fixed sample size requirements (Wohl et al., 2023).

Examples of important high-risk clones recognized globally include *E. coli* ST131, *K. pneumoniae* ST258/ST11/ST14/ST147, *A. baumannii* IC2/ST2, and hospital-adapted *E. faecium* clade A1. Because emerging clones vary by region and evolve over time, continuous, representative genomic surveillance is essential. *E. coli* ST131 emerged around 2003 and subsequently accounted for an increasing proportion of ESBL-producing *E. coli* isolates across regions (Nicolas-Chanoine et al., 2014). *K. pneumoniae* ST307 emerged in 2008 in the Netherlands and rapidly disseminated globally across six WHO regions by 2025 (Sarkar, S. N., & Das, S., 2026). Signs that call for increased surveillance include rapid lineage expansion, spread across multiple facilities, accumulation of key resistance or virulence traits, and persistence despite infection control measures. The public deposition and use of data in INSDC repositories allows for global and regional tracking and enables the understanding of disease dynamics and can help identify localized vs. regional vs. global dynamics.

**Note**: Genomic data alone cannot confirm transmission, outbreaks, or clinical significance. The most reliable public health insights come from combining genomic findings with epidemiological, clinical, microbiological, and contextual data across all use cases.

##  2.3 Specimen Types, Collection, and Handling

Blood culture isolates are the primary specimen for sepsis genomic surveillance, providing direct microbiological evidence of bloodstream infections and invasive disease. Specimens such as rectal, nasal, and skin swabs can be used as colonization screening samples to provide contextual data on transmission pathways and AMR reservoirs and are particularly informative for tracking multidrug-resistant bacteria across a healthcare facility. These specimens provide complementary, rather than equivalent, evidence relative to clinical isolates and should be interpreted accordingly. Environmental specimens should be collected when epidemiological evidence supports a reservoir hypothesis and are most pertinent to investigations of *A. baumannii*, *P. aeruginosa*, and VRE. Routine environmental sampling is not necessary for all programs. When comparing environmental and clinical isolates at the genomic level, interpretation must always include epidemiological, temporal, and microbiological data, as no universal SNP threshold reliably links an environmental source. Individual outbreaks or clones may differ in their mutation rate or background diversity.

Each specimen should be assigned a unique identifier that remains consistent throughout all stages, including collection, laboratory processing, sequencing, bioinformatics analysis, and reporting. Metadata that cannot be reconstructed later, such as collection date, specimen type, ward, healthcare facility, and patient demographics, must be documented at the time of collection. Whenever feasible, laboratory information management systems (LIMS) should support specimen tracking, metadata linkage, audit trails, and integration with laboratory workflows. Biosafety procedures must adhere to relevant national and institutional regulations. Furthermore, isolates suspected of increased virulence, such as hypervirulent *K. pneumoniae*, may require additional institutional risk assessments.

**Note**: The quality of specimens and the completeness of metadata at the point of collection are often more critical for public health utility than the high volume of sequencing.

## 2.4 Retrospective and Prospective Study Designs

Both retrospective and prospective study designs generate valuable genomic data and should be viewed as complementary. Retrospective studies analyze stored isolates, making them useful for establishing baseline lineage diversity, understanding historical AMR trends, detecting previously unnoticed transmission events, and validating laboratory and bioinformatics methods. They may also identify ongoing, low-prevalence outbreaks. However, they cannot support real-time public health responses and are often constrained by incomplete metadata, selection bias, and inconsistent historical sampling. Prospective surveillance involves collecting isolates according to predefined protocols after a program begins, enabling ongoing public health decisions, outbreak identification, and intervention evaluation. This approach, however, relies on continuous funding, proper laboratory infrastructure, skilled personnel, and effective data management (WHO, 2022a).

Many programs, especially those with limited resources, find that a phased hybrid approach is the most practical way to implement genomic surveillance. The initial phase focuses on retrospective sequencing of stored samples to identify circulating lineages and verify workflows. The second phase involves prospective sentinel surveillance conducted in accordance with standardized protocols. In the final phase, genomic surveillance is integrated into routine public health reporting. The baby GERMSSA program is one of the best examples; it uses this phased strategy that allows programs to build capacity gradually while providing immediate public health benefits ([<u>https://www.witsmycology.co.za/baby-germs-surveillance/</u>](https://www.witsmycology.co.za/baby-germs-surveillance/)).

## 2.5 Implementation of genomic surveillance

Implementation plans for genomic surveillance should include an assessment of foundational system requirements, such as specimen pathways, diagnostic confirmation, biosafety, quality management, workforce competencies, data systems, computing resources, procurement, and maintenance. Infrastructure constraints, including unreliable electricity, weak internet connectivity, cold-chain limitations, and limited storage or computing capacity, should be identified during planning, and mitigation measures should be documented in advance (Halpin et al., 2025). Data-sharing arrangements should be established before surveillance begins and should define standards for metadata, ownership, access, attribution, privacy, legal compliance, and equitable benefit-sharing, while supporting routine use and surge readiness during outbreaks or other public health emergencies (Global Genomic Surveillance Strategy, 2022; WHO, 2022a; Griffiths et al., 2024).

Plans should be country-led, financially and operationally sustainable, connected to regional and global systems, and designed with shared responsibility across governments, WHO, partners, academia, and other stakeholders.

In practical terms, the implementation plans are expected to address the five strategic objectives of the strategy indicated in the WHO global genomic surveillance strategies:

- improving access to tools and infrastructure,

- strengthening the workforce,

- enhancing data sharing and data utility,

- maximizing connectivity across the broader surveillance architecture,

- maintaining readiness for emergencies.

**2.6 Practical Adjustments for National or Regional Surveillance in Settings with Limited Resources**

The WHO Global Genomic Surveillance Strategy highlights significant disparities in infrastructure and capacity across regions, underscoring the importance of equitable access. Resource limitations should inform how surveillance is implemented, rather than hinder participation. For long-term sustainable success, programs need to adapt their strategies to local circumstances rather than replicate models from resource-rich countries. The core principles prioritize sustainability over scale, aim for representativeness over completeness, favor reproducibility over complexity, and focus on public health impact over technological innovation (WHO, 2022a).

Several design adaptations can make genomic surveillance feasible and sustainable in low-resource settings:

**Sentinel site approach:** Rather than attempting population-wide surveillance, select one or two sentinel hospitals with adequate microbiology laboratory capacity. Surveillance at these sites can generate data that are broadly informative for the region. The Baby GERMS SA program in South Africa demonstrates this approach in neonatal infection surveillance.

**Systematic rather than comprehensive sampling**: If sequencing all incident cases is not feasible, adopt a systematic sampling scheme (e.g., the first five isolates of each target species per month) rather than convenience sampling. A systematic scheme, even with small numbers, generates interpretable trend data over time.

**Retrospective first strategy:** Begin with a retrospective study of archived isolates (stored at -80 °C). This requires no change to routine clinical workflows and can be performed in batch when sequencing resources are available, providing immediate information about local pathogen populations. Operationalizing genomic surveillance in LMICs requires context-appropriate infrastructure and interdisciplinary engagement.

**Partnerships and regional collaboration:** Laboratories without in-house sequencing capacity can partner with national or international sequencing centers. The WHO GLASS roadmap for integrating WGS into existing AMR surveillance frameworks draws on practical experience in Colombia, India, Nigeria, and the Philippines and offers a model for such partnerships.

**Resource-sensitive pathogen prioritization:** In the most resource-constrained settings, it may be necessary to prioritize certain pathogens and specimen types.

Note: A smaller, well-maintained genomic surveillance program typically offers more value than a larger but unsustainable one. Sentinel sites, systematic small-volume sampling, and phenotype-triggered sequencing are recommended for LMIC.

# 3. Metadata standards

Standardized metadata are the foundation of interoperable genomic epidemiology. Without consistent, structured information describing when, where, how, and from whom a pathogen isolate was obtained, genomic sequences lose much of their epidemiological value and cannot be reliably compared across laboratories, regions, or time periods. This section introduces the metadata standards and tools that are essential for sepsis pathogen genomic surveillance. It is built upon the existing PHA4GE Neonatal Sepsis Community Metadata Standard ([<u>https://github.com/pha4ge/Neonatal-Sepsis-Community-Metadata-Standard</u>](https://github.com/pha4ge/Neonatal-Sepsis-Community-Metadata-Standard)).

**Importance of standardized metadata**

- Improves data quality and completeness

- Enables interoperability across databases, tools, and studies

- ⁠Facilitates curated data sharing and reuse in line with FAIR principles (Findable, Accessible, Interoperable, and Reusable)

- Supports reproducibility and transparent interpretation of results

- ⁠Enables accurate linkage between genomic, clinical, and epidemiological data

- ⁠Improves comparability of datasets generated by different institutions, laboratories, and countries

- Facilitates large-scale surveillance, outbreak detection, and monitoring of pathogen transmission dynamics

The FAIR principles, Findable, Accessible, Interoperable, and Reusable, provide the essential framework for managing the high-quality metadata required for effective genomic surveillance. By ensuring metadata is context-aware, structured, ontology-based, and harmonized across sites, data can be automatically discovered, integrated, and re-analyzed. This approach maximizes the public health return on sequencing investments and ensures that pathogen genomic data is immediately actionable for global health interventions.

## The PHA4GE Community Metadata Standards for Sepsis Pathogens

PHA4GE is actively developing a sepsis data specification package in partnership with stakeholders and experts. This package will define the core metadata fields required to standardize and harmonize genomic surveillance data for sepsis-causing pathogens globally. The initiative is building the PHA4GE Neonatal Sepsis Community Metadata Standard, which provides a consensus-based schema of fields that capture sample provenance, patient demographics, clinical presentation, laboratory methods, AMR, and sequencing metadata. Metadata fields can be organized into three priority tiers: Required, Strongly Recommended, Optional.

A representative field catalogue is shown below. The specification should also map to other international standards, including the Genomic Standards Consortium MIxS pathogen checklists and NCBI BioSample attributes (NCBI utilizes specific BioSample packages for pathogen submissions), ensuring that data formatted to the PHA4GE specification are automatically compatible with INSDC repositories.

| **Field Name**              | **Priority**         | **Description**                                                      | **Controlled Vocabulary / Format**                                                                |
|-----------------------------|----------------------|----------------------------------------------------------------------|---------------------------------------------------------------------------------------------------|
| sample_id                   | Required             | Unique identifier for the sample; links isolate to clinical metadata | Text string, local laboratory ID system                                                           |
| organism                    | Required             | Scientific name of the pathogen                                      | NCBI Taxonomy (e.g., *Klebsiella pneumoniae* \[txid573\])                                         |
| collection_date             | Required             | Date of sample collection                                            | ISO 8601 (YYYY‑MM‑DD)                                                                             |
| geographic_location         | Required             | Country and administrative level of sample collection                | ISO 3166 country codes; GAZ or GeoNames ontology for finer resolution                             |
| specimen_source             | Required             | Anatomical site or material from which the isolate was obtained      | SNOMED‑CT or NCBI BioSample package terms (e.g., blood, CSF, urine, respiratory)                  |
| host_age                    | Strongly Recommended | Age of the patient at time of sampling                               | Numeric value with unit (days, months, years); for neonates, use days of life                     |
| host_sex                    | Strongly Recommended | Biological sex of the patient                                        | PATO ontology (male, female, intersex, not collected)                                             |
| infection_type              | Strongly Recommended | Classification of sepsis onset                                       | early‑onset (\< 72 h), late‑onset (≥ 72 h), healthcare‑associated, community‑acquired             |
| antimicrobial_suscptibility | Strongly Recommended | Phenotypic AST result (MIC or disk diffusion)                        | CLSI or EUCAST breakpoint interpretation categories; include method standard                      |
| purpose_of_sampling         | Strongly Recommended | Reason for sample collection or sequencing                           | PHA4GE‑controlled vocabulary (e.g., outbreak_investigation, routine_surveillance, AMR_monitoring) |
| sequencing_platform         | Strongly Recommended | Instrument model used for sequencing                                 | NCBI SRA controlled list (e.g., Illumina NovaSeq, ONT MinION)                                     |
| host_outcome                | Optional             | Clinical outcome of the infection episode                            | survived, died, unknown                                                                           |
| prior_antibiotic_exposure   | Optional             | Antibiotics administered before sample collection                    | ATC classification codes; list agent name, route, and duration                                    |
| device_associated_infection | Optional             | Whether infection is associated with an indwelling medical device    | Boolean (yes/no); if yes, specify device type                                                     |

**Integration with International Sequence Repositories and the PHA4GE QC Tags**

Metadata should ultimately be linked to sequence data deposited in public repositories. The International Nucleotide Sequence Database Collaboration (INSDC), comprising NCBI (USA), ENA (Europe), and DDBJ (Japan), provides the global infrastructure for sequence data sharing. The metadata specifications should map directly to INSDC BioSample and SRA metadata fields. Every sepsis-specific bacterial genome raw read or analysis QC scenario should be mapped to the five-field PHA4GE QC Contextual Data Tag specification: quality_control_method_name,quality_control_method_version, quality_control_determination, quality_control_issues, and quality_control_details. The PHA4GE standardized contextual data QC tags and associated controlled terms should be included in public repository submissions to flag sequence datasets with known quality issues. These tags are organism and sequencing platform agnostic, so they apply equally to Illumina, Oxford Nanopore, or other platform data.

**Mapping sepsis-specific QC scenarios onto the five fields**

| **QC scenario**                                                                              | **quality_control_determination**            | **quality_control_issues**                                                                | **Notes**                                                                                                                                                                                     |
|----------------------------------------------------------------------------------------------|----------------------------------------------|-------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| \>5% non-target reads (Kraken2)                                                              | flagged or failed, by severity               | sequence contaminated \[GENEPIO:0100569\]                                                 | Use low signal-to-noise ratio \[GENEPIO:0100574\] instead if framing as background/host-read contamination from a clinical specimen (per PHA4GE Worked Example 5)                             |
| Coverage \<30x or contig count outside expected range                                        | failed, or minor issues identified           | low average genome coverage \[GENEPIO:0100570\]; low quality sequence \[GENEPIO:0100568\] | Put the actual depth/contig numbers in quality_control_details                                                                                                                                |
| Evidence of multiple strains / co-infection (e.g. mixed K. pneumoniae STs)                   | flagged for potential quality control issues | sequence contaminated \[GENEPIO:0100569\]                                                 | PHA4GE's own Worked Example 1 uses this same term for ambiguous-site signals that may indicate contamination *or* a real mixed infection — the distinction belongs in quality_control_details |
| Species identity unresolved (ANI \<95%; Kraken2 reads split across KpSC/ABC complex members) | flagged for potential quality control issues | taxonomic designation inconsistent across methods \[GENEPIO:0101038\]                     | Mirrors PHA4GE Worked Example 8 (conflicting Mash/Kraken2/FastANI calls)                                                                                                                      |

These tags ensure that genomes of variable quality are not silently discarded but are instead annotated with transparent, ontology-backed caveats, making them available for training, method development, benchmarking, and sensitivity analyses while preventing their misuse as high-quality reference material. The specification, ontology definitions, and a JSON representation are maintained at [<u>https://github.com/pha4ge/contextual_data_QC_tags</u>](https://github.com/pha4ge/contextual_data_QC_tags).

The collection and sharing of standardized metadata is governed by the seven baseline principles of the PHA4GE Microbial Data Sharing Accord ([<u>https://pha4ge.org/wp-content/uploads/2024/03/PHA4GE_Microbial_Data_Sharing_Accord_v1.0.pdf</u>](https://pha4ge.org/wp-content/uploads/2024/03/PHA4GE_Microbial_Data_Sharing_Accord_v1.0.pdf)). In particular, the principles of transparency, accountability, and stewardship require that metadata be as complete as possible, that limitations (e.g., missing fields, QC flags) be clearly documented, and that data providers and users agree on responsible use boundaries

**Adapting Metadata Collection for Different Resource Settings: Minimum, Standard, and Enhanced Metadata Sets**

Metadata collection should not become a bottleneck that prevents laboratories from contributing genomic data. A one-size-fits-all metadata requirement may not be appropriate across all settings. Laboratories and surveillance programs differ in scope, resources, information systems, and legal constraints. Accordingly, this guidance recommends a tiered metadata model with minimum, standard, and enhanced implementation levels. This expert-consensus operational framework is informed by PHA4GE standards development and WHO guidance (PHA4GE, 2026a, 2026b; WHO, 2022a).

**Minimum metadata set:** is the smallest set of fields that should be collected for every genome intended for public health use. At a minimum, the following fields should be captured:

- sample_id: unique local identifier for the specimen or isolate

- organism: scientific name using a stable taxonomic reference

- collection_date: date of specimen collection in ISO 8601 format (YYYY-MM-DD)

- geographic_location: country and, where feasible, first subnational administrative level

- specimen_source: anatomical site or material from which the isolate was obtained (distinguishing bloodstream isolate, screening isolate, or environmental isolate)

- purpose_of_sampling: routine surveillance, outbreak investigation, AMR monitoring, research, or another defined category

- Health facility or sentinel site name: identifier for the source facility or surveillance site

- sequence record linkage field: a field linking the metadata record to the sequence record or sequencing batch

- data_custodian_organisation_name or authors: a field to acknowledge the origin of the data and the contributors

This minimum set supports basic trend analysis, cluster review, and repository submission compatibility, and should be considered the floor for participation rather than the ideal target (WHO, 2022a).

**Standard metadata set:** is recommended for routine public health surveillance and outbreak investigation. In addition to the minimum fields, it should include:

- host age with unit

- host sex or sex recorded using a locally approved standardized term

- specimen type / isolate type distinguishing bloodstream isolate, screening isolate, or environmental isolate

- healthcare acquisition context such as community-acquired, healthcare-associated, early-onset neonatal sepsis, or late-onset neonatal sepsis, where relevant

- ward, unit, or service line at an appropriate level of granularity

- collection and receipt dates if different

- phenotypic AST result summary if performed

- AST method and interpretive standard including standard name and edition where possible

- Purpose of sequencing and sequencing platform

- analysis pipeline or workflow identifier if results are produced routinely

This level is generally sufficient for surveillance interpretation, AMR monitoring, outbreak investigation, and public health reporting (WHO, 2020, 2023).

**Enhanced metadata set is** recommended for reference laboratories, formal outbreak investigations, special studies, and programs with mature data governance arrangements. Additional fields may include:

- patient movement history relevant to the event

- transfer history between facilities

- device association

- prior antibiotic exposure

- hospitalization dates

- symptom onset dates

- environmental sampling metadata

- colonization-screening context

- outcome or disposition fields where ethically and legally appropriate

- detailed laboratory process metadata

- sequencing run and library metadata

- Detailed bioinformatics and QC data

- richer provenance and data-quality documentation

Enhanced metadata can significantly improve inference and facilitate secondary analyses; however, programs should be cautious not to gather more data than they can validate, govern, and use responsibly (Griffiths et al., 2024; WHO, 2022b).

Regardless of the implementation level, all users are encouraged to apply the PHA4GE QC Contextual Data Tags to any datasets that fail quality thresholds, ensuring that their limitations are transparently documented rather than silently embedded in public databases.

**Data minimization and local governance**

Although richer metadata often improves interpretation, programs should still apply data-minimization principles. Identifiable patient data should not be included in publicly shared metadata, and any link between local identifiers and patient identity should remain under secure control at the originating institution, in line with local ethics and legal requirements (Griffiths et al., 2024; WHO, 2022b).

# 4. Ethical, Legal and Data Governance

The PHA4GE Microbial Data-Sharing Accord provides a practical framework for the ethical and responsible secondary use of microbial and pathogen data. The Accord sets out seven simple, baseline principles designed to address common concerns among researchers and organisations contributing microbial datasets for secondary use, while also promoting responsible practices among data users (Griffiths et al., 2024). These principles emphasise transparency, appropriate attribution, responsible data stewardship, and equitable collaboration, helping to build trust and facilitate data sharing across institutions. This model could be adapted, supporting the responsible sharing and reuse of clinical, genomic, and associated metadata while safeguarding privacy and recognising the contributions of data generators.

All data sharing must comply with applicable national and institutional data protection regulations. Publicly deposited genomic data must be de-identified, and any linkage between sample IDs and patient identifiers must be maintained securely and separately at the originating institution. The PHA4GE Microbial Data-Sharing Accord provides a practical framework for the ethical and responsible secondary use of microbial and pathogen data. The Accord sets out seven baseline principles: (1) Attribution, (2) Overview of outputs prior to their publication, (3) Onward sharing of data, (4) Host and phenotype data, (5) Geospatial data, (6) Intellectual Property, and (7) Opportunity for collaboration (see Supplementary Table 6 : PHA4GE Microbial Data-Sharing Accord Clauses). These principles are designed to address common concerns among researchers and organisations contributing microbial datasets for secondary use, while also promoting responsible practices among data users (Griffiths et al., 2024). See this paper on [<u>10.1136/bmjgh-2024-016474</u>](https://doi.org/10.1136/bmjgh-2024-016474) defined clauses regarding secondary use of microbial data.

# 5. Laboratory and Sequencing Best Practices

The quality of bioinformatics analysis is fundamentally limited by the quality of the upstream laboratory processes. Even the most sophisticated genomic pipelines cannot compensate for misidentified species, mixed cultures, degraded DNA, or poorly prepared sequencing libraries. This section provides concise, pathogen-agnostic guidance on the key wet laboratory steps that directly determine the success of downstream bioinformatics for sepsis pathogen genomics. It is not a substitute for detailed standard operating procedures (SOPs), which should be developed and validated locally; rather, it highlights the critical decision points, quality control checkpoints, and international standards that underpin robust, reproducible genomic surveillance.

## 5.1 Pre-sequencing Pathogen Confirmation (Species Identification) 

Accurate species-level identification before WGS is essential to ensure that limited sequencing resources are used only on priority bacterial pathogens relevant to sepsis pathogens. Pre-sequencing confirmation reduces the risk of sequencing contaminants, non-target organisms, or mixed cultures and supports efficient outbreak investigation, AMR monitoring, and genomic surveillance.

We recommend automated ID systems (VITEK 2, Phoenix, MicroScan - where present), MALDI-TOF, Molecular/nucleic acid based methods before WGS. Targeted molecular approaches may be used in some settings to confirm species identity or specific resistance markers. These may be particularly useful when:

- Routine identification is uncertain;

- Urgent outbreak response is required; or

- Known high-priority resistance mechanism needs rapid confirmation

## 5.2 Antimicrobial Susceptibility Testing (AST)

Phenotypic antimicrobial susceptibility testing (AST) plays a crucial role in sepsis pathogen genomic surveillance for two main reasons. Firstly, it offers the clinical results necessary to guide patient-specific treatments. Secondly, and just as vital for this purpose, it facilitates genotype-phenotype correlation by systematically comparing genomic resistance markers with actual susceptibility patterns. This process is vital for validating bioinformatic AMR prediction tools, identifying new or emerging resistance mechanisms, and forming the evidence base that will eventually allow a shift from phenotypic AST to genotypic prediction for specific pathogen–drug pairs.

There are two principal international standards govern AST methodology and interpretation:

- **CLSI (Clinical and Laboratory Standards Institute)**: Publishes the M100 performance standards annually, which define disk diffusion (M02) and broth microdilution (M07) methodologies along with species specific interpretive breakpoints. CLSI standards are widely used in the Americas and in many countries in Africa and Asia.

- **EUCAST (European Committee on Antimicrobial Susceptibility Testing)**: Publishes clinical breakpoint tables annually, together with standardised disk diffusion and broth microdilution methodologies. EUCAST standards are harmonised across Europe and increasingly adopted in other regions.

For sepsis genomic surveillance, laboratories should document which standard and edition were used, as breakpoints evolve over time and interpretive categories (susceptible, intermediate, and resistant) may differ between CLSI and EUCAST for certain organism–drug combinations.

To support genotype-phenotype correlation in sepsis pathogens, laboratories participating in or contributing data to GLASS-compatible surveillance are encouraged to test and report antimicrobial susceptibility data for a defined minimum set of priority pathogen-antibiotic pairs. For example, this includes testing E. coli against specific penicillins, cephalosporins, fluoroquinolones, aminoglycosides, carbapenems, and folate pathway inhibitors. These standardized combinations promote consistent global resistance monitoring and enable effective routine data collection. Because baseline antibiotic needs vary by the specific pathogen isolated, such as E. coli, K. pneumoniae, or S. aureus, laboratories should refer to the WHO GLASS manual for comprehensive, pathogen-specific minimum testing profiles ([<u>https://www.who.int/publications/i/item/9789241549400</u>](https://www.who.int/publications/i/item/9789241549400)).

Whenever possible, MICs (determined by broth microdilution or gradient diffusion) should be recorded rather than relying solely on disk diffusion zone diameters. MICs provide a quantitative phenotype for comparison with genomic predictions. For example, in A. baumannii, disk diffusion is unreliable for cefiderocol susceptibility testing; the reference method is broth microdilution (BMD) in iron-depleted media. Discrepancies between disk diffusion and BMD results have been observed during CRAB outbreaks (Maldonado-Barrueco et al., 2025), and relying solely on disk diffusion could miss emerging cefiderocol resistance. Laboratories submitting cefiderocol AST data for A. baumannii must specify the method used.

## 5.3 Pure Isolate Culture, Storage, and DNA Extraction

### 5.3.1 Pure Isolate Confirmation and Subculture

Whole genome sequencing of bacterial isolates requires a pure, axenic culture. Mixed cultures (two or more distinct bacterial populations within the same specimen or derived from the same colony pick generates chimeric assemblies and unreliable genotyping results, particularly for plasmid-borne resistance genes and MLST assignment. Before proceeding to DNA extraction:

- **Confirm purity by streaking the isolate onto a non-selective agar plate and incubating overnight.** Inspect for uniform colony morphology. If more than one colony type is observed, subculture each distinct morphology separately and repeat the identification.

- **Single colony pick:** For DNA extraction, always start from a single, well-isolated colony grown on solid agar. This minimizes the risk of sampling a mixed population.

- **Avoid serial passage:** Minimize the number of subculture steps between the original clinical specimen and DNA extraction, as repeated passage can select for laboratory-adapted variants and lead to loss of plasmids or other mobile genetic elements.

### 5.3.2 Isolate Storage for Genomic Archives

Long-term bacterial isolate storage is vital for genomic epidemiology, enabling re-analysis, re-sequencing of key strains, and external quality checks.

- Storage media include commercial cryobead systems (such as Microbank and Cryobank) or 15–20% glycerol in growth media such as tryptic soy broth. Cryobeads in peptone broth with 15% glycerol effectively maintain stock cultures of non-fastidious bacteria.

- Long-term storage temperature should be -80 °C; -20 °C is not recommended long-term, as it permits residual activity and viability loss.

- Minimize freeze-thaw cycles: Repeated freeze-thaw cycles reduce viability and may select for subpopulations with altered characteristics. Aliquot stock cultures into multiple single-use vials during initial preservation is strongly recommended.

- Documentation: Record the storage location, vial identifier, and date of preservation. Link each cryovial identifier to the corresponding BioSample accession in the laboratory information management system (LIMS).

Good practice, per ISO 23418:2022 for WGS of bacteria, involves handling bacterial cultures for purity and identity, isolating axenic genomic DNA with documented methods, confirming DNA is free of PCR inhibitors, and preparing libraries with size-selection steps validated for the sequencing platform.

### 5.3.3 DNA Extraction

The goal of DNA extraction for WGS is to obtain high-molecular-weight, pure genomic DNA in sufficient quantity, free of PCR inhibitors, and representative of the entire genome (including plasmids). The extraction method must be compatible with both the organism's Gram-staining status and the intended sequencing platform.

**Quality control of extracted DNA:**

Before proceeding to library preparation, a laboratory should assess:

- **Quantity**: Measured using a fluorometric method (e.g., Qubit dsDNA HS Assay). UV spectrophotometry (NanoDrop) alone is insufficient because it cannot distinguish DNA from RNA, degraded nucleic acids, or contaminating small molecules.

- **Purity**: A260/A280 ratio of ~1.8–2.0 indicates pure DNA. Ratios below 1.7 indicate protein contamination; ratios above 2.0 suggest RNA carry-over. A260/A230 ratio \> 2.0 is desirable; lower values indicate carry-over of chaotropic salts or other organic contaminants from the extraction process.

- **Integrity**: For long-read (ONT) sequencing, input DNA distribution must peak above 30 kb to maximize read lengths; because standard agarose gels and capillary systems (Bioanalyzer/TapeStation) cannot accurately resolve macromolecules of this size, fragment length must be verified using the Agilent Femto Pulse System or pulsed-field gel electrophoresis (PFGE). Conversely, precise fragment length is highly critical for Illumina short-read sequencing to prevent flow cell clustering failures, adapter-dimers formation or adapter read-through. While workflows utilize physical or enzymatic shearing to fragment the DNA, final library sizes must target a narrow window (typically 300–600 bp) verified via an Agilent Bioanalyzer or TapeStation prior to sequencing.

**Minimum DNA requirements vary by platform:**

- **Illumina**: Typically 1-5 ng for tagmentation-based library preparation (e.g., Illumina DNA Prep, Nextera XT). The Illumina DNA Prep kit (formerly Nextera DNA Flex) has been validated for enteric bacterial pathogens and performs well, although enzymatic library preparation kits using transposases may exhibit some sequence-context bias.

- **Oxford Nanopore:** Typically 200 ng for the Rapid Barcoding Kit (SQK-RBK114), with an optimal input of high-molecular-weight DNA (\> 30 kb). ONT's Nanopore-Only Microbial Isolate Sequencing Solution (NO-MISS) provides a flexible approach that allows sequencing of 4 to 24 microbial isolate genomes per MinION Flow Cell, generating a minimum coverage of 50× per genome.

## 5.4 Sequencing Library Preparation and Platform Choice

The choice of sequencing platform and library preparation method fundamentally shapes the resulting genomic data and determines which bioinformatic analyses are feasible. The choice of sequencing platform has significant implications for downstream analysis. Illumina short-read sequencing is preferred for high-accuracy SNV detection, outbreak phylogenetics, and AMR gene detection. Oxford Nanopore long-read sequencing is preferred for complete genome closure, plasmid reconstruction, and real-time outbreak response. Table 5.1 outlines the key features of the two platforms that currently dominate public health bacterial genomics.

Table 5.1: Comparison of sequencing platforms for sepsis pathogen genomics

| **Characteristic**         | **Illumina (short‑read)**                                                                                                                                 | **Oxford Nanopore Technologies (ONT; long‑read)**                                                                                                                                                                                                                           |
|----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Read length                | 2 × 150 bp or 2 × 250 bp (paired‑end)                                                                                                                     | Variable, up to \> 100 kb; typical N50 5–30 kb                                                                                                                                                                                                                              |
| Base accuracy (modal)      | \> 99.9 % (Q30 ≥ 85 %)                                                                                                                                    | \> 99 % (Q20+) with R10.4.1 flow cells and latest chemistry; \> 99.9 % (Q30+) in duplex mode                                                                                                                                                                                |
| Throughput per run         | 1–120 Gb (MiSeq) to 3,000 Gb (NovaSeq X)                                                                                                                  | 10–30 Gb (MinION/GridION) to \> 200 Gb (PromethION)                                                                                                                                                                                                                         |
| Library preparation time   | 2–4 h (tagmentation‑based)                                                                                                                                | 10–30 min (Rapid Barcoding Kit)                                                                                                                                                                                                                                             |
| Sequencing run time        | 4–56 h (depending on platform and read length)                                                                                                            | Real‑time; 1–72 h                                                                                                                                                                                                                                                           |
| Per‑sample consumable cost | Moderate (~\$30–100/sample at scale)                                                                                                                      | Moderate (~\$30–80/sample with multiplexing)                                                                                                                                                                                                                                |
| Best for                   | High‑accuracy SNV detection, outbreak phylogenetics, AMR gene detection                                                                                   | Complete genome closure, plasmid reconstruction, K/O locus typing, real‑time outbreak response                                                                                                                                                                              |
| Key limitation             | Short reads fail to resolve repetitive regions, large mobile genetic elements, and chromosomal rearrangements; plasmid reconstruction is often fragmented | Higher raw read error rate than Illumina, though the accuracy of consensus sequences (after polishing) may be comparable. ONT-only sequencing may be accurate enough for outbreak investigation when used with appropriate basecalling, assembly, and polishing procedures. |

Hybrid assembly, which combines the accuracy of Illumina short reads for single-nucleotide precision with the contiguity of ONT long reads to span repeats and mobile elements, produces the highest-quality genome assemblies and is the gold standard for reference-grade genomes, complex plasmid reconstruction, and detailed characterization of surface antigen loci (e.g., K and O loci in K. pneumoniae, O-antigen clusters in E. coli, and capsule loci in A. baumannii). However, hybrid assembly doubles sequencing costs and bioinformatic complexity. For most routine public health applications (AMR surveillance, outbreak cluster detection, MLST/cgMLST typing), a single-platform approach—either Illumina-only or ONT-only with appropriate quality control—is sufficient.

## 5.5 Quality Control Before Sequencing and Pre-analytical Documentation

The main causes of sequencing failure or poor data quality come from wet-laboratory steps before reaching the sequencer. A pre-sequencing quality control checklist reduces wasted runs.

1.  Species identity confirmed by MALDI-TOF or an alternative method → record the identification method and confidence score (if available) in LIMS.

2.  Culture purity verified by uniform colony morphology on subculture → document any evidence of mixed morphology.

3.  DNA concentration measured by fluorometric method (e.g., Qubit) → ensure concentration meets the minimum input for the chosen library prep kit.

4.  DNA purity assessed by spectrophotometry (A260/A280 1.8–2.0; A260/A230 \> 2.0) → if outside range, repeat extraction or perform additional cleanup (e.g., AMPure bead purification - developed for the purification of PCR products).

5.  DNA integrity checked by gel or TapeStation → for ONT, ensure high molecular weight DNA is present (\> 30 kb).

6.  AST results recorded → document which standard (CLSI/EUCAST) and method (disk diffusion, broth microdilution, gradient diffusion) were used.

It is recommended that the laboratory should participate in quality assurance, including external quality assessment (EQA) or proficiency testing (PT) programs, like those by the WHO AMR Surveillance Network and national labs. These programs independently evaluate lab performance, detect errors early, and prevent issues in genomic analyses.

# 6. Standard bioinformatics data analysis workflow - core bioinformatics steps

Analyzing and interpreting pathogen sequencing data can be challenging due to the complexity of microbial genomes and the diversity of sequencing platforms and assembly strategies. The choice of computing infrastructure should be guided by the volume of sequencing data generated, the complexity of the analyses performed, and the available bioinformatics expertise. There is a wide range of community resources, established workflows, and a range of bioinformatic tools available to support researchers with different levels of bioinformatics and data analysis experience. This section is focused primarily on the whole-genome sequencing analysis and brings together the core bioinformatics steps that apply across all priority sepsis pathogens: *Klebsiella pneumoniae*, *Escherichia coli*, *Acinetobacter baumannii*, *Pseudomonas aeruginosa*, *Staphylococcus aureus*, and *Enterococcus* spp.

When starting data analysis, it is helpful first to consider the level of experience and preferred computing environment. That is, if you are using it.

1.  Existing bioinformatics pipelines/tools (with command-line experience)

2.  Existing bioinformatics pipelines/tools (for non-bioinformaticians)

3.  Developing a custom pipeline using existing tools

Computational requirements should be matched to the scale and complexity of the sequencing workload. Server or HPC systems are recommended for large-scale datasets, including whole-genome sequencing projects where substantial processing power and storage are essential for timely and efficient analysis. Local computing infrastructure may be adequate for low-throughput workflows or targeted analyses and remains a practical option for laboratories with limited resources.

Cloud-based platforms represent a flexible and increasingly viable alternative to local or HPC infrastructure. For example, Galaxy is a user-friendly platform and allows researchers to execute a broad range of bioinformatics workflows without the need for advanced programming expertise or computational hardware while also facilitating reproducibility and cross-institutional collaboration. Despite these advantages, adoption of cloud-based solutions requires careful consideration of several practical factors, including computational costs, data upload and transfer times, internet reliability,

## 6.1 Base calling Nanopore data

Basecalling is the process of converting raw electrical signal data from an Oxford Nanopore sequencing run (stored in FAST5 or POD5 format) into nucleotide sequence reads (FASTQ) with associated quality scores. It is the first analytical step for ONT data and is not required for Illumina data, which is delivered as base-called FASTQ files by the instrument software. For this step, we recommend Dorado [<u>https://github.com/nanoporetech/dorado</u>](https://github.com/nanoporetech/dorado) and Guppy as suitable Oxford Nanopore basecalling tools. Dorado is the current default basecaller integrated within MinKNOW and supports both real-time and post-run base calling, while Guppy remains widely used in established workflows and provides additional post-processing functions, including demultiplexing, alignment, and modified base calling.

## 6.2 Raw data quality control 

FASTQ and FAST5 are standard formats used in sequencing workflows. FASTQ is the standard format for sequence reads with associated Phred-scaled base quality scores and is widely used for Illumina data. FAST5 is a hierarchical data format used primarily by Oxford Nanopore Technologies (ONT) to store raw signal data generated during sequencing.

Quality control and read preprocessing are essential first steps for all sequencing datasets, regardless of platform. The purpose is to identify and, where possible, correct issues that would compromise downstream analyses. Datasets should be assessed for total read yield, base quality profiles, adapter contamination, GC content, sequence duplication, and evidence of contamination.

For short-read quality assessment, we recommend FastQC [<u>http://github.com/s-andrews/fastqc</u>](http://github.com/s-andrews/fastqc) and MultiQC [<u>https://github.com/MultiQC/MultiQC</u>](https://github.com/MultiQC/MultiQC) . FastQC provides a rapid sample-level overview of key quality metrics, including per-base sequence quality, per-sequence quality scores, GC content, sequence duplication levels, overrepresented sequences, and adapter contamination. MultiQC then aggregates FastQC reports across multiple samples into a single summary, making it easier to compare run performance, identify outlier samples, and detect batch-wide quality issues before downstream analysis.

For Nanopore datasets, NanoPlot [<u>http://github.com/wdecoster/nanoplot</u>](http://github.com/wdecoster/nanoplot) can be used to assess read length and quality distributions.

## 6.3 Read trimming and filtering: preprocessing of reads

Standard preprocessing usually includes removal of adapter sequences and trimming of low-quality bases from the ends of reads. Depending on the study design and intended downstream analyses, additional filtering may also be applied, such as filtering of reads that fall below minimum length or quality thresholds. The following tools are recommended for read trimming and filtering:

**Fastp** [<u>https://github.com/opengene/fastp</u>](https://github.com/opengene/fastp) is an all-in-one FASTQ pre-processing and quality-control tool that <span class="mark">supports batch processing of multiple FASTQ</span> files for adapter trimming, quality-based filtering, length filtering, sliding-window trimming, and automatic adapter detection. It generates HTML and JSON reports, making it particularly convenient for rapid routine processing.

**Trimmomatic** [<u>https://github.com/usadellab/trimmomatic</u>](https://github.com/usadellab/trimmomatic) is a Java-based tool developed for Illumina sequencing data and is especially useful for both single-end and paired-end datasets. It provides flexible modular steps such as adapter clipping, leading and trailing quality trimming, sliding-window trimming, minimum-length filtering, and average-quality filtering.

**NanoFilt** [<u>https://github.com/wdecoster/nanofilt</u>](https://github.com/wdecoster/nanofilt) is intended for long-read data and can be used to filter reads on the basis of mean quality score, read length, and GC content. <span class="mark">Trimming is done with a user-specified number of nucleotides from either read</span> end.

**Porechop** [<u>https://github.com/rrwick/porechop</u>](https://github.com/rrwick/porechop) designed to identify and remove Nanopore adapter sequences from read ends and can also split reads containing internal adapters, which may indicate chimeric molecules.

<span class="mark">**Dorado** ([<u>https://github.com/nanoporetech/dorado</u>](https://github.com/nanoporetech/dorado)) can also trim adapters and/or primer sequences from the beginning and end of DNA and RNA reads during basecalling</span>.

**BactScout: an integrated** **pipeline** that performs fast post-sequencing checks on bacterial WGS data: short and long read QC (**fastp, nanoq**), taxonomic profiling (**Sylph**) and MLST-based (**stringMLST**) checks to help decide whether samples are ready for assembly or downstream analysis. Full user documentation, configuration reference, and examples are available at [<u>https://ghruproject.github.io/bactscout/</u>](https://ghruproject.github.io/bactscout/).

## 6.4 Species confirmation or taxonomic classification

Confirming the species identity of each isolate before proceeding downstream, pathogen‑specific analyses are essential. Misidentification wastes sequencing and analytical resources on non‑target organisms and can lead to erroneous public health conclusions. The following tools are recommended for the determination of species:

**Speciator** ([<u>https://github.com/pathogenwatch-oss/speciator</u>](https://github.com/pathogenwatch-oss/speciator)) is used to identify species from microbial genome sequences (FASTA/FASTQ) by comparing them to a curated reference library. It is fast and accurate, utilizing a consensus approach with Mash to assign species.

**BactInspector** (and its PyPI package variant, BactInspectorMax): designed to rapidly identify bacterial species from raw sequencing reads or assembled genomes. In addition, we can also use it to select the closest reference genome ([<u>https://gitlab.com/antunderwood/*bactinspector*</u>](https://gitlab.com/antunderwood/bactinspector)).

**FastANI/PyANI** [<u>https://github.com/ParBLiSS/FastANI</u>](https://github.com/ParBLiSS/FastANI) is used to calculate Average Nucleotide Identity (ANI) to determine species-level similarity between query genomes, with a standard cutoff of **≥95–96%** ANI to a RefSeq-type strain. Below 95%: Indicates the query genome may belong to a distinct, novel species.

**Kraken2 ([<u>https://github.com/DerrickWood/kraken2</u>](https://github.com/DerrickWood/kraken2)**) is a taxonomic sequence classifier that assigns taxonomic labels to short DNA reads. Read-level taxonomic screening with Kraken 2 can identify obvious non-target or mixed content (contamination).

**nf-core/bacass:** is an integrated pipeline fo**r** standardized, automated, and scalable analysis, [<u>https://github.com/nf-core/bacass</u>](https://github.com/nf-core/bacass). It is a community-curated pipeline for bacterial assembly and annotation that supports short-read, long-read, and hybrid assemblies. It includes contamination assessment steps (within its bacterial assembly workflow) using **Kraken2** and **KmerFinder** to help verify sample purity.

**PHA4GE QC Tag Integration Point**: If species identification cannot be confidently established, for example, ANI less than 95% to the reference type strain, or ambiguous assignment within the KpSC or ABC complex (If Kraken2 shows many reads split nearly equally across several species within the KpSC or ABC complex, the identity is "ambiguous), apply the PHA4GE QC tag.

Record this using the controlled fields flag:

> quality_control_method_name: Kraken2; FastANI
>
> quality_control_method_version: 2.1.3; 1.34
>
> quality_control_determination: sequence flagged for potential quality control issues \[GENEPIO:0100566\]
>
> quality_control_issues: taxonomic designation inconsistent across methods \[GENEPIO:0101038\]
>
> quality_control_details: Kraken2 reads split ~48%/45% between K. pneumoniae and K. quasipneumoniae; ANI to K. pneumoniae type strain = 93.2%.

For isolates showing \>5% non-target reads by Kraken2 (suspected contamination):

> quality_control_method_name: Kraken2
>
> quality_control_method_version: 2.1.3
>
> quality_control_determination: sequence failed quality control \[GENEPIO:0100564\]
>
> quality_control_issues: sequence contaminated \[GENEPIO:0100569\]
>
> quality_control_details: 12% of reads assigned to Pseudomonas spp. in a submitted Klebsiella pneumoniae isolate.

Use sequence flagged for potential quality control issues \[GENEPIO:0100566\] instead of "failed" if the non-target proportion is borderline or the tool only tells a warning rather than a pass/fail call (Kraken2 itself does not issue pass/fail results - that determination is made by the lab applying the threshold). As always, quality_control_method_name must be populated before any other tag is added. Apply both blocks together (semicolon-separating method names, versions, determinations, and issues) if a single isolate has both an unresolved species call and elevated non-target reads.

## 6.5 Genome assembly

Genome reconstruction can be approached in two complementary ways: *de novo* assembly and reference-based mapping. The choice depends on the intended downstream application. De novo assembly is generally preferred when the objective is to characterize genome content, including plasmids, antimicrobial resistance (AMR) genes, virulence, and mobile genetic elements. For high-resolution SNP analysis for outbreak investigation and transmission analysis, the use of de novo assembly is recommended, as they avoid reference bias and do not require the selection of an appropriate reference genome. De novo assembly is particularly well suited to bacterial species with highly diverse and open pangenomes (to discover entirely new genes that were never seen before). If you only use a reference-based assembly, you might miss unique or novel genes that your specific sample has but the reference doesn't.

*De novo* hybrid assembly is the gold standard for genomic reconstruction because it combines the high accuracy of short reads with the long-range structural information of long reads to resolve complex, repetitive regions. This approach is helpful for plasmid reconstruction, as it allows to bridge repetitive gaps and fully circularize large, multi-drug-resistant plasmids that would otherwise remain fragmented and incomplete using short reads alone.

The following *de novo* assemblers with their key features are the current recommendations for bacterial genome reconstruction, offering specialized options for short-read, long-read, or hybrid assembly approaches.

- **SPAdes** ([<u>https://github.com/ablab/spades</u>](https://github.com/ablab/spades)) is a widely used de Bruijn graph-based assembler optimized for bacterial genomes that supports Illumina, ONT, and hybrid platforms. It supports paired-end, single-end, and mate-pair data, includes an IonTorrent mode, and serves as the core assembly engine of many higher-tier pipelines.

- **SKESA ([<u>https://github.com/ncbi/SKESA</u>](https://github.com/ncbi/SKESA))** is a high-accuracy, high-speed, and low-resource de Bruign graph assembler optimized for Illumina WGS sequences and outbreak investigation. It supports paired-end, single-end, and mate-pair data.

- **Shovill** ([<u>https://github.com/tseemann/shovill</u>](https://github.com/tseemann/shovill)) is a pipeline for the Illumina platform that uses SPAdes at its core but streamlines the pre- and post-assembly steps (adaptor trimming and post-assembly corrections) to produce comparable results in substantially less time. It is designed specifically for bacterial isolate genomes; it also supports alternative assemblers, including SKESA and Megahit.

- **Unicycler** ([<u>https://github.com/rrwick/Unicycler</u>](https://github.com/rrwick/Unicycler)) is a hybrid (Illumina + ONT) assembler that builds an initial assembly graph from short reads using SPAdes and then simplifies the graph using long reads. It produces assemblies that are accurate, complete, and cost-effective, serving as the standard for complete, circularized bacterial genomes and plasmid reconstruction.

- **Flye** ([<u>https://github.com/fenderglass/Flye</u>](https://github.com/fenderglass/Flye)) is a de novo assembler for ONT and PacBio platforms that uses an A Bruijn graph approach for long, noisy reads. It balances accuracy, speed, and assembly integrity across datasets, capable of assembling a 5 Mb bacterial genome with ~80 × coverage in approximately 30 minutes on a modest compute node.

## 6.6 Reference-based mapping and variant calling

Reference mapping is generally preferred when the question concerns high-resolution SNP analysis for outbreak investigation or transmission review. The following bioinformatic tools provide standardized workflows for aligning sequencing reads to a reference genome to identify genetic variations and establish phylogenetic relationships.

- **Snippy**: designed for rapid haploid variant calling and core genome alignment, specialized in finding SNPs and small indels between a reference genome and NGS reads. It uses FreeBayes internally with a simple variant reporting model, and its companion tool, snippy-core, generates core genome SNP alignments from multiple isolates suitable for direct phylogenetic analysis [(<u>https://github.com/tseemann/snippy</u>](https://github.com/tseemann/snippy)).

- **nf-core/bactmap** is a community-validated Nextflow pipeline for mapping short reads from bacterial WGS to a reference sequence, creating filtered VCF files, making pseudogenomes based on high-quality positions in the VCF files, and optionally creating a phylogeny from an alignment of the pseudogenomes ([<u>https://nf-co.re/bactmap</u>](https://nf-co.re/bactmap)). The development version of the pipeline also supports long reads (Oxford Nanopore) ([<u>https://nf-co.re/bactmap/dev</u>](https://nf-co.re/bactmap/dev)).

nf-core/bactmap is a reproducible, Nextflow‑based, containerized multi‑sample pipeline that automates read trimming, mapping, variant calling, pseudogenome construction, optional recombination masking (Gubbins) and phylogeny building for large surveillance or cloud/HPC workflows; Snippy is a fast, single‑sample haploid variant caller and consensus/alignment generator (with snippy-core for core SNP alignments) optimized for quick, ad‑hoc analyses on a single multi‑core workstation. Use **bactmap** when you need standardized, scalable, multi‑sample processing and integrated phylogenetics; use **Snippy** when you want rapid per‑isolate SNP calling, simple consensus/alignment outputs, and lightweight workflows for exploratory or small‑scale projects.

## 6.7 Assembly quality control

Following de novo assembly, contigs must be checked for completeness, contamination, and contiguity before downstream analysis. Key assembly metrics include the N50 (the contig length at which 50% of the total assembly is covered), the total number of contigs, the largest contig, and the total assembly length; reference-based analysis additionally reports genome fraction (the percentage of the reference covered by aligned contigs), the number of misassemblies, and the rate of mismatches and indels per 100 kbp. There are various tools used to assess the quality of the assembly: **QUAST** ([<u>https://github.com/ablab/quast</u>](https://github.com/ablab/quast)) for standard assembly metrics (N50, total length, contig count, GC, and reference‑based misassembly rates), **CheckM2** ([<u>https://github.com/chklovski/CheckM2</u>](https://github.com/chklovski/CheckM2)) for lineage‑aware completeness and contamination estimates, and **BUSCO** ([<u>https://github.com/metashot/busco</u>](https://github.com/metashot/busco)) to assess the presence of universal single‑copy orthologs.

**QualiBact** ([<u>https://qualibact.org</u>](https://qualibact.org)) provides species-specific thresholds for assessing the quality of bacterial genome assemblies using assembled genomes. For complementary checks at the read level (species identification, contamination, coverage), we recommend **bactscout** as a companion tool. The recommended thresholds for each species are shown in Table **6.7**

**Table 6.7: Screening flags based on QualiBact assembly quality thresholds**

| **Pathogen**            | **Genome size (Mbp)** | **Minimum N50 (bp)** | **GC content (%)** | **Max contamination CheckM2 (%)** |
|-------------------------|-----------------------|----------------------|--------------------|-----------------------------------|
| *A. baumannii*          | 3.6 – 4.7             | 24,000               | 38.68 – 39.75      | 7                                 |
| *P. aeruginosa*         | 6.0 – 7.8             | 42,000               | 65.15 – 66.69      | 7                                 |
| *K. pneumoniae*         | 4.9 – 6.4             | 58,000               | 55.49 – 58.64      | 5                                 |
| *E. coli*               | 4.1 – 6.3             | 20,000               | 50.09 – 51.13      | 16                                |
| *S. aureus*             | 2.6 – 3.3             | 28,000               | 32.58 – 33.1       | 4                                 |
| *Enterococcus faecalis* | 2.6 - 3.6             | 51,000               | 36.8 - 37.9        | 3                                 |
| *Enterococcus faecium*  | 2.4 - 3.5             | 18,000               | 37.3-38.6          | 5                                 |

Recommended thresholds for completeness and contamination CheckM2 completeness ≥ 95%, and contamination ≤ 5%. flag assemblies that fail these criteria for low quality or contamination and interpret N50 in the context of genome size. For routine workflows, automate these checks and tag or exclude assemblies that breach thresholds before variant calling, phylogeny, or AMR gene screening to avoid spurious results

**PHA4GE QC Tag Integration Point:** If assembly quality does not meet the recommended minimum thresholds, for example, coverage depth \<30×, or a contig count exceeding 200 for Enterobacterales or 300 for P. aeruginosa, apply:

> quality_control_method_name: QUAST; Samtools depth
>
> quality_control_method_version: 5.2.0; 1.19
>
> quality_control_determination: sequence failed quality control \[GENEPIO:0100564\]
>
> quality_control_issues: low average genome coverage \[GENEPIO:0100570\];
>
> low-quality sequence \[GENEPIO:0100568\]
>
> quality_control_details: 22x mean depth; 287 contigs; high sample multiplexing on sequencing run.

Use minor quality control issues identified \[GENEPIO:0100565\] instead of "failed" if the assembly only modestly falls outside the threshold. This aligns with PHA4GE Worked Example 7, where an assembly with an elevated contig count but 15× coverage was scored as a minor warning rather than a hard failure.

For isolates with \>5% contamination by CheckM2, or genome completeness \<95% when evaluated using CheckM2, apply the following:

> quality_control_method_name: CheckM2
>
> quality_control_method_version: 1.0.2
>
> quality_control_determination: sequence failed quality control \[GENEPIO:0100564\]
>
> quality_control_issues: sequence contaminated \[GENEPIO:0100569\]
>
> quality_control_details: CheckM2 completeness 91.4%, contamination 6.2%.

## 6.8 Detection of key features

### 6.8.1 AMR gene and mutation detection

Antimicrobial resistance (AMR) arises through two main mechanisms: (i) **intrinsic resistance** (naturally present within a bacterial species) and (ii) **acquired resistance**, which develops through genetic mutation or horizontal gene transfer. AMR determinants are genes or genetic modifications that confer resistance to one or more antibiotics or antibiotic classes. <span class="mark">AMR genes encode proteins that modify the antibiotic (e.g., β-lactamases), modify and protect the antibiotic target site (e.g., ribosomal RNA methyltransferases), provide an additional target for which the antibiotic has reduced affinity (e.g., altered penicillin-binding proteins), provide alternative metabolic pathways bypassing the antibiotic’s action (e.g., dihydrofolate reductases), or extrude the antibiotic outside the cell (e.g., efflux pumps)</span> (Darby et al., 2024). Acquired AMR determinants are frequently disseminated through horizontal gene transfer mediated by mobile genetic elements, including insertion sequences, transposons, plasmids, and integrative conjugative elements (Partridge et al., 2018).

AMR determinants are detected using AMR detection tools and curated repositories that contain reference nucleotide and protein sequences associated with antimicrobial resistance, together with the information required for their identification and interpretation. In addition to known resistance genes, these databases may include wild-type genes that confer resistance when modified. Databases may also incorporate classification hierarchies, detection rules, and computational models that support resistance prediction. Existing AMR databases vary in scope, content, curation methods, and annotation standards. They can be divided into species-specific databases, w<span class="mark">hile others focus on ARGs from all sources</span> (Table 6.8).

Bioinformatic tools use these databases to identify AMR determinants within pathogen genome sequences by comparing query sequences against curated reference datasets. Detected determinants are reported with additional information such as the associated antibiotic or antibiotic class, genomic location, and sequence similarity to the reference sequence. AMR detection tools employ a range of computational approaches and differ in their analytical methods, reporting formats, and output content. Many tools are available as command-line applications that can be integrated into bioinformatic workflows, while others provide web-based interfaces that offer greater accessibility for users with limited bioinformatics expertise (see Supplementary table 1 on commonly used tools for ARG detection).

Table 6.8: Commonly used ARG databases

| Database                                | Developer                                                               | Content type                                                                                                               | Content class                                                          | Curation strategy                                                                                                                                                                                 | Species-specific curation                                    | Phenotype prediction                            | URL                                                                                                                                                                       |
|-----------------------------------------|-------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------|-------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| CARD                                    | McMaster University                                                     | Proteins, genes, point mutations, ontologies for antibiotic resistance, and detection models                               | Antibiotics                                                            | Manual and computer-assisted curation of literature, QC checks, community curation                                                                                                                | Yes for mutations in some species                            | No                                              | [<span class="mark"><u>https://card.mcmaster.ca/download</u></span>](https://card.mcmaster.ca/download)                                                                   |
| <span class="mark">AMRFinderPlus</span> | <span class="mark">National Center for Biotechnology Information</span> | <span class="mark">Proteins, genes and point mutations, reference gene hierarchy and reference hidden Markov models</span> | <span class="mark">Antibiotics, stress (heat, metal), virulence</span> | Manual <span class="mark">curation of literature searches, communication with experts, Lahey and Pasteur β-lactamase databases and CARD and ResFinder and PointFinder, automated QC checks</span> | <span class="mark">Yes, for mutations in some species</span> | No                                              | [<span class="mark"><u>https://github.com/ncbi/amr/wiki/AMRFinderPlus-database</u></span>](https://github.com/ncbi/amr/wiki/AMRFinderPlus-database)                       |
| <span class="mark">ResFinder</span>     | <span class="mark">Technical University of Denmark</span>               | <span class="mark">Genes, descriptive genotype to phenotype and species-specific bacterial resistance data</span>          | <span class="mark">Antibiotics</span>                                  | <span class="mark">Manual curation of literature, CARD, ARDB, BLDB and community curation.</span>                                                                                                 | <span class="mark">Yes, for some species</span>              | <span class="mark">Yes, for some species</span> | [<span class="mark"><u>https://bitbucket.org/genomicepidemiology/resfinder_db/src/master/</u></span>](https://bitbucket.org/genomicepidemiology/resfinder_db/src/master/) |
| <span class="mark">Kleborate</span>     | The London School of Hygiene & Tropical Medicine and Monash University  | <span class="mark">Genes, point mutations, gene truncations and intrinsic β-lactamases</span>                              | <span class="mark">Antibiotics</span>                                  | <span class="mark">Manual curation of CARD v3.2.9 and ARG-ANNOT databases and AMRFinder databases</span>                                                                                          | <span class="mark">Yes</span>                                | <span class="mark">Yes, for some species</span> | [<span class="mark"><u>https://github.com/klebgenomics/Kleborate</u></span>](https://github.com/klebgenomics/Kleborate)                                                   |
| <span class="mark">Pathogenwatch</span> | <span class="mark">University of Oxford</span>                          | <span class="mark">Genes and point mutations, interactions</span>                                                          | <span class="mark">Antibiotics</span>                                  | <span class="mark">Manual curation of literature searches, personal communications, and CARD, ResFinder, AMRfinderplus and Kleborate databases</span>                                             | <span class="mark">Yes</span>                                | <span class="mark">Yes</span>                   | [<span class="mark"><u>https://pathogen.watch</u></span>](https://pathogen.watch/)                                                                                        |

Note that for AMRFinderPlus to identify mutational resistance (point mutations), the specific --organism option should be used. The organism option is only used where there is organism-specific curation for the priority sepsis pathogens. See the [<u>AMRFinderPlus documentation</u>](https://github.com/ncbi/amr/wiki/Running-AMRFinderPlus#--organism-option) for details.

| **Organism**            | **Acquired Resistance** | **Mutational Resistance** | **Virulence Genes** | **Stress Response Genes** |
|-------------------------|-------------------------|---------------------------|---------------------|---------------------------|
| Acinetobacter baumannii | X                       | X                         |                     | X                         |
| Enterococcus faecalis   | X                       | X                         |                     | X                         |
| Enterococcus faecium    | X                       | X                         |                     | X                         |
| Escherichia coli        | X                       | X                         | X                   | X                         |
| Klebsiella pneumoniae   | X                       | X                         | X                   |                           |
| Pseudomonas aeruginosa  | X                       | X                         |                     | X                         |
| Staphylococcus aureus   | X                       | X                         | X                   | X                         |

Note: An 'X' indicates curated, high-quality database coverage for that specific feature. Mutational resistance tracking strictly requires you to use the --organism flag during your run.

###  6.8.2 Virulence factor profiling

Virulence factors are molecules, or toxins, produced by pathogens that enable them to colonize a host, evade immune responses, and cause disease. Characterization of virulence determinants can provide insights into pathogenesis, disease severity, and host adaptation. However, the detection of a virulence-associated gene should not automatically be equated with phenotypic expression or clinical severity.

**The Virulence Factor Database (VFDB)** [<u>https://www.mgc.ac.cn/VFs/</u>](https://www.mgc.ac.cn/VFs/), [<span class="mark"><u>www.genomicepidemiology.org</u></span>](https://www.genomicepidemiology.org/) is one of the most widely used resources and contain curated information on experimentally validated virulence factors from bacterial pathogens. VFDB provides detailed annotations of virulence genes, their biological functions, associated pathogenic mechanisms, and reference nucleotide and protein sequences that can be used for sequence-based searches.

Bioinformatic tools identify virulence factors by comparing pathogen genome sequences against curated reference databases:

**ABRicate** [<u>https://github.com/tseemann/abricate</u>](https://github.com/tseemann/abricate) screens for virulence-associated genes using assembled genome contigs against VFDB database and generates tabulated reports containing detected genes, sequence identity, and coverage statistics.

Species-specific tools also provide additional virulence characterization. For example, Kleborate is designed for genomic analysis of *Klebsiella* and *Escherichia* species [<u>https://github.com/klebgenomics/Kleborate</u>](https://github.com/klebgenomics/Kleborate). Kleborate reports clinically relevant virulence loci, including siderophores such as yersiniabactin, aerobactin, salmochelin, and the genotoxin colibactin. Kleborate also identifies hypervirulence-associated determinants and provides a virulence score that facilitates interpretation of the clinical significance of detected virulence factors. See the pathogen-specific section for more details on Kleborate.

For *Escherichia* species, Kleborate performs pathotyping based on <span class="mark">the presence or absence of virulence marker genes using a curated</span> database, <span class="mark">VirulenceFinder DB [<u>https://cge.food.dtu.dk/services/VirulenceFinder/</u>](https://cge.food.dtu.dk/services/VirulenceFinder/). The</span> input <span class="mark">assemblies are aligned to the database using Minimap2. Additionally, Kleborate reports other</span> virulence-associated genes available in VFDB.

For pathogen-specific virulence profiling tools, such as Kleborate for *K. pneumoniae* hypervirulence markers or AgrVATE (https://github.com/VishnuRaghuram94/AgrVATE) for S. aureus agr typing, refer to the relevant pathogen-specific section.

### 6.8.3 Plasmid and mobile genetic element analysis

Mobile genetic elements (MGEs), including plasmids, transposons, and insertion sequences, play a key role in understanding genetic diversity, the spread of AMR genes, etc. Plasmids are key vectors of antimicrobial resistance and virulence genes in sepsis pathogens, and their accurate characterization is essential for understanding the dissemination of resistance and outbreak dynamics. Short-read assemblies often do not resolve gene-to-plasmid localization with sufficient confidence for strong transmission claims. Reconstruction of complete plasmid sequences from short-read data alone is challenging due to repetitive elements; hence, hybrid or long-read sequencing and assemblies substantially improve plasmid resolution.

**Plasmid identification and characterization tools**

To profile the mobile genetic elements of sepsis bacterial pathogens, workflows can implement PlasmidFinder via the command line ([<u>https://github.com/genomicepidemiology/plasmidfinder</u>](https://github.com/genomicepidemiology/plasmidfinder)) or the web-based interface ([<u>https://cge.food.dtu.dk/services/PlasmidFinder/</u>](https://cge.food.dtu.dk/services/PlasmidFinder/)). It identifies plasmid replicons in whole-genome or partial bacterial sequences using a curated database of replicon sequences maintained by the Center for Genomic Epidemiology (CGE). However, PlasmidFinder remains primarily oriented toward Enterobacterales and has limited utility for *A. baumannii* and *P. aeruginosa* (Carattoli et al., 2014). For a broader, cross-species approach, MOB-suite ([<u>https://github.com/phac-nml/mob-suite</u>](https://github.com/phac-nml/mob-suite)) accurately reconstructs plasmids from draft assemblies and classifies them by relaxase type and mobility dynamics into conjugative, mobilizable, or non-mobilizable groups across diverse bacterial species. For pathogen-specific plasmid typing tools, such as AcinetobacterPlasmidTyping for A. baumannii, analysts should refer directly to the relevant pathogen-specific section of this guidance.

### 6.8.4 MLST and Core Genome MLST 

Multilocus Sequence Typing (MLST) is the standard method for assigning bacterial isolates to sequence types (STs) based on seven housekeeping genes. It provides the universal nomenclature necessary for global clone tracking. Core genome MLST (cgMLST) extends this analysis to hundreds or thousands of genes, providing the high resolution required to distinguish closely related outbreak strains from background isolates. The following command-line or web-based tools are recommended for identifying Sequence Types (ST):

**mlst (CLI Tool):** A rapid command-line interface (CLI) tool designed to scan genome assemblies (FASTA) against PubMLST and Pasteur schemas. It is designed to pull schemes from PubMLST and PasteurMLST to run locally, which is much faster than using web interfaces for multiple genomes. It features automatic species detection, allowing users to process mixed batches of sepsis bacterial pathogens without manual schema selection. [Run MLST only on assemblies that pass QC (coverage, contiguity); partial loci or contamination produce ambiguous STs. <u>https://github.com/tseemann/mlst</u>](https://github.com/tseemann/mlst)

**PubMLST & PasteurMLST (Web-based -** [<u>https://pubmlst.org</u>](https://pubmlst.org) \| [<u>https://bigsdb.pasteur.fr/</u>](https://bigsdb.pasteur.fr/))**:** The authoritative global repositories for curated allele sequences and ST profiles. It allows for manual or batch uploads to identify new or existing sequence types, and the submission of novel alleles or STs. While PubMLST hosts the majority of species, the Pasteur Institute remains the primary authority for the *Klebsiella pneumoniae* species complex (KpSC) ([<u>https://bigsdb.pasteur.fr/klebsiella/</u>](https://bigsdb.pasteur.fr/klebsiella/)) and *E. coli* ([<u>https://bigsdb.pasteur.fr/ecoli/</u>](https://bigsdb.pasteur.fr/ecoli/))

**chewBBACA (High-Resolution Typing)**: A comprehensive software suite for the creation and evaluation of core genome and whole genome MultiLocus Sequence Typing (cg/wgMLST) schemas and results. It provides significantly higher resolution than traditional 7-gene MLST by analyzing thousands of loci. It is recommended for outbreak investigations and high-resolution surveillance where 7-gene STs do not provide sufficient discriminatory power. [<u>https://github.com/B-UMMI/chewBBACA</u>](https://github.com/B-UMMI/chewBBACA)

### Integrated Analysis Platforms

- **EnteroBase** (Web): A comprehensive platform for automated MLST, HierCC (cgMLST), and serotype prediction. It maintains a database of over 1.1 million genomes for global population comparisons. [<u>https://enterobase.warwick.ac.uk</u>](https://enterobase.warwick.ac.uk)

- **Pathogenwatch** (Web): A free platform for automated typing and interactive phylogeny. It is specifically designed for outbreak investigation and supports metadata annotation for collaborative data sharing. [<u>https://pathogen.watch</u>](https://pathogen.watch)

## 6.9 Phylogenetic and epidemiological analysis

Phylogenetic analysis integrates genomic variation into an evolutionary framework. This enables researchers to identify transmission clusters, estimate outbreak origins, and determine if epidemiologically linked cases are genetically related.

### 6.9.1 SNP and cgMLST thresholds for outbreak cluster definition

There is no universal, pathogen-agnostic SNP or allele threshold for outbreak cluster definition. Cluster thresholds can be determined by pairing SNP or allelic differences with epidemiological information (patient timelines, ward locations, shared exposures). As noted by a 2024 study from Germany, "there is no universally accepted threshold for these measures to assess the likelihood of transmission," and "thresholds in the literature are frequently determined through retrospective analysis of outbreaks within their epidemiological context," leading to "the adoption of diverse thresholds.” Nevertheless, several widely accepted or published community thresholds have been established for specific pathogens through systematic analysis and may serve as starting points for local validation:

### 6.9.2 Pathogen-specific outbreak thresholds from the literature 

**MRSA, MDR E. coli, and VRE (cgMLST):** A 2024 study presented at the DGHM & VAAM conference determined the following cgMLST thresholds using a novel correlation method that links allelic distances to epidemiological linkage:

- MRSA: ≤4 alleles

- MDR E. coli: ≤3 alleles

- VRE: ≤3 alleles

Critically, the authors note that even with identically typed isolates (0 allele differences), no epidemiological link could be identified in approximately half of the cases, and for VRE, this value was even below 40% . This underscores the essential principle in this guidance that the genomic thresholds must always be combined with epidemiological evidence. [<u>https://programme.conventus.de/en/dghm-vaam-2024/program/program-points/b4ad1a9a-55b1-443c-bb2d-f8d73bd4bdab</u>](https://programme.conventus.de/en/dghm-vaam-2024/program/program-points/b4ad1a9a-55b1-443c-bb2d-f8d73bd4bdab)

### 6.9.3 Recombination filtering

Homologous recombination introduces clustered substitutions that do not reflect vertical inheritance and can mislead tree topology and branch lengths (bias phylogenetic reconstruction). Filtering is strongly recommended before tree construction, especially for species with high recombination rates such as *E. coli, K. pneumoniae, A. baumannii*, and *P. aeruginosa*. Gubbins and ClonalFrameML are considered the gold standard tools for detecting and masking recombination in bacterial phylogenomics.

When accounting for horizontal gene transfer in recombinogenic bacterial pathogens, workflows should incorporate either Gubbins ([<u>https://github.com/nickjcroucher/gubbins</u>](https://github.com/nickjcroucher/gubbins)) or ClonalFrameML ([<u>https://github.com/xavierdidelot/clonalframeml</u>](https://github.com/xavierdidelot/clonalframeml)) to detect and mask recombinant regions prior to final phylogenetic inference. Gubbins utilizes an iterative, heuristic spatial-clustering algorithm that scans the core genome alignment to flag localized windows of high SNP density, making it exceptionally fast and highly scalable for large surveillance datasets or recent outbreak investigations. Conversely, ClonalFrameML applies a parametric maximum likelihood framework driven by a Hidden Markov Model (HMM) to estimate specific evolutionary parameters, such as relative recombination rates and mean tract lengths, requiring a pre-computed starting tree but offering superior sensitivity when detecting short or ancient recombination events across more diverse lineages. Both tools ultimately output a filtered, polymorphism-only alignment with confounding homoplasies masked, ensuring that downstream maximum likelihood tree construction reflects true clonal vertical evolution and yields accurate branch lengths.

### 6.9.4 Variant discovery and core SNP Alignment strategies: Snippy vs. kSNP4

When establishing standardized workflows for variant detection in bacterial genomic surveillance, pipelines can leverage either reference-dependent or reference-independent tools depending on the genomic diversity of the dataset. **Snippy ([<u>https://github.com/tseemann/snippy</u>](https://github.com/tseemann/snippy))** provides a highly accurate, alignment-based approach optimized for closely related clonal lineages; it maps raw sequencing reads or assemblies against a single, close-relative reference genome to identify high-confidence single nucleotide polymorphisms (SNPs) while generating the structured, coordinate-based alignments required by downstream recombination-masking software like Gubbins. Conversely, **kSNP4 ([<u>https://github.com/kissake/kSNP4</u>](https://github.com/kissake/kSNP4))** offers an alignment-free, reference-independent alternative that relies on a split k-mer analysis to identify central base variations flanked by conserved oligo sequences across a dataset. This approach circumvents reference bias and effectively captures variation across the entire pan-genome, including accessory elements like plasmids and genomic islands, making it ideal for rapid, first-pass evaluations of heterogeneous isolate collections where a suitable reference genome is unavailable.

### 6.9.5 When to use which tool: Snippy vs. kSNP4

**Use Snippy if,**

- You are investigating a localized outbreak of a clonal lineage (e.g., E. coli ST131 tracking in a hospital network).

- You have access to an excellent, closed reference genome for that specific lineage.

- You plan to filter your alignment for recombination using Gubbins. (Gubbins requires structural coordinate alignments, which Snippy provides; it cannot process the disjointed SNP lists of kSNP4).

**Use kSNP4 if,**

- You have a diverse, heterogeneous collection of bacterial genomes with no logical, singular reference strain.

- You want to run a rapid first-pass analysis of an uncharacterized multi-species or multi-genus group of isolates directly from mixed assembly fasta files.

- You wish to quickly survey variations across both the core and accessory components (plasmids/phages) of your dataset simultaneously without dealing with the hassle of coordinate liftovers.

**NOTE**: When a dataset spans multiple distinct lineages, sequence types (STs), or highly divergent clades, choosing a single reference genome introduces severe reference bias, and kSNP4 circumvents this by identifying shared k-mers across the entire dataset.

### 6.9.6 Phylogenetic tree construction tools

- **IQ-TREE**: A fast stochastic algorithm for estimating maximum-likelihood phylogenies. It features automated model selection, ultrafast bootstrap approximation, and handles bacterial-sized alignments efficiently. [<u>http://www.iqtree.org</u>](http://www.iqtree.org)

- **Fast Tree** : Infers approximately maximum-likelihood trees. It is exceptionally fast and ideal for initial exploratory analysis or massive datasets exceeding 1,000 genomes. [<u>https://microbesonline.org/fasttree/</u>](https://microbesonline.org/fasttree/)

- **RAxML:** A robust and well-validated tool for maximum-likelihood inference. While computationally intensive for large alignments, it is highly effective for moderate-sized datasets. [<u>https://github.com/stamatak/standard-RAxML</u>](https://github.com/stamatak/standard-RAxML)

- **BEAST2**: A Bayesian framework for time-calibrated phylogenies. It estimates evolutionary rates and divergence dates, allowing for the reconstruction of transmission histories with temporal precision. [<u>https://www.beast2.org</u>](https://www.beast2.org)

**Note on BEAST2:** Due to the heavy computational burden of Markov Chain Monte Carlo (MCMC) sampling, it is best practice to use a "downsampled" representative dataset.

**Tree Visualization**

- **Microreact** (Web): A free web application that links phylogenetic trees to geographic maps, timelines, and metadata. It is designed for collaborative exploration of genomic epidemiology data. [<u>https://microreact.org</u>](https://microreact.org)

- **iTOL** (Interactive Tree of Life) (Web): A tool for annotating large trees with diverse data types. It is highly scriptable and the standard for producing publication-quality phylogenies. [<u>https://itol.embl.de</u>](https://itol.embl.de)

## 6.10 All-in-One Pipelines and Web-Based Analysis Platforms

For laboratories that prefer to avoid the manual orchestration of individual tools or that require standardized, automated workflows for high-throughput surveillance, several all-in-one pipelines and web-based platforms provide end-to-end solutions, from raw reads to interpreted reports, suitable for sepsis pathogen genomics. Please see Supplementary Table 3 and Supplementary Table 4 on available pipelines for pathogen analysis.

# 7. Data Management, Reproducibility & Infrastructure

The public health impact of sepsis pathogen genomics depends on a seamless pipeline from data generation to actionable insight. This pipeline rests on two interdependent pillars: the ability to share and reuse data through robust repositories and the ability to reproduce and validate analyses through standardized workflows and computational infrastructure. Without shared data, transmission chains remain hidden. Without reproducible workflows, analytical results cannot be trusted or compared. This section provides integrated guidance on data submission, repository ecosystems, workflow management, and the computational environments necessary to make sepsis bacterial genomic research and surveillance FAIR (Findable, Accessible, Interoperable, Re-usable) and scientifically rigorous.

## 7.1 Data storage, sharing, and repositories

The public health impact of sepsis and other pathogen genomics depends absolutely on the ability to share, discover, and reuse sequence data and their associated contextual metadata. Isolated genomic data locked within a single institution cannot reveal transmission chains that cross hospital boundaries, cannot identify international high-risk clones, and cannot contribute to the global antimicrobial resistance (AMR) surveillance that is essential for evidence-based treatment guidelines. This section provides practical guidance on repositories, submission workflows, and governance to make sepsis bacterial genomic data FAIR (Findable, Accessible, Interoperable, Re-usable) while aligning with the PHA4GE Microbial Data-Sharing Accord and related standards.

### The Global Repository Ecosystem and Platforms

Pathogen genomic data storage comprises two complementary layers:

1.  The International Nucleotide Sequence Database Collaboration (INSDC) for long-term archival.

2.  Specialized public health platforms offering automated analysis, clustering, visualization, and controlled access data sharing tailored to public health needs.

### 7.1.1 The INSDC: Global Archival Infrastructure

The INSDC, a collaboration between NCBI (USA), ENA (Europe), and DDBJ (Japan), serves as the primary global archive for nucleotide sequences. Submissions to any member are synchronized daily across all three, ensuring worldwide accessibility and preservation. In March 2026, the INSDC introduced Minimal Specifications for Submitting Nucleotide Sequence Data, establishing unified requirements for metadata structure, sample attributes, sequencing details, and data connectivity.

**Primary Submission Portals for Sepsis Pathogens:**

<table>
<colgroup>
<col style="width: 31%" />
<col style="width: 17%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Repository</strong></th>
<th><strong>Data Type</strong></th>
<th><strong>Recommended Use for Sepsis Pathogens</strong></th>
</tr>
<tr class="odd">
<th>NCBI SRA (<a href="https://submit.ncbi.nlm.nih.gov/subs/sra/"><u>submit.ncbi.nlm.nih.gov/subs/sra</u></a>)</th>
<th>Raw reads (FASTQ)</th>
<th>Deposit Illumina/Oxford Nanopore reads; link to BioProject/BioSample.</th>
</tr>
<tr class="header">
<th>NCBI GenBank <a href="https://submit.ncbi.nlm.nih.gov/subs/genome/"><u>submit.ncbi.nlm.nih.gov/subs/genome</u></a></th>
<th>Assembled/annotated genomes</th>
<th>High-quality assemblies with annotation.</th>
</tr>
<tr class="odd">
<th><p>ENA Webin-CLI</p>
<p><a href="https://ena-docs.readthedocs.io/en/latest/submit/general-guide.html"><u>https://ena-docs.readthedocs.io/en/latest/submit/general-guide.html</u></a></p></th>
<th>Raw reads + assemblies</th>
<th>Programmatic submissions; supports pathogen checklists.</th>
</tr>
<tr class="header">
<th>DDBJ DRA <a href="https://www.ddbj.nig.ac.jp/dra/index-e.html"><u>ddb.j.nig.ac.jp/dra</u></a></th>
<th>Raw reads</th>
<th>Submissions to the Japanese INSDC node.</th>
</tr>
</thead>
<tbody>
</tbody>
</table>

**Key Practices:**

- Use stable accessions: BioProject (PRJNAxxxxxx), BioSample (SAMNxxxxxx), and SRA (SRRxxxxxx) accessions are required by most journals

- Apply embargoes: To protect data generators' right to first analysis, set a release date (typically up to 1 year) during submission. The data will remain private until that date.

- Submit raw reads: Even when assemblies are submitted, depositing raw reads is strongly encouraged to enable independent quality assessment, contamination screening, and reanalysis with future tools.

### 7.1.2 Specialized Public Health Platforms

Specialized public health platforms complement the INSDC archival infrastructure by providing rapid, interactive, and integrated tools tailored for genomic epidemiology. These platforms offer automated genotyping, cluster detection, phylogenetic analysis, and visualization features that support real-time surveillance and outbreak investigation of sepsis pathogens. The following platforms are recommended based on their usability, analytical capabilities, and relevance to key sepsis-causing bacteria. They enable laboratories to move beyond data storage toward actionable public health insights while maintaining compatibility with FAIR principles and standards.

**Pathogenwatch ([<u>https://pathogen.watch/en</u>](https://pathogen.watch/en)):** stands out as an ideal entry point for most laboratories conducting sepsis genomic surveillance. This free, web-based platform developed by the Centre for Genomic Pathogen Surveillance requires no command-line expertise. Users simply upload genome assemblies in FASTA and Fastq format along with a metadata CSV file. The system then automatically performs species identification, MLST, cgMLST, AMR, and virulence gene detection and generates interactive phylogenetic trees with metadata overlays. It also supports the creation of isolate collections for focused outbreak investigations, making it particularly effective for *K. pneumoniae, E. coli, A. baumannii, S. aureus, Pseudomonas spp., and Enterococcus spp.*

**EnteroBase ([<u>https://enterobase.warwick.ac.uk/</u>](https://enterobase.warwick.ac.uk/))** is a web-based free pipeline for exploring the genomic epidemiology of pathogens. It assembles, analyses, and interprets bacterial genomes to provide insights for researchers, epidemiologists, and healthcare professionals. It excels in providing deep contextual analysis for enteric sepsis pathogens (it supports *E. coli* and *Enterococcus*). With over 1.7 million genomes, it enables users to place local isolates within a broad global population structure. The platform automatically assigns species, sequence types, serotypes, and HierCC cgMLST clusters while performing AMR profiling. This makes EnteroBase especially valuable for determining whether emerging resistant clones in sepsis cases are locally evolving or represent international introductions.

**NCBI Pathogen Detection** offers powerful automated surveillance with minimal additional effort from submitters. Integrated directly with INSDC submissions, it performs real-time SNP-based clustering across all publicly available genomes for major sepsis pathogens, including *E. coli, K. pneumoniae, A. baumannii, S. aureus,* and *Enterococcus*. The platform includes an Antimicrobial Susceptibility Testing (AST) Browser and supports outbreak detection. Submission of raw sequence reads alongside assemblies is strongly encouraged to improve clustering accuracy and quality assessment.

## 7.2 Workflow Reproducibility & Infrastructure

The public health impact of pathogen genomics depends not only on the quality of the sequence data and the accuracy of the analytical tools but also on the ability to reproduce an analysis and to obtain the same result from the same input data using the same computational methods, regardless of who performs the analysis or where it is executed. Reproducibility is a cornerstone of the scientific method and a practical necessity for public health, where decisions about outbreak containment, antimicrobial stewardship, diagnostics, and vaccine policy must be grounded in transparent, verifiable evidence. This section provides guidance on the workflow management systems, software containerization strategies, version control practices, and computing infrastructure options that make bioinformatics analyses for sepsis bacterial pathogens robust, portable, and reproducible.

### 7.2.1 The PHA4GE Ten Best Practices for Public Health Bioinformatics Pipelines

The Bioinformatics Pipelines and Visualization Working Group of PHA4GE has developed a set of ten best practices, tailored specifically for public health bioinformatics pipelines, to provide a guidance framework for the development, testing, and maintenance of robust, sustainable software. These best practices were motivated by the recognition that the absence of domain specific guidelines has limited progress towards accessible, reproducible, interoperable, and standardized bioinformatics analysis in public health pathogen genomics. By adhering closely to these best practices, developers can enhance the quality, reliability, and sustainability of their software, facilitating impact throughout the public health community.

The full best practices document is maintained as a living resource at [<u>https://github.com/pha4ge/public-health-pipeline-best-practices</u>](https://github.com/pha4ge/public-health-pipeline-best-practices) and is summarized in Table 7.2. Users of this sepsis guidance are not expected to master every practice; rather, the table serves as a reference framework for evaluating and selecting tools, and for understanding what constitutes a well-engineered pipeline. The practices most directly relevant to the day to day work of sepsis genomic surveillance are expanded in the sections that follow.

Table 7.2: The PHA4GE Ten Best Practices for Public Health Bioinformatics Pipelines

| **N<u>o</u>** | **Best Practice**                          | **What It Means for Sepsis Genomics Users**                                                                                                                                                                          |
|---------------|--------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **1**         | **Publicly‑Accessible Repository**         | The source code for the pipeline should be hosted on an open platform (e.g., GitHub, GitLab). This enables any public health laboratory to inspect, download, and use the software.                                  |
| **2**         | **Open‑Source License**                    | The repository must include a plain‑text LICENSE file with an OSI‑approved license (e.g., MIT, GPL). Without a license, others cannot legally use, modify, or distribute the code.                                   |
| **3**         | **Semantic Versioning of Stable Releases** | Pipelines should follow MAJOR.MINOR. PATCH versioning and maintain a changelog. Laboratories can then reference the exact version used in an analysis, ensuring auditability and enabling comparison across runs.    |
| **4**         | **Workflow Management System**             | Pipelines should use a workflow manager (Nextflow, Snakemake, WDL, CWL). This automates complex multi‑step analyses, enhances scalability, and ensures consistent execution across different computing environments. |
| **5**         | **Containerized/Packaged Software**        | All software dependencies should be encapsulated in containers (Docker, Singularity/Apptainer) or managed through package managers (Conda). This eliminates the “works on my machine” problem.                       |
| **6**         | **Common File Formats**                    | Pipelines should accept and generate standard bioinformatics file formats (FASTQ, FASTA, VCF, BAM, GFF, JSON, CSV). This ensures interoperability with other tools and repositories.                                 |
| **7**         | **Software Testing**                       | Automated and/or manual tests (smoke tests, unit tests, end‑to‑end tests) should be documented and run regularly to verify pipeline functionality.                                                                   |
| **8**         | **Benchmark/Validation Datasets**          | A publicly available set of input data with known outputs should be provided. Users can run this dataset to confirm correct installation and compare performance against other tools.                                |
| **9**         | **Reference Data Requirements**            | Any external reference databases or data dependencies must be clearly documented, versioned, publicly accessible, and maintained.                                                                                    |
| **10**        | **Pipeline Documentation**                 | Documentation should be clearly written, publicly accessible, and include installation instructions, usage examples, authorship attribution, and a verified point of contact.                                        |

These ten best practices provide the quality benchmark against which the tools recommended throughout this guidance document should be assessed. For laboratories that develop their own custom pipelines, these best practices are a design checklist; for laboratories that adopt existing pipelines, they are an evaluation rubric. The full best practices document, including detailed criteria for adherence and verification, is available at: [<u>https://github.com/pha4ge/public-health-pipeline-best-practices/blob/main/docs/pipeline-best-practices.md</u>](https://github.com/pha4ge/public-health-pipeline-best-practices/blob/main/docs/pipeline-best-practices.md)

### 7.2.2 Workflow Management Systems

A workflow management system (WMS) is a software framework that orchestrates the execution of a series of computational tasks, quality control, assembly, gene detection, and phylogenetic reconstruction in a defined, automated, and reproducible order. In the absence of a WMS, we must run each tool manually, transfer intermediate files by hand, and document every parameter and version after the analysis, a process that is error-prone, difficult to replicate, and nearly impossible to scale across dozens or hundreds of isolates. A WMS replaces this ad hoc approach with a scripted, version-controlled workflow that can be executed with a single command on a laptop, a high-performance computing (HPC) cluster, or a cloud platform, producing identical outputs each time. The following WMS platforms have achieved broad adoption in public health pathogen genomics. Their key characteristics are summarized in Table 7.2.2.

Table 7.2.2: Workflow management systems for sepsis pathogen genomics

| **System**                              | **Language**                              | **Key Strengths**                                                                                                                                                                                                                             | **Notable Sepsis‑Relevant Pipelines**                                                                                                                 |
|-----------------------------------------|-------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Nextflow**                            | Domain‑specific language (Groovy‑based)   | Exceptional scalability from laptop to cloud; native integration with Docker, Singularity, and Conda; large and active community; the nf‑core project provides curated, standardised pipelines with automated testing on full‑sized datasets. | nf‑core/bacass (assembly), nf‑core/bactmap (SNP phylogeny), nf‑core/funcscan (AMR gene screening), Bactopia (all‑in‑one), Enteroflow (*Enterococcus*) |
| **Snakemake**                           | Python‑based                              | Familiar syntax for Python users; seamless scalability from single servers to HPC clusters and cloud environments; integrates with Conda and Singularity for dependency management; flexible and readable workflow definitions.               | Pathogenseq (WGS analysis), ChewBBACA (cgMLST), assorted custom public health pipelines                                                               |
| **WDL (Workflow Description Language)** | Human‑ and machine‑readable specification | Developed by the Broad Institute; native integration with the Terra.bio cloud platform; strong support for complex task dependencies; adopted by Theiagen Genomics for public health workflows.                                               | TheiaProk (all‑in‑one bacterial characterization, deployed on Terra), Public Health Bioinformatics (PHB) workflows                                    |
| **Galaxy**                              | Open-source Web-based WMS                 | It allows researchers to design, execute, and visualize complex genomic analyses entirely through a graphical web interface without requiring command-line programming.                                                                       |                                                                                                                                                       |

Among these, **Nextflow** and its associated **nf-core** ecosystem deserve particular emphasis for sepsis pathogen genomics. **nf-core** is a community effort that produces a curated set of standardized, best practice, reproducible, documented analysis pipelines; they are released under the MIT license. Each nf-core pipeline uses Docker or Singularity containers, one container per process, making maintenance straightforward and results highly reproducible. Every time a pipeline is released, it is automatically run on AWS with a real dataset. This makes sure the default resource settings (like CPU and memory) are appropriate, and it provides consistent benchmarks so performance can be compared between versions. nf-core pipelines of direct relevance to sepsis bacterial pathogens include:

- **nf core/bacass: Simple** bacterial assembly and annotation from short reads, long reads, or hybrid data;that includes Kraken2 and KmerFinder contamination screening.

- **nf core/bactmap: Mapping** based SNP calling and phylogeny construction from bacterial WGS data; incorporates recombination removal (Gubbins) and pseudogenome generation.

- **nf core/funcscan**: Screening of assembled contigs for antimicrobial resistance genes, virulence factors, and biosynthetic gene clusters.

For laboratories that prefer a Python-based framework, **Snakemake** WMS offers equivalent functionality with a syntax that may be more accessible to teams with existing Python expertise. Snakemake workflows are defined in a human-readable Python-based language, scale across cluster and cloud environments, and support Conda and Singularity for dependency management.

For laboratories working within the Terra.bio ecosystem, WDL workflows such as TheiaProk provide an all-in-one bacterial characterization solution that integrates directly with Terra's cloud-native infrastructure. Theiagen's Public Health Bioinformatics (PHB) repository contains WDL workflows for genomic characterization, submission preparation, and genomic epidemiology of pathogens of public health concern, and these have been adopted by several state and national public health laboratories.

### 7.2.3 Containerization and Software Packaging

The single greatest threat to reproducibility in bioinformatics is software dependency conflict: Tool A requires Python 3.7 and a specific version of NumPy, while Tool B requires Python 3.10 and a conflicting version. Installing both on the same system can produce unpredictable failures that are invisible to the user until results are nonsensical. Containerization solves this problem by encapsulating each tool, or each step of a pipeline, within an isolated, lightweight environment that contains the exact software versions, libraries, and configurations on which the tool was validated.

The two principal container technologies in public health bioinformatics are the following:

**Docker**: The most widely adopted containerization platform. Docker images are defined by a Dockerfile, built into portable images, and stored in registries such as Docker Hub (https://hub.docker.com) or Quay.io (https://quay.io). Docker is the standard for local development and for cloud deployment.

**Singularity/Apptainer**: Functionally equivalent to Docker but designed specifically for HPC environments where Docker's daemon-based architecture presents security and permission challenges. Singularity (now maintained under the Apptainer project, https://apptainer.org) can import and run Docker images directly, making it the preferred container runtime for institutional HPC clusters. Apptainer is supported by the Linux Foundation and is compatible with Docker images, enabling laboratories to build once and run on either platform.

For laboratories that cannot deploy containers, **Conda** and **Bioconda** provide an alternative software packaging ecosystem that manages dependencies at the environment level. Bioconda ([<u>https://bioconda.github.io</u>](https://bioconda.github.io)) distributes over 10,000 bioinformatics packages, and Conda environments can be exported as environment files (.yml) that precisely capture the software versions used.

### 7.2.4 Version Control and Documentation

Reproducibility requires that every analysis be traceable to the exact version of every piece of software and every reference database that was used. Version control systems can help provide this traceability. **What must be version controlled?**

**Pipeline code:** The workflow definition itself (whether a Nextflow script, a Snakemake file, or a series of shell commands) must be stored in a version-controlled repository (GitHub, GitLab, or Bitbucket). Every change should be committed with a descriptive message.

**Software versions**: The specific versions of all tools used (e.g., assemblers, AMR detectors, MLST callers, phylogenetic software) must be recorded. Container tags (e.g., bactopia:3.1.0) or Conda environment files provide this information automatically when used.

**Reference databases:** The exact versions of curated databases (ResFinder, CARD, PubMLST, VFDB, PlasmidFinder) must be documented with their accession date or release number. A result such as “*bla*NDM-1 detected” is meaningful only if the database version used for detection is known; a gene absent from an older database may be present in the isolate but unreported.

**Custom scripts and parameters**: Any custom code written for a specific analysis must be committed to the repository alongside the pipeline, with all non-default parameters documented.

**Semantic versioning and changelogs**

PHA4GE Best Practice recommends that pipelines follow semantic versioning (MAJOR.MINOR.PATCH) and maintain a detailed changelog. A MAJOR version increment signals incompatible changes (e.g., a fundamental change to the algorithm); a MINOR version increment signals new, backward-compatible functionality; and a PATCH version increment signals backward-compatible bug fixes. This system enables a laboratory to state, “This analysis was performed with Kleborate v4.0.0,” and for any other laboratory to retrieve exactly the same version and reproduce the results.

**Repositories and tagged releases**

GitHub (https://github.com) is currently the dominant platform for public health bioinformatics code. Public repositories enable community scrutiny, facilitate collaboration, and support the PHA4GE principle of transparency. When a pipeline reaches a stable state suitable for production use, a tagged release should be created (e.g., v1.0.0). Tagged releases are immutable reference points that can be cited in publications and referenced in standard operating procedures.

### 7.2.5 Computing Infrastructure Options

Sepsis genomics programs may operate across a wide spectrum of computing environments, from a single laptop in a district hospital laboratory to a dedicated High-Performance Computing (HPC) cluster or server at a national reference center. Robust bioinformatics analysis is highly feasible at every level of infrastructure, provided that software configurations and workflow choices are appropriately aligned with local computational capacity. A comprehensive breakdown of the hardware specifications, optimal use cases, and suitable tool suites for each deployment tier is detailed in Supplementary Table 5 for extended technical reference.

# 8. Pathogen-specific guidance

## *8.1 Klebsiella pneumoniae* <span class="mark">and the *Klebsiella pneumoniae* species complex (KpSC)</span>

*Klebsiella pneumoniae* is a commensal bacterium and a major cause of opportunistic infections, particularly in <span class="mark">healthcare settings</span>. In hospitals, <span class="mark">it causes different types of infection, including bloodstream infections, lower respiratory tract infections, wound infections and urinary tract infections</span>.The burden of the disease is greatest among neonates<span class="mark">, contributing to ~24.9% of neonatal sepsis deaths globally (Sands et al., 2021)</span>. <span class="mark">Outside healthcare settings, *K. pneumoniae* is also recognized as a causative agent of community-acquired infections</span> associated with hypervirulent *K. pneumoniae* (hvKp) and include conditions such as hepatic abscess, meningitis, endophthalmitis or other symptoms that can metastatically spread to multiple sites of the body.

Treatment of *K. pneumoniae* infections is complicated by escalating antimicrobial resistance (AMR). According to WHO Global Antimicrobial Resistance and Use Surveillance System (GLASS), more than 55% of *K. pneumoniae* clinical isolates worldwide are now resistant to third-generation cephalosporins (3GCs) (WHO, 2025). In Africa, this rate exceeds 70%, highlighting the disproportionate burden of AMR in the continent, <span class="mark">and further</span> limiting effective treatment options. Additionally, the <span class="mark">World Health Organization listed carbapenem-resistant *K. pneumoniae* (CRKP) as a critical priority pathogen requiring the development of new antimicrobial agents and therapeutic strategies (WHO, 2024)</span>

*Klebsiella pneumonia* has six close species and subspecies (e.g. *Klebsiella quasivariicola, Klebsiella quasipneumoniae subsp. similipneumoniae, Klebsiella quasipneumoniae subsp. quasipneumoniae, Klebsiella africana, Klebsiella variicola subsp. tropica, Klebsiella variicola subsp. variicola*) , referred to as the *K. pneumoniae* species complex (KpSC). These closely related species <span class="mark">share 95–96% average nucleotide identity with *K. pneumoniae* (Holt et al., 2015; Long et al., 2017),</span> and are often difficult to distinguish using conventional biotyping or MALDI-TOF. As a result, they are frequently misidentified as *K. pneumoniae*. Where accurate species-level identification is required, sequence-based methods provide a more reliable taxonomic assignment within the members of KpSC.

### Key genomic features for typing *K. pneumoniae*

This section provides an overview of the key genomic features used for the characterization and typing of *K. pneumoniae*, with an emphasis on genetic determinants relevant to pathogenicity and invasive infection.

## 8.1.1 Pathogenicity factors

*Klebsiella pneumoniae* <span class="mark">harbours a subset of core chromosomally encoded pathogenicity factors that are associated with opportunistic infections in mammalian hosts. These include the core locus *ent* encoding biosynthesis of the siderophore enterobactin (Ent), the core *fim* and *mrk* loci encoding type 1 and type 3 fimbriae, respectively, as well as two key surface antigen sugars, capsular polysaccharide (K) and lipopolysaccharide (LPS) (Wyres et al 2016; Holt et al., 2015).</span>

### 8.1.1.1 K antigen and locus

The capsular polysaccharide (CPS), or K-antigen, is an extracellular layer of polysaccharide chains, anchored to the outer membrane. <span class="mark">The K locus is</span> synthesised and exported by the Wzy pathway (<span class="mark">Whitfield et al., 2006)</span>. Each KpSC genome contains a single K-locus between 10 and 30 Kbp in length with a set of conserved genes located at the ends of the locus and encoding the capsular export machinery (*galF, cpsACP, wzi, wza, wzb, wzc, ugd*). The centre of the locus contains highly variable genes required for the capsule-specific sugar synthesis and assembly. To date, \>160 distinct K loci that have been identified, however, only 77 capsule types have been defined serologically

### 8.1.1.2 O antigen and locus

The outer lipopolysaccharide (LPS), or O-antigen, locus is located next to the K-locus. It <span class="mark">comprises of a ~7–13 kbp region of the chromosome and</span> each KpSC genome contains a single O-locus (<span class="mark">Follador et al., 2016)</span>. Unlike the K antigen and locus, there is no one-to-one relationship between the O loci and O antigen types. Instead, the O1 and O2 antigens and the associated O2 sub-types are determined by the combination of the O locus variant (one of three possible variants labelled O1/O2v1, O1/O2v2 and O1/O2v3) and genes located elsewhere in the KpSC genome. \> 20 combinations have been identified.

KpSC surface antigen and locus can be typed using Kaptive[<u>https://github.com/klebgenomics/Kaptive,</u>](https://github.com/klebgenomics/Kaptive) which is available as a standalone software tool and is implemented by both Kleborate [<u>https://github.com/klebgenomics/Kleborate</u>](https://github.com/klebgenomics/Kleborate) and PathogenWatch.

## 8.1.2 Virulence factors

<span class="mark">*K. pneumonia* strains carry key virulence factors that are associated with invasive infections and are found at high prevalence among hypervirulent *K. pneumoniae* strains. These include acquired siderophores yersiniabactin (*ybt*), aerobactin (*iuc*) and salmochelin (*iro*), the genotoxin colibactin (*clb*), and the hypermucoidy locus *rmpADC*. The virulence loci sequence typing databases are available through BIGSdb databases and are integrated into the Kleborate genotyping tool.</span>

The biosynthesis of yersiniabactin (*Ybt*) is encoded by the *ybt* locus, which is located on a chromosomal integrative and conjugative element (ICE) known as ICEKp. The *ybt* locus is present in approximately 40% of the *K. pneumoniae* population and is <span class="mark">associated with both hospital acquired infections and hypervirulent community-acquired infections</span>. There are <span class="mark">17 distinct *ybt* lineages that have been identified, embedded within 14 structural variants of ICEKp, that can integrate into any of four tRNA-Asn sites in the chromosome (Lam et al., 2018).</span>

<span class="mark">Aerobactin and Salmochelin synthesis is encoded by *iuc* and *iro* loci respectively, which are co-located on the virulence plasmids of *K. pneumoniae*. Salmochelin exhibits a higher affinity for iron than other accessory siderophores. There are five distinct iro lineages (iro1–iro5), each associated with different mobile genetic elements . Lineages iro1 and iro2 are linked to the virulence plasmids KpVP-1 and KpVP-2, respectively, whereas iro4 is associated with plasmid pINV078-VP. iro3 is integrated within the integrative conjugative element ICEKp1, while iro5 is found on a diverse range of plasmids, see this paper [<u>https://doi.org/10.1186/s13073-018-0587-5</u>](https://doi.org/10.1186/s13073-018-0587-5). Aerobactin (*iuc*) locus is present in fewer than 10% *K. pneumoniae* isolates.There are five distinct aerobactin lineages (*iuc1*–*iuc5*), each associated with different mobile genetic elements.</span>

<span class="mark">Colibactin is a genotoxin produced by some *K. pneumoniae* isolates as well as other members of the *Enterobacteriaceae*. It is encoded by the *clb* (*pks*) locus, which is located within the integrative and conjugative element ICEKp10 (Lam et al., 2018). Colibactin induces DNA double-strand breaks in host cells and has been implicated in the development of colorectal cancer. In *K. pneumoniae*, the *clb* locus is predominantly associated with the hypervirulent liver abscess clones CG23 (approximately 80%) and CG66 (100%), but it is also found in subpopulations of the hypervirulent clones CG65 and CG380 (Lam et al., 2018).</span>

**<span class="mark">8.1.2.1 Hypermucoidy loci</span>**

<span class="mark">Hypermucoidy in *K. pneumoniae* is encoded by the regulator gene of the mucoid phenotype A (*rmpA* gene), which is located in the virulence plasmid in HvKP. The phenotype is commonly associated with capsule overproduction due to the presence of one or both of the accessory regulator genes *rmpA* or *rmpA2*.The *rmpA* and *rmpA2* genes are located adjacent to the *iro* and *iuc* loci, respectively, and therefore share the distribution of both KpVP-1 and KpVP-2. However, *rmpA* can also be co-localised with *iro* within ICEKp1, whereas *rmpA2* may be co-localised with *iuc* on non-canonical virulence plasmids.</span>

### 8.1.3 MLST, cgMLST and LIN codes

Multilocus sequence typing (MLST), core genome MLST (cgMLST), and Life Identification Number (LIN) codes are complementary approaches for genomic typing and epidemiological classification of *Klebsiella pneumoniae*. The 7-gene multilocus sequence typing (MLST) approach assigns each isolate a sequence type (ST) based on allelic variation across seven housekeeping genes (Brisse et al., 2009), providing a highly reproducible and internationally standardised nomenclature that has been widely used for surveillance. Although multilocus sequence typing (MLST) is widely used to describe the population structure of *K. pneumoniae*, the scheme covers only a small fraction of the genome. As a result, isolates sharing the same sequence type (ST) may exhibit substantial genomic diversity, and STs provide limited resolution for inferring recent transmission events. The *K. pneumoniae* MLST schemes are hosted on BIGSdb.

Core genome MLST (cgMLST) extends the advantages of traditional MLST to the genomic scale by interrogating hundreds of conserved core genes, providing higher resolution for population genomics, transmission analysis, and evolutionary studies. For *K. pneumoniae*, a 629-gene cgMLST scheme (scgMLSTv2) has been developed capturing the population structure across the seven phylogroups of the *K. pneumoniae* species complex (<span class="mark">Hennart et al., 2022</span>). Genomes can be grouped into sublineages (SLs) and clonal groups (CGs) based on defined allelic distance thresholds. Sublineages are defined by a maximum of 190 allelic mismatches, whereas clonal groups are defined using a more stringent threshold of 43 allelic mismatches, which shows strong concordance with the traditional seven-gene MLST classification. Building on this framework, cgMLST-based Life Identification Number (cgLIN) codes provide a hierarchical nomenclature in which each genome is assigned a multi-level numeric barcode that reflects its genetic similarity to other genomes across predefined allelic thresholds. Closely related isolates share longer common LIN prefixes, enabling rapid identification of epidemiological and phylogenetic relationships. The cgLIN prefixes correspond to SLs. The <span class="mark">*cgMLST* scheme is hosted on the Institut Pasteur BIGSdb instance [<u>https://bigsdb.pasteur.fr/klebsiella/</u>](https://bigsdb.pasteur.fr/klebsiella/)</span>

### 8.1.4 AMR mechanisms

<span class="mark">Antibiotic resistance in *K. pneumoniae* can be classified as either (i) intrinsic (naturally encoded within the bacterial genome) or (ii) acquired (arising through mutation or horizontal gene transfer). Acquired resistance is mediated by plasmids and other mobile genetic elements that facilitate the dissemination of AMR determinants. These resistance determinants confer reduced susceptibility through several mechanisms, including enzymatic inactivation or modification of antibiotics (β-lactamases), decreased membrane permeability, overexpression of efflux pumps, and mutations that alter antibiotic targets (Assar et al., 2025).</span>

**<span class="mark">8.1.4.1 Core genes and resistance</span>**

*K. pneumoniae* is intrinsically resistant to ampicillin due to the presence of the chromosomally encoded SHV β-lactamase, encoded by the *blaSHV* gene (Holt et al., 2015). Orthologues of this class A β-lactamase are conserved across the *K. pneumoniae* species complex (KpSC), including *LEN* in *K. variicola* and *K. quasivariicola*, and *OKP* in other species. The *blaSHV* gene can be mobilized by insertion sequences such as IS26, forming a mobile genetic element that facilitates dissemination to other bacteria strains via plasmids<span class="mark">. These mobilised variants of bla SHV can acquire point mutations that result in extended spectrum beta-lactamase activity (ESBL) conferring resistance to third generation cephalosporins, β-lactamase inhibitor (BLI) resistance, and carbapenems.</span> Additionally, *K. pneumonia* genomes harbours other chromosomal genes conferring reduced antimicrobial susceptibility such as *fosA* (glutathione S-transferas) and oqxAB (multidrug efflux pump). Although the chromosomally encoded *fosA* and *oqxAB* confer reduced susceptibility to fosfomycin and quinolones, their wild-type expression levels do not meet the breakpoints for clinical resistance. <span class="mark">There are several other core genes known to confer resistance in Kpn, see there papers for reference</span> <span class="mark">[<u>https://doi.org/10.1038/s41579-019-0315-1</u>](https://doi.org/10.1038/s41579-019-0315-1).</span>

<span class="mark">Specific mutations known to increase resistance to antimicrobials</span> include;

- Fluoroquinolone Resistance: resistance is driven by mutations in the Quinolone Resistance Determining Region (QRDR) of core genes gyrA and/or parC (*gyrA*: mutations at codons 83 and 87, and *parC*: mutations at codons 80 and 84).

- Carbapenem resistance: Resistance to carbapenems can arise through mutations in the genes encoding outer membrane porins e.g. ompK36, ompK35 truncation, ompK36 synonymous point mutation ompK36-C25T, ompK36 beta-strand loop insertion/duplication - OmpK36GD and OmpK36D

- Colistin resistance: truncation of *mgrB* (encodes a small transmembrane protein that regulates the PhoP/PhoQ system) and truncation of *pmrB* (sensor kinase which also controls lipopolysaccharide modification)

### 8.1.4.2 Acquired resistance

<span class="mark">Most resistance observed in *K. pneumoniae* is associated with horizontally acquired AMR genes.</span> Acquired AMR genes are frequently mobilised by mobile genetic elements (MGEs), including insertion sequences, transposons, plasmids and integrative conjugative elements. These genes are most commonly located on plasmids, although they can also be integrated into the chromosome (Wyres et al., 2019). More than 100 distinct acquired AMR genes have been identified in *Kp.* See papers [<u>https://doi.org/10.1093/femsre/fux013</u>](https://doi.org/10.1093/femsre/fux013), [<u>10.1016/j.tim.2016.09.007</u>](https://doi.org/10.1016/j.tim.2016.09.007) for references.

**8.1.5 Convergence of resistance and virulence**

The emergence of multidrug-resistant hypervirulent *Klebsiella pneumoniae* (MDR-hvKP) represents a significant public health concern due to the combination of enhanced virulence and limited treatment options. MDR-hvKP can arise through two main mechanisms: a hypervirulent strain may acquire antimicrobial resistance genes or plasmids via horizontal gene transfer, or a classical MDR *K. pneumoniae* strain may acquire a pLVPK-like virulence plasmid. Hypervirulence in MDR-hvKP is associated with the overproduction of capsule and siderophores resulting from the acquisition of plasmid-mediated virulence determinants, including r*mpA/rmpA2*, *iuc*, and *iro*. Convergent strains carrying both MDR and hypervirulence-associated genes have been reported in several regions worldwide (Gu et al., 2018; Turton et al., 2018; Biedrzycka et al., 2022). For example, China reported a high-mortality outbreak of ventilator-associated pneumonia caused by a hypervirulent carbapenemase-producing ST11 carbapenem-resistant *K. pneumoniae* strain that had acquired a virulence plasmid harbouring the iuc (aerobactin siderophore) and *rmpA2* (hypermucoviscosity) loci.

Convergence of virulence and antimicrobial resistance has also been shown to occur on the same plasmid. Several examples have been reported, including pKpvST147L, identified in an ST147 carriage isolate from London, which carries the virulence genes iuc, *rmpA*, and *rmpA2* alongside multiple AMR determinants (*sul2, armA, sul1, and mphA* *blaNDM-1* carbapenemase). Another example is pKP70-2, identified in a K1 ST23 sputum isolate from China, which carried the KpVP-1 virulence plasmid encoding *iuc*, *iro*, *rmpA*, and *rmpA2*, together with an inserted MDR transposon carrying the blaKPC-2 carbapenemase gene. The emergence of these hybrid plasmids highlights the potential for virulence and antimicrobial resistance determinants to converge within a single mobile genetic element, facilitating the dissemination of highly virulent and difficult to treat *K. pneumoniae* strains.

## *8.1.6 Klebsiella* genomics analysis

For all initial processing steps, including raw read quality control, adapter trimming, contamination check, species confirmation, and de novo assembly, please refer to the ‘Standard Bioinformatics Workflows - core bioinformatics steps’ section of this guidance.

For genotyping members of the *Klebsiella pneumoniae* Species Complex (KpSC), we recommend using the Kleborate tool (Lam et al., 2021). <span class="mark">Kleborate provides a unified workflow for species identification, multilocus sequence typing (MLST), genotyping of key virulence and antimicrobial resistance (AMR) determinants, and capsule (K) and lipopolysaccharide (O) antigen typing using Kaptive.</span> Additional modules for core genome MLST (cgMLST), LIN code typing, and characterisation of the *mrk* operon will be available in an upcoming release. Further details on Kleborate and its available modules can be found in the Kleborate documentation [<u>https://kleborate.readthedocs.io/en/latest/index.html</u>](https://kleborate.readthedocs.io/en/latest/index.html).

<span class="mark">Kleborate takes input whole-genome assemblies generated from Illumina or Nanopore long-read sequences (FASTA format). Each assembly is typed against curated reference databases, and the main results are reported in a tab-delimited text file. Kleborate can be installed easily via command-line. For *Kpsc* we recommend using the preset **-p KpSC** with default parameters**.** Alternatively, users can specify individual analysis modules with the **-m option**, depending on the objectives of the analysis [<u>https://kleborate.readthedocs.io/en/latest/kpsc_modules.html</u>](https://kleborate.readthedocs.io/en/latest/kpsc_modules.html).</span>

**Interpretation of Kleborate results**

<span class="mark">Kleborate facilitates detection and tracking of clinically relevant AMR and virulence determinants from genome data</span> by applying species-specific interpretation rules.

- <span class="mark">The intrinsic</span> genes, such as *fosA* and *oqxAB* genes are not reported as they <span class="mark">do not confer resistance to quinolones and fosfomycin.</span>

- <span class="mark">I</span>ntrinsic virulence determinants such as the siderophore enterobactin are excluded, as their presence does not indicate increased virulence.

- <span class="mark">All KpSC carry a core chromosomal beta-lactamase gene, SHV in</span> *K. pneumoniae*, LEN in *K. variicola*, and OKP in *K. quasipneumoniae* that confers resistance to ampicillin. Kleborate reports detected SHV alleles and classifies them according to the predicted resistance phenotype. SHV alleles associated with ampicillin resistance only, will be reported in the Bla_chr column where they are considered chromosomal and are not included in the count of acquired resistance genes or resistance classes. SHV alleles predicted to encode extended-spectrum β-lactamases (ESBLs) or or beta-lactamases with inhibitor resistance are reported in the relevant acquired resistance columns (e.g. Bla_ESBL_acquired, Bla_inhR_acquired), as these alleles are almost always carried on plasmids.

When reporting AMR genes, <span class="mark">Kleborate has logic to choose the best allele hit,</span> the exact nucleotide matches are preferred, followed by exact amino acid matches, and finally inexact nucleotide matches.

- ^ symbol denotes an inexact nucleotide match but an exact amino acid match

- \* symbol indicates <span class="mark">inexact nucleotide and inexact amino acid match</span>

- denotes an incomplete match,

- X% indicates t<span class="mark">runcated amino acid sequence</span>

Kleborate scores each genome <span class="mark">according to the clinical risk associated with the AMR and virulence loci that are detected</span>. Virulence scores range from 0 to 5 <span class="mark">depending on the presence of key loci associated with increasing risk (yersiniabactin \< colibactin \< aerobactin). Resistance scores range from 0 to 3, based on detection of genotypes warranting escalation of antimicrobial therapy (ESBL \< carbapenemase \< carbapenemase plus colistin resistance.</span>

<span class="mark">Kleborate is also integrated into several genomic analysis platforms and workflows, including Pathogenwatch [<u>https://pathogen.watch</u>](https://pathogen.watch), Bactopia [<u>https://github.com/bactopia/bactopia</u>](https://github.com/bactopia/bactopia) and</span> TheiaProk workflows.

**Note: Kleborate does not include modules for plasmid replicon detection. PlasmidFinder can be run separately via web or commandline** ([<u>https://cge.food.dtu.dk/services/PlasmidFinder/</u>](https://cge.food.dtu.dk/services/PlasmidFinder/)), ([<u>https://bitbucket.org/genomicepidemiology/plasmidfinder/src/master/</u>](https://bitbucket.org/genomicepidemiology/plasmidfinder/src/master/))

**<span class="mark">8.1.6.1 Resources for non-bioinformaticians</span>**

<span class="mark">Several user-friendly platforms and automated workflows are available to support *Klebsiella* genome</span> analysis, <span class="mark">particularly</span> for <span class="mark"></span>public health staff <span class="mark">with limited command-line or bioinformatics experience. These resources provide web-based interfaces or pipelines that simplify tasks</span> including genome <span class="mark">assembly, quality control, typing, AMR prediction, and virulence profiling.</span>

**<span class="mark">PathogenWatch</span>**

<span class="mark">PathogenWatch ([<u>https://pathogen.watch</u>](https://pathogen.watch)) - Users can upload genome assemblies directly through the web interface, the platform performs species identification, MLST and core-genome MLST assignment, AMR prediction, capsule (K) and O-antigen typing. For *Klebsiella* genomes, it integrates Kleborate and Kaptive. Results are presented through interactive tables. Users can compare local isolates with global datasets and identify high-risk clones or potential transmission clusters.</span>

**<span class="mark">TheiaProk</span>**

<span class="mark">TheiaProk ([<u>https://github.com/theiagen/public_health_bioinformatics</u>](https://github.com/theiagen/public_health_bioinformatics)) is a workflow developed by Theiagen Genomics to support standardised bacterial whole-genome sequencing analysis in public health laboratories. TheiaProk workflows cover the complete analysis process from raw reads to genome assembly, quality assessment, taxonomic identification,sequence typing, AMR detection, and plasmid analysis</span>

### <span class="mark">8.1.7 Transmission analysis using whole-genome sequencing</span>

<span class="mark">Whole genome sequencing data can be used to identify clusters of genetically related *Klebsiella pneumoniae* isolates and estimate the proportion of cases attributable to recent transmission. While phylogenetic analysis remains the gold standard for investigating outbreaks, genomic clustering provides a scalable framework for routine surveillance.</span>

<span class="mark">One such method is the Transmission Estimator Tool,[<u>https://github.com/klebgenomics/transmission_estimator</u>](https://github.com/klebgenomics/transmission_estimator) (Odih et al., 2026), which combines pairwise genomic distances with temporal and spatial metadata to infer likely transmission networks and quantify the proportion of cases linked to recent transmission.</span>

**<span class="mark">Transmission cluster definition</span>**

<span class="mark">A transmission cluster is defined as a group of isolates connected through single-linkage clustering, where every linked pair satisfies all of the following criteria:</span>

- **<span class="mark">Pairwise SNP distance: ≤10 SNVs</span>**

- <span class="mark">**Sampling interval:** ≤4 weeks based on date of specimen collection</span>

- <span class="mark">**Spatial linkage:** Shared epidemiological location (e.g., same healthcare facility or neonatal unit).</span>

**Transmission Estimator input data requirements**

**<span class="mark">1. Metadata file</span>**

<span class="mark">The metadata file should contain one row per isolate and include the following minimum information:</span>

- <span class="mark">**id**: Unique isolate identifier matching the genetic distance matrix.</span>

- <span class="mark">**Year**: Year of isolation (YYYY format).</span>

- <span class="mark">**Month**: Month of isolation (MM format).</span>

- <span class="mark">**Day**: Day of isolation (DD format).</span>

- <span class="mark">**Site**: Sampling location or healthcare facility.</span>

- <span class="mark">**Country**: Country of isolation.</span>

- <span class="mark">**ST**: Multilocus sequence type (MLST).</span>

<span class="mark">Additional epidemiological variables such as hospital, ward, intensive care unit, speciality, or healthcare network can also be included and may improve cluster interpretation.</span>

**<span class="mark">2. Genetic distance matrix</span>**

<span class="mark">A pairwise distance matrix generated from sequencing data is required. SNP distance matrix file can be generated using PathogenWatch [<u>https://pathogen.watch/en</u>](https://pathogen.watch/en)</span>

<span class="mark">For detailed step by step instructions on preparing input files, selecting appropriate clustering thresholds, and running the analysis, please refer to the user guide: [<u>https://github.com/klebgenomics/transmission_estimator</u>](https://github.com/klebgenomics/transmission_estimator)</span>

## 8.1.8 Caveats in *K. pneumonia* WGS data analysis<span class="mark">.</span> 

<span class="mark">*Klebsiella pneumoniae* species complex (KpSC) comprises several closely related species, including *K. pneumoniae* sensu stricto, *K. variicola*, *K. quasipneumoniae*, *K. quasivariicola* and *K. africana* etc. These species share high genomic similarity and are frequently misidentified by routine laboratory methods, including some MALDI-TOF and biochemical identification systems. Isolates reported clinically as *K. pneumoniae* may belong to other members of the KpSC. Accurate species assignment should therefore be based on genome-based approaches such as average nucleotide identity (ANI), or Mash distances.</span>

<span class="mark">Interpretation of AMR determinants also requires careful consideration of intrinsic resistance mechanisms. *Klebsiella pneumoniae* carries chromosomally encoded *bla*SHV gene conferring resistance to ampicillin. Therefore, presence of a *bla*SHV gene alone should not be interpreted as evidence of an acquired β-lactam resistance.Furthermore, resistance may arise from combinations of acquired β-lactamases, alterations in outer membrane porins (particularly OmpK35 and OmpK36), efflux mechanisms, meaning that genotype–phenotype concordance is not always straightforward. Genomic AMR predictions should therefore be interpreted alongside AST data where available. Additionally, r</span>esistance-associated mutations are also species-specific, necessitating screening and interpretation with dedicated databases.

<span class="mark">Chromosomal recombination events are considered to contribute to the genetic diversification of *Klebsiella pneumoniae*. Recombination is particularly important during phylogenetic reconstruction and outbreak investigations. Inclusion of recombinant regions may inflate genetic distances between closely related isolates, potentially causing epidemiologically linked isolates to be excluded from transmission clusters. For this reason, phylogenetic analyses intended to assess transmission should ideally be based on core-genome alignments from which recombinant regions have been identified and removed using tools such as Gubbins [<u>https://github.com/nickjcroucher/gubbins</u>](https://github.com/nickjcroucher/gubbins).</span>

<span class="mark">Recombination is also a major driver of diversification in clinically important genomic regions. Capsular polysaccharide synthesis (K locus) and lipopolysaccharide O-antigen loci are frequently exchanged through recombination, meaning that closely related isolates may exhibit different predicted serotypes.</span>

<span class="mark">When interpreting genomic clusters, users should acknowledge that SNP thresholds derived from recombination-filtered datasets are not directly comparable to thresholds generated from unfiltered analyses. Reports should therefore clearly state whether recombinant regions were removed before distance calculation and cluster identification.</span>

<span class="mark">Genomic analyses should be interpreted in the context of assembly quality and completeness. Poor-quality assemblies can lead to missed AMR genes, fragmented virulence loci, and inaccurate plasmid reconstruction. Quality control metrics, including genome size, contamination, coverage and assembly fragmentation, should therefore be reviewed before drawing conclusions from pathogen genomic data.</span>

## *8.1.9 K. Pneumoniae* case study examples

**Case Study \#1: Malawi Neonatal Unit *Klebsiella pneumoniae* ST340 Outbreak (2012-2015)**

[**<u>https://www.microbiologyresearch.org/content/journal/mgen/10.1099/mgen.0.000703</u>**](https://www.microbiologyresearch.org/content/journal/mgen/10.1099/mgen.0.000703)

**Aim**: To investigate a suspected outbreak of multidrug‑resistant K. pneumoniae bloodstream infections in a neonatal unit at a large public hospital in Malawi, identify the outbreak clone(s), characterize their antimicrobial resistance and virulence profiles, and place the strains in a global genomic context.

**Surveillance Strategy/System Design**

- Setting: Chatinkha neonatal special care unit (70‑bed), Queen Elizabeth Central Hospital (QECH), Blantyre, Malawi - a government tertiary referral hospital serving southern Malawi (population ~900,000). Care is free at point of delivery.

- Sampling strategy: All viable, archived K. pneumoniae bloodstream isolates from the neonatal unit over a 4-year period (January 2012 - December 2015) were sequenced. A subset of K. pneumoniae bloodstream isolates (n=38) from other pediatric wards in the same hospital was included for comparison. Intensified sampling was performed during a suspected outbreak period (February–November 2014).

- Isolate types: Blood cultures only (no environmental or staff screening). All from infants with clinically suspected sepsis.

- Sample size: 100 isolates attempted; after QC (Kraken filtering \>5% non‑KpSC), 86 isolates (56 from neonatal unit, 30 from other paediatric wards) were analysed.

- Reason for sampling strategy: A spike in K. pneumoniae bloodstream infections was observed in February (n=7) and March (n=9) 2014, followed by a second peak in September-November 2014. Over 75% of all paediatric K. pneumoniae bloodstream isolates during February-November 2014 came from the neonatal unit despite it having the smallest bed capacity. Isolates were untreatable with locally available antibiotics and showed identical resistance patterns, suggesting a clonal outbreak.

- Laboratory methods: Blood culture collection and processing; antimicrobial susceptibility testing by disc diffusion. Isolates stored at -80 °C on microbank beads.

- Sequencing approach: Illumina HiSeq X‑Ten (2×150 bp) at Wellcome Sanger Centre and Oxford Genomics Centre.

- Use Case(s): Outbreak investigation (primary), detection of high‑risk clones (CC258/ST340), AMR mechanism detection, global phylogenetic contextualisation.

**Ethical/Legal Considerations and Approvals**

- Beneficence and non‑maleficence: The study used retrospective, anonymised residual diagnostic isolates; no additional patient interventions were performed. The research posed no more than minimal risk. Findings on vaccine coverage and AMR trends have potential public health benefit.

- Distributive justice: Not reported. The study did not explicitly address equity or inclusion of underserved populations as a research design goal. The hospital serves a broad population (urban Blantyre and surrounding districts).

- Privacy and autonomy: Patient records were retrospectively anonymised. Ethical approval obtained from University of Malawi College of Medicine Research Ethics Committee (P.08/14/1614 and P.018/17/2255).

- Data custodianship and distribution: Raw reads and assemblies deposited in GenBank (PRJNA641987) and European Nucleotide Archive (PRJEB19322). Global context sequences from ERP000165.

- Transparency and accountability: Findings published open access.

- Data protection: No patient identifiers in public datasets.

- Public health integration: Results led to sustained IPC measures, enhanced environmental monitoring, and surveillance for ST340 re‑emergence. The study contributed to the global genomic network for K. pneumoniae..

**Data Analysis**

**Bioinformatics pipeline(s):**

- Kraken - Species confirmation and contamination filtering (\>5% non‑KpSC reads excluded)

- MLST (in silico) - Sequence type determination (7‑locus scheme) as described \[8\]

- SRST2 v0.2.0 - Resistance gene identification

- in silico PCR‑based replicon typing & PlasmidFinder v2.0.1 - Plasmid detection

- Kaptive v0.5.1 - Capsular (K) and O‑antigen typing

- Kleborate v0.3.0 - Virulence gene detection

- roary - Core genome alignment of combined dataset (Malawian + global)

- RAxML v7.8.6 - Maximum‑likelihood phylogeny from core genome SNPs

- Pairwise SNP distance calculation - Clonality assessment (≤30 SNPs threshold for outbreak‑related isolates)

- QC thresholds: Average 2.3 million reads per sample; average 77 contigs (range 22-259); \>5% non‑KpSC reads excluded.

- Typing methods: MLST (in silico); Kaptive for KL (capsular type 15) and O (O4) typing.

- AMR detection: SRST2; phenotypic AST by disc diffusion; ST340 isolates resistant to 7 antibiotic classes, susceptible only to amikacin. Concordance demonstrated.

- Virulence detection: Kleborate v0.3.0 (virulence genes not the focus; main finding was MDR).

- Phylogenetic/cluster analysis: Core gene alignment with roary; RAxML tree; pairwise SNP differences (ST340 isolates differed by ≤30 SNPs). Global context with dataset from Holt et al. (ERP000165).

- Statistical/epidemiological integration: Temporal mapping of cases by month and ST; mortality outcome analysis (4/13 ST340 cases died, CFR 31%); comparison of ST340 vs ST14 vs ST372 contributions during outbreak period (58%, 4%, 21% respectively).

- Visualisation tools: Schematic of isolates by month and ST (Fig. 1); bar chart of culture positivity (Fig. 2); SNP heatmap (Fig. 3); resistance element distribution (Fig. 4); global phylogeny (Fig. 5).

**Data Sharing Strategy**

- Raw reads: NCBI BioProject PRJNA641987; European Nucleotide Archive PRJEB19322

- Metadata: Limited to collection date, ward, outcome (de‑identified)

- Restrictions: None - open access

**Major Findings:**

This genomic investigation of a neonatal unit outbreak in Malawi identified a single MDR ST340 clone (CC258, KL15, O4) that caused 58% of cases during the outbreak period and 30% of all neonatal unit K. pneumoniae bloodstream infections over four years. The clone was resistant to all locally available antibiotics (susceptible only to amikacin) and had a 31% case fatality rate. Phylogenetic analysis confirmed a single circulating lineage (isolates differed by ≤30 SNPs) that had been present in other pediatric wards for at least one year before the outbreak and was most closely related to ST258 strains from the USA.

**Public health actions:**

- Immediate IPC review with patient cohorting and environmental cleaning;

- Recommendation to make amikacin available for empiric treatment of suspected MDR neonatal sepsis;

- Enhanced surveillance for ST340 re‑emergence with environmental and staff screening;

- Hospital‑wide IPC reinforcement and review of patient transfer practices;

- Contribution of genomic data to the global CC258 surveillance network; and

- Strengthened antimicrobial stewardship to preserve the limited effective treatment options.

**Case Study \#2: Two hospital outbreaks in China caused by hypervirulent, carbapenem-resistant *Klebsiella pneumoniae* (hvCRKP) <span class="mark">ST65-KL2 and ST11-KL64</span>  in intensive care units (ICUs) and transplantation wards** [**<u>https://www.nature.com/articles/s42003-024-07310-2</u>**](https://www.nature.com/articles/s42003-024-07310-2)

**Case Study \#2A: ST65-KL2 CR-hvKP Outbreak (Transplantation Ward, 2019)**

**Use case(s):** Outbreak investigation; detection of high-risk clones (hvCRKP); AMR mechanism detection; transmission source identification (donor-derived).

**Specimen type:** Clinical isolates from bronchoalveolar lavage fluid (BALF), blood, and other specimens from transplant recipients.

**Sampling strategy**: All carbapenem-resistant K. pneumoniae isolates from transplantation ward patients over a 3‑month period (June–August 2019) were collected. Outbreak investigation triggered by an unusual cluster of NDM-5-producing, hypermucoviscous isolates. All available isolates from five patients (three kidney recipients, two lung recipients) were sequenced.

**Ethical/Legal Considerations and Approvals**

- Ethics approval: Obtained from China‑Japan Friendship Hospital (approval number 2022‑KY‑054) – stated in the paper.

- Consent: Not explicitly stated; standard for retrospective outbreak investigation.

- Data deposition: Sequences deposited in NCBI BioProject PRJNA1102845.

- Other ethical/legal considerations: None reported.

**Data Analysis**

**Bioinformatics tools:**

- **Sequencing:** Illumina HiSeq 2500 (all isolates) + Nanopore MinION (representative strains K22877).

- **Assembly:** SPAdes v3.13.1, Unicycler.

- **Typing & virulence/AMR:** Kleborate v2.4.1 (MLST, K/O loci, resistance genes, virulence genes).

- **Plasmid analysis:** PlasmidFinder; oriTfinder for transferability; BRIG for plasmid comparison.

- **Phylogenetics:** Snippy (SNP calling); cgMLST (Ridom SeqSphere+);

- **Comparative genomics:** BLAST+; RAxML phylogenetic trees for plasmids; iTOL visualization.

- **Phenotypic correlation:** AST (microdilution, Vitek‑2); string test; G. mellonella and murine infection models; macrophage phagocytosis assay; capsule thickness and uronic acid quantification.

**Major findings:**

- **Clonal outbreak:** ST65-KL2 (capsule type KL2, O1) carrying blaNDM-5 on an IncX3 plasmid (pK22877-2-NDM) and a full hypervirulence plasmid (pK22877-1-VIR) with rmpA, iucABCD, iroBCDN.

- **Source identification**: Donor-derived transmission - two lungs and two kidneys from the same donor seeded infections in five recipients; subsequent close contact spread within the transplantation ward.

- **Resistance:** High-level carbapenem resistance (meropenem MIC ≥16 µg/mL) due to NDM-5; susceptible to aztreonam, aminoglycosides, and quinolones (initially).

- **Virulence:** Positive string test; hypermucoviscous; high mortality in murine models (stronger than ST11-KL64); LD50 lower than hv-CRKP.

- **Evolutionary pathway:** CR-hvKP (hvKP acquired carbapenem resistance) – the strain originated from a hypervirulent background (ST65-KL2) and later acquired blaNDM-5 plasmid.

- **Resistance evolution during spread**: Two later isolates (K23016, K23033) acquired an IncQ plasmid conferring ciprofloxacin resistance (aac(6’)-Ib-cr, blaOXA-1, blaCTX-M-3, etc.), showing ongoing resistance evolution.

- **Clinical outcomes:** Two lung transplant recipients died within two weeks; aztreonam was effective for survivors.

**Public health action:**

- Immediate IPC measures: Patient cohorting, contact precautions, enhanced environmental cleaning in transplantation ward.

- Donor screening protocol: Implemented routine screening of organ donors for carbapenem-resistant organisms.

- Enhanced surveillance: Active screening for hvCRKP in ICU and transplantation wards.

- Treatment guidance: Aztreonam recommended for NDM-5-producing CR-hvKP infections; caution against ciprofloxacin use due to emerging resistance.

- National alert: Notified regional and national CRE surveillance networks of donor-derived hvCRKP transmission.

**Case Study \#2B: ST11-KL64 hv-CRKP Outbreak (Multiple Wards, 2023)**

**Use case(s):** Outbreak investigation; detection of high-risk clones (hvCRKP); AMR mechanism detection (dual carbapenemases); transmission chain mapping; virulence evolution tracking.

**Specimen type:** Clinical isolates from blood, BALF, urine, and other specimens from ten patients across multiple wards (ICU, transplantation, general medicine).

**Sampling strategy:** All carbapenem-resistant K. pneumoniae isolates with unusual susceptibility profiles (co-resistant to CZA) collected over 10 months (March–December 2023). Outbreak investigation identified 21 ST11-KL64 isolates from ten patients. Multiple chains of transmission (five distinct chains) mapped by time, location, and phylogenetic relatedness.

**Bioinformatics tools:** Same as Case Study \#4A (Illumina + Nanopore for K56649 and K60365; Kleborate, Snippy, cgMLST, PFGE, plasmid analysis, virulence phenotyping).

**Major findings:**

- **Clonal outbreak with polyphyletic spread:** All 21 isolates belonged to ST11-KL64 (capsule KL64, O2/O2v1) and formed a single cgMLST cluster, but with five distinct transmission chains across different wards and hospitals.

- **Dual carbapenemases:** Co-carried blaKPC-2 (IncFII/IncR plasmid pK56649-2-KPC) and blaNDM-13 (IncI1 plasmid pK56649-4-NDM) – first report of NDM-13 in K. pneumoniae.

- **Hypervirulence plasmid:** pK56649-3-VIR (IncHI1B/IncFIB) carried rmpA (promoter truncated by ISKpn26 or ISKpn74 in most isolates), rmpA2 (intact), and iucABCD, but lacked iroBCDN.

- **Phenotypic virulence:** No hypermucoviscosity (string test negative) despite virulence genes; however, G. mellonella and murine models <span class="mark">(mouse models for studying microbial pathogenesis and testing antimicrobial drugs)</span> confirmed hypervirulence (comparable to NTUH-K2044), though LD50 was higher than ST65-KL2.

- **Evolutionary pathway:** hv-CRKP (CRKP acquired hypervirulence) – the strain originated from a carbapenem-resistant classical K. pneumoniae (ST11-KL64) background that later acquired the hypervirulence plasmid.

- **Virulence evolution within outbreak**: Isolate K60365 (from patient 2-7) acquired enhanced capsule production (higher uronic acid content, thicker capsule, positive string test) and increased resistance to macrophage phagocytosis compared to the index strain K56649, indicating in-host virulence evolution.

- **Clinical impact:** Occult and persistent infections - several patients had recurrent infections after discharge; 60% mortality (6/10) despite susceptibility to the ATM-CZA combination.

- **Global context:** ST11-KL64 hv-CRKP globally dominated by blaKPC-2 (96.9%); ST65-KL2 CR-hvKP dominated by blaKPC-2 (67.9%) but also carried blaNDM-5 (10.7%).

**Public health action:**

- Immediate IPC escalation: Enhanced hand hygiene, patient cohorting, environmental decontamination, and active screening in ICUs and transplantation wards.

- Regional surveillance alert: Notified surrounding hospitals of regional dissemination (four patients had hvCRKP isolated within 24 hours of admission, indicating prior community or healthcare exposure).

- Treatment protocol review: ATM-CZA combination as last-line therapy; cautioned against colistin and tigecycline as first-line.

- Laboratory guidance: Recommended both phenotypic (string test, MIC) and genotypic (Kleborate) confirmation of hvCRKP; **noted that absence of hypermucoviscosity does not exclude hypervirulence.**

- Research priorities: Urged development of phage therapy, immunological approaches, and novel antimicrobials for hvCRKP that persists intracellularly and causes occult infections.

- Long-term follow-up: Established protocol for post-discharge monitoring of patients with hvCRKP infections due to risk of occult persistence and recurrence.

**Case Study \#3 – South Africa Neonatal Unit CRKP Outbreak (NDM‑1 ST152 and OXA‑181 ST307) - [<u>https://doi.org/10.3201/eid2908.230484</u>](https://doi.org/10.3201/eid2908.230484)**

Aim: To investigate an outbreak of carbapenem‑resistant K. pneumoniae bloodstream infections in a neonatal unit, describe antimicrobial susceptibility profiles, resistance mechanisms, and transmission dynamics using genomic and epidemiologic data.

**Surveillance Strategy/System Design**

- Pathogen(s): Carbapenem‑resistant Klebsiella pneumoniae (CRKP)

- Setting: Tembisa Provincial Tertiary Hospital, Gauteng Province, South Africa - 840-bed hospital serving a population of 2.5 million.

- Sampling strategy: All CRKP bloodstream infection isolates from infants \<6 months of age in the neonatal unit during the outbreak period (October 2019–February 2020) were collected. Baseline data (January 2017–September 2019) and follow‑up (March 2020–May 2021) were reviewed.

- Sampling frame: Outbreak period: 5 months; follow‑up: 15 months.

- Isolate types: Blood cultures only.

- Sample size: 31 cases (27 viable isolates sequenced); 14 deaths.

- Reason for sampling strategy: An increase of \>100% in CRKP cases compared to baseline triggered an outbreak investigation. Part of Baby GERMS‑SA enhanced neonatal surveillance.

- Laboratory methods: MALDI‑TOF for species; MicroScan WalkAway 96‑plus for AST; carbapenemase PCR (LightMix Modular); PFGE for initial relatedness.

- Sequencing approach: Illumina NextSeq 550 (2×150 bp, 100× coverage) at NICD Sequencing Core Facility.

- Use case(s): Outbreak investigation, transmission network reconstruction, AMR mechanism detection, detection of high‑risk clones.

**Data Analysis**

**Bioinformatics tools:**

- **Bioinformatics Pipeline called Jekesa v1.0 (**which automates the entire analysis workflow from raw read processing to downstream analyses like phylogenetics.)

- Trim Galore v0.6.2 – Read filtering (Q\>30, length \>50 bp)

- SPAdes v3.13 – De novo assembly

- Shovill v1.1 – Assembly optimisation

- Kleborate - Species prediction, MLST, acquired AMR genes, plasmid replicons, O/K locus typing

- Snippy v4.6 - Core genome alignment (reference: K. pneumoniae HS11286, CP003200)

- Gubbins - Recombination region detection and removal

- snp‑sites - Extract core SNP alignment from Gubbins output

- IQ‑TREE 2 - Maximum‑likelihood phylogeny (GTR model with ascertainment bias correction)

- Microreact - Tree visualisation

- seqTrack (adgenet v2.1.3, R) – Transmission network reconstruction; ≤11 SNP cutoff for outbreak‑related isolates

- Transmission networks: Core genome SNP distances (\<10 SNPs considered clonal) combined with epidemiological data (admission dates, ward location, bed movements) to reconstruct transmission chains.

**Major findings:**

- **Outbreak confirmation:** 31 CRKP bloodstream infection cases and 14 deaths over 5 months (October 2019 - February 2020). December 2019 peak of 14 cases (baseline average 1.5 non-CRKP cases/month).

- **Two co-circulating outbreak clones:**

- **blaNDM-1 ST152 (n=16, 59% of isolates):** Major clone, accounted for 9/14 deaths (64%). Carried on E. coli B171 plasmid pB171. Also carried blaCTX-M-15, blaTEM-1, blaSHV-1.

- **blaOXA-181 ST307 (n=6, 22%):** Three isolates co-harbored blaOXA-48. Carried on K. pneumoniae KP3 plasmid KP3-A.

- **Additional sporadic STs:** ST17 (n=2), ST25, ST45, ST297 (n=1 each).

- **Transmission networks:**

<!-- -->

- ST307 index case on October 10, 2019 (Pt1); subsequent cases linked by \<10 SNPs; intermediate host or environmental source suggested.

- ST152 index case on November 15, 2019 (Pt4); Pt4 died the next day, but transmission continued through intermediate sources; nine patients linked directly to Pt4; further transmission chains identified among patients moving between wards A and B.

<!-- -->

- **IPC audit findings (external, January 2020):**

<!-- -->

- Bed occupancy exceeded approved capacity by 60% in ward A (64 admissions vs 40 beds).

- Bed-to-nurse ratio 5:1 (target 3:1).

- Adherence to sterilization/disinfection \<50%.

- Hand hygiene supplies initially inadequate but improved.

- No SOP for multidose vials; no designated area for IV fluid mixing.

<!-- -->

- **Follow-up (March 2020 – May 2021):** 11 additional CRKP cases (29% of K. pneumoniae isolates), but WGS not performed. Hand hygiene adherence maintained \>96% via peer monitoring.

**Public health action:**

1.  **Immediate IPC interventions (November 2019 onward):**

- Cohorting and isolation of colonized/infected babies.

- Enhanced cleaning of the unit (multiple rounds).

- Hand hygiene monitoring for staff and parents; alcohol-based dispensers installed at each bed; elbow-operated taps installed.

- Development of SOPs for sterilization/disinfection; staff signed to demonstrate understanding.

2.  **Staffing and capacity interventions:**

- Attempted to reroute maternity cases when bed capacity reached (unsustainable during COVID-19).

- Established an integrated IPC and occupational health team.

3.  **Antimicrobial stewardship:** Committee established (implementation delayed due to COVID-19).

4.  **Surveillance recommendations:**

- Continued monitoring of endemic carbapenemase genes (blaNDM, blaOXA-48 variants) in healthcare settings.

- Enhanced genomic surveillance for ST307 superclone, which has spread across \>40 hospitals in three South African provinces.

5.  **Infrastructure improvements:**

- Recommended converting milk room into kangaroo mother care unit (not sustained due to COVID-19).

6.  **National guidance:** Called for a nationally endorsed prevention strategy for neonatal healthcare-associated infections, including adequate staffing, bed occupancy limits, and sustained IPC resources.

# 8.2 *Escherichia coli*

*Escherichia coli* is a facultatively anaerobic, rod‑shaped bacterium that is a ubiquitous commensal of the gastrointestinal tract of humans and warm‑blooded animals but also includes lineages that cause intestinal and extraintestinal infections. The extraintestinal pathogenic variants are a leading cause of extraintestinal infections, including urinary tract infections (UTIs) and bloodstream infections (BSIs) (Kaper et al., 2004; Dale & Woodford, 2015). *E. coli* is one of the common causes of bacteremia and sepsis globally, contributing significantly to the overall burden of sepsis‑related morbidity and mortality. According to the World Health Organization (WHO), more than 40% of *E. coli* infections worldwide (in the WHO <span class="mark">African Region exceed 70%</span>) are now resistant to third‑generation cephalosporins, the primary choice of treatment for severe bloodstream infections, and this resistance is driving increased mortality, particularly in low‑ and middle‑income countries (WHO, 2015).

Escherichia coli species have marked genomic plasticity, with a core genome shared across the strains and large accessory genes shaped by horizontal gene transfer, plasmids, pathogenicity islands, prophages, and recombination. While most commensal strains are harmless, a subset of lineages, collectively termed Extraintestinal Pathogenic *E. coli* (ExPEC), possess a specific repertoire of virulence factors that enable them to survive in normally sterile body sites, evade host defenses, and cause severe disease. Clinically significant ExPEC phenotypes repeatedly emerge in specific chromosomal backgrounds following the acquisition of various combinations of virulence and resistance determinants. (Köhler & Dobrindt, 2011; Denamur et al., 2021). The global dissemination of multidrug‑resistant (MDR) ExPEC clones, particularly those producing Extended‑Spectrum Beta‑Lactamases (ESBLs) and carbapenemases, poses a serious public health threat.

## Key Genomic Features of *E. coli*

## 8.2.1 *E. coli* Population Structure and Phylogroups

The population structure of E. coli is predominantly clonal, organized into distinct phylogenetic groups (phylogroups) that correlate with ecological niche and pathogenic potential. Modern genomic surveillance uses the expanded Clermont phylotyping system, which classifies isolates into eight main phylogroups (A, B1, B2, C, D, E, F, and G). ExPEC pathotypes are primarily grouped in phylogroups B2 and, to a lesser extent, D or F. These groups are most frequently isolated from human extraintestinal infections (e.g., urinary tract infections, sepsis) and are prevalent in the patient's own intestinal tract and in human-impacted environments like sewage. Phylogroups B2, F, and D are associated with higher virulence. Key ExPEC lineages frequently found in clinical collections include ST131, ST73, ST95, ST69, ST12, and ST14. Of these, ST131 stands out as the most significant high-risk pandemic lineage, notable for its ability to effectively colonize outside the intestines, cause disease, resist multiple drugs, and spread worldwide (Dale & Woodford, 2015; Schembri et al., 2015; Denamur et al., 2021).

Phylogroup assignment serves as an initial indicator of ecology and pathogenicity rather than a definitive classification. Being assigned to B2, D, or F suggests a higher likelihood that an isolate is associated with ExPEC backgrounds, but it does not alone confirm extraintestinal pathogenicity. On the other hand, isolates outside these groups should not be automatically regarded as clinically irrelevant, since non-B2/D E. coli can also cause extraintestinal infections, especially in immunocompromised individuals (Dale & Woodford, 2015; Köhler & Dobrindt, 2011).

## 8.2.2 *E. coli* Virulence Factors

Pathogenicity in E. coli is defined by the acquisition of specific virulence gene sets (via Horizontal Gene Transfer (HGT)) not typical of intestinal commensal strains. Unlike intestinal E. coli pathotypes, ExPEC pathotype does not cause diarrhea. ExPEC virulence factors are encoded on the bacterial chromosome, where they are usually located within pathogenicity islands (PAIs), or on plasmids. A common molecular definition classifies an E. coli as ExPEC if it possesses at least two of the following virulence-related genes: papA and/or papC, sfa/foc, afa/draBC, kpsM II, and iutA. These markers should be viewed as supportive evidence of an ExPEC-related genomic profile rather than a strict cutoff between pathogenic and commensal strains. Additional loci, such as hlyA, cnf1, capsule-associated genes, serum-resistance factors (protectins, that enable the bacteria to evade the host's complement system and survive bactericidal killing in the bloodstream), and siderophore systems (Enterobactin, Salmochelin, Yersiniabactin and Aerobactin - scavenge ferric iron (Fe³⁺) from host transport proteins like transferrin and lactoferrin) may further support interpretation. However, no small set of virulence markers can definitively distinguish ExPEC from commensal E. coli in all contexts (Dale & Woodford, 2015; Köhler & Dobrindt, 2011).

## 8.2.3 O (Lipopolysaccharide) and H (Flagellar) Antigens of *E. coli*

Extraintestinal Pathogenic E. coli (ExPEC) are defined by specific O (lipopolysaccharide or somatic) and H (flagellar) antigens that help them survive outside the gut, often causing UTIs, sepsis, and meningitis. Common ExPEC O-serogroups include O1, O2, O4, O6, O15, O18, O25b and O75, often paired with H1, H4, or H7 antigens. These antigens aid in virulence by resisting serum killing (evading complement-mediated killing) and mediating adhesion (Denamur et al., 2021). .

- O-Antigen (Somatic): Determined by the wzx (flippase) and wzy (polymerase) genes within the O-antigen gene cluster. Common sepsis-associated serogroups include O1, O2, O4, O6, O15, O18, and the pandemic O25b.

- H-Antigen (Flagellar): Determined by the fliC gene (or its homologs flkA, fllA, flnA).

- The O25b:H4 Link: This specific serotype is strongly linked to the globally disseminated multi-drug resistant ExPEC ST131 lineage.

Over 180 O (somatic) and 53 H (flagellar) antigen types have been identified in E. coli. These serve as primary markers for classifying pathogenic strains into serogroups (O Antigen only) and serotypes (O Antigen + H Antigen). Serotyping remains valuable in ExPEC genomics because specific O- and H-antigen combinations often highlight important clonal lineages. When combined with phylogroup, sequence type, virulence profile, and resistance determinants, they provide comprehensive insights (Köhler & Dobrindt, 2011; Schembri et al., 2015). These antigens are vital for vaccine development, as they are highly exposed on the bacterial surface. This exposure enables the formation of serotype-specific vaccines targeting prevalent and antibiotic-resistant strains, such as the pandemic O25b:H4 serotype.

## 8.2.4 Antimicrobial Resistance (AMR) Mechanisms

While the wild-type E. coli lacks many acquired AMR determinants, clinically important resistance is frequently mediated by acquired beta-lactamases, plasmid-mediated resistance genes, and chromosomal mutations. The primary driver of the global AMR crisis is due to its ability to rapidly accumulate resistance via horizontal gene transfer (HGT) and vertical chromosomal evolution. In sepsis pathogen surveillance, distinguishing between these two pathways is essential for identifying high-risk pandemic lineages.

**A. Acquired Resistance (Horizontal Gene Transfer)**

E. coli serves as a major reservoir for mobile genetic elements (MGEs), such as plasmids, gene cassettes, integrons, insertion sequences, transposons and bacterial phages IncF plasmids, which facilitate the spread of the following priority mechanisms:

- Extended-Spectrum beta-Lactamases (ESBLs)- the enzymes that confer resistance to third-generation cephalosporins and are frequently co-located on plasmids with other AMR genes

- Carbapenemases (Metallo-beta-lactamases: bla_NDM and bla_VIM, and Serine-carbapenemases: bla_OXA-48-like and bla_KPC) - the enzymes that confer resistance to carbapenem drugs

- Plasmid-Mediated AmpC (pAmpC): Enzymes like bla_CMY-2 and bla_DHA provide resistance to cephalosporins and are typically not inhibited by clavulanic acid, complicating phenotypic detection.

- Colistin Resistance: The plasmid-borne mcr gene family (predominantly mcr-1) is a vital surveillance marker. Detection of mcr in E. coli must be flagged immediately, as it compromises last-resort therapy for carbapenem-resistant infections.

- Aminoglycoside Resistance: High-level pan-aminoglycoside resistance is often mediated by 16S rRNA methyltransferases such as rmtB. Lower-level resistance is driven by aminoglycoside-modifying enzymes (AMEs) like aac(3)-II.

**B. Chromosomal Mutations (Vertical Evolution)**

Certain high-level resistance phenotypes in E. coli are the result of specific, stable chromosomal modifications that are characteristic of "high-risk" clones:

- Fluoroquinolone Resistance (QRDR): High-level ciprofloxacin resistance is primarily driven by mutations in the Quinolone Resistance-Determining Regions (QRDR). For example, gyrA: mutations at positions S83L and D87N, parC: mutations at position S80I.

Note: The "triple mutation" (gyrA S83L/D87N + parC S80I) is the definitive genomic signature of the pandemic ST131-H30Rx sublineage.

- Enhanced Carbapenem Resistance (Porin Loss): E. coli can develop a carbapenem-resistant phenotype without a carbapenemase through the loss or truncation of outer membrane porins, specifically ompC and ompF. When combined with high-level production of ESBLs or AmpC, these permeability defects significantly reduce carbapenem susceptibility.

## 8.2.5 Pathogen-Specific Analysis and Interpretation

For all initial processing steps, including raw read quality control, adapter trimming, contamination check, species confirmation, and de novo assembly, please refer to the ‘Standard Bioinformatics Workflows - core bioinformatics steps’ section of this guidance. Once a high-quality assembly (FASTA) is obtained, proceed with the E. coli-specific analysis detailed below.

### 8.2.5.1. Phylogenetic Grouping (Phylogrouping)

Phylogrouping is the primary step in assessing the ecological niche and pathogenic potential of E. coli isolates. It allows practitioners to differentiate between commensal strains and potential extra-intestinal pathogenic E. coli (ExPEC).

**Clinical Significance & Interpretation**

- High-Risk Groups: Most sepsis-associated and ExPEC isolates belong to phylogroups B2 or D.

- Actionable Flag: Any isolate assigned to phylogroup B2 that also carries high-priority AMR markers (e.g., blaCTX-M-15) must be prioritized. This profile is characteristic of high-risk pandemic clones, such as ST131, which require immediate epidemiological follow-up.

**In Silico Phylogrouping:** Current tools simulate the extended Clermont quadruplex PCR method. This targets specific marker genes, chuA, yjaA, and the DNA fragment TspE4.C2, along with additional markers to assign isolates to one of the eight primary phylogroups (A, B1, B2, C, D, E, F, G) or cryptic clades.

**Recommended Bioinformatics Tools:** The following tools are recommended for in silico phylogrouping. These tools simulate the experimental PCR markers and are prioritized based on their accuracy and utility in public health workflows.

1.  **ClermonTyping** (The Gold Standard): This is the most comprehensive *in silico* implementation of the extended Clermont method. It is highly recommended for research-grade analysis and for identifying cryptic clades or rare lineages. It offers 99% concordance with laboratory-based assays.

- Web Interface: [<u>http://clermontyping.iame-research.center/</u>](http://clermontyping.iame-research.center/)

- Command Line (CLI) for Batch Processing: [<u>https://github.com/A-BN/ClermonTyping</u>](https://github.com/A-BN/ClermonTyping)

2.  **EzClermont**:EzClermont is suitable for rapid screening of the phylogroups. For comprehensive surveillance use ClermonTyping (the extended Clermont method) or the phylogroup assignment built into EnteroBase.

- Web App (Single Sample): [<u>https://www.ezclermont.org/</u>](https://www.ezclermont.org/)

- Command Line (CLI): [<u>https://nickp60.github.io/EzClermont/</u>](https://nickp60.github.io/EzClermont/)

### 8.2.5.2 *In Silico* Serotyping (O and H Antigens)

In silico serotyping of E. coli uses WGS data to predict O (somatic) and H (flagellar) antigens by matching against databases of known E. coli serogroup genes. This approach provides rapid, accurate, and cost-effective alternatives to traditional lab-intensive, antibody-based agglutination assays, enabling quick identification of pathogenic strains (e.g., O157:H7) and outbreak surveillance.

**Clinical Significance & Interpretation**

Lineage Identification: Serotyping serves as a vital cross-check for MLST and phylogrouping results.

High-Risk Pandemic Clone Flag: Identifying the O25b:H4 serotype is a critical genomic diagnostic for the ST131 lineage (specifically the B2-ST131 clade). In the context of sepsis or hospital-acquired infections, this serotype should trigger immediate antimicrobial resistance (AMR) profiling, as it is frequently associated with ESBL production (e.g., blaCTX-M-15).

In *silico* methodology bioinformatics tools typically use a BLAST-based or mapping-based approach to identify specific genetic markers:

- O-antigen: Targeted via the wzx (flippase), wzy (polymerase), wzt, and wzm (ABC transporter) genes.

- H-antigen: Targeted via the fliC gene (and occasionally flkA, fllA, or flnA variants).

**Recommended Bioinformatics Tools**

> **A.** **ECTyper** (Recommendation for Batch Processing) Developed by the Public Health Agency of Canada (PHAC-NML), ECTyper is a rapid standalone tool that provides both serotype prediction and species verification. It is highly robust, handles both raw reads and assemblies, and is optimized for large-scale surveillance pipelines. The Command Line (CLI) is found at: [<u>https://github.com/phac-nml/ecoli_serotyping</u>](https://github.com/phac-nml/ecoli_serotyping). ECTyper is also available as a wrapper in Galaxy ([<u>https://usegalaxy.eu/?tool_id=ectyper</u>](https://usegalaxy.eu/?tool_id=ectyper)) and EnteroBase.
>
> **B.** **SerotypeFinder:** Maintained by the Center for Genomic Epidemiology (CGE), this tool uses a highly curated database of O and H antigen genes. It is the preferred choice for users who require a user-friendly web interface for single-sample analysis or for verifying specific gene hits ([<u>ttps://cge.food.dtu.dk/services/SerotypeFinder/</u>](https://cge.food.dtu.dk/services/SerotypeFinder/)). SerotypeFinder also has a CLI service that contains one Python script, serotypefinder.py, at [<u>https://bitbucket.org/genomicepidemiology/serotypefinder/src/master/</u>](https://bitbucket.org/genomicepidemiology/serotypefinder/src/master/).

### 8.2.5.3 Virulence Factor Detection

Distinguishing ExPEC from commensal *E. coli* and tracking virulent clones requires systematic virulence genotyping. The following are the recommended tools or workflow for detecting these virulence genes in silico.

- **ABRicate** ([<u>https://github.com/tseemann/abricate</u>](https://github.com/tseemann/abricate)) with the VFDB database - widely used, command-line, and batch-capable.

- **VirulenceFinder** from CGE ([<u>https://cge.food.dtu.dk/services/VirulenceFinder/</u>](https://cge.food.dtu.dk/services/VirulenceFinder/)) - web and local option, curated *E. coli* virulence genes.

Detection of more than two ExPEC-defining virulence genes (e.g., papC, sfaS, iutA, kpsMTII) in a phylogroup B2 or D background strongly suggests an ExPEC pathotype and warrants enhanced surveillance.

### 8.2.5.4 Integrated Genomic Platforms

For practitioners who prefer a comprehensive suite (all-in-one analysis) that combines phylogrouping with MLST, AMR detection, and phylogenomic visualization, these global platforms are recommended. They allow for easy comparison of local isolates against global datasets.

1.  **EnteroBase (**[<u>https://enterobase.warwick.ac.uk</u>](https://enterobase.warwick.ac.uk)): EnteroBase is the largest curated database and analysis platform for Escherichia and other enteric bacteria. On upload, every genome automatically receives:

- Species confirmation and phylogroup assignment (via internal implementation of the Clermont method).

- Achtman 7‑locus MLST and assignment to a HierCC core‑genome MLST (cgMLST) cluster at multiple resolutions. A threshold of ≤5 allele differences (HC5) is widely used to flag recent transmission or outbreak clusters.

- In silico O:H serotype prediction.

- AMR gene and plasmid replicon detection.

- cgMLST-based hierarchical clustering (HierCC) and interactive tree visualization. Pairwise SNP distances can also be calculated.

> Because EnteroBase contains thousands of global E. coli genomes, it enables direct comparison of local sepsis isolates against international populations, making it invaluable for detecting novel high‑risk clones or emerging resistance patterns.

2.  **Pathogenwatch** ([<u>https://pathogen.watch</u>](https://pathogen.watch)): it provides a streamlined, public‑health‑focused interface for E. coli. It draws on the same cgMLST scheme and curated databases as EnteroBase, but emphasises rapid interpretation and easy sharing of results. Key features include:

- MLST, phylogroup, serotype, AMR, and virulence profiles.

- An interactive core‑genome phylogeny with metadata overlay (time, location, sequence type, resistance markers).

- Collection‑based outbreak investigation, where users can group isolates, visualize clusters, and export reports.

> Pathogenwatch is particularly suited to frontline public health staff who need actionable outputs without extensive bioinformatics training.

3.  **Kleborate (Escherichia Module)** (https://github.com/klebgenomics/Kleborate) is the recommended command-line tool for batch screening of MLST, phylogroup (via Clermont method), in silico serotype (via ECTyper), and acquired AMR genes/mutations (via AMRFinderPlus). For virulence-based pathotyping, supplement Kleborate’s output with a dedicated virulence detection step (see 6.8.2). Although Kleborate was originally developed for Klebsiella, the package includes a dedicated ‘–preset escherichia’ that runs only the modules relevant to Escherichia species (https://kleborate.readthedocs.io/en/latest/Escherichia_modules.html). Once the escherichia preset is selected, the tool automatically verifies that the input genome belongs to the Escherichia genus and then runs a series of analyses in a single workflow. For sepsis surveillance, the following module’s flag provide the most actionable information for ExPEC isolates:

- **escherichia\_\_mlst_achtman:** for the 7 locus (adk, fumC, gyrB, icd, mdh, purA, recA.) Achtman MLST (Institut Pasteur scheme also available). Imprecise matches are flagged with \* and ST calls are reported as e.g. 131-1LV (single locus variant).

- **escherichia\_\_ezclermont:** for phylogroup and cryptic clade assignment using the Clermont PCR logic

- **escherichia\_\_ectyper:** for *in silico* O and H antigen serotyping via ECTyper

- **escherichia\_\_amr**: for acquired AMR genes and point mutations using AMRFinderPlus. The AMR module uses the latest AMRFinderPlus database

Note that Kleborate does not include plasmid replicon detection; PlasmidFinder must be run separately. After serotyping or alongside AMR detection, it is recommended to perform plasmid replicon typing in standalone workflows, either the web PlasmidFinder ([<u>https://cge.food.dtu.dk/services/PlasmidFinder/</u>](https://cge.food.dtu.dk/services/PlasmidFinder/)) or the command-line ([<u>https://bitbucket.org/genomicepidemiology/plasmidfinder/src/master/</u>](https://bitbucket.org/genomicepidemiology/plasmidfinder/src/master/)).

**Guidance for selecting a platform**

- EnteroBase is the most comprehensive choice for laboratories that can upload data to a centralized web service and need access to global contextual genomes.

- PathogenWatch is ideal for rapid outbreak visualization and for users who prefer a focused, curated interface.

- Kleborate is the best option for high‑volume batch screening, offline environments using command-line, or scenarios where local execution is mandatory for data governance reasons.

#### 8.2.5.5 Caveats and Limitations in E. coli WGS Analysis, Interpretation, and Reporting

The following are caveats during WGS analysis of *E. coli* isolates.

Phylogroup assignment indicates a strain's evolutionary lineage rather than its pathogenicity in *E. coli*. While phylogroup B2 increases the likelihood of an ExPEC-associated genomic profile, it does not confirm pathogenicity, as B2 also contains many commensal strains. Conversely, isolates outside B2/D/F can still cause invasive disease, especially in neonates and immunocompromised patients (Denamur et al., 2021).

The two-gene threshold (≥2 of 5 canonical ExPEC markers) is widely applied but imperfectly sensitive and specific across all clinical contexts (Köhler & Dobrindt, 2011). Virulence gene carriage represents genomic potential, not confirmed pathogenic activity; gene presence does not establish that the organism caused disease in a given patient. Virulence databases (VFDB, VirulenceFinder) carry geographic and phylogenetic biases; novel or regionally uncommon variants may be absent. Report virulence profiling results as "genomic features consistent with an ExPEC pathotype," specifying the database and version, and never as a standalone clinical diagnosis.

Isolates sharing the same sequence type may differ by hundreds to thousands of SNPs, reflecting distinct clonal lineages without recent epidemiological connection (Denamur et al., 2021). ST131 is particularly heterogeneous and must not be reported without sublineage designation (Clade A, B, or C; H30R or H30Rx). Single-locus variants (SLVs, e.g., ST131-1LV) require cgMLST or SNP-based confirmation before any transmission inference is made. Whole-genome SNP analysis, or cgMLST is required for all outbreak investigation and transmission analysis.

The HC5 threshold (≤5 allele differences, EnteroBase HierCC) is a provisional indicator of potential recent transmission, not a biological absolute. Closely related outbreak isolates can exceed HC5 due to within-host evolution; unrelated isolates can fall within HC5 through convergent allele acquisition or endemic clone persistence. Different cgMLST schemas (EnteroBase vs. other platforms) produce non-comparable allele distances and must not be cross-compared without conversion. *E. coli* accumulates approximately 1-3 core-genome SNPs per genome per year, so collection dates must always be considered when interpreting cluster boundaries. Genomic cluster membership must be verified by epidemiological evidence before any transmission conclusion is drawn.

In silico AMR prediction does not perfectly predict phenotypic MICs or AST results for all drug-pathogen combinations. Key discordance risks for *E. coli* include:

- **Porin-mediated carbapenem resistance**: Carbapenem resistance driven by combined OmpC/OmpF porin loss and ESBL/AmpC overproduction is not detected by tools screening only for carbapenemase genes. A negative carbapenemase result does not exclude clinically significant carbapenem resistance.

- **Heteroresistance**: Resistant subpopulations coexisting within a predominantly susceptible culture cannot be reliably detected by WGS.

- **Database gaps**: Novel resistance genes or mutations absent from current database versions will be missed entirely.

MLST allele assignments, serotype predictions, AMR gene calls, and virulence profiles depend on active database versions. Updates can change results for the same genome; reanalysis with updated databases may differ from original findings, complicating trend interpretation. Record and report database names and versions in analysis statements. For surveillance, fix database versions by period and document transitions.

Core-genome SNP phylogenetics relies on reference genome choice. Using a distantly related reference causes misalignment, false SNPs, and inaccurate branch lengths. Use a complete, closed reference genome matching the MLST sequence type and, if possible, the same sublineage as the study isolates. For ST131, use a validated H30Rx or H30R reference. Due to high recombination in phylogroup B2, employ recombination-aware tools like Gubbins or ClonalFrameML.

Illumina short-read assemblies for *E. coli* typically produce 50-200 contigs, often fragmenting large, circular AMR-carrying plasmids (\>100 kb) and misassembling regions with IS elements, integrons, and tandem resistance gene duplications. Accurate AMR gene placement (chromosome vs. plasmid) and MGE context require long-read or hybrid sequencing. Short-read-only assemblies are inadequate for precise plasmid characterization in outbreak investigations.

Genomic data alone cannot determine the causality of infection, confirm transmission pathways, or replace culture and phenotypic testing in patient care. These genomic results need to be combined with clinical and epidemiological information.

## 8.2.6 *E. coli* case study examples

**Case Study \#1 - Malawi Neonatal Invasive Escherichia coli Genomic Surveillance (2012-2021) (<span class="mark">Pearse, O. et al., 2025)</span>**

[**<u>https://www.nature.com/articles/s43856-025-01007-1</u>**](https://www.nature.com/articles/s43856-025-01007-1)

**Aim:** To characterize the genomic diversity, antimicrobial resistance trends, and O‑antigen and H‑antigen profiles of *E. coli* causing invasive disease in neonates at a large tertiary hospital in Malawi, and to assess the potential coverage of O‑antigen vaccines in clinical development for this high‑burden, low‑resource population.

**Surveillance Strategy/System Design**

- Setting: Queen Elizabeth Central Hospital (QECH), Blantyre, Malawi - a government tertiary referral hospital serving southern Malawi (population ~800,000). Care is free at the point of delivery. Chatinkha nursery (~5,000 admissions/year) and paediatric nursery. Diagnostic blood and CSF culture services provided by Malawi‑Liverpool‑Wellcome (MLW) Programme since 1998.

- Sampling strategy: All *E. coli* isolates from neonates (\<29 days old) with bloodstream or cerebrospinal fluid (CSF) infection between September 2012 and March 2021 (about 8.5 years) were selected for whole genome sequencing.

- Isolate types and sample size: Blood cultures (81.1%) and CSF (18.9%). From 207 isolates identified; 169 (81.6%) successfully recovered and passed QC for sequencing. 203 samples from individual neonates (four had two distinct *E. coli* morphologies)

- Reason for sampling strategy: To establish robust genomic surveillance in a high‑burden, low‑resource setting, monitor clonal and antigenic diversity over time, assess the potential utility of O‑antigen vaccines under development (ExPEC4V, ExPEC9V), and generate locally relevant evidence for vaccine design and empiric therapy.

- Laboratory methods: Routine diagnostic blood/CSF culture; disc diffusion antimicrobial susceptibility testing; isolates stored at −80 °C on microbank beads.

- Sequencing approach: Illumina NovaSeq SP (150 bp paired‑end, 364‑plex) for short reads; Oxford Nanopore MinION for 14 selected isolates with unresolved O‑types.

- Use case(s): Routine genomic surveillance, AMR mechanism detection and monitoring, detection of high‑risk clones and population structure, vaccine target coverage assessment.

**Ethical / Legal Considerations and Approvals**

- Beneficence and non‑maleficence: The study used retrospective, anonymized residual diagnostic isolates; no additional patient interventions were performed. The research posed no more than minimal risk. Findings on vaccine coverage and AMR trends have potential public health benefits.

- Distributive justice: Not reported. The study did not explicitly address equity or inclusion of underserved populations as a research design goal.

- Privacy and autonomy: Patient data (residual diagnostic samples) were anonymized. The ethics committee waived informed consent for this retrospective study (COMREC P.06.20.3071).

- Data custodianship: Raw reads deposited in the European Nucleotide Archive (ERP120687 for short reads; PRJNA1121524 for long reads). Aggregated data in supplementary tables available on GitHub. Codes for figure reproduction are available on GitHub (https://github.com/ohapearse/invasive_neonatal_ecoli).

- Transparency and accountability: Not reported beyond publication in an open‑access journal.

- Legal authorization: Ethical approval obtained from Kamuzu University of Health Sciences College of Medicine Research Ethics Committee (COMREC P.06.20.3071). Retrospective study of samples collected during clinical care; consent waived.

- Public health integration: The paper discusses potential implications for ExPEC vaccine development and treatment guidelines. It highlighted the need for higher‑valency or alternative vaccine strategies and reinforced IPC and antimicrobial stewardship priorities.

**Data Analysis**

**Bioinformatics pipeline(s):**

- Species confirmation & QC: Kraken v1.1.1 – any sample with \>5% non‑*E. coli* or unclassified reads was excluded.

- Typing: mlst v2.23 (ST determination); EnteroBase v1.2.0 (novel ST assignment).

- AMR detection: AMRFinderPlus v3.10.40.

- Serotyping (O:H): SRST2 v0.2.0 with EcOH database; ECTyper for Oxford Nanopore assemblies.

- Manual subtyping (vaccine‑relevant subtypes): O1A/O1B, O18A/O18B, O25A/O25B using specific primers, IS element analysis, and operon structure as described previously.

- Short‑read assembly: SPAdes v3.14.0 (k‑mer lengths 41–127 optimised). Assembly improvement: SSPACE v2.0234 (scaffolding) and GapFiller v1.1124 (gap filling). Assembly statistics from Sanger Pathogens pipeline (assembly-stats; https://github.com/sanger-pathogens/assembly-stats).

- Long‑read assembly (hybrid): guppy v2.6.1 (basecalling, super‑accurate model); porechop v0.2.49 (adapter removal); filtlong v0.2.23 (low‑quality read removal). Flye v2.9.33911 (long‑read‑first assembly); Bandage v0.8.1 (visualisation). Polishing: Medaka v1.8.0 (long‑read), then Polypolish v0.6.0 and Pypolca v0.3.0 (short‑read).

- Annotation: PROKKA v1.5 with RefSeq genus‑specific databases.

- Statistical & visualisation: R environment (tidyverse, lubridate, ggplot2, ghibli, RColorBrewer, pals, MetBrewer, gggenes, ggpubr); glm (binomial family) for AMR trend analysis; Chi‑squared tests for categorical comparisons; rarefaction curves for vaccine coverage.

- QC thresholds: Samples with \<20 or \>200 contigs, genome size \<4.4 Mb or \>5.6 Mb excluded; isolates with \>5% heterozygous SNPs excluded; Kraken \>5% non‑target reads excluded.Final exclusions: 17 isolates excluded for contamination, 17 for poor assembly (12 failed both). One duplicate removed. Final n=169.

- Typing methods: MLST (7‑locus Achtman); in silico O:H serotyping via SRST2 and ECTyper; manual confirmation of vaccine‑relevant O‑subtypes.

- AMR detection: AMRFinderPlus; compared to disc diffusion AST. Trend analysis using generalised linear model (binomial family) over time.

- Phylogenetic/cluster analysis: Rarefaction curves for ST, O‑type and H‑type accumulation; comparison of O‑type distribution across years; identification of ten putative novel O‑types via long‑read sequencing and manual curation of the O‑antigen locus (galF–gnd region).

- Statistical/epidemiological integration: Generalised linear model (glm, binomial family) for AMR trends over time; Chi‑squared tests for categorical comparisons (e.g., ST410 association with CSF); rarefaction analysis for hypothetical vaccine coverage (ExPEC4V, ExPEC9V, and custom valency curves). Early‑onset vs late‑onset sepsis comparisons for AMR prevalence.

- Visualisation tools: ggplot2 (rarefaction curves, AMR trends bar charts, O‑type and H‑type frequency plots), gggenes (O‑antigen locus structures for novel types), ggpubr (composite figures).

**Note:** *This study used tools (Kraken v1.1.1, SSPACE, GapFiller) now outdated in favor of faster, more accurate alternatives. Current pipelines should use Kraken2/Bracken for taxonomic classification and Unicycler or Dragonflye for hybrid assembly. This case study remains valuable for its epidemiological insights, but future projects should adopt the contemporary recommended tools*

**Data Sharing Strategy**

- Raw reads (short read): European Nucleotide Archive (ENA) under ERP120687; individual accessions in Supplementary Data 1 of the publication.

- Raw reads (long read): ENA/NCBI under PRJNA1121524; accessions in Supplementary Data 2.

- Metadata: Detailed per‑isolate information (ST, O‑type, H‑type, AMR profile, specimen type, year) in Supplementary Data 3; blood culture/CSF trends data in Supplementary Data 4; AMR gene data in Supplementary Data 5.

- Code / pipelines: GitHub repository (https://github.com/ohapearse/invasive_neonatal_ecoli) and Zenodo (https://doi.org/10.5281/zenodo.15622585) for reproducing all figures

- Restrictions: None – open access.

**Major Findings:**

This 8.5‑year genomic surveillance of neonatal invasive E. coli in Malawi revealed extreme diversity (71 STs, 63 O‑types, 34 H‑types) with rapid temporal turnover (70% of STs detected in only one year) and identified ten previously undescribed O‑antigen types. Vaccine coverage analysis showed that the ExPEC9V vaccine (developed for high‑income countries) would protect against only 38% of Malawian neonatal isolates, and an O‑antigen vaccine would require 30 different O‑types to achieve 80% coverage. Rising resistance to empiric antibiotics was quantified: ceftriaxone resistance increased from 0% (2012) to 46% (2020, p=0.00014) and gentamicin resistance from 20% to 41% (p=0.0035), driven largely by blaCTX‑M‑15 and aac(3) genes. The high‑risk clone ST410 (O8, H9) was disproportionately associated with meningitis (75% of ST410 isolates from CSF versus 1.5% of other STs) and carried extensive AMR genes, leaving only meropenem as a treatment option.

**Public health actions:**

- Recommendation against introduction of current ExPEC vaccines in Malawi without local coverage assessment;

- Updated national empiric therapy guidelines to reflect rising ceftriaxone and gentamicin resistance;

- Enhanced clinical monitoring for ST410 bloodstream infections as a flag for possible meningitis;

- Reinforcement of antimicrobial stewardship to preserve meropenem; and

- There is a need for larger such genomic surveillance studies in sub‑Saharan Africa to enable a better understanding of the *E. coli* present and to enable effective vaccines to be developed (to capture undescribed O‑antigen diversity and inform equitable vaccine development)

**Case Study \#2: Clinical Characteristics and WGS-Based Surveillance of *Escherichia coli* Community-Onset Bloodstream Infections at a Non‑Tertiary Hospital in China (2018–2019)**

[<u>https://www.frontiersin.org/journals/microbiology/articles/10.3389/fmicb.2021.748471/full#DS1</u>](https://www.frontiersin.org/journals/microbiology/articles/10.3389/fmicb.2021.748471/full#DS1)

Aim: To examine the clinical characteristics of patients with *E. coli* community‑onset bloodstream infections (EC‑COBSI) at a non‑tertiary hospital in China, characterize the population structure, antimicrobial resistance, virulence gene profiles, and genetic relationships of the isolates using whole‑genome sequencing (WGS), and identify factors associated with ESBL status and patient outcomes.

**Surveillance Strategy/System Design**

- Setting: The First Hospital of Putian City, a non‑tertiary (~1,200 beds) hospital in Putian, eastern China. The hospital participates in the Blood Bacterial Resistant Investigation Collaborative System (BRICS) program.

- Sampling strategy: Consecutive patients with monomicrobial *E. coli* bloodstream infections were enrolled retrospectively from 1 January 2018 to 31 December 2019. Community‑onset infection is defined as a positive blood culture within 48 hrs of hospital admission.

- Isolate types: Blood cultures only

- Sample size: 148 isolates (from 148 patients). Exclusions: isolates from infants, repetitive strains, poor sequencing coverage.

- Reason for sampling strategy: To provide a comprehensive WGS‑based characterization of EC‑COBSI at a non‑tertiary hospital (underrepresented in previous Chinese studies that focused on tertiary hospitals or resistant strains only) and to link clinical metadata with genomic features.

- Laboratory methods: Blood cultures using BacT/ALERT®3D; species identification by MicroScan WalkAway 96 plus System; antimicrobial susceptibility testing (AST) by MIC (20 agents) per CLSI 2020; ESBL phenotype confirmed by synergy testing.

- Sequencing approach: Illumina platform (details as per Raven et al., 2016). Reads mapped to *E. coli* reference EC958 (NZ_HG941718.1) for SNP calling.

- Use case(s): Routine genomic surveillance, AMR mechanism detection, detection of high‑risk clones, population structure analysis, virulence profiling, pangenome analysis, genome‑wide association study.

**Ethical/Legal Considerations and Approvals**

- Beneficence and non‑maleficence: The study used retrospective, anonymized residual diagnostic isolates and posed no additional patient risk.

- Distributive justice: Not reported. The study did not explicitly address equity or inclusion of underserved populations as a research design goal.

- Transparency and accountability: Published open access.

- Public health integration: Results informed local empirical therapy guidelines (e.g., low resistance to carbapenems and BLBLICs) and highlighted the need for community‑level interventions targeting the living environment and gut colonization.

- Privacy and autonomy: Ethical approval obtained from the Committee on Human Research, Publications and Ethics of the First Hospital of Putian City (No. 2021‑004). Written informed consent was waived in accordance with national legislation and institutional requirements; data were anonymised.

- Data custodianship: Raw sequences deposited in NCBI under BioProject PRJNA747133. Supplementary data (AMR genes, virulence genes, STs) provided in online supplementary files.

- Data protection: No patient identifiers in public datasets.

- No other ethical/legal considerations is reported.

**Data Analysis**

**Bioinformatics pipeline(s):**

- Read mapping: SAMtools mpileup (Li et al., 2009)

- SNP calling: VarScan (Koboldt et al., 2013)

- Recombination filtering & MGE masking: Gubbins (Croucher et al., 2015)

- Phylogenetic tree: RAxML (Stamatakis, 2015) with GTR + gamma model, 1000 bootstrap replicates

- Minimum spanning tree (cgMLST): PHYLOViZ v2.0 with geoBURST Full MST algorithm (Nascimento et al., 2017)

- Pangenome analysis: Roary (Page et al., 2015); accessory gene accumulation curves; NMDS (vegan package in R)

- Plasmid typing: PlasmidFinder (Carattoli et al., 2014)

- Genome‑wide association study (GWAS): Kruskal‑Wallis test with Bonferroni correction (Brynildsrud et al., 2016)

- QC thresholds: Poor sequencing coverage excluded; not further detailed.

- Typing methods: MLST; serotyping; fimH subtyping; phylogroup assignment.

- AMR detection: AST plus molecular detection of resistance genes and QRDR mutations (not specified which tool for gene detection).

- Virulence detection: Not explicitly described

- Phylogenetic / cluster analysis: SNP‑based maximum likelihood tree; cgMLST minimum spanning tree; presumptive transmission defined as ≤10 SNP distance between isolates (in absence of epidemiological links).

- Statistical / epidemiological integration: Compared patient characteristics by ESBL status, sex, infection source (UTI, IAI, primary bacteremia) using χ², t‑test, Mann‑Whitney U; multivariate logistic regression for mortality; accessory gene diversity by ST; GWAS for ST95, ST131, ST69.

- Visualization tools: Manhattan plots, NMDS plots, accessory gene accumulation curves, RAxML tree, MST (PHYLOViZ).

**Data Sharing Strategy**

- Raw reads: NCBI BioProject PRJNA747133

- Metadata: Clinical and demographic data (age, sex, residency, comorbidities, infection source, therapy, outcome) in main tables (Table 1)

- Code / pipelines: Not deposited; standard public tools used

- Restrictions: None – open access

**Major Findings:**

This two‑year retrospective study of 148 *E. coli* community‑onset bloodstream infections at a Chinese non‑tertiary hospital found an overall 30‑day mortality of 9.5%, with no significant difference between patients infected with ESBL‑positive (35.1%) and ESBL‑negative isolates, despite higher inappropriate empirical therapy in the ESBL‑positive group (61.5% vs 91.4% appropriate, p\<0.001). All isolates remained susceptible to carbapenems, ceftazidime/avibactam, and tigecycline; blaCTX‑M‑14 was the most common ESBL gene (21.2% of ESBL+ isolates). One isolate carried mcr‑1.1 (polymyxin B resistance). The population was highly diverse: 59 sequence types, with ST95 (13.5%), ST131 (12.8%), and ST69 (8.1%) most prevalent. Intra‑abdominal infection was the leading source (38.8%), and isolates from these patients had lower frequencies of virulence genes. ST95 carried more virulence genes (e.g., ompT, pap, hlyF), while ST131 carried more antimicrobial resistance genes (e.g., blaCTX‑M, QRDR mutations). The minimum spanning tree identified three presumptive transmissions (≤10 SNPs) among ST1193 and ST131 isolates, but no epidemiological links were found, suggesting possible common environmental or food chain sources.

**Public health actions:**

- ESBL status alone should not dictate prognosis or empiric therapy escalation.

- targeted surveillance for community dissemination of ST131 (H30‑R/H30‑Rx clades) and ST95;

- recommendation for multi‑level prevention strategies targeting gut colonization and the living environment, as isolates from intra‑abdominal infections (likely gut translocation) were highly diverse and often less resistant; and

- Demonstration that non‑tertiary hospitals can effectively implement WGS‑based surveillance for community‑onset bloodstream infections.

# 8.3 Acinetobacter baumannii

**Overview**

*Acinetobacter baumannii* is a leading opportunistic, multidrug-resistant pathogen causing healthcare-associated sepsis in NICUs, adult ICUs, and among immunocompromised patients globally. It is known for intrinsic and acquired multidrug resistance (MDR), including carbapenem resistance (CRAB), which is classified as a critical priority by the WHO. *A. baumannii* possesses a relatively small genome (~3.9-4.2 Mbp) with a conserved core genome and a highly variable accessory genome acquired through horizontal gene transfer. The population structure is largely clonal, dominated by two global high-risk international clones (IC1 and IC2) that drive the majority of multidrug-resistant infections worldwide and are responsible for outbreaks in hospitals worldwide. Genome GC content is ~39%. Key public-health-relevant features include extreme environmental persistence and rapid acquisition of resistance determinants.

*Acinetobacter baumannii* is a Gram-negative, strictly aerobic, non-fermenting coccobacillus and a high-priority opportunistic pathogen. It is classified in the "Critical Priority" tier of the World Health Organization (WHO) Bacterial Priority Pathogens List (BPPL) 2024, underscoring the urgent need for new antimicrobial treatments. It is a leading cause of healthcare-associated infections, particularly sepsis, ventilator-associated pneumonia, and wound infections in intensive care and burn units. The species is notorious for its extreme environmental resilience, capable of surviving on dry surfaces for up to five months, as well as its ability to form robust biofilms and rapidly acquire diverse antimicrobial resistance (AMR) determinants. Global estimates suggest that CRAB was alone responsible for approximately 57,000 deaths in 2019, making it one of the most lethal pathogen-drug combinations worldwide.

### 8.3.1 Background and Public Health Relevance

Acinetobacter baumannii is a critical priority pathogen and recognized as a leading cause of healthcare-associated sepsis due to its extreme environmental resilience and rapid evolution of multi-drug resistance. Capable of surviving on dry surfaces for a long time, it frequently colonizes hospital infrastructure, leading to prolonged outbreaks often dominated by the globally disseminated International Clones 1 and 2 (IC1 and IC2). While it is the most clinically significant member of the A. baumannii-calcoaceticus (ABC) complex, its phenotypic similarity to other members like A. pittii and the environmental A. calcoaceticus makes accurate identification challenging. Consequently, sequence-based confirmation (e.g., WGS or rpoB (RNA polymerase beta-subunit gene) sequencing) is mandatory to differentiate species with varying pathogenic potentials. Genomic surveillance is now indispensable for providing the high-resolution data required to track the acquisition of resistance to last-line agents, such as carbapenems, colistin, and cefiderocol, and to guide effective infection prevention and control (IPC) interventions.

####  8.3.2.1 Population Structure and International Clones

The global population structure of *A. baumannii* is highly clonal, dominated by a small number of successful epidemic lineages known as International Clones (ICs), or Global Clones (GCs). This structure is identified through two distinct Multilocus Sequence Typing (MLST) schemes: the Pasteur (Pas) scheme, which provides a stable backbone for broad phylogenetic classification, and the Oxford (Ox) scheme, which offers higher resolution for outbreak investigation. To date, at least twelve major ICs (IC1–IC12) have been described ([<u>https://acinetobacterbaumannii.no/overview/global-epidemiology/</u>](https://acinetobacterbaumannii.no/overview/global-epidemiology/)). International Clone 2 (IC2) (defined as ST2ᴾᵃˢ and represented by the ST92ᴼˣ, ST195ᴼˣ, and ST208ᴼˣ, ST451ᴼˣ lineages) is the most prevalent lineage worldwide, followed by International Clone 1 (IC1) (ST1ᴾᵃˢ/ST231ᴼˣ, ST81ᴼˣ, ST101ᴼˣ, ST109ᴼˣ). While these two clones drive the global burden of carbapenem resistance, the population structure continues to diversify with the emergence of regional threats, such as IC5 (ST79ᴾᵃˢ) in Latin America and IC9 (ST85ᴾᵃˢ) in the Middle East and North Africa. This clonal dominance is largely attributed to the stable maintenance of Acinetobacter Resistance Islands (such as AbaR1, AbaR3) and the rapid acquisition of mobile genetic elements, making these lineages the primary drivers of healthcare-associated sepsis. AbaRs are large, distinct segments of DNA within the chromosome of *A. baumannii* that cluster multiple antibiotic resistance genes together. They enable this pathogen to quickly acquire and spread multi-drug resistance (MDR), specifically in high-risk global clones (Fournier P et al., 2005).

#### 8.3.2.2 Genomic Typing: MLST and cgMLST

Precise characterization of *A. baumannii* may require a tiered approach, transitioning from broad lineage classification to high-resolution outbreak analysis. Multilocus Sequence Typing (MLST) remains the standard for defining global population structure through two co-existing 7-gene schemes: the **Pasteur scheme** (cpn60, fusA, gltA, pyrG, recA, rplB, rpoB), which is preferred for long-term epidemiological stability, and the **Oxford scheme** (gltA, gyrB, gdhB, recA, cpn60, gpi, rpoD), which offers higher resolution but is prone to technical artifacts like gdhB paralogy and gpi recombination. To address these limitations and provide the granularity needed for infection prevention and control (IPC), **core genome MLST (cgMLST)** has become the modern benchmark. Utilizing schemes of approximately 2,390 core genes, **cgMLST** allows for hierarchical clustering (**HierCC**). This enables laboratories to identify and support probable transmission chains (when integrated with epidemiological data) using standardized thresholds, typically ≤3 to 8 allelic differences for recent outbreaks, effectively resolving distinct sub-clusters within globally dominant sequence types like ST2ᴾᵃˢ.

***8.3.2.3 Capsule (KL) and Lipooligosaccharide Outer Core (OCL) Typing***

Beyond sequence typing, characterizing surface polysaccharides is essential for understanding *A. baumannii* virulence, immune evasion, and environmental persistence. Unlike many Gram-negative bacteria, *A. baumannii* lacks a structurally variable O-antigen; instead, surface diversity is driven by the chromosomal K locus (KL), responsible for capsular polysaccharide biosynthesis, and the OC locus (OCL), which encodes the lipooligosaccharide outer core. To date, over 230 KL and 20 OCL types have been identified, with KL2 being the most prevalent among clinical isolates. These loci are highly plastic and can vary even among isolates of the same sequence type (e.g., ST2), providing additional resolution for outbreak investigations and transmission tracking. In silico typing using tools like Kaptive is now a standard bioinformatic step, as these surface structures are primary targets for emerging treatments, such as phage therapy and monoclonal antibodies.

#### 8.3.2.4 Intrinsic and Acquired Antimicrobial Resistance Mechanisms

*A. baumannii* possesses a formidable resistome that combines baseline intrinsic defenses with a high capacity for acquiring mobile genetic elements (MGEs). Intrinsic resistance is driven by naturally low outer membrane permeability, the constitutive expression of RND-family efflux pumps (e.g., adeABC), and chromosomal beta-lactamases such as blaOXA-51-like and blaADC (Acinetobacter-derived cephalosporinase). Clinical carbapenem resistance (CRAB) most frequently arises from the acquisition of OXA-type carbapenemases-primarily (blaOXA-23), blaOXA-24/40), and blaOXA-58) or metallo-beta-lactamases like blaNDM. Resistance to last-line agents is also increasing: colistin resistance typically emerges through chromosomal mutations in the pmrAB regulatory system that modify lipid A, while cefiderocol resistance is increasingly linked to blaADC mutations and disrupted iron-uptake pathways (e.g., piuA, pirA). These genomic features necessitate the use of WGS to accurately profile the evolving resistome and guide therapeutic decision-making.

#### 8.3.2.5 Virulence Factors

The pathogenicity of A. baumannii is driven by a specialized "survival toolkit" that facilitates host colonization, nutrient acquisition, and immune evasion. Key genomic determinants include outer membrane protein A (ompA), which mediates adhesion to host cells and induces apoptosis, and the chaperone-usher pili (csu) and biofilm-associated protein (bap), which are essential for robust biofilm formation on medical devices. To survive the iron-restricted environment of the human bloodstream during sepsis, the pathogen utilizes high-affinity siderophores such as acinetobactin. Furthermore, the capsular polysaccharide (KL) provides a critical shield against complement-mediated killing, while Type VI Secretion Systems (T6SS) allow A. baumannii to outcompete commensal microbiota during infection. These factors, often co-located with resistance determinants on mobile genetic elements, enable the organism to transition from an environmental contaminant to a lethal cause of systemic sepsis.

###  8.3.3 Pathogen-Specific Analysis and Interpretation

For all initial processing steps, raw read QC, adapter trimming, contamination check, species confirmation, and de novo assembly, refer to the core bioinformatics section. Species confirmation is critical for the ABC complex: use Kraken2 or FastANI (≥ 95 % ANI to an *A. baumannii* type strain) and confirm the presence of the intrinsic blaOXA 51 like gene. Once you have a confirmed *A. baumannii* assembly, proceed with the pathogen-specific analyses below.

#### 8.3.3.1 Recommended Bioinformatics Tools for A. baumannii

For the genomic analysis of *A. baumannii*, the following tools and databases are recommended to ensure high-resolution characterization of lineage, resistance, and transmission dynamics.

| **Analysis Step**          | **Recommended Tool(s)**            | **Specific Parameters / Notes**                                                                                                                                |
|----------------------------|------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **MLST (Pasteur)**         | **mlst (Seemann)**                 | Use --scheme abaumannii. This scheme is the gold standard for global clone (GC/IC) identification and long-term surveillance.                                  |
| **MLST (Oxford)**          | **mlst (Seemann)**                 | Use --scheme abaumannii_2. Use alongside Pasteur for backward compatibility; be aware of *gdhB* paralogy and *gpi* recombination.                              |
| **cgMLST & Clustering**    | **chewBBACA** / **Pathogenwatch**  | Use for high-resolution outbreak detection. Pathogenwatch provides automated cgMLST and HierCC assignment upon assembly upload.                                |
| **Surface Typing**         | **Kaptive (v2.0.5+)**              | Use -k Abaumannii. Essential for identifying Capsule (**KL**) and Lipooligosaccharide (**OCL**) types, providing sub-ST resolution for outbreaks.              |
| **AMR Detection**          | **AMRFinderPlus**                  | Use --organism Acinetobacter_baumannii. Superior for detecting both acquired genes (e.g., *bla*OXA-23) and chromosomal mutations (*pmrAB*, *adeRS*).           |
| **Virulence Factors**      | **VFDB** (via **ABRicate**)        | Identifies determinants for biofilm (*csu*, *bap*), serum resistance (*pbpG*), and iron acquisition (*bas/bau* clusters).                                      |
| **Plasmid Typing**         | **AcinetobacterPlasmidTyping**     | BLAST against the curated *rep* database. Version 3.0 (2025) covers 258 *rep* types across R1, R3, and RP families.                                            |
| **Plasmid reconstruction** | MOB-suite                          | Identifies plasmid replicons and reconstructs plasmid structures. Essential for tracking the horizontal transfer of *resistance gene* plasmids across strains. |
| **MGE Identification**     | **MobileElementFinder**            | Critical for linking resistance genes to mobile elements (e.g., **ISAba1**-mediated carbapenemase expression).                                                 |
| **SNP Phylogeny**          | **Snippy** + **Gubbins**           | Reference-based variant calling. Mask recombination with Gubbins; a threshold of **≤10 SNPs** is is widely used to support outbreak clusters.                  |
| **Integrated Pipelines**   | **Bactopia** / **nf-core/bactmap** | Comprehensive, community-validated workflows for high-throughput assembly, typing, and pangenome analysis.                                                     |

#### 8.3.3.2 Caveats and Limitations

- **Species identification is not trivial:** MALDI TOF and biochemical tests cannot distinguish ABC species. Confirm with genome-based methods (Kraken2, FastANI) and verify blaOXA 51-like presence.

- **Recombination can mask phylogenetic signal**: *A. baumannii* undergoes recombination in capsular loci and resistance islands. Always use Gubbins or an equivalent before SNP-based cluster inference.

- **cgMLST and SNP thresholds**: cgMLST (e.g., HC5) or SNP thresholds (e.g., ≤ 10 SNPs) require integration with epidemiological metadata.

- **Plasmid typing databases are incomplete:** AcinetobacterPlasmidTyping covers the major rep types, but novel plasmid replicons are regularly discovered. Supplement with MOBsuite for plasmid reconstruction.

### 8.3.4 Case Studies for A. baumannii 

**Case Study \#1 - Detecting a Protracted Outbreak of Carbapenem‑Resistant Acinetobacter baumannii at a Referral Hospital in Botswana Using Whole‑Genome Sequencing (2021–2022) -** [<u>https://pmc.ncbi.nlm.nih.gov/articles/PMC12772292/</u>](https://pmc.ncbi.nlm.nih.gov/articles/PMC12772292/)

Aim: To investigate a sustained rise in carbapenem‑resistant Acinetobacter baumannii (CRAB) bloodstream infections at a large public referral hospital in Botswana by analyzing clinical and environmental isolates with whole‑genome sequencing, to determine whether the infections were linked to a single protracted outbreak, to identify environmental reservoirs, and to explore the development of low‑cost diagnostic markers for future outbreak tracking.

**Surveillance Strategy/System Design**

**Setting**: A 530‑bed public tertiary referral hospital in Gaborone, Botswana, serving a large catchment population. The hospital has an 8‑bed adult intensive care unit (ICU) and a 33‑bed neonatal intensive care unit (NICU). Background bloodstream infection surveillance had documented that the proportion of A. baumannii‑attributable neonatal sepsis rose from 1% to 16% between 2012 and 2021, with a case fatality rate of 56%.

**Sampling strategy:**

1.  **Clinical isolates:** All stored, viable A. baumannii blood culture isolates collected between 1 March 2021 and 31 August 2022 were submitted for sequencing. During this period, 54 blood cultures were reported as A. baumannii; 23 isolates were available (the remainder had been discarded). Blood cultures had been taken from patients aged 2 days to 69 years across five wards: ICU (6), NICU (8), Male Medical (3), Female Medical (2), and Emergency Department (4). Of these, 19/23 were classified as healthcare‑associated (positive culture \>72 hours after admission, or after the first day of life for inborn neonates).

2.  **Environmental isolates:** Over a 6‑month period (January-June 2021), four point‑prevalence environmental surveys were conducted in the NICU to identify multidrug‑resistant organism reservoirs. High‑touch surfaces, sink drains and water, equipment, and hands of caregivers and healthcare workers were swabbed with sterile flocked swabs, enriched, and plated on chromogenic ESBL agar. Twenty banked environmental isolates presumptively identified as Acinetobacter spp. were selected for sequencing.

**Isolate types and final sample size**:

- After WGS species confirmation, all 23 blood culture isolates were confirmed as A. baumannii.

- Of the 20 environmental isolates, only 5 (25%) were confirmed as A. baumannii. The remaining 15 were other Acinetobacter spp. (3), Serratia spp. (6), Pseudomonas spp. (3), Exiguobacterium spp. (1), Microbacterium spp. (1) and one unclassified organism highlighting the poor specificity of chromogenic ESBL agar for A. baumannii. Total A. baumannii genomes: 28 (23 clinical, 5 environmental).

**Reason for sampling:** Rising CRAB incidence in the hospital, particularly among neonates, prompted the need to distinguish a monoclonal outbreak from hyperendemic polyclonal spread and to guide targeted environmental remediation. Traditional epidemiological investigation had been insufficient to clarify transmission pathways.

**Laboratory methods:** Species identification at the hospital was by Gram stain, colony morphology and biochemical testing (API strips). Antimicrobial susceptibility testing by disk diffusion was performed inconsistently due to antibiotic disc stock‑outs. Isolates were stored at −80 °C. DNA extraction at NICD (South Africa) used the Invitrogen PureLink Microbiome DNA Purification Kit.

**Sequencing approach:** Illumina NextSeq (2 X 150 bp paired‑end, average coverage 165X (range 89–235X). Library preparation with Illumina DNA Prep kit.

**Use cases:** Outbreak investigation, AMR mechanism detection, detection of high‑risk clones, environmental reservoir identification, and diagnostic biomarker development for resource‑limited settings.

**Ethical / Legal Considerations and Approvals**

**Beneficence and non‑maleficence:** The study used residual diagnostic and environmental surveillance isolates. Genomic findings were fed back to the hospital IPC team and contributed to international understanding of CRAB transmission in LMICs, where the burden is highest.

**Distributive justice:** The investigation addressed a severe, ongoing AMR threat in a resource‑limited setting and provided evidence to support targeted, feasible interventions. The inclusion of environmental sampling prevented an exclusive focus on infected patients and recognized the role of the healthcare environment in maintaining transmission.

**Privacy and autonomy:** Ethical approvals were obtained from the University of Pennsylvania IRB (IRB# 2022‑851492), the University of Botswana IRB, the Health Research and Development Committee at Botswana’s Ministry of Health (2022‑HPDME18/13/1), and the study healthcare facility (2022‑2/2A(7)/201). Written informed consent was waived for this retrospective abstraction of surveillance data because only de‑identified bacterial isolates were studied.

**Data custodianship:** Raw sequencing data deposited in NCBI under BioProject PRJNA1082310. Supplementary data, including resistance gene profiles, Kaptive typing outputs, SNP matrices and diagnostic allele sequences, are provided as online supplemental material accompanying the publication.

**Transparency and accountability:** Published open access.

**Data protection:** Public data sets contain no patient identifiers. Isolates are referenced by coded sample IDs.

**Public health integration:** Results informed hospital IPC review, contributed to advocacy for environmental remediation strategies, and demonstrated the feasibility of South–South collaborative genomic surveillance under the SEQAFRICA project (Fleming Fund).

**Data Analysis**

**Bioinformatics tools or pipelines:**

Quality control and assembly: Read processing and de novo assembly performed using the Bactopia v2.2.0 pipeline, which integrates Shovill v1.1.0 for assembly.

QC thresholds: Average coverage 165 × (range 89–235 ×); assemblies ranged 3.73–4.02 Mb.

Species confirmation and taxonomic assignment: WhatsGNU with a custom A. baumannii database of 14,627 publicly available genomes.

MLST: mlst v2.19.0 (Pasteur scheme) referencing the PubMLST database.

K and OCL locus typing: Kaptive v2.0.1 with default settings applied to assemblies.

AMR gene identification: Resistance genes identified as part of the Bactopia pipeline.

Phylogenetic reconstruction (all STs): Cladebreaker pipeline, which uses Prokka v1.14.6 for annotation, Roary v3.13.0 for core gene alignment, and RAxML v8.2.9 (GTRGAMMA model, 100 maximum parsimony starting trees, 100 bootstrap replicates) for maximum likelihood phylogeny. The tree included 28 local genomes and 16 reference genomes chosen by WhatsGNU.

ST1 sub phylogeny: Snippy SNP alignment to a local reference (ST1 FMW BSI Jun 22) and pairwise SNP distance calculation using SNP dists.

Diagnostic allele discovery: Roary pangenome analysis followed by Scoary to identify genes uniquely present/absent in each phylogenetic clade; DAMAGE (which integrates WhatsGNU output) to identify clade specific protein alleles with 100% sensitivity and 100% specificity, and a gene novelty unit score of 0 (allele absent from all 14,627 database genomes).

**Data Sharing Strategy**

Raw reads: NCBI BioProject PRJNA1082310.

Assemblies and supplementary data: Resistance gene profiles (File S1), pairwise SNP matrices (Files S2–S3), diagnostic allele outputs (Files S4–S5), FASTA sequences of outbreak specific alleles (File S6), and Kaptive typing outputs (File S7) are publicly available with the publication.

Interactive phylogenies: iTOL links provided in the manuscript.

Code/pipelines: All tools used are publicly available.

Restrictions: None – open access.

**Challenges and Lessons Learned**

Poor sensitivity of chromogenic screening for environmental A. baumannii: Only 25% of isolates presumptively identified as Acinetobacter from chromogenic ESBL agar were confirmed as A. baumannii by WGS. Future environmental surveillance for CRAB should employ Acinetobacter selective media or molecular screening to avoid large numbers of false positives and unnecessary sequencing costs.

Low isolate recovery limited outbreak resolution: Only 23 of 54 blood culture isolates were available for sequencing; the rest had been discarded. Systematic isolate banking is critical for retrospective outbreak investigations and should be embedded in routine laboratory practice.

WGS uncovered a protracted outbreak that traditional epidemiology missed: Despite a prolonged period of elevated CRAB incidence, a monoclonal outbreak was not suspected because of the wide temporal spread and diverse ward locations. Only WGS based phylogeny, combined with environmental sampling, revealed the clonal nature of the event.

Sink drains as reservoirs demand specific interventions: The demonstration that a sink drain isolate was genetically indistinguishable from neonatal blood isolates provides actionable evidence for targeted remediation (e.g., sink replacement, boiling water flushes, or splash guard installation) that goes beyond standard surface cleaning.

Proof of concept for low-cost molecular tracking: The identification of clade-specific diagnostic alleles demonstrates that a modest upfront investment in WGS can produce tools (e.g., PCR primers) that enable ongoing surveillance without recurrent sequencing, an important consideration for resource-constrained public health laboratories.

Crossward connection unresolved: The inclusion of an adult patient’s isolates within the neonatal clade suggests shared exposures (healthcare workers, equipment, or plumbing) that could not be fully resolved, underscoring the need for whole facility environmental surveillance during outbreak investigations.

**Major Findings**

WGS analysis of 28 A. baumannii isolates from a 530-bed referral hospital in Botswana revealed that 79% (22/28) belonged to a single clone: ST1 (Pasteur), KL17, OCL1, consistent with Global Clone 1 (GC1). All 19 healthcare-associated blood isolates and 3/5 environmental isolates were ST1; four community-associated infections were caused by genetically diverse, non-ST1 strains.

All ST1 isolates carried genes encoding the carbapenemases NDM 1 and OXA 23, together with aminoglycoside, tetracycline, sulfonamide, macrolide and biocide resistance determinants, conferring an extensively drug resistant (XDR) phenotype. Phylogenetic analysis demonstrated that nearly identical ST1 isolates spanned a time range of \>1 year, indicative of ongoing transmission from persistent environmental reservoirs.

A distinct neonatal clade (average 2.3 SNPs, range 0–5 SNPs) contained all eight neonatal blood isolates and three NICU environmental isolates recovered from a sink drain, a bed rail, and a healthcare worker’s hand swab. This tight genomic cluster provides strong evidence that sink associated biofilms act as a long term reservoir, with hands and surfaces functioning as transmission vehicles.

Using phylogenetically informed methods, the study identified 11 diagnostic protein alleles specific to the neonatal clade and 10 alleles specific to the broader local ST1 clade. These markers were 100% sensitive and 100% specific when tested against a database of 14,627 publicly available A. baumannii genomes, demonstrating the feasibility of developing low cost, PCR based tracking tools for future outbreak surveillance.

Environmental linkage analysis: The sink drain isolate clustered within the neonatal clade, providing strong evidence that sink associated biofilms serve as enduring reservoirs. The presence of genetically indistinguishable isolates on a bed rail and a healthcare worker’s hand suggests that hands and surfaces act as transmission vehicles.

Diagnostic marker validation: 11 protein alleles were 100% specific and 100% sensitive for the neonatal clade; 10 others defined the broader local ST1 clade. These markers could be targeted by low-cost PCR or Sanger sequencing to track future CRAB isolates without requiring WGS.

**Public Health Actions**

**Enhanced environmental remediation:** Following identification of the sink drain as a likely reservoir, the hospital initiated targeted disinfection of sink drains and water pipelines and considered retrofitting sinks with splash guards.

**Strengthened IPC bundles:** Multimodal infection prevention measures were reinforced, including hand hygiene optimization, increased frequency of surface disinfection, and review of invasive device reprocessing protocols.

**Systematic isolate banking:** The investigation highlighted the critical need to store all clinically significant isolates, leading to a hospital-wide policy for routine biobanking of sterile site Gram-negative organisms.

**CRAB-specific environmental screening:** Chromogenic ESBL agar was replaced with media better suited to Acinetobacter recovery for future environmental point prevalence surveys.

**National and regional reporting:** Findings were shared with the Botswana Ministry of Health and contributed to the SEQAFRICA project outputs, strengthening the case for sustained genomic surveillance of AMR in Southern Africa.

**Development of low-cost molecular tracking:** The diagnostic alleles identified serve as a proof of principle for the creation of PCR-based assays that could be deployed at the hospital for prospective CRAB outbreak detection without the need for recurrent WGS.

**Cross ward IPC coordination:** Because an adult isolate clustered within the neonatal clade, the hospital IPC team initiated joint ward-level surveillance and standardized cleaning protocols for shared equipment, healthcare worker hand hygiene, and plumbing infrastructure.

**Case Study \#2 - Genomic analysis of carbapenem-resistant Acinetobacter baumannii outbreak in a burn intensive care unit of a tertiary-care hospital in Madrid, Spain -** [<u>https://pmc.ncbi.nlm.nih.gov/articles/PMC12538852/</u>](https://pmc.ncbi.nlm.nih.gov/articles/PMC12538852/)

The aim of the study was to investigate a prolonged outbreak of carbapenem-resistant Acinetobacter baumannii (CRAB) in a burn intensive care unit in Madrid, Spain, to identify transmission pathways between patients and the hospital environment, and to determine how whole-genome sequencing (WGS) could support outbreak tracking, antimicrobial resistance monitoring, and infection prevention and control.

**Surveillance Strategy/System Design:**

**Sampling location:** Hospital Universitario La Paz, Madrid, Spain

**Sampling site:** Adult Burn Intensive Care Unit (BICU), including patient clinical specimens, routine rectal screening samples, and environmental surfaces and shared medical equipment in affected rooms and common areas

**Sampling frequency:** Outbreak period from October 2022 to August 2023. Isolates were collected throughout the outbreak as part of routine clinical diagnostics, epidemiological screening, and targeted environmental investigation. Environmental sampling was intensified after persistence of transmission despite disinfection.

**Sample collection method:** (1) Clinical isolates were obtained from routine diagnostic microbiology specimens from patients. (2) Colonization screening used rectal swabs processed on ChromID® Carba Smart plates. (3) Environmental samples were collected by surface wipes from rooms, common areas, and equipment, enriched in BHI broth, and cultured on selective agar

**Reason for sampling method(s):** Routine patient and colonization isolates were used to identify the outbreak clone and monitor spread among patients. Environmental sampling was included because CRAB is well known to persist on surfaces and equipment in ICU settings. Sequencing the first isolate from each patient, plus isolates with relevant phenotypic changes and selected environmental isolates, allowed the team to track transmission, persistence, and within-outbreak evolution while keeping sequencing focused on outbreak-relevant isolates.

**Detection & sequencing approach**: Species identification by MALDI-TOF, antimicrobial susceptibility testing by broth microdilution, and cefiderocol testing by disk diffusion with broth microdilution confirmation. WGS used Ion Torrent short-read sequencing for outbreak isolates, with Oxford Nanopore long-read sequencing for the index isolate to generate a hybrid reference genome.

**How data was used:** To determine whether the outbreak was caused by a single clone, compare patient and environmental isolates, identify adaptive mutations emerging under treatment pressure, assess persistence in the ICU environment, and support real-time infection prevention and control actions.

**Ethical/Legal Considerations and Approvals**

**Beneficence and non-maleficence:** WGS was used during an active ICU outbreak to improve patient safety by identifying the outbreak clone, linking patient and environmental isolates, and detecting emergence of more difficult-to-treat variants, including cefiderocol-associated mutants. This information supported more effective infection control escalation than routine microbiology alone.

**Distributive Justice:** The investigation covered all identified outbreak-associated patients in the unit, together with environmental sources considered relevant to transmission, rather than focusing selectively on one subset of patients.

**Privacy and Autonomy:** The study used bacterial isolates collected through routine care and outbreak investigation. Published genomic outputs used coded sample identifiers only and did not include direct patient identifiers.

**Data Custodianship, Distribution, and Communication:** Sequence data were deposited publicly in the European Nucleotide Archive (PRJEB62407), and novel blaADC alleles were deposited in GenBank. During the outbreak, genomic findings were communicated regularly to the hospital Preventive Medicine Unit at HULP.

**Transparency and accountability:** The study reported the sequencing and analytical methods in detail and described how genomic reports (issuing up to fourteen reports to the Preventive Medicine Department) were provided approximately every two weeks to support infection control decision-making.

**Legal authorization:** The study was approved by the local ethics committee at Hospital Universitario La Paz (PI-5933).

**Mandatory Reporting Requirements:** The paper does not describe a specific legal reporting requirement for CRAB outbreak genomics, but the investigation was integrated into hospital outbreak response structures.

**Data Protection and Privacy:** Public datasets contained no direct patient identifiers. Isolates were represented using coded IDs.

**Public Health Integration:** Genomic findings were used directly by the Preventive Medicine Department to guide environmental investigation, identify likely shared-device transmission, and justify the closure of the BICU for disinfection with high-concentration H<sub>2</sub>O<sub>2</sub>.

**Community and Indigenous Rights:** This was a hospital-based outbreak investigation and did not target any specific community or socially defined population group outside routine clinical care.

**Wet Lab Methods:**

- The study utilized a combination of culture-based techniques and dual-sequencing technologies to characterize the outbreak. Bacterial colonies were identified using MALDI-TOF mass spectrometry (Bruker Daltonik GmbH).

- DNA Extraction: Performed using the DNeasy® Blood & Tissue Kit (Qiagen).

- Short-Read Sequencing: Conducted on the Ion GeneStudio S5 system using the NEBNext® Fast DNA Library Prep Set.

- Long-Read Sequencing: The index isolate (P0​) was sequenced using the MinION™ Mk1C system with a Flongle flowcell and the Rapid Library Preparation Kit (SQK-RAD004).

**Bioinformatic tool/pipelines:**

- Basecalling by Guppy 7.1.4: Fast basecalling for Nanopore long-read data.

- Genome Assembly - SPAdes v3.14.1: De novo assembly of short-read data.

- Hybrid Assembly - Unicycler v0.5.0: Combining short and long reads for the reference genome (P0).

- Annotation- Bakta: Comprehensive functional annotation of coding sequences.

- Typing- mlst tool v2.23: MLST analysis (Pasteur and Oxford schemes).

- SNP Calling - Snippy v4.6.0: Identification of single nucleotide polymorphisms across isolates.

- Phylogenetics - Beast2 v2.7.7: Construction of time-scaled phylogenetic trees.

- Visualization - FigTree v1.4.4: Graphical visualization of phylogenetic trees.

- Resistance Analysis - ABRicate v1.0.1: Screening for antimicrobial resistance genes and plasmids. CARD v3.3.0 (RGI) Comprehensive Antibiotic Resistance Database analysis.

**Data Analysis**

**Genomic relatedness and outbreak tracking:** SNP-based analysis using Snippy, with phylogenetic reconstruction in BEAST2, was used to determine the relatedness of patient and environmental isolates and estimate the rate of genomic evolution across the outbreak.

**Typing**: MLST was performed using both Pasteur and Oxford schemes, identifying the outbreak clone as ST2/ST451 (Pasteur (Pas) and Oxford (ox) scheme STs: **ST2**<sub>Pas</sub>/**ST451**<sub>Ox</sub> CRAB strain, the first isolate labelled as P0 and taken as the reference isolate). The genome of the first isolate from the index patient was sequenced with short- and long-read sequencing methodologies. Hybrid de novo assembly yielded a single 3.99 Mb contig.

**Antimicrobial resistance analysis:** Resistance genes and plasmids were identified using ABRicate and CARD. Particular attention was given to carbapenem resistance (blaOXA-23) and cefiderocol-associated changes.

**Adaptive evolution analysis:** The study tracked mutations emerging during the outbreak, including (1) dnaQ changes associated with a hypermutator lineage, (2) wzc mutations associated with a hypermucoid phenotype, and (3) blaADC-73 and bfrD changes associated with increased cefiderocol MICs.

**Environmental linkage analysis:** Patient and environmental isolate genomes were compared alongside room occupancy and ward timeline data to identify likely environmental reservoirs and shared-device transmission pathways.

**Data Sharing Strategy:** (1) Raw sequence data available in ENA under PRJEB62407 (2) Novel blaADC allele sequences deposited in GenBank (3) Isolate metadata and susceptibility data included in publication tables and supplementary files (4) Open-access publication enabling reuse of methods and findings

**Major Findings:**

Whole-genome sequencing revealed that a prolonged outbreak (during 320 days) of carbapenem-resistant Acinetobacter baumannii (CRAB) in the burn intensive care unit was caused by a single ST2<sub>Pas</sub>/ST451<sub>Ox</sub> clone carrying blaOXA-23. Genomic surveillance showed linear within-outbreak evolution at 13.1 SNPs/year, with the emergence of a hypermutator lineage (dnaQ mutation) and a hypermucoid phenotype (wzc mutations) that likely promoted environmental persistence due to biofilm formation. Most notably, the study tracked the rapid, independent development of cefiderocol resistance (stepwise increases in cefiderocol MICs) linked to novel mutations in the blaADC−73​ ampC beta-lactamase (R172L/Q, I315T, Q144K, S310R) and the bfrD (a TonB-dependent receptor truncation (bfrD K228\*)) siderophore receptor under therapeutic pressure. Phylogenetic comparison of patient and environmental isolates (19% of tested surfaces were contaminated) linked contamination of common areas and shared medical devices to transmission both inside and outside the unit, demonstrating that the outbreak was sustained by widespread environmental seeding until enhanced disinfection.

**Public Health Actions Triggered:**

**Real-Time Genomic Surveillance:** The Microbiology Department issued 14 genomic reports (approximately every two weeks) to the Preventive Medicine Unit to guide the outbreak response.

**Targeted Environmental Investigation:** Intensive sampling of common areas and equipment was conducted, identifying a crash cart as the vector for transmission to patients outside the BICU.

**Unit Closure:** Admissions to the Burn Intensive Care Unit (BICU) were halted in May 2023 to prevent further colonization of new patients.

**Patient Relocation (new admissions to the BICU were halted):** New burn patients were admitted to a different ICU ward in a separate building of the same hospital to break the chain of transmission.

**Enhanced Disinfection Protocols successfully contained the outbreak**: Following the failure of low-concentration H<sub>2​</sub>O<sub>2</sub>​, the unit underwent a enhanced cleaning with high-concentration (20%) vaporized H<sub>2</sub>​O<sub>2</sub>​ using a long-range nebulization system (Aeroturbex).

**Validation of Testing Methods:** The findings prompted a shift toward broth microdilution for cefiderocol susceptibility testing, as it proved more sensitive than disk diffusion for detecting emerging resistance mutations.

## 8.4 Pseudomonas aeruginosa

*Pseudomonas aeruginosa* is a highly versatile non-fermenting Gram-negative bacterium and a major cause of healthcare-associated opportunistic infections like sepsis, ventilator-associated pneumonia (VAP), and chronic respiratory infections. In the WHO Bacterial Priority Pathogens List (BPPL) 2024, carbapenem-resistant *P. aeruginosa* (CRPA) is classified as a high-priority pathogen (WHO, 2024). It is characterized by its metabolic flexibility, ability to thrive in aquatic hospital environments (e.g., sinks, taps, medical equipment), and an exceptionally large genome (5.5 - 7.76 Mbp with a high GC content of 65 - 67%) that facilitates rapid adaptation to antibiotic pressure. It contains an unusually extensive set of regulatory genes and an accessory genome that facilitate quick adaptive responses to antibiotic pressure. (Klockgether et al., 2011).

### 8.4.1 Background and Public Health Relevance

The public health significance of *P. aeruginosa* stems from its role as a primary driver of sepsis and ventilator-associated pneumonia (VAP) in immunocompromised and critically ill patients. It is among the six leading bacterial pathogens responsible for antimicrobial resistance (AMR)-related deaths globally (Murray et al., 2022). Its ability to form robust biofilms and its extensive "mutational resistome" make infections notoriously difficult to eradicate. Genomic surveillance is essential for identifying high-risk clones and tracking the dissemination of acquired resistance genes (e.g., carbapenemases) that can lead to multi- and extensive drug-resistant (MDR and XDR) phenotypes. The resistome is uniquely resistant to therapy due to a combination of intrinsic low permeability, inducible chromosomal beta-lactamases, constant efflux pumps, and quick resistance acquisition through mobile genetic elements (Breidenstein et al., 2011).

### 8.4.2 Key Genomic Features

#### 8.4.2.1 Population Structure and High-Risk Clones:

*P. aeruginosa* has a non-clonal population structure characterized by a few widely disseminated "high-risk clones." The ten highest-risk P. aeruginosa clones worldwide, categorized by their prevalence, global spread, and connection to MDR/XDR profiles, as well as extended-spectrum β-lactamases (ESBLs) and carbapenemases, include ST235, ST111, ST233, ST244, ST357, ST308, ST175, ST277, ST654, and ST298. Among these, ST235 stands out as the most significant high-risk clone due to its global distribution and its association with over 60 β-lactamase variants, including multiple carbapenemases from classes A and B. It also shows a highly virulent phenotype and correlates with a high mortality rate, likely driven by the ExoU cytotoxin production. ST111 and ST233 are also widespread MDR/XDR clones, especially linked to VIM-2 metallo-β-lactamase (MBL). In contrast, ST244 is a common clone that is not always linked to MDR/XDR profiles. Furthermore, ST357, ST308, and ST298, which are also exoU-positive, may be associated with increased virulence (Barrio-Tofiño et al., 2020, Pirnay et al., 2009). Most environmental and clinical isolates are genetically diverse, but a small group of globally spread high-risk clones accounts for a disproportionate share of hospital outbreaks and XDR cases (Oliver et al., 2015).

#### 8.4.2.2 MLST and cgMLST

The P. aeruginosa MLST scheme uses seven housekeeping loci (acsA, aroE, guaA, mutL, nuoD, ppsA, trpE) and is maintained at PubMLST (https://pubmlst.org/paeruginosa/) (Curran et al., 2004). Although 7-locus MLST provides a framework for lineage identification and enables cross-study comparisons, it lacks sufficient resolution to investigate outbreaks within a single sequence type; cgMLST or whole-genome SNP analysis is required for epidemiological inference.

Core-genome MLST (cgMLST), which analyzes 3,867 conserved core loci in the P. aeruginosa core genome (https://www.cgmlst.org/ncs/schema/Paeruginosa/), provides sufficient resolution to identify transmission clusters. In outbreak studies, a difference of ≤10–12 cgMLST alleles typically indicates recent transmission. However, this threshold should be interpreted alongside collection dates, epidemiological data, and the specific scheme used, as no universally accepted threshold has been validated across all clinical contexts (Oliver et al., 2015). All cluster-threshold determinations must be supported by epidemiological evidence.

#### 8.4.2.3 O-Antigen Serotyping

O-antigen serotyping in P. aeruginosa categorizes strains based on the structural diversity of the O-specific antigen (OSA) component of their lipopolysaccharide (LPS) that protects the bacteria against immune recognition and serum-mediated killing. P. aeruginosa possesses a structurally diverse O-antigen, which defines 20 internationally recognized serogroups (O1-O20) (Lam et al., 2011). O-antigen serotyping was historically used for epidemiological typing; in modern surveillance, it serves primarily as a supplementary discriminatory tool alongside MLST and cgMLST.

In silico serotyping from WGS assemblies is feasible using curated O-antigen gene cluster databases. The O11 serogroup is closely linked to major high-risk international clones, such as ST235. O11 strains often carry the exoU toxin gene, which causes severe tissue damage, and are frequently extensively drug-resistant (XDR) or multidrug-resistant (MDR). Serogroup O11 is notably associated with high-risk international clones and hospital outbreaks; other serogroups like O1, O6, and O12 are also common among clinical MDR isolates ((Lam et al., 2011, Thrane et al., 2016).

#### 8.4.2.4 Antimicrobial Resistance Mechanisms

*P. aeruginosa* possesses a multi-layered resistome driven by the interplay of intrinsic, acquired, and adaptive mechanisms. Intrinsic resistance forms the baseline defense, mediated by exceptionally low outer membrane permeability, inducible chromosomal (ampC beta-lactamases, and the constitutive expression of resistance-nodulation-division (RND) efflux pumps, most notably mexAB-oprM and mexCD-oprJ. Acquired resistance rapidly escalates this baseline via mobile genetic elements, introducing Class B metallo-beta-lactamases (blaVIM), blaIMP, blaNDM) or Class A carbapenemases (blaKPC, blaGES) that render the pathogen extensively drug-resistant (XDR). This is frequently exacerbated by mutational inactivation of the OprD porin, which restricts carbapenem entry. Moreover, adaptive resistance provides a transient, non-mutational layer where exposure to environmental stressors or antibiotics triggers biofilm formation and metabolic shifts into a non-replicating persister state, drastically reducing phenotypic susceptibility within the host.

P. aeruginosa possesses a uniquely multi-layered resistome driven by the interplay of three mechanistic categories: intrinsic, acquired, and adaptive resistance. Understanding the contribution of each category is essential for accurate genomic interpretation (Breidenstein et al., 2011; Strateva & Yordanov, 2009).

**A. Intrinsic Resistance**

Intrinsic mechanisms constitute the baseline resistance of all P. aeruginosa isolates, irrespective of prior antibiotic exposure:

**Low outer membrane permeability:** The P. aeruginosa outer membrane has an exceptionally low general diffusion rate for hydrophilic molecules, including beta-lactam antibiotics, due to low porin density and porin selectivity (Breidenstein et al., 2011).

**Inducible chromosomal AmpC beta-lactamase (bla_AmpC):** This chromosomally encoded, inducible Class C beta-lactamase is activated by beta-lactam exposure, particularly through derepression following ampD inactivation, and confers resistance to most penicillins and narrow-spectrum cephalosporins. Stable derepression (stable AmpC hyperproduction) following mutational ampD or dacB inactivation results in high-level resistance to expanded-spectrum cephalosporins.

**Constitutive Resistance-Nodulation-Divisio**n (**RND) efflux pumps:** P. aeruginosa constitutively expresses the MexAB-OprM efflux system, which actively exports a broad range of antibiotics, including beta-lactams, quinolones, and tetracyclines. MexXY-OprM is induced by aminoglycosides and is a primary driver of aminoglycoside resistance. Two additional RND systems, MexCD-OprJ and MexEF-OprN, are normally repressed in wild-type strains but become upregulated through regulatory mutations (in nfxB and mexT, respectively), conferring additional resistance to beta-lactams and quinolones (Poole, 2011).

**B. Acquired Resistance**

Horizontal acquisition of resistance genes via Mobile Genetic Elements: integrons, transposons, genomic islands, and plasmids significantly escalates the intrinsic resistance baseline:Class B Metallo-Beta-Lactamases (MBLs): mainly bla_VIM (such as VIM-1, VIM-2, and VIM-4) and bla_IMP, are the most common acquired carbapenemases in P. aeruginosa globally. The bla_NDM enzyme is becoming more frequently reported. These enzymes can hydrolyze almost all beta-lactam antibiotics, including carbapenems, and are not affected by existing beta-lactamase inhibitors.

**Class A Carbapenemases**: bla_KPC and bla_GES variants (e.g., bla_GES-5) confer carbapenem resistance and co-occur with other MDR determinants.

**OprD Porin Inactivation**: Mutational loss or truncation of the OprD porin (the primary entry channel for imipenem) is a critical acquired resistance mechanism. OprD inactivation is particularly important when combined with AmpC hyperproduction, as it confers resistance to both imipenem and meropenem without requiring a carbapenemase gene. Genomic screening must explicitly assess oprD gene integrity because mutational inactivation—such as frameshift mutations, premature stop codons, and IS element insertions—directly causes porin deficiency in Pseudomonas aeruginosa. These alterations disrupt the structural integrity of the outer membrane porin, a primary mechanism driving high-level carbapenem (e.g., imipenem) resistance (Strateva & Yordanov, 2009).

**Efflux Pump Overexpression (Mutational):** Mutations in regulatory genes like mexR, nalC, and nalD in Pseudomonas aeruginosa cause constitutive overexpression of MexAB-OprM efflux systems. Similarly, nfxB, mexT, and mexZ mutations upregulate MexCD-OprJ, MexEF-OprN, and MexXY-OprM systems. This overexpression drastically increases Minimum Inhibitory Concentrations (MICs) across multiple antibiotic classes.

**16S rRNA methyltransferases (RMTs):** Enzymes such as RmtB, RmtC, and ArmA confer high-level pan-aminoglycoside resistance; their presence in P. aeruginosa often indicates co-carriage on MDR plasmids with carbapenemase genes.

**C. Adaptive Resistance**

Adaptive resistance is a transient, non-heritable phenotypic response to environmental and antibiotic stressors that does not involve genomic mutation and cannot be detected by WGS. It encompasses:

**Biofilm formation**: Sessile bacteria within biofilms are shielded from antibiotic penetration and immune clearance by the extracellular polymeric substance (EPS) matrix. Biofilm-associated P. aeruginosa can show MICs 100–1,000-fold higher than those of planktonic cells from the same isolate (Høiby et al., 2010).

**Persister cell formation:** A subpopulation of metabolically dormant cells enters a non-replicating state, rendering them phenotypically tolerant to bactericidal antibiotics while retaining full genetic susceptibility.

**Phenotypic switching:** Stress-induced regulatory changes (e.g., via the GacS/GacA and Rsm regulatory cascades) alter surface antigen expression and metabolic state, transiently reducing antimicrobial susceptibility.

#### 8.4.2.5 Virulence Factors

Pseudomonas aeruginosa has a wide range of virulence factors that help it colonize hosts, evade immune responses, invade tissues, acquire nutrients, and persist during infections. The combined action of these factors influences disease severity, including bloodstream infections and sepsis (Letizia et al., 2025; Liao et al., 2022).

**Surface-Associated Virulence Factors:** Surface structures are vital for attaching to hosts and establishing infection. Type IV pili facilitate adhesion to tissues, twitching motility, DNA uptake, and biofilm formation, while flagella assist in mobility, biofilm growth, and host-cell interactions (Liao et al., 2022). Lipopolysaccharide (LPS), a key component of the outer membrane, promotes adherence, resistance to phagocytosis and serum killing, and triggers strong inflammatory responses through immune signaling pathways (Liao et al., 2022).

**Secretion Systems and Cytotoxins:** The Type III Secretion System (T3SS) is a crucial virulence mechanism of P. aeruginosa. It injects effector proteins directly into host cells via a needle-like apparatus. Effectors like ExoS, ExoT, ExoU, and ExoY disrupt cytoskeletal structure, impede phagocytosis, alter cell signaling, and cause host-cell damage. ExoU, a phospholipase linked to rapid cell death, is often associated with severe infections and poor outcomes, while ExoS is linked to invasive disease (Letizia et al., 2025; Liao et al., 2022).

Exotoxin A (ToxA), secreted through the Type II Secretion System, is another key virulence factor. This ADP-ribosylating toxin blocks protein synthesis in eukaryotic cells by targeting elongation factor-2, leading to cell death and tissue damage (Letizia et al., 2025; Liao et al., 2022).

**Extracellular Enzymes and Toxic Metabolites:** P. aeruginosa produces various proteases and toxic substances aiding tissue destruction and immune defense evasion. Elastases LasA and LasB, alkaline protease (AprA), and protease IV degrade host extracellular matrix, complement, immunoglobulins, and other immune molecules, promoting bacterial spread and survival. Additional virulence-associated metabolites include pyocyanin, hydrogen cyanide, rhamnolipids, phospholipases, and lipoxygenase. These compounds induce oxidative stress, impair immune cells, disrupt epithelial barriers, and contribute to tissue injury during infection (Letizia et al., 2025; Liao et al., 2022).

**Iron Acquisition Systems:** Infection success depends on overcoming host nutritional immunity. P. aeruginosa uses siderophores pyoverdine and pyochelin to extract iron from the host environment. Pyoverdine also regulates virulence genes such as toxA and prpL, linking nutrient acquisition to pathogenicity (Letizia et al., 2025; Liao et al., 2022).

**Quorum Sensing and Biofilm Formation:** Virulence gene expression is coordinated by quorum-sensing systems, mainly Las, Rhl, and Pqs. These networks regulate about 10% of the genome, controlling virulence factors like pyocyanin, hydrogen cyanide, proteases, rhamnolipids, and biofilm components (Letizia et al., 2025). Mutations in regulators like lasR are common in clinical isolates and can influence virulence, adaptation, and persistence (Letizia et al., 2025).

Biofilms help bacteria persist by resisting immune responses and antibiotics. Their matrix mainly consists of exopolysaccharides (alginate, Pel, and Psl), extracellular DNA, and proteins. Mucoid strains overproducing alginate are typical in chronic infections, while Pel and Psl support biofilm stability and drug tolerance (Letizia et al., 2025; Liao et al., 2022).

Whole-genome sequencing enables analysis of virulence potential by detecting genes linked to secretion systems (exoS, exoT, exoU, exoY, toxA), extracellular enzymes (lasA, lasB, aprA, prpL), iron acquisition (pvd and pch), quorum sensing (lasR, lasI, rhlR, rhlI, pqsR), motility and adhesion (pil and fli), and biofilm production (alg, pel, and psl). Combining virulence profiles with resistance data and phylogenomic analysis supports risk assessment and outbreak tracking of P. aeruginosa linked to sepsis.

### 8.4.3 Pathogen-Specific Analysis and Interpretation

For all initial processing steps, including raw read quality control, adapter trimming, contamination checks, and de novo assembly, refer to the core bioinformatics section. For *P. aeruginosa*, sequence-based confirmation is critical due to its phenotypic similarity to other pseudomonads. Species confirmation must be verified using Kraken2 or FastANI (requiring ≥ 95% average nucleotide identity to the reference strain PAO1). Once the assembly is validated, proceed with the following bioinformatics workflow:

#### 8.4.3.1 Recommended Bioinformatics Tools for P. aeruginosa

**MLST Typing using mlst CLI (https://github.com/tseemann/mlst):** Use --scheme paeruginosa to screen against the PubMLST database. Alternatively, use PubMLST website and upload assembly sequences directly to [<u>https://pubmlst.org/paeruginosa/</u>](https://pubmlst.org/paeruginosa/) for manual or batch ST assignment.

- Imprecise allele matches are reported as single-locus variants (SLVs, e.g., ST235-1LV). These require confirmation by cgMLST or SNP before being treated as equivalent to the reference ST.

- Novel STs must be formally assigned via PubMLST submission before reporting.

**O-Antigen Serotyping:** Two in silico tools enable *P. aeruginosa* serotyping from genome assemblies: the command-line tool PAst ([<u>https://github.com/Sandramses/PAst</u>](https://github.com/Sandramses/PAst)), which is also hosted as a single-isolate web service (Web interface: [<u>https://cge.cbs.dtu.dk/services/PAst-1.0/</u>](https://cge.cbs.dtu.dk/services/PAst-1.0/)) by the Center for Genomic Epidemiology, and pasty ([<u>https://github.com/rpetit3/pasty</u>](https://github.com/rpetit3/pasty)), a BLAST-based alternative optimized for high-throughput batch analysis. Both utilities determine isolate serogroups by comparing FASTA sequences against reference O-antigen gene clusters.

**AMR Detection: AMRFinderPlus** (Feldgarden et al., 2021) is recommended. Run with --organism Pseudomonas_aeruginosa to activate organism-specific screening of known chromosomal resistance mutations in addition to acquired gene detection.

**Key outputs for P. aeruginosa:**

> **Acquired carbapenemases**: bla_VIM (VIM-1, VIM-2), bla_IMP, bla_NDM, bla_KPC, bla_GES, each must be reported as a critical finding and notified to national surveillance.
>
> **OprD porin integrity:** AMRFinderPlus flags inactivating mutations in oprD; however, supplementary manual inspection of oprD assembly contigs is recommended to detect IS element insertions or frameshift mutations that automated tools may miss.
>
> **Efflux pump regulatory mutations:** Mutations in mexR, nalC, nalD, nfxB, mexT, mexZ are flagged as indicators of efflux pump overexpression. Their detection should prompt review of phenotypic MIC data for beta-lactam and quinolone agents.
>
> **AmpC derepression markers:** Mutations in ampD, ampR, and dacB associated with stable AmpC hyperproduction are flagged.
>
> Note: **AMRFinderPlus** is the recommended primary AMR screening tool for P. aeruginosa. **ResFinder** (CGE) is an acceptable alternative for detecting acquired genes but provides less comprehensive coverage of P. aeruginosa-specific chromosomal mutations. Cross-reference outputs with phenotypic AST.

**Virulence Profiling: ABRicate** ([<u>https://github.com/tseemann/abricate</u>](https://github.com/tseemann/abricate)) is recommended with the Virulence Factor Database (VFDB) (Liu et al., 2022). Crucial for delineating the Type III Secretion System (T3SS) pathotypes by confirming the presence of ExoU (hyper-virulent/cytotoxic) or ExoS (invasive).

Priority targets for P. aeruginosa sepsis surveillance:

- T3SS effector genotyping: Distinguish ExoU-positive (exoU+/exoS−) from ExoS-positive (exoS+/exoU−) strains. ExoU-positive strains carry a significantly elevated risk of severe disease and ICU mortality (Shaver & Hauser, 2004). Also screen for exoT and exoY.

- T6SS loci: Screen for the presence of H1-T6SS (hcp1, vgrG, tse genes), H2-T6SS, and H3-T6SS clusters.

- Alginate locus: Screen algD, mucA for signatures of mucoid phenotype determinants.

- Siderophore systems: Screen pvdS, pchE for pyoverdine and pyochelin biosynthesis genes.

- Protease determinants: Screen lasB (elastase), aprA (alkaline protease), toxA (Exotoxin A).

#### 8.4.3.2 Plasmid detection & reconstruction:

Reconstructs plasmids from draft assemblies; identifies mobility types and relaxase type.

- Primary tool: MOB-suite ([<u>https://github.com/phac-nml/mob-suite</u>](https://github.com/phac-nml/mob-suite)) reconstructs plasmids from draft short-read assemblies, predicts mobility type (conjugative, mobilizable, non-mobilizable), and identifies relaxase classification.

- PlasmidFinder's replicon database (Carattoli et al., 2014) is primarily based on Enterobacteriaceae plasmids and performs poorly for P. aeruginosa and A. baumannii. PlasmidFinder must not be used as the primary plasmid-typing tool for P. aeruginosa; MOB-suite is the appropriate alternative.

- Limitations of short-read plasmid reconstruction: Short-read assemblies frequently fragment large P. aeruginosa resistance plasmids. For complete plasmid characterization, particularly in outbreak investigations of plasmid-mediated carbapenemase transmission, long-read (ONT) or hybrid sequencing is required.

#### 8.4.3.3 Phylogenetic Analysis and Transmission Investigation

For outbreak investigation and transmission cluster definition, whole-genome SNP-based or cgMLST analysis is required:

- Core SNP analysis involves using Snippy ([<u>https://github.com/tseemann/snippy</u>](https://github.com/tseemann/snippy)) for reference-based SNP calling, choosing a closed reference genome that matches the MLST sequence type of the study isolates (for example, a complete ST235 reference for an ST235 outbreak investigation). Recombination filtering can be done with Gubbins or ClonalFrameML; although P. aeruginosa has a lower recombination rate than many pathogens, applying recombination filtering is still recommended for rigorous phylogenomic analysis.

- cgMLST clustering: Use the PubMLST cgMLST scheme for P. aeruginosa. A provisional cluster threshold of ≤10–12 allele differences indicates potential recent transmission and should be interpreted alongside epidemiological data.

- Phylogenetic reconstruction: IQ-TREE2 (with automatic model selection) for maximum-likelihood phylogenies; FastTree for rapid screening of large datasets.

- Visualisation: Microreact (https://microreact.org) for interactive metadata-overlaid trees; iTOL (https://itol.embl.de) for annotated publication-quality phylogenies.

- Environmental source investigation: When hospital environmental sampling (sinks, drains, water outlets) accompanies clinical isolate sequencing, include environmental isolate sequences in the phylogenetic analysis to assess environmental reservoir-to-patient transmission.

#### 8.4.3.4 Caveats and Limitations in P. aeruginosa WGS Analysis, Interpretation, and Reporting

- WGS cannot detect adaptive resistance, such as biofilm tolerance, persister cell formation, or mechanisms without stable genomic changes, which are invisible to genome sequencing. Hence, a genomically susceptible isolate might fail treatment due to biofilm tolerance or persistence (Høiby et al., 2010).

- Genotype-phenotype resistance concordance is imperfect, especially for P. aeruginosa, which has a complex resistome of intrinsic, acquired, and adaptive mechanisms (Breidenstein et al., 2011).

- Genomic predictions may not fully explain susceptibility to drugs like carbapenems and polymyxins. Phenotypic testing remains essential.

- Porin loss and efflux resistance are hard to predict from WGS; mutations in regulators don't reliably indicate resistance levels, so phenotypic testing is necessary.

- Genomic clustering does not prove transmission, as thresholds are epidemiological tools, not absolute boundaries, and results should be interpreted with epidemiological data.

- Detection of virulence genes indicates potential, not expression or outcome, and may not predict disease severity (Shaver & Hauser, 2004).

- Short-read sequencing may not resolve mobile genetic elements well; long-read or hybrid approaches are often needed.

- Environmental reservoirs, common for P. aeruginosa, can confound source attribution, as environmental and clinical isolates may be indistinguishable (Pirnay et al., 2009).

- MLST alone is not enough for outbreak analysis; core-genome MLST or SNP phylogenetics are more accurate. Genomic results must be integrated with clinical and epidemiological data, as sequencing doesn't confirm transmission or causality or replace phenotypic tests.

### 8.4.4 Case Study for *P. aeruginosa*

**Case Study \#1 - Whole‑Genome Sequencing Reveals Resistance Mechanisms and Molecular Epidemiology of Carbapenem‑Resistant Pseudomonas aeruginosa Bloodstream Infections, Nanchang, China (2021–2023)**

[<u>https://pmc.ncbi.nlm.nih.gov/articles/PMC12542409/</u>](https://pmc.ncbi.nlm.nih.gov/articles/PMC12542409/)

**Aim**: To characterize the resistance mechanisms, molecular epidemiology, and virulence determinants of *P. aeruginosa* bloodstream infection (BSI) isolates using whole‑genome sequencing; to identify clinical risk factors for carbapenem‑resistant *P. aeruginosa* (CRPA) BSI development and mortality; and to integrate genomic and clinical data to inform local antimicrobial stewardship and infection control.

**Surveillance Strategy/System Design**

**Setting**: The First Affiliated Hospital of Nanchang University, Nanchang, Jiangxi Province, eastern China - a tertiary university teaching hospital. The study was a retrospective analysis of *P. aeruginosa* BSI cases over a three‑year period.

**Sampling strategy:** All first positive blood culture isolates of *P. aeruginosa* from hospitalised patients between 2021 and 2023 were collected. Only a single isolate per patient was included (non‑repetitive collection). Clinical data were retrospectively abstracted from electronic medical records.

**Isolate types and sample size**: 61 *P. aeruginosa* blood culture isolates from 61 patients (68.8% male; median age ~55 years; 60.6% aged \>55 years). Of these, 18 (29.5%) were CRPA and 43 (70.5%) were carbapenem‑susceptible *P. aeruginosa* (CSPA). The majority of patients were admitted to hematology (37.7%) and ICU (32.7%) wards; 39.3% had hematological malignancy; 70.4% had at least one prior hospitalization.

**Reason for sampling**: To address the rising local prevalence of CRPA BSIs, characterize the molecular mechanisms driving carbapenem resistance, and identify clinical and genomic predictors of poor outcome to inform local treatment guidelines.

**Laboratory methods:** Species identification by MALDI‑TOF MS (Bruker). Antimicrobial susceptibility testing by VITEK 2 Compact system, interpreted per CLSI breakpoints. CRPA defined as resistance to imipenem and/or meropenem. MDR and DTR defined according to international criteria. WGS performed on the BGI DNBSEQ‑T7 platform (2 × 150 bp paired‑end). De novo assembly with Velvet v1.2.10. Mutations identified by alignment to reference PAO1 (NC_002516) using BLASTn. AMR genes predicted with CARD; virulence genes with VFDB. O‑antigen serotype predicted using PAst 1.0. MLST performed using the 7‑gene PubMLST scheme. Efflux pump gene expression measured by qRT‑PCR with ATCC 27853 as reference; relative quantification using 2⁻ΔΔCt method with rspL as internal control.

**Use cases:** Routine genomic surveillance, AMR mechanism detection, detection of high‑risk clones, population structure analysis, virulence factor detection, clinical risk factor analysis.

**Ethical / Legal Considerations and Approvals**

**Beneficence and non‑maleficence:** The study used residual diagnostic bacterial isolates and anonymised retrospective clinical data; no additional patient interventions were performed. Results were used to inform local antimicrobial stewardship and infection control policy.

**Distributive justice:** All consecutive *P. aeruginosa* BSI isolates meeting the inclusion criteria during the three‑year period were included.

**Privacy and autonomy**: Ethical approval was obtained from the Ethical Committee of the First Affiliated Hospital of Nanchang University (Approval No: IIT2025369). Given the retrospective nature of the study using anonymous clinical data, the requirement for informed consent was waived. The study was conducted in accordance with the Declaration of Helsinki.

**Data custodianship:** Raw sequencing data deposited in NCBI under BioProject PRJNA1242498.

**Transparency and accountability:** Published open access.

**Data protection:** Published data tables use coded strain identifiers; no direct patient identifiers are present.

**Public health integration:** Findings were used locally to refine empiric therapy recommendations for suspected *P. aeruginosa* BSI and to strengthen central venous catheter care bundles as a CRPA prevention measure.

**Data Analysis**

**Bioinformatic tools/analysis pipeline:**

- **Assembly and mutation detection:** Velvet v1.2.10; BLASTn v2.9.0 against PAO1 reference.

- **MLST**: 7‑gene scheme; sequences submitted to PubMLST for allelic profile and ST assignment; novel STs submitted for new designation.

- **Phylogenetic analysis:** Maximum‑likelihood tree from MLST data using FastTree v2.1.11 with 1,000 bootstrap replicates.

- **AMR and Virulence gene detection:** CARD and VFDB database, respectively. The paper does not explicitly state which specific software tool (e.g., RGI, ABRicate) was used for analyzing AMR and virulence genes.

- **Serotype prediction:** PAst 1.0.

- **OprD genotyping:** oprD sequences compared to PAO1; stratified into Type 1 (wild‑type or silent mutations) and Type 2 (premature stop codons or frameshift mutations producing truncated protein).

- **Efflux pump expression**: qRT‑PCR for mexB, mexD, mexF and mexY; ≥ 2‑fold upregulation considered significant.

- **Statistical analysis:** Chi‑square/Fisher's exact test for categorical variables; t‑test/Mann–Whitney U for continuous variables; binary logistic regression for CRPA BSI predictors; Cox regression for mortality risk factors; Kaplan–Meier for time‑to‑mortality.

**QC thresholds:** not explicitly specified except ATCC 27853 was used as reference for qRT‑PCR. Triplicate qRT‑PCR assays for reproducibility.

**Typing methods**: MLST (7‑gene scheme). Among 61 isolates, 49 distinct STs were identified, including 2 novel STs. The most frequent were ST244 (n=4, 6.5%), ST235 (n=3, 4.9%) and ST274 (n=3, 4.9%). Three clonal complexes were identified; the largest (CC1) contained 9 STs and 13 isolates. 39 of 49 STs were singleton types, demonstrating high clonal diversity.

**O‑antigen serotyping**: The most prevalent serotypes were O6 (26.2%) and O11 (19.6%). O11 was significantly associated with CRPA (p=0.02) and MDRPA (p=0.004) and was strongly correlated with oprD mutations (83.3% vs. 34.5% in non‑O11, p=0.008) and the exoU⁺/exoS⁻ genotype. O6 was evenly distributed across resistance phenotypes.

**Data Sharing Strategy**

- Raw reads and assemblies: NCBI BioProject PRJNA1242498.

- MLST data: Allelic profiles submitted to PubMLST; novel STs assigned.

- Code/pipelines: Standard publicly available tools used

- Restrictions: None – open access.

**Major Findings**

This WGS‑based analysis of 61 *P. aeruginosa* BSI isolates from a Chinese tertiary hospital (2021–2023) identified 29.5% CRPA prevalence, with MDR in 33.3% and DTR in 16.7% of CRPA strains. Carbapenem resistance was driven primarily by OprD inactivation (44.4% of CRPA had truncated OprD due to frameshift or nonsense mutations) and efflux pump overexpression (61.1% with ≥ 2‑fold upregulation, predominantly MexY), acting synergistically in many strains. Carbapenemase genes were detected in 33.3% of CRPA, including blaGES‑5, blaKPC‑2, blaNDM‑5, and the uncharacterised blaKPC‑99 and blaVEB‑1.

MLST revealed exceptionally high clonal diversity: 49 distinct STs among 61 isolates, including two novel STs, with 39 singleton STs - indicating endemic diversification rather than clonal outbreaks. The most prevalent STs were ST244, ST235 and ST274. O‑antigen serotype O11 was significantly associated with CRPA (p=0.02), MDRPA (p=0.004), oprD mutations (p=0.008) and the exoU⁺/exoS⁻ virulence genotype, predominantly in ICU isolates.

Convergence of resistance and virulence was documented: strains with oprD mutations were significantly more likely to carry exoU (p=0.032); three isolates co‑harboured oprD mutations, exoU, and multiple β‑lactamase genes, with high‑level carbapenem resistance (MIC \> 8 µg/mL).

Clinically, central venous catheterization was the sole independent risk factor for CRPA BSI development (OR 6.6, p=0.002). The 30‑day mortality was 50.8%, with prior carbapenem exposure, mechanical ventilation, and low haemoglobin identified as independent mortality predictors. Mortality did not differ significantly between CRPA and CSPA.

**Public Health Actions**

- Central Venous Catheter (CVC) care bundle reinforcement: With central venous catheterization conferring a 6.6‑fold increased risk of CRPA BSI, the hospital intensified CVC insertion and maintenance care bundles,

- Carbapenem stewardship: Prior carbapenem exposure was an independent predictor of mortality; antimicrobial stewardship rounds were instituted in ICU and haematology wards with prospective audit and feedback for all carbapenem prescriptions.

- Empiric therapy guidance: Given the 29.5% CRPA prevalence and the dominance of non‑carbapenemase resistance mechanisms, the paper guide evidence-based antimicrobial therapy for suspected *P. aeruginosa* BSI in patients with CVCs or prior carbapenem exposure.

- Enhanced surveillance for O11 strains: O11 was flagged as a potential marker for MDR *P. aeruginosa*; the laboratory began reporting O‑serotype for all sterile‑site *P. aeruginosa* isolates to guide infection control risk assessment.

- Future research direction: The authors committed to investigating clinical isolates with similar genetic backgrounds but divergent carbapenem susceptibility to elucidate the evolutionary pathways leading to carbapenem resistance.

- Molecular testing augmentation: The finding that two‑thirds of CRPA lacked carbapenemase genes (OprD inactivation and efflux pump overexpression) prompted the addition of targeted sequencing of oprD to the laboratory's resistance mechanism investigation algorithm for isolates with unexplained carbapenem resistance.

**Case Study \#2 – Molecular Epidemiology of a Nationwide *Pseudomonas aeruginosa* Outbreak in Norway Reveals Multiple Distinct Clusters Including High‑Risk Clone ST244 (2021–2022)**

[**<u>https://www.sciencedirect.com/science/article/pii/S0195670125003603</u>**](https://www.sciencedirect.com/science/article/pii/S0195670125003603)

**Aim**: To investigate the molecular epidemiology of *Pseudomonas aeruginosa* bacteraemia across Norway by analyzing a comprehensive, nationwide collection of blood culture isolates assembled during an outbreak investigation, identifying additional unrecognized phylogenetic clusters and assessing the prevalence of high‑risk and epidemic clones.

**Surveillance Strategy/System Design**

**Setting**: A nationwide, multi-center study covering Norway. The study included all four Regional Health Trusts and 20 diagnostic microbiology laboratories that serve the country's 65 public hospitals. The collection captured \> 90% of the national catchment area.

**Sampling strategy:** The study was initiated during an investigation of a nationwide clonal outbreak of wild‑type *P. aeruginosa* ST3875, later linked to contaminated pre‑moistened washcloths. During this investigation, all microbiology laboratories were asked to submit stored *P. aeruginosa* isolates from blood cultures for WGS analysis. The collection comprised all unique blood culture isolates of *P. aeruginosa* collected between 1 January 2021 and 30 June 2022.

**Isolate types and sample size:** The collection included 376 unique patients with *P. aeruginosa* bacteraemia from 33 hospitals. After sequencing and quality control, sequence types (STs) were determined for 362 isolates, with further bioinformatic analyses conducted on 350 isolates that met all QC criteria. The majority of patients (69%) were male; the median age was 76 years (range 6–103). The incidence of *P. aeruginosa* bacteraemia varied by region (5.1–16.3 per 100,000 population).

**Reason for sampling:** The primary investigation aimed to confirm and track the ST3875 outbreak. The comprehensive collection of all bacteraemia isolates over 18 months also enabled a secondary objective: to determine whether additional, unrecognized phylogenetic clusters were circulating nationally and to characterize the broader molecular epidemiology of invasive *P. aeruginosa* in Norway.

**Laboratory methods:** Species identification was performed at each contributing laboratory using standard methods. All isolates were stored at the diagnostic laboratories. WGS was carried out at five university hospitals across Norway. DNA was extracted using commercial kits (EZ1 DNA Tissue Kit or MagNa Pure DNA Kit). Library preparation used the DNA Prep or Nextera XT kit. Sequencing was performed on Illumina MiSeq platforms (150/250/300 bp paired‑end) for most isolates, supplemented by Oxford Nanopore Technologies (ONT) GridION/MinION sequencing (R9.4.1 flow cells, Rapid Barcoding Kit) for selected isolates.

**Use cases:** Routine genomic surveillance, outbreak investigation, detection of high‑risk clones, population structure analysis, transmission cluster detection, virulence factor characterization.

**Ethical / Legal Considerations and Approvals**

**Beneficence and non‑maleficence:** The study used bacterial isolates and data recorded as part of routine hospital infection control and outbreak investigations, with no additional patient interventions. Genomic findings provided direct public health benefit by identifying unrecognized clusters requiring investigation and by characterizing the dissemination of the ST244 high‑risk clone.

**Distributive justice:** The study covered \> 90% of the national catchment area, including all four health regions and 33 hospitals, providing equitable representation of the Norwegian population.

**Privacy and autonomy:** Data were recorded as part of hospital routines for outbreak investigations, authorized by institutional infection control programs and the Norwegian regulation of infection control in the healthcare service (FOR‑2005‑06‑17‑610). No individual patient consent was required for this public health surveillance activity. Published data are de‑identified; isolate‑level metadata are limited to sampling date, hospital, and health region.

**Data custodianship:** All raw sequencing reads were deposited in the European Nucleotide Archive (ENA) under project PRJEB102899. Data were also stored and shared within the secure Norwegian e‑Infrastructure for Life Sciences (NeLS) platform.

**Transparency and accountability**: Published open access under a Creative Commons license. The analytical pipeline (MinTyper, Parsnp, cgMLST via Ridom SeqSphere+, AMRFinderPlus, ABRicate/VFDB) and all QC thresholds are fully described. The Norwegian Pseudomonas Study Group includes collaborators from all contributing laboratories.

**Data protection:** Metadata in the publication are aggregated by health region and hospital; individual patient identifiers are not included.

**Public health integration:** The study was embedded within a national outbreak response. Results directly informed the withdrawal of contaminated washcloth products and identified the ST244 cluster and other novel clusters as priorities for further epidemiological investigation.

**Data Analysis**

**Bioinformatics pipeline(s):**

> **Quality control and read trimming**: Chopper v0.8.0 (‑q 10 ‑l 500) for ONT reads; TrimGalore v0.6.10 (‑q 20, --length 50) for Illumina reads. Mean sequencing depth \> 20× required.
>
> **Assembly**: SPAdes v4.0 for Illumina‑only; Flye v2.8.1 for ONT‑only; Unicycler v0.4.8 for hybrid assemblies.
>
> **MLST**: mlst v2.23 using the *P. aeruginosa* 7‑gene scheme (PubMLST).
>
> **AMR gene detection**: AMRFinderPlus v4.0.19 (database version 2024‑12‑18.1).
>
> **Virulence factor detection**: ABRicate v1.0.1 screening contigs against the Virulence Factor Database (VFDB, accessed 20 December 2024).

**Phylogenetic and cluster analysis**: MinTyper v1.1.2 used to generate a distance matrix and neighbour‑joining phylogenies. Clusters were initially identified using a core‑genome SNP (cgSNP) distance ≤ 5 and confirmed with a threshold of cgSNP ≤ 12 in cluster‑specific analyses. cgMLST analysis was performed using Ridom SeqSphere+ v8.5.1 with the public *P. aeruginosa* cgMLST scheme (3,867 loci); clusters defined at ≤ 12 allelic differences. Parsnp v2.1.3 was used for global phylogenetic context, incorporating a 100‑genome reference panel, the reference strains PAO1, PA14 and PA7, four ST3875 isolates from contaminated washcloths, and the historical ST27 *P. aeruginosa* isolate from the national Dent‑O‑Sept outbreak (2002).

**Comparative genomics of genomic island (GI):** NCBI BLASTn of the 49.9 kb GI against all completed Pseudomonas genomes (n=3,685) and against all assembled study genomes. Annotation with Bakta v1.7.0, eggNOG‑mapper, and the NCBI conserved domain database. Chromosome alignments with ACT and EasyFig.

**QC thresholds**: Mean depth \> 20×; isolates failing assembly excluded (n=9 for assembly‑dependent analyses). Clusters confirmed by two independent methods (MinTyper and cgMLST).

**Typing methods**: MLST (7‑gene scheme). Among 362 isolates with resolved STs, 164 distinct STs were identified, including 116 singletons. Groups of identical STs (n=48) accounted for 68% of the collection.

**AMR detection**: None of the 350 analysed isolates harboured genes encoding acquired carbapenemases or extended‑spectrum β‑lactamases, consistent with Norway's low prevalence of MDR *P. aeruginosa*. Detected AMR genes and point mutations are summarized in the supplementary material; none conferred MDR/XDR profiles.

**Virulence detection:** The T3SS virulence determinant distribution varied: of the 10 identified clusters, four carried exoS and six carried exoU. The ST3875 outbreak clone was exoU⁺, a genotype associated with severe infection, sepsis and mortality. The C‑2 (ST244) cluster isolates carried exoU. A distinct outlier clade containing C‑10 and three other study isolates was predominantly exoS⁺.

**Phylogenetic/cluster analysis:**

- All study isolates belonged to phylogroups 1 and 2, consistent with clinically associated *P. aeruginosa* lineages.

- Beyond the ST3875 outbreak cluster (C‑1, n=56 isolates), nine additional phylogenetic clusters (C‑2 to C‑10) were identified, encompassing two to 20 isolates each and accounting for 12% of the collection. These clusters spanned multiple hospitals and health regions, with no previously recognized epidemiological links.

- C‑1 (ST3875 outbreak): 56 patients, 16 hospitals, all four regions, timespan 8 months. Linked to pre‑moistened washcloths.

- C‑2 (ST244, n=20): 9 geographically dispersed hospitals, timespan 17 months. The cluster displayed a pattern resembling the ST3875 outbreak, suggesting a possible common source. Four isolates in the central node of the MST originated from three different regions over 10 months.

- C‑3 (ST3889, n=6): 4 hospitals, 3 regions, timespan 11 months. This ST is rare, previously reported only once outside Norway (China).

- C‑4 (ST1094, n=3), C‑5 to C‑10 (n=2 each): Each involved 2–3 patients at different hospitals, with no confirmed epidemiological links.

- Global high‑risk clones accounted for 30% of the collection: ST244 (n=44), ST308 (n=3), ST233 (n=1), ST277 (n=1), ST298 (n=1). Additional epidemic‑associated STs comprised a further 16%.

- Global Parsnp tree showed Norwegian isolates distributed broadly across the worldwide *P. aeruginosa* phylogeny, with C‑2, C‑4, C‑6 and C‑10 in phylogroup 1.

**Genomic island discovery (PAGI‑N07):** A 49.9 kb genomic island was identified in the C‑2 (ST244) cluster genome NorPa_0007, inserted into the chromosome relative to the reference ST244 genome W16407. The GI contained 40 coding sequences, including a putative virulence module with nine CDS encoding an SDR‑family oxidoreductase, a metallopeptidase complex, an ABC‑type multidrug efflux transporter, TonB2/TonB3 metal transport systems, an RND multidrug efflux system, and the mercury resistance mer operon. Flanking ISPa41 and Tn3‑family transposases, bordered by short direct repeats (DR1: CTAG, DR2: CCTTAAGG), indicated a mobile composite transposon. Homologous elements (≥ 90% coverage, 99.6–100% identity) were identified in 66 global *P. aeruginosa* genomes, including unrelated STs associated with epidemic clones (ST111, ST179, ST244, ST260, ST298, ST309, ST395, ST446, ST463, ST532). Within the Norwegian collection, nearly complete GIs were detected in additional ST244 (n=4), ST313 (n=3), and one each of ST233, ST395, ST2025 and ST3003.

**Statistical/epidemiological integration:** Incidence rates stratified by health region and hospital; timeline visualization of clusters C‑1 to C‑4; MST with colour‑coding by health region and, for C‑2, by isolation date.

**Data Sharing Strategy**

- Raw reads: ENA project PRJEB102899.

- Assemblies: Stored and shared within the NeLS platform (Norwegian e‑Infrastructure for Life Sciences).

- Metadata: Aggregated patient demographics, hospital/region distribution, and cluster assignments in publication figures and tables. Supplementary data include ST assignments, AMR genes, virulence factors and cluster details.

- Code/pipelines: All tools used are publicly available; detailed parameters provided in the Methods.

- Restrictions: None – open access publication; raw data publicly available via ENA.

**Major Findings**

This nationwide genomic surveillance study of 376 *P. aeruginosa* bacteraemia isolates from 33 Norwegian hospitals, representing \> 90% of the national catchment area over 18 months, identified 164 distinct STs and 10 phylogenetic clusters. Beyond the known ST3875 outbreak clone (C‑1, n=56, linked to contaminated washcloths), nine previously unrecognized clusters (C‑2 to C‑10) were discovered, encompassing two to 20 patients each across multiple hospitals and health regions, accounting for 12% of the collection.

The largest of these, C‑2 (ST244, n=20), spanned 17 months and nine geographically dispersed hospitals. A novel 49.9 kb putative virulence‑encoding genomic island (PAGI‑N07) was identified in the C‑2 clone, carrying genes for metal transport, multidrug efflux, mercury resistance, and oxidative stress response, flanked by mobile elements indicating a composite transposon. Homologous islands were detected in 66 global *P. aeruginosa* genomes, enriched in epidemic STs including ST111, ST179, ST244, ST260 and ST298, suggesting a selective advantage for dissemination.

Global high‑risk and epidemic clones comprised 30% of all bacteraemia isolates, dominated by ST244 (n=44). None of the 350 analyzed genomes harbored acquired carbapenemase or ESBL genes, demonstrating that in Norway's low‑AMR setting, clonal success is driven by factors other than antibiotic resistance, potentially including the identified virulence island.

All isolates clustered within phylogroups 1 and 2, and the T3SS virulence genotype varied by cluster: the ST3875 outbreak clone was exoU⁺, the ST244 C‑2 cluster was exoU⁺, and C‑10 was predominantly exoS⁺. The study demonstrates that comprehensive, nationally coordinated WGS‑based surveillance, integrated with epidemiological data, can detect emerging high‑risk clones and transmission clusters that would otherwise remain invisible to routine typing.

**Public Health Actions**

- Product recall and national alert: Confirmation that the ST3875 outbreak was linked to pre‑moistened washcloths led to a national product recall in March 2022 and an international notification through the Norwegian Institute of Public Health. Cases declined following product withdrawal.

- Enhanced surveillance for ST244: The discovery of the widespread, 17‑month ST244 cluster across nine hospitals prompted national recommendations for heightened surveillance and investigation of possible common sources.

- National WGS‑based surveillance integration: The study's findings catalyzed discussions within the Norwegian health authorities to integrate routine WGS‑based surveillance of *P. aeruginosa* bloodstream infections into the national infection control program, complementing existing phenotypic surveillance.

- Cross‑regional cluster investigation framework: Identification of clusters spanning multiple health regions highlighted the need for a coordinated, national‑level outbreak investigation protocol, with clear data‑sharing pathways between hospitals, reference laboratories, and public health authorities.

- Genomic island screening for high‑risk clones: The discovery of the PAGI‑N07 virulence‑associated Island in multiple epidemic STs was shared with the international community to facilitate global screening and risk assessment.

- International notification regarding washcloth contamination: The finding that the manufacturer continued distributing potentially contaminated products until notified by Norwegian authorities underscored the need for a proactive international system for sharing product recall information.

## 8.5 Staphylococcus aureus 

*Staphylococcus aureus* is a Gram-positive, catalase-positive, facultative anaerobic coccus that exists both as a widespread human commensal and an opportunistic pathogen. Approximately 30% of healthy individuals carry S. aureus, most commonly in the anterior nares and on skin, where carriage serves as a reservoir for subsequent infection (Laux et al., 2019). The global clinical threat posed by methicillin‑resistant S. aureus (MRSA) has been recognized by the World Health Organization, which lists drug‑resistant *S. aureus* among the High Priority pathogens in the 2024 Bacterial Priority Pathogens List, underscoring the need for enhanced surveillance and targeted R&D (WHO, 2024). Advances in whole‑genome sequencing (WGS) have transformed diagnostic, epidemiologic, and infection‑control workflows by providing high‑resolution strain typing, accurate detection of resistance and virulence determinants, and robust phylogenetic context for outbreak investigation.

## 8.5.1 Background and Public Health Relevance 

*Staphylococcus aureus* remains a leading cause of invasive bacterial disease worldwide and is a major driver of both healthcare‑associated and community‑onset sepsis. Global analyses attribute on the order of 166, 000-485,000 deaths annually to infections in which *S. aureus* is a principal pathogen, placing it among the top bacterial contributors to infection‑related mortality (Ikuta et al., 2022). Case fatality for *S. aureus* bacteremia within 30 days (15% and 30%) is high, reflecting the organism’s capacity for rapid progression and severe systemic disease. Report showed that \>30% of patients with *S. aureus* bacteremia develop secondary foci, including infective endocarditis (~10-15%), septic arthritis, vertebral osteomyelitis, and deep‑tissue abscesses; these complications substantially increase morbidity, length of stay, and mortality. The clinical burden is amplified by antimicrobial resistance, most notably methicillin‑resistant *S. aureus* (MRSA), which carries the mecA/mecC determinants on staphylococcal cassette chromosome mec (SCCmec) elements that confer resistance to most β‑lactams. Horizontal transfer and diversification of SCCmec among staphylococci have driven repeated emergence of MRSA lineages in both hospitals and the community (Mylotte & Tayara, 2000; van Hal et al., 2012).

The therapeutic landscape is further threatened by vancomycin‑intermediate (VISA) and vancomycin‑resistant (VRSA) phenotypes and by evolving resistance to other last‑line agents; these trends underscore the need for early detection of resistance determinants and for genomic markers that predict treatment failure. Whole‑genome sequencing (WGS) provide high‑resolution phylogenetic context for transmission mapping, precise identification of SCCmec types and other mobile elements, detection of single‑nucleotide variants associated with reduced susceptibility, and comprehensive profiling of virulence loci (for example, Panton‑Valentine leukocidin \[PVL\] and toxic shock syndrome toxin‑1 \[TSST‑1\])). WGS therefore enables differentiation of true nosocomial outbreaks from independent introductions, supports targeted infection‑control interventions in critical‑care settings, and informs antimicrobial stewardship and public‑health responses (Aanensen et al., 2016).

## 8.5.2 Key Genomic Features

### 8.5.2.1 Species Complex and Taxonomic Differentiation

The *Staphylococcus aureus* complex (SAC) comprises closely related species including *Staphylococcus aureus*, *Staphylococcus argenteus*, and *Staphylococcus schweitzeri*, which share substantial genomic similarity but differ in epidemiology, virulence characteristics, and host adaptation (Chantratita et al., 2020; Tong et al., 2019). Comparative genomic studies have demonstrated that these species form distinct phylogenetic clusters despite exhibiting highly conserved core genomes. Average nucleotide identity (ANI) analysis has further supported their taxonomic separation, with threshold values commonly used to distinguish species boundaries within the complex (Tong et al., 2019).

*Staphylococcus argenteus* was initially misidentified as *S. aureus* because of similar phenotypic and biochemical characteristics. However, genomic investigations revealed significant divergence, including the absence of the carotenoid pigment staphyloxanthin that typically gives *S. aureus* its golden coloration (Chantratita et al., 2020). Similarly, *S. schweitzeri* represents a related lineage predominantly associated with animal reservoirs and has been proposed as part of the broader SAC evolutionary framework (Tong et al., 2019).

Accurate differentiation among SAC members remains clinically and epidemiologically important because routine laboratory methods, including conventional biochemical assays and some MALDI-TOF MS databases, may incorrectly classify *S. argenteus* or *S. schweitzeri* as *S. aureus* (Chantratita et al., 2020). Such misidentification can lead to underestimation of species diversity, inaccurate surveillance data, and incomplete understanding of transmission dynamics. Whole-genome sequencing and high-resolution genomic analyses therefore play an essential role in resolving species-level taxonomy and improving global surveillance strategies for staphylococcal pathogens.

### 8.5.2.2 Population Structure and Major Lineages

The global population structure of *S. aureus* is considered highly clonal, organized into well-defined Clonal Complexes (CCs) that are shared across both methicillin-susceptible (MSSA) and methicillin-resistant (MRSA) strains. While thousands of sequence types exist, a small group of major lineages drives the global burden of invasive sepsis and bacteremia:

- CC5 and CC8: The dominant global lineages responsible for the majority of healthcare-associated MRSA (HA-MRSA) and community-associated MRSA (CA-MRSA) infections. CC8 includes the USA300 epidemic clone.

- CC22 and CC30: Major global lineages frequently associated with hospital-acquired bacteremia, infective endocarditis, and toxic shock syndrome.

- CC398: Once primarily known as a Livestock-Associated MRSA (LA-MRSA) in Europe, it is increasingly identified in human infections worldwide.

### 8.5.2.3 Genotyping 

In *S. aureus* genomics, structural classification relies on a dual-typing framework combining multi-locus and single-locus targets:

**Protein A (spa) Typing:** A highly discriminatory, single-locus typing method that sequences the polymorphic X-region of the **spa gene** (highly variable gene which codes for Protein A). This region contains variable numbers of 24-base-pair tandem repeats. Strains are assigned a unique spa type (e.g., t008, t032) based on the specific repeat sequence and arrangement.

**Agr Typing and Quorum Sensing Regulation:** The accessory gene regulator (agr) system is a primary quorum-sensing regulatory network in S. aureus that coordinates the expression of many virulence-associated genes (expression of toxins, extracellular enzymes, adhesins, and immune evasion factors) in response to bacterial population density. Based on hypervariable sequence polymorphisms within the agr locus, S. aureus strains are classified into four principal groups (agr I-IV) that exhibit distinct auto-inducing peptide specificities and correlate with specific clonal lineages and pathogenic behaviors. Activation of this system acts as a molecular switch, promoting the critical transition from colonization-associated phenotypes to invasive virulence states by up-regulating extracellular toxins and enzymes while concurrently reducing the expression of surface-associated adhesins, a mechanism central to the pathogenesis of acute bacteremia, deep-tissue infections, and severe sepsis (Cheung et al., 2011).

**MLST:** A standard 7-gene scheme (arcC, aroE, glpF, gmk, pta, tpi, yqiL) is used to assign a Sequence Type (ST) and group strains into broad Clonal Complexes. MLST provides a stable, highly reproducible backbone for long-term global evolutionary surveillance, though it lacks the fine granularity needed for immediate local outbreak investigation.

**cgMLST:** provides the ultra-high resolution required to investigate local hospital transmission and distinguish between active sepsis outbreaks and sporadic, unlinked introductions.

### 8.5.2.4 Mechanisms of Resistance

The therapeutic challenges associated with *S. aureus* sepsis are driven by a highly dynamic resistome capable of executing broad target modifications, enzymatic drug inactivation, and rapid horizontal gene transfer (HGT).

**Methicillin Resistance and SCCmec Structural Classification**

Methicillin resistance (MRSA) is defined by absolute resistance to virtually all standard beta-lactam antibiotics. This phenotype is mediated by the acquisition of the mecA or mecC genes, which encode alternative penicillin-binding proteins (PBP2a or PBP2c) featuring an exceptionally low binding affinity for beta-lactams. These resistance determinants are structurally carried on a mobile genomic island termed the Staphylococcal Cassette Chromosome mec (SCCmec).

### Mobile Genetic Elements and Horizontal Gene Transfer

Horizontal gene transfer plays a central role in the evolution, adaptation, and pathogenicity of *Staphylococcus aureus* (Malachowa & DeLeo, 2017). The acquisition and dissemination of mobile genetic elements (MGEs) contribute significantly to antimicrobial resistance, virulence diversification, and host adaptation. Major MGEs identified in *S. aureus* include staphylococcal cassette chromosome mec (SCCmec) elements, plasmids, prophages, insertion sequences (IS elements), transposons, and staphylococcal pathogenicity islands (SaPIs) (Malachowa & DeLeo, 2017; Novick & Ram, 2016).

SCCmec elements are among the most clinically important MGEs because they carry the *mecA* or *mecC* resistance genes responsible for methicillin resistance in MRSA strains. Comparative genomic analyses have demonstrated extensive SCCmec diversity and mobility, highlighting their role in the rapid emergence and global dissemination of resistant clones. Recombination and horizontal transfer events involving SCCmec contribute to continuous genomic evolution within staphylococcal populations (Hiramatsu et al., 2014).

Prophages also represent critical drivers of genomic variability by mediating the transfer of virulence-associated genes. In particular, bacteriophages carrying Panton–Valentine leukocidin (PVL) genes have been strongly associated with enhanced virulence and severe skin and soft tissue infections. Similarly, SaPIs function as highly specialized pathogenicity islands capable of mobilization through helper phages, facilitating the spread of toxin genes and superantigen determinants across strains (Novick & Ram, 2016).

Plasmids and IS elements further contribute to genomic plasticity by promoting gene rearrangements, resistance gene acquisition, and adaptive evolution. Antimicrobial resistance (AMR) plasmids frequently encode determinants for multidrug resistance, including resistance to macrolides, aminoglycosides, tetracyclines, and other clinically relevant antibiotics. In addition, toxin islands and other accessory genomic regions enhance the pathogenic potential of specific lineages by encoding enterotoxins, immune evasion factors, and additional virulence-associated proteins (Malachowa & DeLeo, 2017).

Overall, MGEs constitute a dynamic component of the *S. aureus* genome and are fundamental to the organism’s capacity for rapid adaptation, persistence, and epidemiological success in both healthcare and community settings.

### 8.5.2.5 Virulence Profiling and Toxins

The clinical severity of *S. aureus* sepsis, tissue necrosis, and toxic shock syndrome stems from an expansive virulence arsenal. These factors are categorized into cell wall-anchored surface proteins, immune-evasion molecules, and potent secreted toxins.

**Core Virulence Categories**

> **Adhesion and Colonization**: *S. aureus* expresses a specialized array of surface proteins known as MSCRAMMs (Microbial Surface Components Recognizing Adhesive Matrix Molecules), encoded by genes such as fnbA/fnbB (fibronectin-binding), clfA/clfB (clumping factors), and cna (collagen-binding). These factors mediate primary attachment to host endothelial surfaces and fibrin clots, establishing the initial focus of invasive bacteremia and endocarditis.
>
> **Immune Evasion**: The pathogen neutralizes the host immune response using surface Protein A (spa), which binds the Fc region of IgG molecules to prevent opsonophagocytosis. Secreted factors like Staphylokinase (sak) and the Chemotaxis Inhibitory Protein of *S. aureus* (chp) further block complement activation and neutrophil recruitment.

**Secreted Cytotoxins and Superantigens**

The presence of mobile genetic elements (prophages, pathogenicity islands, and plasmids) dictates an isolate's toxin profile, which correlates with distinct clinical sepsis syndromes:

> **Panton-Valentine Leukocidin (PVL):** is a cytotoxin that forms pores and is encoded by the lukF-PV and lukS-PV genes, usually carried on lysogenic bacteriophages. PVL specifically destroys neutrophils, causing the release of pro-inflammatory contents. It is linked to highly virulent community-associated MRSA (CA-MRSA) strains and is associated with severe conditions like necrotizing hemorrhagic pneumonia and deep-tissue abscesses.
>
> **Toxic Shock Syndrome Toxin-1 (TSST-1):** Encoded by the tsst-1 (tst) gene and located on staphylococcal pathogenicity islands (SaPIs). TSST-1 is a potent **superantigen** that cross-links MHC Class II molecules on antigen-presenting cells with T-cell receptors without typical antigen processing. This bypass induces massive clonal T-cell proliferation and an immediate "cytokine storm" (hyper-production of IL-1, IL-6, TNF-alpha), driving staphylococcal toxic shock syndrome and lethal multi-organ failure.
>
> **Enterotoxins and Exfoliative Toxins**: *S. aureus* genomes can harbor a wide array of enterotoxin genes (such as SEA through SEU) that act as superantigens during systemic infections, contributing to persistent hypotension and capillary leak syndrome. The exfoliative toxins A and B (eta, etb) are protease enzymes that specifically cleave desmoglein-1 in the epidermis, causing staphylococcal scalded skin syndrome (SSSS).

**Biofilm Formation and Persistence**

Biofilm formation is a critical virulence mechanism in Staphylococcus aureus that contributes to chronic infection, antimicrobial tolerance, and immune evasion (Otto, 2013). The development of biofilms is strongly associated with the icaADBC operon, which encodes enzymes involved in the synthesis of polysaccharide intercellular adhesin (PIA), an important component of the extracellular biofilm matrix. In addition to polysaccharide-mediated mechanisms, S. aureus biofilms may also contain extracellular DNA, proteins, and other surface-associated factors that enhance structural stability and persistence (Otto, 2013). Persistent bloodstream infections have been associated with enhanced biofilm-producing capacity, altered virulence regulation, and increased tolerance to antibiotic therapy. These characteristics contribute to treatment failure, relapse, and increased clinical severity in invasive S. aureus infections (Tong et al., 2019).

## 8.5.3 Pathogen-Specific Analysis and Interpretation

For all baseline processing steps, including raw read quality control, adapter removal, contamination screening, taxonomic verification, and de novo assembly, refer to the core bioinformatic section. For the *Staphylococcus aureus* complex (SAC), bioinformatic species verification must differentiate true *S. aureus* from closely related members like S. argenteus and S. schweitzeri. Species confirmation must be verified using Kraken2 or FastANI (requiring ≥ 95% ANI to the reference strain NCTC 8325).

#### 8.5.3.1 Recommended Bioinformatics Tools for S. aureus

| **Analysis Step**                                      | **Recommended Tool(s)** | **Specific Parameters / Notes**                                                                                                                                             |
|--------------------------------------------------------|-------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **AgrVATE (agr Variant Assessment and Typing Engine)** | **AgrVATE**             | is a tool for rapid identification of S. aureus agr locus type and also reports possible variants in the agr operon. Requires a *S. aureus* genome assembly in FASTA format |
| **MLST Typing**                                        | mlst (Seemann)          | Use --scheme saureus to screen against the PubMLST database. Essential for establishing the broad genetic backbone and determining Clonal Complexes (CCs).                  |
| **spa Typing**                                         | spaTyper / Bactopia     | Automatically extracts and characterizes the polymorphic X-region repeat sequences of the *spa* gene. Reports standardized t-types (e.g., t008, t032).                      |
| **cgMLST**                                             | chewBBACA               | A cgMLST analysis to evaluate genetic variation across 1,861 core loci to precisely differentiate clonal S. aureus strains during outbreak investigations.                  |
| **SCC*mec* Characterization**                          | SCCmecFinder            | Analyzes short-read assemblies or long-read fasta inputs to identify structural combinations of the *mec* and *ccr* gene complexes (e.g., Type IV(2B)).                     |
| **AMR Detection**                                      | AMRFinderPlus           | Run with --organism Staphylococcus_aureus. Accurately catalogs acquired genes (*mecA*, *mecC*, *blaZ*, *vanA*) and tracks critical ribosomal or regulatory mutations.       |
| **Virulence Profiling**                                | VFDB (via ABRicate)     | Screens for staphylococcal-specific cytotoxins (*lukS/F-PV* for PVL), superantigens (*tst* for TSST-1), enterotoxins, and MSCRAMM adhesins.                                 |
| **SNP Phylogeny**                                      | Snippy + Gubbins        | Reference-based variant calling mapping against a lineage-matched closed genome (e.g., USA300_FPR3757 for CC8). Filter recombinations using Gubbins.                        |

#### 8.5.3.2 Caveats and Limitations

Surveillance and clinical interpretation of *S. aureus* WGS data face several biological and technical constraints:

**Phenotype-Genotype Discordance** where the detected genetic profile does not fully correspond with observed antimicrobial susceptibility patterns. Oxacillin-susceptible mecA-positive S. aureus (OS-MRSA) represents a notable example of discordance. These isolates carry the mecA gene associated with methicillin resistance but may appear phenotypically susceptible to oxacillin or cefoxitin during routine susceptibility testing.

**SCCmec Cassette Dropouts and Empty Cassettes**: *S. aureus* can undergo spontaneous deletions of the mecA/C genes while retaining the rest of the structural staphylococcal cassette chromosome. Short-read sequencing pipelines may misidentify these "empty cassettes" or partial dropouts as true MRSA if they only search for structural SCCmec elements without explicitly verifying the presence of the mecA/C structural genes.

**Assembly Fragmentation at the spa Locus**: The protein A (spa) gene contains a highly repetitive polymorphic X-region. Short-read Illumina platforms often fail to resolve these 24-base-pair tandem repeats, resulting in a fragmented assembly where the spa locus is split across multiple contigs. This can cause in silico tools like spaTyper to fail or report incomplete spa types, requiring raw-read mapping methods to resolve the sequence.

**Copy Number Variations in 23S rRNA Linezolid Resistance:** *S. aureus* possesses 5 to 6 copies of the 23S rRNA gene. Mutational linezolid resistance (such as the G2576T substitution) is highly dependent on gene copy number; low-level resistance occurs when only one or two copies are mutated, whereas full clinical resistance requires mutations in the majority of copies. Standard consensus assembly pipelines often hide this heterogenous mix (heteroplasmy), making it necessary to calculate raw-read allele frequencies to accurately predict the phenotype.

## 8.5.4 Case Study for *S. aureus* 

**Case Study \#1 – Genomic Epidemiology of *Staphylococcus aureus* Bloodstream Infections in a Tertiary Hospital, Central China (2020–2024)**

[<u>https://www.frontiersin.org/journals/public-health/articles/10.3389/fpubh.2026.1807676/full</u>](https://www.frontiersin.org/journals/public-health/articles/10.3389/fpubh.2026.1807676/full)

**Aim**: To clarify the epidemiological characteristics, antimicrobial resistance profiles, clonal lineages, virulence gene carriage, and SCCmec types of *S. aureus* causing nosocomial bloodstream infections (BSIs) over five years, and to evaluate the application of whole‑genome sequencing (WGS) for genomic surveillance and infection control in a tertiary hospital in central China.

**Surveillance Strategy/System Design**

**Setting**: Wanbei Coal‑Electricity Group General Hospital, a tertiary sentinel hospital in Suzhou, central China

**Sampling strategy**: Consecutive, retrospective inclusion of all blood culture‑positive *S. aureus* isolates from nosocomial BSI between January 2020 and December 2024. Only the first isolate per patient per hospitalization episode was included. Nosocomial BSI defined per CDC criteria (blood culture \>48 h after admission).

**Sampling frame: 5 years (2020–2024)**

**Isolate types:** Blood cultures only; no colonisation or environmental isolates

**Sample size:** 96 isolates (71 MRSA, 25 MSSA)

**Reason for sampling strategy:** To monitor temporal trends in MRSA proportion, identify dominant clones and transmission clusters, characterize resistance and virulence determinants, and assess the utility of WGS for hospital infection prevention and control.

**Laboratory methods:** Species identification by MALDI‑TOF MS (Biotyper 2.0 database); antimicrobial susceptibility testing (AST) by VITEK‑2XL Compact (AST‑GP639 cards) with confirmation by disk diffusion and oxacillin agar screen for discordant results; interpretation per CLSI M100 (2025) and EUCAST v13.0 (tigecycline).

**Sequencing approach**: Illumina NovaSeq 6000 (PE150); DNA extracted using Coolaber Bacterial Genomic DNA Extraction Kit; library prepared with Illumina Nextera DNA Flex Library Prep Kit.

**Use case(s):** Routine genomic surveillance, AMR mechanism detection, detection of high‑risk clones, SCCmec typing, nosocomial transmission inference.

**Ethical / Legal Considerations and Approvals**

**Beneficence and non‑maleficence**: The study used residual bacterial isolates and de‑identified clinical data; no additional patient interventions. Findings directly informed local empiric therapy guidelines and departmental infection control prioritization.

**Distributive justice:** Consecutive inclusion of all *S. aureus* BSI isolates over 5 years across 19 hospital departments ensured broad representation, with a particular focus on the high‑burden Department of Nephrology. Single‑center design limits generalisability but provides local baseline data.

**Privacy and autonomy**: The study was approved by the Ethics Committee of Wanbei Coal Electric Group General Hospital (Approval No: WBCEGGH20241025033). Written informed consent was waived in accordance with national legislation and institutional requirements for retrospective studies using de‑identified clinical and strain data.

**Data custodianship**: Raw whole‑genome sequencing data deposited in NCBI under BioProject PRJNA1419524.

**Transparency and accountability**: Published open access. All supplementary data are available online.

**Data protection**: De‑identified clinical and strain data used throughout; no patient identifiers in public datasets.

**Public health integration**: Results were used to designate the Department of Nephrology as a key prevention and control ward, to reinforce vancomycin as first‑line MRSA therapy, and to flag the detection of vancomycin‑resistant, tigecycline‑resistant and phenotypically discordant MRSA strains for enhanced surveillance.

**Data Analysis**

**Bioinformatics pipeline(s):**

> **Quality control and assembly**: FastQC v0.11.9; fastp v0.23.2 (remove adapters, discard N \> 5%, trim \< Q20, minimum length 50 bp); SPAdes v3.15.5 (--careful, k‑mers 21,33,55,77); QUAST v5.0.2 for assembly metrics; CheckM (completeness ≥ 95%, contamination ≤ 5%). Assembly inclusion: N50 ≥ 20 kb, contigs ≤ 500, total length consistent with S. aureus reference.
>
> **Genome annotation:** Prokka v1.14.6.
>
> **AMR gene detection**: ABRicate v1.0.1 against Resfinder database.
>
> **Virulence factor detection**: ABRicate v1.0.1 against VFDB database.
>
> **MLST**: mlst v2.23.0 against PubMLST scheme.
>
> **Phylogenetic tree**: Snippy‑core with Gubbins recombination removal; FastTreeMP with GTRGAMMA model; visualisation via Chiplot.
>
> **SCCmec typing**: SCCmecFinder v1.2 (2024_01 database).

**QC thresholds:** CheckM completeness ≥ 95%, contamination ≤ 5%; N50 ≥ 20 kb; contigs ≤ 500.

**Typing methods**: MLST identified 21 sequence types (STs), including 10 novel (unknown) STs.

**Phylogenetic/cluster analysis**: Recombination‑corrected core‑genome phylogeny showed good clustering by ST, consistent with MLST assignments. ST5 and ST59 strains were predominantly MRSA. MRSA strains showed no significant correlation with department or year, presenting a sporadic distribution but often clustering together within STs, indicating close genetic relatedness within lineages. Resistance and virulence gene profiles showed genotypic stability over time, with no significant association with isolation year or clinical department.

**Visualization tools**: Chiplot (phylogenetic tree), UpSet plots, heatmaps, minimum spanning tree.

**Lineage‑resistance associations**: MRSA prevalence was 100% in both ST59 and ST22. Erythromycin/clindamycin resistance was 90.5%/85.7% in ST59 and 100%/100% in ST22. Levofloxacin resistance was higher in ST59 (33.3%) than ST22 (7.7%). ST5 clones (100% MRSA) showed lower resistance to erythromycin (37.5%), clindamycin (37.5%) and levofloxacin (0%).

**Statistical/epidemiological integration**: Temporal trend of declining total S. aureus isolates but persistently high MRSA proportion (57.14–100.00%, mean 72.92%). Departmental distribution mapping identified Nephrology as the highest‑burden ward (36.46%). Co‑occurrence analysis of top 7 ARGs.

**Data Sharing Strategy**

Raw reads: NCBI BioProject PRJNA1419524

Metadata: Supplementary Tables S1–S5 provide detailed

Code / pipelines: Tools are standard public software (FastQC, fastp, SPAdes, QUAST, CheckM, Prokka, ABRicate, mlst, Snippy, Gubbins, FastTreeMP, SCCmecFinder)

Restrictions: None - open access

**Major Findings**

This five‑year genomic surveillance study of 96 nosocomial S. aureus BSI isolates from a tertiary hospital in central China (2020–2024) found that MRSA accounted for 72.92% of all isolates, with the proportion remaining persistently high (57.14–100.00%) despite an overall declining trend in total S. aureus BSIs. The Department of Nephrology was the highest‑burden ward (36.46%), reflecting the vulnerability of hemodialysis patients with invasive vascular access.

All isolates were susceptible to linezolid and rifampicin. One vancomycin‑resistant MRSA (A12‑22) and one tigecycline‑resistant MRSA (A200‑20) were detected. One phenotypically discordant strain (oxacillin‑susceptible/cefoxitin‑positive) was confirmed as MRSA, potentially attributable to pseudo‑SCCmec carriage.

MLST identified 21 STs, with ST59 (21.88%) as the dominant CA‑MRSA clone, ST22 (13.54%) as a persistently epidemic clone (detected all five years), and ST5 (8.33%) . MRSA prevalence was 100% in both ST59 and ST22. SCCmec type IV (58.93%) was predominant, with all type IV and V strains lacking the mecI repressor. Three strains carried pseudo‑SCCmec elements. A total of 29 ARG types were detected, with frequent co‑carriage of mec and bla family genes. Strains carried an average of 74 VFs, including 45 core virulence genes; lukF‑PV was detected in 59.38% of isolates, and tsst‑1 in 11.46%.

The dominance of ST59‑MRSA‑SCCmec IV confirms that CA‑MRSA has become the core pathogenic population of nosocomial BSIs in this hospital, demonstrating "community‑hospital" cross‑border transmission with sporadic departmental distribution but strong intra‑lineage genetic clustering.

**Public Health Actions**

**Nephrology designated as key prevention and control ward**: The Department of Nephrology was prioritised for enhanced infection control measures, including intensified hemodialysis equipment disinfection, catheter care bundle reinforcement, and routine MRSA screening of dialysis patients.

**Vancomycin retained as first‑line MRSA therapy**: Given the extremely low vancomycin resistance rate, vancomycin was confirmed as the recommended empiric agent for suspected MRSA BSI. Linezolid was recommended as an alternative, particularly in Nephrology and ICU settings.

**Sentinel alert for vancomycin‑ and tigecycline‑resistant strains**: The Departments of Hepatobiliary and Pancreatic Surgery and Oncology were alerted to the detection of vancomycin‑resistant and tigecycline‑resistant MRSA, respectively, with enhanced surveillance and antimicrobial stewardship audits initiated.

**WGS‑based transmission tracing for ST59 and ST22**: Active genomic surveillance for the dominant ST59 and the persistent ST22 clones was recommended to detect potential nosocomial transmission clusters and guide targeted infection control interventions.

**Macrolide and quinolone stewardship**: The high prevalence of erythromycin/clindamycin resistance (68.75/66.67%) and emerging levofloxacin resistance (19.72%) prompted review of macrolide and fluoroquinolone prescribing practices to reduce selective pressure.

**Cefoxitin screening as primary MRSA detection method maintained**: The discordant phenotype case reinforced the hospital laboratory's policy of using cefoxitin screening as the primary MRSA detection test, with oxacillin agar screen and WGS for resolution of discordant results.

# 8.6 Enterococcus Species (Enterococcus faecium and Enterococcus faecalis)

The genus *Enterococcus* consists of the most clinically relevant species, *E. faecalis* and *E. faecium*, accounting for over 90% of clinical isolates. They are natural commensals of the human and animal gastrointestinal tracts, however they have emerged as major opportunistic pathogens in healthcare settings. On the World Health Organization (WHO) Bacterial Priority Pathogens List (BPPL) 2024, vancomycin-resistant *E. faecium* (VREfm) is classified as a High Priority pathogen. *E. faecalis* remains a frequent cause of healthcare-associated infections, but *E. faecium* represents a more severe public health challenge due to its extreme multi-drug resistance profiles and rapid hospital dissemination.

## 8.6.1 Background and Public Health Relevance

*Enterococcus faecalis* and *Enterococcus* *faecium* are major causes of hospital-acquired bacteremia and sepsis, frequently affecting immunocompromised, elderly, or surgical patients, with *E. faecium* often showing higher mortality due to increased antibiotic resistance. In patients with sepsis, *enterococcal* bacteremia carries an all-cause 30-day mortality rate between 20% and 40%. A defining characteristic of enterococcal sepsis is its frequent association with infective endocarditis, occurring in up to 15% of *E. faecalis* bacteremia cases, which requires prolonged, synergistic bactericidal therapy. The public health relevance of this enterococcus is heavily driven by the global expansion of vancomycin-resistant (VRE), which limits therapeutic options to a few last-line agents such as linezolid, daptomycin, and tigecycline. *Enterococci* possess remarkable environmental stability; they tolerate high salt concentrations, wide temperature ranges, and desiccation, allowing them to persist on hospital surfaces for months. Whole-genome sequencing (WGS) is essential in public health infrastructure to accurately differentiate between *E. faecium* and *E. faecalis,* track the horizontal transmission of plasmid-borne resistance determinants, and detect outbreaks within intensive care and oncology units.

## 8.6.2 Key Genomic Features

### 8.6.2.1 Population Structure and Major Lineages

The population structures of *E. faecium* and *E. faecalis* differ significantly, though both are shaped by distinct hospital-adapted lineages.

***Enterococcus faecium* Clade A1:** The global population of *E. faecium* is split into two major clades, with Clade A1 representing the hospital-adapted, multi-drug resistant lineage. This clade is heavily dominated by Clonal Complex 17 (CC17). Isolates within CC17 are characterized by ampicillin resistance, a high mutation rate, and the accumulation of mobile genetic elements. This lineage drives the global burden of vancomycin-resistant *E. faecium* (VREfm) sepsis. A definitive genomic marker of CC17 is IS16 which is used for differentiating highly pathogenic, hospital-associated *E. faecium* strains from commensal.

***Enterococcus faecalis* Hospital Lineages:** Unlike *E. faecium*, *E. faecalis* maintains a more stable, non-clade-separated population structure. However, healthcare-associated outbreaks and severe bacteremia cases are predominantly driven by a few highly successful lineages, most notably CC2 and CC9. These clonal complexes frequently carry large pheromone-responsive plasmids (PRPs). Pheromone-responsive plasmids are a specialized group of narrow-host-range plasmids, found primarily in *E. faecalis*, that utilize a high-efficiency conjugation system to spread rapidly between cells. They detect peptide signals ("pheromones") secreted by plasmid-free recipient cells, inducing the donor to produce aggregation substances that facilitate fast transfer.

### 8.6.2.2 MLST Schemes

Because *E. faecium* and *E. faecalis* are distinct species, bioinformatic workflows must deploy separate 7-gene MLST schemes to assign Sequence Types (STs):

- **E. faecium MLST Scheme:** Evaluates seven housekeeping genes (atpA, ddl, gdh, purK, gyd, pstS, rpoA). High-risk CC17 isolates typically cluster into founder sequence types such as ST17, ST18, ST80, and ST117.

- **E. faecalis MLST Scheme**: Evaluates seven separate housekeeping loci (gdh, gyd, pstS, gki, aroE, xpt, yqiL). Dominant healthcare-associated lineages are represented by sequence types such as ST6, ST9, and ST28

### 8.6.2.3 cgMLST and Hierarchical Clustering

To provide the high-resolution tracking necessary to differentiate true nosocomial transmission from baseline environmental contamination, core genome MLST (cgMLST) is recommended for high-resolution.

- **E. faecium cgMLST Scheme:** Standardized scheme tracks 1,423 core genes. For active outbreak definition, a threshold of ≤20 allelic differences can be used. Isolates within this threshold are considered part of an active transmission chain.

- **E. faecalis cgMLST Scheme:** Standardized schemas track approximately 1,972 core genes. Due to the lower baseline recombination rates in *E. faecalis* compared to *E. faecium*, a stricter cluster threshold of ≤5 to 7 allelic differences is typically applied to identify active hospital transmission.

- **Hierarchical Clustering (HierCC):** Utilizing hierarchical clustering levels (such as those integrated into EnteroBase) allows reference laboratories to automatically categorize enterococcal genomes into stable, predefined groups based on fixed allelic distance thresholds. This removes the need for local laboratories to generate resource-intensive de novo phylogenies during routine surveillance.

### 8.6.2.4 Mechanisms of Resistance

The enterococcal resistome combines significant intrinsic resistances with highly mobile acquired mechanisms that challenge frontline sepsis therapies.

**Vancomycin Resistance (VRE) Operons**

Glycopeptide resistance is mediated by the acquisition of **van gene** clusters, which alter the cell wall peptidoglycan target from D-Ala-D-Ala to alternative structures with a 1,000-fold lower affinity for vancomycin.

- **The vanA Operon:** Carried on highly mobile transposons like Tn1546. It mediates high-level resistance to both vancomycin and teicoplanin by remodeling the cell wall precursor to D-Ala-D-Lac. Expression is inducible via the VanS-VanR two-component regulatory system.

- **The vanB Operon:** Frequently integrated into the chromosome via large conjugative transposons. It mediates resistance to vancomycin only, while isolates remain phenotypically susceptible to teicoplanin. It also substitutes precursors with D-Ala-D-Lac, but its regulatory system is only induced by vancomycin.

- **Other van Variants:** Rare clusters like vanD, vanE, vanG, vanL, vanM, and vanN are occasionally reported. Notably, vanM has emerged as a significant threat in parts of Asia, mimicking the vanA phenotype (dual vancomycin/teicoplanin resistance) but lacking sequence homology, causing diagnostic failures in traditional PCR assays.

**Ampicillin Resistance:** Intrinsic to *E. faecium* Clade A1 (CC17), driven by point mutations and over-expression of the chromosomal ***pbp5*** gene encoding low-affinity penicillin-binding protein 5. Conversely, *E. faecalis* remains largely ampicillin-susceptible; resistance in *E. faecalis* is rare and typically mediated by plasmid-borne blaZbeta-lactamases.

**Daptomycin Non-Susceptibility:** Driven by complex, polygenic mutations in cell membrane regulatory networks. In *E. faecalis*, mutations occur primarily in the liaFSR three-component regulatory system, which alters cell membrane charge to repel daptomycin. In *E. faecium*, resistance is frequently driven by mutations in both liaFSR and the cls (cardiolipin synthase) genes.

**Linezolid Resistance:** Arises through point mutations in the Domain V region of the 23S rRNA gene (most notably the G2576T substitution, equivalent to S. aureus) or mutational alterations in ribosomal proteins uL3 (rplC) and uL4 (rplD). Horizontal transfer of plasmid-encoded ribosomal protection genes, such as the cfr methyltransferase, and optrA or poxtA ABC-F proteins, is a critical public health flag as they can drive rapid, clonal outbreaks in critical care units.

### 8.6.2.5 Virulence Factors

While enterococci possess fewer potent cytotoxins than *S. aureus*, their pathogenicity in sepsis and infective endocarditis is driven by colonization, tissue adherence, and biofilm factors:

- **Microbial Surface Components Recognizing Adhesive Matrix Molecules (MSCRAMMs):** Genes like acm (in *E. faecium*) and ace (in **E. faecalis**) encode collagen-binding proteins that mediate adherence to damaged heart valves, serving as key drivers of infective endocarditis.

- ***Enterococcal* Surface Protein (esp):** Located on a pathogenic genomic island, esp promotes robust biofilm formation on indwelling medical devices (e.g., central lines and urinary catheters), providing a continuous niche for bloodstream seedings.

- **Secreted Proteases and Hemolysins:** *E. faecalis* frequently carries the gelE gene (gelatinase) and the cyl operon (cytolysin). Cytolysin is a pore-forming toxin that lyses human erythrocytes and leukocytes, and its presence is directly correlated with increased severity and mortality in enterococcal sepsis.

## 8.6.3 Pathogen-Specific Analysis and Interpretation

For all initial sequence processing, including raw read quality control, adapter removal, contamination checks, and de novo assembly, refer to the core bioinformatics section. For the genus *Enterococcus*, precise species confirmation is mandatory to differentiate between *E. faecium* and *E. faecalis*, as they have significantly different baseline susceptibility profiles. Species confirmation must be verified using Kraken2 or FastANI (requiring ≥95 ANI to their respective reference strains: *E. faecium* Aus0004 or *E. faecalis* V583).

#### 8.6.3.1 Recommended Bioinformatics Tools for Enterococcus spp.

| **Analysis Step**                  | **Recommended Tool(s)**   | **Specific Parameters / Notes**                                                                                                                                                                                                                                                                                                             |
|------------------------------------|---------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Species Confirmation**           | Kraken2 / FastANI         | Differentiates *E. faecium* from *E. faecalis* and other species                                                                                                                                                                                                                                                                            |
| **MLST Typing**                    | mlst (Seemann)            | Automatically directs assemblies to the correct species-specific PubMLST schema (efaecium or efaecalis). Database: [<u>https://pubmlst.org/efaecium/</u>](https://pubmlst.org/efaecium/) [<u>https://pubmlst.org/efaecalis/</u>](https://pubmlst.org/efaecalis/)                                                                            |
| **cgMLST and Clustering**          | chewBBACA / EnteroBase    | Standardizes allelic profiling using the 1,423-locus core scheme (*E. faecium*) or 1,972-locus scheme (*E. faecalis*). Employs HierCC to track stable clusters.                                                                                                                                                                             |
| **AMR Detection**                  | AMRFinderPlus / ResFinder | Run with --organism Enterococcus_faecium or --organism Enterococcus_faecalis. Identifies *van* operons (*vanA/B/M*), *pbp5* ampicillin mutations, and ribosome/efflux variants.                                                                                                                                                             |
| **Linezolid resistance screening** | LRE-Finder                | Highly specialized web designed tool for enterococci. Detects 23S rRNA point mutations (G2576T or G2505A), *rplC/D* mutations, and plasmid-borne resistance genes (optrA, cfr, cfr(B), and poxtA). using using raw FastQ or fasta files [<u>https://cge.food.dtu.dk/services/LRE-finder/</u>](https://cge.food.dtu.dk/services/LRE-finder/) |
| **Virulence Profiling**            | VFDB (via ABRicate)       | Screens for enterococcal colonization and tissue injury elements, including MSCRAMMs (*acm*, *ace*), biofilm factors (*esp*), and cytolysin (*cyl* operon).                                                                                                                                                                                 |
| **Plasmid and Mobilome Analysis**  | MOB-suite                 | Identifies plasmid replicons and reconstructs plasmid structures. Essential for tracking the horizontal transfer of *vanA* or *optrA* plasmids across strains.                                                                                                                                                                              |
| **SNP Phylogeny**                  | Snippy + Gubbins          | Reference-mapped variant calling. Must utilize an isolation step with Gubbins to filter out frequent recombination events, particularly in *E. faecium*.                                                                                                                                                                                    |

#### 8.6.3.2 Integrated Analysis Pipelines for Enterococcus spp.

For high-throughput workflows and routine reference surveillance, deploying all-in-one integrated pipelines streamlines data processing by executing assembly, typing, and resistome profiling in a single command. The following validated platforms are recommended for enterococcal analysis:

**Enteroflow**: is an automated Nextflow-based bioinformatics pipeline designed for the rapid in silico characterization of *E. faecium and E. faecalis* from short-read sequencing data. It streamlines AMR surveillance and genomic analysis by integrating quality control, *de novo* assembly, and MLST assignment, surface virulence screening, and plasmid replicon typing into a single, structured clinical report ([<u>https://github.com/CRAB-IZSLT/EnteroFlow</u>](https://github.com/CRAB-IZSLT/EnteroFlow)).

**EnteroBase/Pathogenwatch:** Accessible web-based interfaces ideal for laboratories lacking local high-performance computing resources. Uploaded fasta assemblies are automatically analyzed for 7-gene MLST, cgMLST (HierCC), and surface antigen markers, generating interactive, publication-ready phylogenetic clusters.

**8.6.4 Case Study for *Enterococcus faecium and Enterococcus faecalis***

**Case Study \#1 – Whole‑Genome Sequencing Revealed Independent Emergence of Vancomycin‑Resistant Enterococcus faecium Causing Sequential Outbreaks over 3 Years in a Tertiary Care Hospital, Switzerland (2014–2017) -** [<u>https://link.springer.com/article/10.1007/s10096-019-03524-z</u>](https://link.springer.com/article/10.1007/s10096-019-03524-z)

**Aim**: To investigate the population structure and transmission dynamics of vancomycin‑resistant *Enterococcus faecium* (VREfm) causing sequential outbreaks over three years at a large Swiss tertiary care hospital, using whole‑genome sequencing to assess genetic relatedness among all collected isolates, reconcile epidemiological outbreak definitions with genomic data, and explore within‑host evolution in long‑term carriers.

**Surveillance Strategy/System Design**

**Setting:** University Hospital of Lausanne (Centre Hospitalier Universitaire Vaudois, CHUV), Lausanne, Switzerland – a 1,100‑bed tertiary care hospital with a mix of one‑ to five‑bed rooms and open units. The hospital had experienced several VRE outbreaks in 2011, 2015 and 2016.

**Sampling strategy:**

- **Clinical and screening isolates**: All VREfm isolates detected from clinical specimens (The sample was not indicated as Blood) or rectal/stool screening samples between January 2014 and May 2017 were prospectively collected. At least one isolate per patient was stored at −80 °C.

- **Screening protocol:** Patients were screened on admission if transferred from a foreign hospital. Contact patients (those sharing a room or open unit with a VRE‑positive case for ≥ 24 h in the preceding month) were screened and placed on contact isolation until three rectal samples taken one week apart were VRE‑negative. When contact screening identified new positives, all patients in the affected unit were screened weekly and at discharge.

- **Outbreak definition (epidemiological):** An outbreak was defined as ≥ 2 cases with epidemiological links; single cases had no identified epidemiological connections. Links were established through: (i) contact tracing, (ii) detection of new cases in the same unit during weekly screening, and (iii) retrospective review of hospitalization charts for links to previously identified cases.

**Isolate types and sample size:**

- 183 VREfm isolates from 156 patients were sequenced. Only 10 isolates were from clinical samples; the remaining 146 were from screening (rectal swabs or stool).

- For 146 patients, one isolate was sequenced; for 10 patients, between 2 and 17 serial isolates were analyzed to study within‑host evolution.

- Isolates were collected from visceral surgery (n = 76), medical wards (n = 33), septic surgery (n = 25), intensive care units (n = 10) and other wards.

**Reason for sampling:** To distinguish between ongoing monoclonal transmission and independent introductions of VREfm into the hospitalized population, to reconcile epidemiological outbreak designations with genomic clustering, and to understand the relative contribution of cross‑transmission versus de novo emergence of vancomycin resistance in driving the hospital VRE burden.

**Laboratory methods:** VRE screening by enrichment culture in brain–heart infusion with 3.3 mg/L vancomycin followed by plating on chromogenic selective agar. Species confirmed by MALDI‑TOF MS. vanA/vanB detection by Xpert vanA/vanB rapid test.

**Sequencing approach:** Illumina MiSeq (2 × 150 bp paired‑end). DNA extraction with Wizard Genomic DNA Purification Kit; library preparation with Nextera XT.

**Use cases:** Outbreak investigation, routine genomic surveillance, AMR mechanism detection, detection of high‑risk clones, population structure analysis, within‑host evolution, transmission chain reconstruction.

**Ethical / Legal Considerations and Approvals**

**Beneficence and non‑maleficence:** The study used bacterial isolates collected during routine clinical care and infection control screening. WGS results directly improved the precision of outbreak detection: 16% of cases initially classified as outbreak‑associated were excluded by genomic evidence, preventing unnecessary contact tracing and ward closures.

**Distributive justice:** The investigation included all VREfm‑positive patients detected through universal screening in affected units, regardless of clinical presentation, ensuring that asymptomatic carriers were included in transmission analyses.

**Privacy and autonomy:** The study was conducted in accordance with the 1964 Helsinki declaration and approved by the regional and national research committee. Informed consent was not required for this type of epidemiological surveillance study using anonymised bacterial isolates. No patient identifiers were included in genomic outputs.

**Data custodianship:** Sequence data and detailed metadata tables (patient epidemiological data, resistance and virulence factors) are provided as electronic supplementary material with the publication.

**Transparency and accountability:** Published open access (Springer). The analytical pipeline is fully described, and all tools are referenced. A public BioProject accession is **not explicitly stated in the publication**; isolate data are accessible through the supplementary files and from the corresponding author.

**Data protection:** Isolates are referenced by coded study identifiers; no directly identifiable patient information is present in public data.

**Public health integration:** Results directly informed infection control policy, including transformation of five‑bed rooms into two‑bed rooms, staffing reinforcement for environmental disinfection, and implementation of prolonged weekly screening in units with recurrent VRE outbreaks. The study also contributed evidence for antimicrobial stewardship as a VRE emergence prevention strategy.

**Data Analysis**

- **Bioinformatics pipeline(s):**

  - **MLST**: SRST2 pipeline for in silico 7‑locus MLST assignment.

  - **Read mapping and SNP calling**: Snippy v3.1, using VREfm reference genome Aus0004 (GenBank NC‑017022). BWA‑MEM for alignment; Freebayes v1.0.2 for variant calling. SNP filtering parameters: minimum read coverage 10 ×, minimum base quality 30, and a minimum proportion for variant evidence of 0.9.

  - **Core‑genome definition:** SNPs within the 1,755,155 bp core genome were retained; SNPs in mobile genetic elements (insertion sequences, transposons, conjugative plasmids), repetitive regions, and putative prophages (identified via PHAST) were excluded.

  - **Recombination filtering:** Gubbins v2.2.2 with default settings; high‑SNP‑density regions and recombinant segments were removed. Substantial recombination was observed: 216 events in ST80, 95 events in ST117.

  - **Phylogenetic reconstruction:** Maximum‑likelihood tree from non‑recombinant core‑genome SNPs using PhyML; visualised with Seaview v4.6.

  - **Antimicrobial resistance and virulence gene detection:** SRST2 and ARIBA, using ARG‑ANNOT, CARD and VFDB databases.

  - **Van transposon analysis**: To study the genetic variation within vanA and vanB transposons, sequence reads were mapped against Tn1549 (M97297) and Aus0004 (2,835,430–2,869,240 bp) reference genomes, respectively, using the Snippy pipeline version 3.1

- **QC thresholds:** SNP calling required coverage ≥ 10 × and base quality ≥ 30; recombinant and MGE‑associated regions excluded. Outgroup isolate H32990 (ST82) was used to root the tree; it was distantly related to the remaining 182 isolates.

- **Typing methods:** MLST (SRST2). The 156 patients harboured 11 STs, dominated by ST80 (n = 77), ST117 (n = 36) and ST17 (n = 30). Additional STs: ST203 (3), ST18 (3), ST192 (2), and one each of ST82, ST182, ST412, ST721 and a novel ST.

- **AMR detection:** vanA was present in 91.3% of isolates; vanB in 8.7%. Aminoglycoside resistance genes (aac(6′)-aph(2″), sat4, aph(3′)-IIIa, ant(6′)-Ia) were lineage‑specific. Macrolide resistance genes (msrC universal, ermB 98%). Daptomycin resistance‑associated liaS/liaR mutations were detected in 20% of isolates, predominantly ST80. The vanA transposon showed limited diversification (0-5 SNPs) and no correlation with phylogenetic clusters, consistent with recent acquisition from a common plasmid pool. The vanB transposon clustered into three distinct groups with 8-11 SNP differences, congruent with the core‑genome phylogeny.

- **Virulence detection:** All but two isolates carried acm (collagen adhesin). Pilin gene cluster absent from clusters ST80‑B and ST80‑D. ecbA (endocarditis‑associated antigen) present in \> 50% but absent from all ST17 isolates.

- **Phylogenetic/cluster analysis:** Three major clades were resolved: clade ST17, clade ST117 and clade ST80‑ST18. Clade ST17 was monophyletic (51 isolates, median 0 SNPs, range 0–2 SNPs), consistent with direct person‑to‑person transmission in outbreaks 1 and 2. Clade ST80‑ST18 subdivided into six distinct clusters (ST80‑A through ST80‑E, and ST18), each representing independent introductions. Clade ST117 subdivided into four clusters (ST117‑A through ST117‑D). Within‑cluster SNP distances were 0-5 SNPs; inter‑cluster distances were up to 82 SNPs.

- **Transmission network reconstruction:** Among 129 cases classified as outbreak‑associated by epidemiology, 109 (91%) were confirmed by genomics (≤ 3 SNPs); 20 cases (16%) were excluded as genetically distinct. Among 27 epidemiologically defined single cases, 12 carried unique genotypes, but 15 were genomically linked to outbreak clusters, identifying unsuspected transmission events. Four of ten outbreaks involved more than one genotype. A striking example was cluster ST117‑D: a single case in March 2016 was followed by five further cases between October 2016 and January 2017 and a final case in May 2017, with no epidemiological links identified, strongly suggesting a chain of undetected carriers.

- **Within‑host evolution:** Serial isolates from six patients sampled up to 391 days apart differed by 0-3 SNPs, demonstrating limited intra‑host diversification. Two patients showed evidence of colonization by multiple distinct genotypes: patient P033 simultaneously carried ST80‑A and ST80‑B (mean 20 SNPs apart) over 370 days; patient P089 carried two genotypes 42 SNPs apart on different occasions. Evidence of intra‑host recombination was observed in patients P037 and P089, emphasising the necessity of accounting for recombination when interpreting SNP distances.

- **Statistical/epidemiological integration:** Temporal mapping of outbreaks and clusters; comparison of epidemiological and genomic outbreak classifications; analysis of time from admission to first VRE detection (median 25 days, range 0–280 days); admission screening results (1/187 positive during a 6‑week universal screening period in the surgical unit).

- **Visualisation tools:** Seaview for phylogenetic tree visualisation; epidemiological distribution maps.

**Data Sharing Strategy**

- **Raw reads:** Not deposited in a public database at the time of publication (2019). This represents a limitation for independent re‑analysis.

- **Supplementary data:** Detailed per‑patient epidemiological data (Table S1) and comprehensive resistance/virulence gene profiles (Table S2) are available as electronic supplementary material with the publication.

- **Phylogenetic data**: Core‑genome SNP alignment used to construct the ML tree is described but not directly linked; tree figures are provided in the publication.

- **Code/pipelines**: All tools used are publicly available and referenced; specific parameters are detailed in the Methods.

- **Restrictions:** Open‑access publication; supplementary data freely available.

**Limitations:**

- No raw read deposition: Sequence data were not submitted to a public repository (ENA/SRA/NCBI), preventing independent re‑analysis and limiting the value of these genomes for global VREfm surveillance.

- Vancomycin‑susceptible isolates not sequenced: The study could not definitively prove de novo emergence, because susceptible E. faecium from the same patients or wards were not included to demonstrate the parent strain from which vancomycin resistance emerged.

- Environmental sampling not performed: The hypothesis of persistent environmental contamination as a reservoir was suggested by the data but could not be tested directly; no environmental cultures were collected during the study.

- Single‑center setting: Findings reflect a well‑resourced tertiary hospital in a high‑income country; the relative contribution of importation vs. de novo emergence may differ in settings with higher community VRE prevalence.

- Short‑read sequencing only: Complete vanA/vanB transposon structures and plasmid backbones were not fully resolved.

**Major Findings:**

WGS of 183 VREfm isolates from 156 patients over three years resolved 13 distinct genomic clusters within three dominant sequence types (ST80, ST117, ST17), demonstrating that sequential outbreaks were driven by multiple independent introductions and de novo emergence rather than a single sustained outbreak. Within clusters, core‑genome SNP distances of 0–3 SNPs confirmed direct patient‑to‑patient transmission. Genomics corrected epidemiological misclassifications by excluding 16% of presumed outbreak cases and identifying unsuspected transmission among 15 of 27 epidemiologically sporadic cases. The median 25‑day interval from admission to first VRE detection and a very low admission prevalence (1/187) indicated that vancomycin resistance frequently emerged within the hospitalised population under antibiotic pressure, shifting the strategic focus toward antimicrobial stewardship alongside intensified infection control.

**Public Health Actions and interventions**

**Infection control intensification:** Following the outbreaks, the hospital reinforced staff training, hand hygiene observation, environmental disinfection protocols, and dedicated additional personnel to environmental cleaning.

**Infrastructure modification:** Five‑bed rooms were converted to two‑bed rooms with improved sanitation and individual toilet facilities to reduce transmission risk in shared spaces.

**Extended screening:** Weekly screening of all patients in units with recurrent VRE outbreaks was continued for several months after the last case was detected. Universal temporary admission screening was implemented in the surgical unit during peak outbreak periods.

**Antimicrobial stewardship prioritization:** Recognition of the de novo emergence pattern shifted strategic emphasis toward antimicrobial stewardship, particularly restriction of cephalosporin and glycopeptide use as a primary VRE prevention measure.

**Exclusion of non‑outbreak cases from contact tracing:** Genomic exclusion of 16% of epidemiologically suspected cases allowed the IPC team to focus resources on confirmed transmission chains.

**Active surveillance for undetected carriers:** The finding that genomically linked cases appeared months apart prompted implementation of systematic screening in wards where VRE cases had previously been identified.

**Post‑study impact:** In the year following the study, with sustained interventions, only 16 new cases were detected, including only three small outbreaks (2, 2 and 3 cases each), a marked decrease from the study period.

**Case Study \#2 – Genomic Insights into a Hospital‑Acquired High‑Risk Vancomycin‑Resistant Enterococcus faecium Outbreak in Guangdong, China (2021–2023) -** [<u>https://pmc.ncbi.nlm.nih.gov/articles/PMC13076189/</u>](https://pmc.ncbi.nlm.nih.gov/articles/PMC13076189/)

**Aim**: To conduct a comprehensive molecular epidemiological investigation of a vancomycin‑resistant *Enterococcus faecium* (VR‑Efm) outbreak across multiple hospitals in Guangdong, China, using whole‑genome sequencing to characterize transmission dynamics, antimicrobial resistance patterns, and genetic relationships with previously reported global strains and to develop a specific PCR‑based diagnostic tool for early detection of the outbreak clone.

**Surveillance Strategy/System Design**

**Setting**: Two hospitals in Guangdong Province, China – the First Affiliated Hospital of Guangzhou Medical University and The First People's Hospital of Foshan. These hospitals serve a large, densely populated region in southern China. The investigation was prompted by a concerning rise in VR‑Efm prevalence: according to the China Antimicrobial Resistance Surveillance System, the Guangdong Province VR‑Efm rate increased from 1.5% in 2021 to 8.0% in 2022, substantially exceeding the national rates (1.2% to 1.7% over the same period).

**Sampling strategy:** All VR‑Efm isolates from clinical or screening samples obtained from inpatients with a hospital stay exceeding 24 hours were collected between March 2021 and November 2023. Isolates originated from 40 distinct departments across the two hospitals, capturing a wide cross‑section of the affected inpatient population.

**Isolate types and sample size**: 101 VR‑Efm isolates were collected from 101 patients. Specimen sources were predominantly urine (66/101, 65.3%) and sputum (11/101, 10.9%), with the remainder from ascitic fluid, wound swabs, blood, bile, cerebrospinal fluid, catheter sites, pleural fluid, stool, and other body fluids. Geographically, 38 isolates (37.6%) originated from 12 departments at Guangzhou Hospital, and 63 isolates (62.4%) from 28 departments at Foshan Hospital.

**Reason for sampling:** An integrated hospital network investigation was launched in response to the rapid escalation of VR‑Efm isolation rates and evidence of inter‑facility transmission suggested by laboratory data. WGS was employed to determine whether the outbreak was driven by clonal expansion, to assess its genetic proximity to international strains, and to identify genomic markers for the development of rapid diagnostics.

**Laboratory methods:** Species identification by MALDI‑TOF mass spectrometry (Bruker Microflex LT). Antimicrobial susceptibility testing by agar dilution or broth microdilution with cation‑adjusted Mueller–Hinton broth, interpreted according to CLSI and EUCAST breakpoints. Nine antimicrobials were tested: vancomycin, ampicillin, gentamicin, streptomycin, linezolid, teicoplanin, rifampin, doxycycline, and daptomycin. DNA for WGS was extracted using the E.Z.N.A. Stool DNA Kit.

**Sequencing approach:** Illumina NovaSeq 6000 (2 × 150 bp paired‑end), with \>100‑fold coverage. Library preparation used the TruSeq Nano DNA LT Library Preparation Kit.

**Use cases:** Outbreak investigation, AMR mechanism detection and monitoring, detection of high‑risk clones, population structure analysis, diagnostic biomarker development, global phylogenetic contextualisation.

**Ethical / Legal Considerations and Approvals**

**Beneficence and non‑maleficence**: The study used bacterial isolates collected during routine clinical care and infection control surveillance. WGS results provided immediate, actionable evidence for understanding transmission and developing a rapid diagnostic assay for the outbreak clone.

**Distributive justice:** The investigation systematically covered 40 departments across two large public hospitals, ensuring broad representation of the affected inpatient population rather than focusing selectively on high‑acuity units or critical care units.

**Privacy and autonomy**: The study was approved by the Research Project Review Ethics Committee of the First Affiliated Hospital of Guangzhou Medical University (Approval No: ES‑2023‑057‑01). Written informed consent was obtained from all participants or their legal guardians prior to sample collection.

**Data custodianship**: All sequencing data have been deposited in NCBI under BioProject Accession PRJNA1152711. Detailed supplementary tables with isolate metadata, sequence types, and resistance profiles accompany the publication.

**Transparency and accountability:** Published open access. The analytical pipeline, including MLST, kSNP4, ChewBBACA, BactDating, and TransPhylo, is fully described, enabling replication. The PCR primer sequences for the outbreak clone are publicly provided.

**Data protection:** Patient‑level data were de‑identified; published data tables use coded sample identifiers.

**Public health integration:** The development of a clone‑specific PCR assay was directly informed by genomic findings and is intended for integration into hospital screening protocols to enable rapid, low‑cost identification of the outbreak strain.

**Data Analysis**

**Bioinformatics pipeline(s):**

- **Quality control, assembly and variant calling**: fastp v0.23.4 (adapter removal, quality trimming); human read removal using BWA v0.7.17 and SAMtools v1.17 alignment to GRCh38; de novo assembly with SPAdes v3.15.5; SNP and indel calling with Snippy v4.6.0.

> The use of Snippy for calling SNPs against the A10290 reference is standard and reliable for short-read data. However, the authors correctly identify that without long-read data for the specific 101 isolates, they cannot fully resolve the plasmid structures or large structural variations in this particular outbreak.

- **MLST and cgMLST**: mlst v2.23.0 (PubMLST *E. faecium* scheme). cgMLST performed with ChewBBACA v3.3.3: schema creation, allele calling (BLAST score ratio 0.6), schema evaluation, and core‑genome matrix extraction (loci present in ≥ 99% of isolates).

- **Phylogenetic analysis:** kSNP4 for core‑SNP identification and maximum‑parsimony tree construction across 577 genomes (101 outbreak + 476 NCBI: 52 China, 24 Japan, 21 India, 16 Australia, 464 other countries). IQ‑TREE v2.2.6 (‑m MFP) used for maximum‑likelihood confirmation. Tree visualization with ggtree v3.6.2. Recombination filtering was not applied; the authors note this is acceptable for short‑term clonal outbreaks. A notable limitation was the explicit decision not to filter for recombination prior to phylogenetic inference. E. faecium is characterized by high rates of homologous recombination, which can distort phylogenetic topology and branch lengths. Hence, for a more accurate phylogeny, the authors should have implemented a recombination-filtering step using tools like Gubbins or ClonalFrameML. Without this, the calculated genetic distance between the China and Japan/India strains may be influenced by shared recombinant blocks rather than vertical descent

- **Dimensionality reduction and clustering:** UMAP (uwot package, R) for cgMLST profile visualisation; PCA (VCF2PCACluster v1.40) on all ST80‑type genomes.

- **MST and transmission analysis:** GraphSNP v1.0 for minimum spanning tree construction from core SNPs.

- **Time‑calibrated phylogeny:** 31 isolates selected after clonal redundancy reduction (≤ 10 SNP clustering) and temporal signal assessment (R² = 0.83, p \< 0.0001). BactDating v1.1.2 (mixedcarc model, 10⁶ MCMC iterations); ESS for substitution rate μ = 801. TransPhylo v1.3.2 for transmission tree reconstruction.

- **Comparative genomics:** Mauve v2.3.1 (whole‑genome alignment of outbreak and reference strains); synteny analysis with Tbtools (MCScanX).

- **Functional annotation:** Prokka v1.14.5; Kofamscan for KEGG pathway assignment; clusterProfiler for enrichment analysis.

- **Pan‑genome analysis:** OrthoFinder v2.5.5; pan‑genome curve fitting with minpack.lm.

- **Resistance and virulence gene detection:** ABRicate v1.0.1 against VFDB and CARD databases.

**QC thresholds:** \>100‑fold coverage; assemblies of 2.79–3.13 Mb; GC content 37.3–37.8%; N50 31,195–40,661 bp; 2,717–3,017 protein‑coding sequences annotated per genome.

**Data Sharing Strategy**

- **Raw reads**: NCBI BioProject PRJNA1152711.

- **Metadata:** Detailed supplementary files with isolate information, ST assignments, resistance gene profiles and assembly QC are available with the publication.

- **PCR primer sequences:** Forward: 5′‑AATCAGACGATCAAGATTGGAACAAC‑3′; Reverse: 5′‑AAGGATTCATCTCATCCGTTGCG‑3′. Publicly available in the publication for adoption by other laboratories.

- **Code/pipelines**: All tools are publicly available; specific parameters and versions are detailed in the Methods.

- **Restrictions:** None – open access.

**MajorFindings:**

A multicenter genomic investigation of 101 vancomycin-resistant Enterococcus faecium (VR-Efm) isolates from 40 hospital departments in Guangzhou and Foshan, Guangdong Province, revealed that 96.0% belonged to a single ST80 (CC17) clone harboring a vanA-mediated multidrug-resistance phenotype: universal resistance to vancomycin, ampicillin, and teicoplanin, high-level resistance to rifampin (99.0%) and gentamicin (93.1%), emerging daptomycin resistance (43.6%), and preserved susceptibility to streptomycin and linezolid (96.0%). Global phylogenetic contextualization against 476 publicly available E. faecium genomes demonstrated that the outbreak clone was most closely related to ST80 VR-Efm from India and Japan, with cgMLST UMAP, PCA, and MST analyses confirming a tight genetic cluster (Group 1) sharing a recent common ancestor whose time-calibrated phylogeny placed the most recent common ancestor between 2018 and 2022, contemporaneous with the detection of related ST80 strains in India. Structural variation analysis identified a lineage-specific divergence near the 2.1 Mb locus in the Indian reference strain A10290 that was absent from the Chinese outbreak strains, indicating that A10290 is not the direct progenitor; instead, the outbreak strains showed evidence of recombination within the Chinese VR-Efm population, suggesting local evolution following introduction, and annual SNP accumulation with functional enrichment in genes linked to beta-lactam resistance and quorum sensing further supported progressive divergence. Critically, the unique ~2.1 Mb genomic architecture enabled the design and validation of a clone-specific PCR assay that reliably distinguished ST80 outbreak strains from non-ST80 VREfm and unrelated clinical enterococci, providing a practical, low-cost molecular screening tool for outbreak containment.

**Public Health Actions**

- **Multi‑centre surveillance alert:** Notified authorities of ST80 VREfm dissemination across the Guangzhou–Foshan network, mandating enhanced screening and reporting across all Guangdong provincial hospitals.

- **Enhanced Infection Control**: Intensified contact precautions, patient isolation, and rigorous environmental cleaning in high-detection departments.

- **Antimicrobial Stewardship**: Updated treatment guidelines to leverage preserved susceptibility to linezolid and streptomycin, reserving daptomycin strictly for confirmed-susceptible cases.

- **Clone-Specific PCR Screening**: Developed and validated a PCR assay targeting a unique 2.1 Mb region to rapidly distinguish the outbreak clone from sporadic strains.

- **Long-Read Sequencing Investment:** Advocated for ONT or PacBio platforms at the provincial reference lab to resolve complex structural variations missed by short-read sequencing.

- **Global Data Sharing**: Deposited outbreak genomes into NCBI (PRJNA1152711) to expand public datasets and enable international comparative analysis.

# 9. Reporting, Interpretation, and Public Health Action

Genomic epidemiology reports should be tailored for decision-making rather than just technical archiving. They must present findings in a clear, traceable, and actionable way suitable for the target audience. Different groups need varying levels of detail. For example, infection prevention and control (IPC) teams may require quick interpretations of clusters and control advice; microbiology and antimicrobial stewardship teams (AMS) might need genotype–phenotype summaries; national authorities could focus on surveillance trends and alert levels; policymakers need brief reports highlighting strategic importance. This aligns with WHO's guidance that genomic surveillance should enable timely public health responses as part of larger surveillance and laboratory systems (WHO, 2022a).

## 9.1 Purpose and Guiding Principles

Genomics data for sepsis bacterial pathogens acquire public health value only when interpreted (within epidemiological and metadata information), communicated, and linked to action. As WHO emphasizes timeliness and actionable reporting, this guidance stresses adaptation to country needs (the guidance is intended for settings with widely varying infrastructure and turnaround capability). Reporting pathways must be fast enough to support timely infection prevention and control (IPC) and public health decisions while still feeding the slower national and international surveillance cycles that track the antimicrobial resistance (AMR) burden driving sepsis mortality worldwide (Murray et al., 2022; Rudd et al., 2020).

Reporting frameworks should support both immediate public health response and long-term surveillance objectives. Reports may inform infection prevention and control (IPC) investigations, AMR surveillance, outbreak detection, transmission analysis, and policy development. Reporting elements should facilitate the translation of whole-genome sequencing (WGS) findings into public health action, in line with the recommended triangulation of genomic, clinical, and epidemiological evidence in genomic epidemiology (Gardy & Loman, 2018; Struelens & Brisse, 2013).

This guidance emphasizes essential principles for reporting and interpretation; ensuring reports are fit for purpose, timely, incorporating contextual data, transparent about methods and limitations, and actionable. Reports should be customized to the specific use case and audience while maintaining a consistent analytical approach across all products. The urgency of reporting should align with the use case: urgent alerts for infection prevention and control (IPC), outbreak management, or emerging resistance should be prioritized and dispatched quickly, whereas routine surveillance findings can be shared periodically and summarized (ECDC, 2019; 2022; WHO, 2022a).

Note: Reporting structures should support reproducibility, interoperability, and responsible data sharing in line with open standards and collaborative public health genomics practice.

## 9.2 Audience-Tailored Reporting

A single report usually doesn't meet the needs of all readers. Reports should be tailored to each audience while maintaining scientific consistency, using the framework outlined in Table 9.1.

Table 9.1. Audience-specific reporting requirements

| **Audience**                                                                                | **Core Need**                                                                 | **Reporting Approach**                                                                                                                                                                                                                                                                                                                                   |
|---------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **IPC teams**                                                                               | Patient-level findings with spatial and temporal context                      | Lead with recommended IPC actions; plain-language risk statement; include locally approved case or sample identifiers needed for operational follow-up, consistent with institutional privacy, governance, and legal requirements; avoid genomic jargon                                                                                                  |
| **Clinical microbiology and treating teams receiving laboratory/public health information** | Organism identity, resistance profile, and clonal relationship to other cases | State organism, genomic resistance findings reported alongside available phenotypic AST results, with concordance or discordance noted where relevant, clonal-relatedness, and implications for infection prevention, microbiology interpretation, and communication to clinical teams in accordance with local clinical governance; omit methods detail |
| **National AMR / GLASS focal points**                                                       | Standardized, denominator-based trend data                                    | GLASS-compatible structured format; explicit flagging of new high-risk clones or resistance mechanisms                                                                                                                                                                                                                                                   |
| **Policymakers and institutional leadership**                                               | Burden, required action, resource needs                                       | Visual summaries (trend graphs, resistance heat-maps); short “what this means” statement; no methods section                                                                                                                                                                                                                                             |
| **International repositories and networks**                                                 | Full reproducibility for submission/publication                               | Complete methods, tool/database versions, accession numbers, community metadata standards                                                                                                                                                                                                                                                                |

## 9.3 Minimum Content and Structure of Public Health Genomic Reports

To ensure consistency, reproducibility, and public health utility, all public health genomic reports should follow a consistent structure appropriate to the genomic surveillance use cases and include the minimum information necessary to support interpretation and decision-making. For example, outbreak investigation reports are event-driven and operational, whereas routine surveillance reports are periodic, aggregated, and trend-focused.

**Public health question and reporting context:** Public health reports should begin by clearly stating the purpose of the analysis and its context. This includes specifying the surveillance use case, such as outbreak investigation, routine monitoring, tracking antimicrobial resistance (AMR) mechanisms, or identifying a high-risk lineage or clone. The report must also specify the pathogen, specimen type, time frame, setting, and target audience. This information is crucial because the surveillance goal shapes how the results are interpreted and which actions are appropriate (ECDC, 2019; WHO, 2020, 2022).

**Core data elements for reporting:** Identifiers and metadata included in reports should be limited to those approved for the intended operational purpose and handled in accordance with applicable confidentiality, governance, and legal requirements. The report should include the essential data elements needed to support interpretation, reproducibility, and public health use. International and regional guidance consistently recommends reporting that links genomic results to case details, isolates, and epidemiological information. When available and appropriate, this includes local case or sample identifiers, demographic variables, healthcare facility and ward, specimen type, specimen collection date, isolate source, and relevant epidemiological context. Additionally, reports should also include phenotypic AST results when available, as genomic AMR findings are most useful when interpreted alongside phenotypic susceptibility data (PAHO, 2022; WHO, 2020).

**Genomic and analytical outputs:** The report should clearly summarize the genomic findings relevant to the defined use case. It should focus on the public health implications of the results rather than simply listing bioinformatic outputs. Depending on the analysis performed, this may include species confirmation, sequence type, AMR determinants, virulence-associated markers where relevant, cluster designation, and measures of genomic relatedness. Where applicable, the report should also document the analytical approach used to generate the reported result including the sequencing method, key quality indicators, and the bioinformatics workflow or typing or clustering approach. The level of detail should be sufficient to support transparency and reproducibility and appropriate for the targeted audience (ECDC, 2019; WHO, 2020).

**Interpretation:** Reports should not consist solely of bioinformatic outputs. A concise interpretation should explain what the findings mean for the specific public health question. Genomic reporting complements rather than replaces epidemiological investigation, clinical microbiology, or phenotypic AST. For outbreak investigations, this should state whether the isolates are genetically consistent with a common cluster, given the limitations of the methods used and whether the combined genomic and epidemiological evidence supports a plausible transmission hypothesis. For AMR surveillance, the interpretation should indicate whether the findings are more consistent with clonal spread, dissemination of specific resistance determinants, or both. For routine surveillance, the report should describe the significance of observed sequence type or resistance trends over time. When monitoring sequence type and resistance trends, interpret the results considering the sampling strategy (such as universal testing, sentinel sites, periodic surveys, or outbreak investigations), available denominator data, case definitions, and any shifts in laboratory or analytical methods over time (ECDC, 2019; WHO, 2020).

Interpretation should address five questions:

1.  Has the organism and relevant sequence type or clone been identified with sufficient quality and analytical confidence for the intended use?

2.  Are key AMR determinants or other relevant markers present, and do these findings align with available phenotypic AST results?

3.  Are the isolates genetically similar in a way consistent with recent spread or a common source, given the organism, setting, and metadata?

4.  Do the genomic findings change the risk assessment, for example, by identifying a high-risk clone, a priority resistance mechanism, or spread across wards or facilities?

5.  What is the most likely public health implication given the combined evidence? (ECDC, 2019; WHO, 2020).

Genomic relatedness alone does not prove direct transmission, and detection of a resistance gene alone does not replace phenotypic susceptibility testing or clinical assessment. When findings are preliminary, discordant, or limited by incomplete metadata, the report should state this clearly and recommend confirmatory epidemiological, laboratory, or IPC review rather than presenting a definitive conclusion (WHO, 2020).

**Limitations and uncertainty:** Each report must clearly identify the main limitations and uncertainties affecting the findings. It is important to underscore that genomic data should not be viewed in isolation, and WGS does not typically replace phenotypic AST for most bacterial pathogens. Therefore, reports should highlight key constraints such as incomplete sampling, missing or limited metadata, uncertainties in genotype–phenotype correlations, and the limitations of inferring transmission solely based on genomic relatedness. Effectively communicating this uncertainty is crucial to ensure that conclusions are appropriately weighted by the available evidence (WHO, 2020).

**Public health implication and recommended next step:** Every report should conclude with a brief statement of the public health implication and the next recommended step. The recommendation should be proportionate to the strength of the evidence and framed for the intended audience. For IPC teams, this may include immediate case review, enhanced investigation, or targeted follow-up actions in accordance with local protocols. For surveillance summaries, it may include highlighting signals or trends requiring review. For national surveillance systems, reporting should use standardized variables and formats compatible with national surveillance structures and, where applicable, GLASS reporting requirements (WHO, 2020)

For public health implications, reports should include clear next-step recommendations that are proportionate to the evidence and tailored to the responsible operational level. When recommending follow-up monitoring, avoid vague language and clearly define the purpose, scope, and specific escalation criteria, such as quantitative thresholds, markers, or data triggers that would require a more intensive public health response. Avoid vague suggestions like "continue to monitor." If monitoring is necessary, specify what will be monitored, the frequency, and the criteria for escalation. Public health action following genomic analysis should therefore be linked to the surveillance objective and to the level at which action is required: facility, subnational, national, regional, or international.

## 9.4 Reporting Timelines

Reporting timelines should align with the surveillance objective, urgency, and required action level. International guidance emphasizes timely genomic reporting to support IPC, outbreak investigation, risk assessment, and routine surveillance, though no universal turnaround time applies across pathogens, settings, and capacities. Programs should set locally appropriate targets within protocols, distinguishing urgent communications requiring immediate escalation from routine outputs that follow reporting cycles. As shown in Table 9.4, suspected healthcare-associated clusters require rapid reporting for IPC; alert signals, such as resistance mechanisms or high-risk clones, should be promptly escalated through national pathways; routine findings should be communicated regularly based on program objectives and capacity; and sequence data submission should adhere to predefined procedures for timely sharing, metadata linkage, and governance. Reporting workflows and turnaround targets should be adapted to local capacity, governance requirements, and surveillance priorities, while preserving timeliness for urgent public health action.

Note: As endemicity, virulence, and antimicrobial resistance profiles differ significantly across regions, definitions and alert thresholds for high-risk lineages or clones should be informed by local and regional epidemiology and may change over time.

Table 9.4. Suggested Reporting Timeline Framework

| **Scenario**                                                                                    | **Recommended timing approach**                                                                                                    |
|-------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
| Suspected nosocomial bloodstream-infection cluster                                              | Report as rapidly as needed to support IPC action; preliminary communication may precede the final written report                  |
| Alert-level signal, such as a priority resistance mechanism or high-risk clone in a new setting | Report promptly through established national pathways, without waiting for the next routine reporting cycle                        |
| Routine surveillance reporting                                                                  | Report on a predefined schedule, such as monthly, quarterly, or another interval aligned with surveillance objectives and capacity |
| Submission to repositories or external data-sharing platforms                                   | Follow established national or program procedures for timely submission, metadata linkage, and governance compliance               |

**9.5 Recommended reporting templates**

**Routine genomic surveillance report:**

- Organism and sampling context

- Analytical method

- Key genomic findings

- AMR-associated determinants and available AST correlation

- Trend or surveillance interpretation

- Limitations and uncertainty

**Outbreak investigation report:**

- Investigation question

- Included isolates and sampling framework

- Genomic analysis method

- Relatedness findings

- Epidemiological integration

- Conclusion and uncertainty statement

# 10. Future Directions

This first version of the PHA4GE Sepsis Pathogen Bioinformatics Guidance document has focused on the prioritization of the WHO bacterial priority bacterial pathogens list isolated from culture and the practical needs of public health laboratories. Future versions of this guidance will incorporate culture-independent metagenomic next-generation sequencing (mNGS)-specific bioinformatics recommendations alongside the culture-based workflows described here. Moreover, a dedicated fungal and viral sepsis section will be added in the future versions of the guidance document.

# 

# 

# 

# 

# 

# 

# 

# 

# References

Aanensen, D. M., Feil, E. J., Holden, M. T., Dordel, J., Yeats, C. A., Fedosejev, A., ... & European SRL Working Group. (2016). Whole-genome sequencing for routine pathogen surveillance in public health: a population snapshot of invasive Staphylococcus aureus in Europe. MBio, 7(3), 10-1128. https://journals.asm.org/doi/full/10.1128/mbio.00444-16

Abdelbary, M. H., Senn, L., Greub, G., Chaillou, G., Moulin, E., & Blanc, D. S. (2019). Whole-genome sequencing revealed independent emergence of vancomycin-resistant *Enterococcus faecium* causing sequential outbreaks over 3 years in a tertiary care hospital. *European Journal of Clinical Microbiology & Infectious Diseases, 38*(6), 1163–1170.

Alcock, B. P., Raphenya, A. R., Lau, T. T. Y., Tsang, K. K., Bouchard, M., Edalatmand, A., Huynh, W., Nguyen, A.-L. V., Cheng, A. A., Liu, S., Min, S. Y., Miroshnichenko, A., Tran, H.-K., Werfalli, R. E., Nasir, J. A., Oloni, M., Speicher, D. J., Florescu, A., Singh, B., … McArthur, A. G. (2020). CARD 2020: Antibiotic resistome surveillance with the Comprehensive Antibiotic Resistance Database. *Nucleic Acids Research, 48*(D1), D517–D525. https://doi.org/10.1093/nar/gkz935

Armstrong, G. L., MacCannell, D. R., Taylor, J., Carleton, H. A., Neuhaus, E. B., Bradbury, R. S., Posey, J. E., & Gwinn, M. (2019). Pathogen genomics in public health. *New England Journal of Medicine, 381*(26), 2569–2580. https://doi.org/10.1056/NEJMsr1813907

Boccella, M., Santella, B., Pagliano, P., De Filippis, A., Casolaro, V., Galdiero, M., ... & Franci, G. (2021). Prevalence and antimicrobial resistance of *Enterococcus* species: A retrospective cohort study in Italy. *Antibiotics, 10*, 1552.

Bortolaia, V., Kaas, R. S., Ruppe, E., Roberts, M. C., Schwarz, S., Cattoir, V., Philippon, A., Allesoe, R. L., Rebelo, A. R., Florensa, A. F., Fagelhauer, L., Chakraborty, T., Neumann, B., Werner, G., Bender, J. K., Stingl, K., Nguyen, M., Coppens, J., Xavier, B. B., … Aarestrup, F. M. (2020). ResFinder 4.0 for predictions of phenotypes from genotypes. *Journal of Antimicrobial Chemotherapy, 75*(12), 3491–3500. https://doi.org/10.1093/jac/dkaa345

Breidenstein, E. B., de la Fuente-Núñez, C., & Hancock, R. E. (2011). *Pseudomonas aeruginosa*: All roads lead to resistance. *Trends in Microbiology, 19*(8), 419–426. https://doi.org/10.1016/j.tim.2011.04.005

Byarugaba, D. K., Osman, T. S., Sayyouh, O. M., Wokorach, G., Kigen, C. K., Muturi, J. W., Onyonyi, V. N., Said, M. M., Nasrat, S. A., Gazo, M., & Erima, B. (2024). Genomic epidemiology of multidrug-resistant *Escherichia coli* and *Klebsiella pneumoniae* in Kenya, Uganda, and Jordan. *Emerging Infectious Diseases, 30*(Suppl 2), S33.

Carattoli, A., Zankari, E., García-Fernández, A., Voldby Larsen, M., Lund, O., Villa, L., Møller Aarestrup, F., & Hasman, H. (2014). In silico detection and typing of plasmids using PlasmidFinder and plasmid multilocus sequence typing. *Antimicrobial Agents and Chemotherapy, 58*(7), 3895–3903. https://doi.org/10.1128/AAC.02412-14

Chen, F., Lv, T., Xiao, Y., Chen, A., Xiao, Y., & Chen, Y. (2021). Clinical characteristics of patients and whole genome sequencing-based surveillance of *Escherichia coli* community-onset bloodstream infections at a non-tertiary hospital in China. *Frontiers in Microbiology, 12*, 748471.

Cosgrove, S. E. (2006). The relationship between antimicrobial resistance and patient outcomes: Mortality, length of hospital stay, and health care costs. *Clinical Infectious Diseases, 42*(Suppl 2), S82–S89. https://doi.org/10.1086/499406

Curran, B., Jonas, D., Grundmann, H., Pitt, T., & Dowson, C. G. (2004). Development of a multilocus sequence typing scheme for the opportunistic pathogen *Pseudomonas aeruginosa*. *Journal of Clinical Microbiology, 42*(12), 5644–5649. [<u>https://doi.org/10.1128/JCM.42.12.5644-5649.2004</u>](https://doi.org/10.1128/JCM.42.12.5644-5649.2004)

<span class="mark">Cuthbertson L, Kimber MS, Whitfield C. Substrate binding by a bacterial ABC transporter involved in polysaccharide export. Proc Natl Acad Sci USA. 2007;104:19529–19534. doi: 10.1073/pnas.0705709104.</span>

Dale, A. P., & Woodford, N. (2015). Extra-intestinal pathogenic *Escherichia coli* (ExPEC): Disease, carriage and clones. *Journal of Infection, 71*(6), 615–626.

Denamur, E., Clermont, O., Bonacorsi, S., & Gordon, D. (2021). The population genetics of pathogenic *Escherichia coli*. *Nature Reviews Microbiology, 19*(1), 37–54.

Feldgarden, M., Brover, V., Gonzalez-Escalona, N., Frye, J. G., Haendiges, J., Haft, D. H., Hoffmann, M., Pettengill, J. B., Prasad, A. B., Tillman, G. E., Tyson, G. H., & Klimke, W. (2021). AMRFinderPlus and the Reference Gene Catalog facilitate examination of the genomic links among antimicrobial resistance, stress response, and virulence. *Scientific Reports, 11*(1), 12728. [<u>https://doi.org/10.1038/s41598-021-91456-0</u>](https://doi.org/10.1038/s41598-021-91456-0)

<span class="mark">Follador R, Heinz E, Wyres KL, Ellington MJ, Kowarik M, et al. The diversity of Klebsiella pneumoniae surface polysaccharides. Microb Genom. 2016;2:e000073. doi: 10.1099/mgen.0.000073</span>

García-Solache, M., & Rice, L. B. (2019). The Enterococcus: a model of adaptability to its environment. Clinical microbiology reviews, 32(2), 10-1128.

Gilchrist, C. A., Turner, S. D., Riley, M. F., Petri, W. A., Jr., & Hewlett, E. L. (2015). Whole-genome sequencing in outbreak analysis. *Clinical Microbiology Reviews, 28*(3), 541–563. https://doi.org/10.1128/CMR.00075-13

Gorrie, C. L., Mirčeta, M., Wick, R. R., et al. (2022). Genomic dissection of *Klebsiella pneumoniae* infections in hospital patients reveals insights into an opportunistic pathogen. *Nature Communications, 13*, 3017. https://doi.org/10.1038/s41467-022-30717-6

Guffey, A. A., & Loll, P. J. (2021). Regulation of resistance in vancomycin-resistant enterococci: The VanRS two-component system. *Microorganisms, 9*(10), 2026.

Guo, Y., Hao, Y., Huang, M., Sun, Y., Tao, Z., Liu, Y., ... & Wei, D. (2025). Whole-genome sequencing reveals resistance mechanisms and molecular epidemiology of carbapenem-resistant *Pseudomonas aeruginosa* bloodstream infections. *BMC Microbiology, 25*(1), 1–11.

Guo, Y., Zhuo, C., Zhang, T., Wu, K., Shi, Z., Zhu, Y., ... & Qi, N. (2026). Genomic insights into a hospital-acquired high-risk vancomycin-resistant *Enterococcus faecium* outbreak in Guangdong, China. *MicrobiologyOpen, 15*(2), e70288. https://doi.org/10.1002/mbo3.70288

Halpin, A. L., Mathers, A. J., Walsh, T. R., Zingg, W., Okeke, I. N., McDonald, L. C., ... & Zanella, M. C. (2025). A framework towards implementation of sequencing for antimicrobial-resistant and other health-care-associated pathogens. *The Lancet Infectious Diseases, 25*(4), e235–e244. https://doi.org/10.1016/S1473-3099(24)00729-1

Hennart, M., Guglielmini, J., Bridel, S., Maiden, M. C. J., Jolley, K. A., Criscuolo, A., & Brisse, S. (2022). A dual barcoding approach to bacterial strain nomenclature: Genomic taxonomy of *Klebsiella pneumoniae* strains. *Molecular Biology and Evolution, 39*(7), msac135. https://doi.org/10.1093/molbev/msac135

Hetsa, B. A., Asante, J., Mbanga, J., Ismail, A., Abia, A. L., Amoako, D. G., & Essack, S. Y. (2024). Genomic characterization of methicillin-resistant and methicillin-susceptible *Staphylococcus aureus* implicated in bloodstream infections, KwaZulu-Natal, South Africa: A pilot study. *Antibiotics, 13*(9), 796.

Høiby, N., Bjarnsholt, T., Givskov, M., Molin, S., & Ciofu, O. (2010). Antibiotic resistance of bacterial biofilms. *International Journal of Antimicrobial Agents, 35*(4), 322–332. https://doi.org/10.1016/j.ijantimicag.2009.12.011

Hollenbeck, B. L., & Rice, L. B. (2012). Intrinsic and acquired resistance mechanisms in enterococcus. Virulence, 3(5), 421-569.

<span class="mark">Holt, K. E. et al. Genomic analysis of diversity, population structure, virulence, and antimicrobial resistance in *Klebsiella pneumoniae*, an urgent threat to public health. *Proc. Natl Acad. Sci. USA* **112**, E3574–E3581 (2015)</span>

Ikuta, K. S., Swetschinski, L. R., Aguilar, G. R., Sharara, F., Mestrovic, T., Gray, A. P., ... & Dhingra, S. (2022). Global mortality associated with 33 bacterial pathogens in 2019: A systematic analysis for the Global Burden of Disease Study 2019. *The Lancet, 400*(10369), 2221–2248.

Kaper, J. B., Nataro, J. P., & Mobley, H. L. (2004). Pathogenic *Escherichia coli*. *Nature Reviews Microbiology, 2*(2), 123–140.

Klockgether, J., Cramer, N., Wiehlmann, L., Davenport, C. F., & Tümmler, B. (2011). *Pseudomonas aeruginosa* genomic structure and diversity. *Frontiers in Microbiology, 2*, 150. https://doi.org/10.3389/fmicb.2011.00150

Köhler, C. D., & Dobrindt, U. (2011). What defines extraintestinal pathogenic *Escherichia coli*? *International Journal of Medical Microbiology, 301*(8), 642–647.

Lam, J. S., Taylor, V. L., Islam, S. T., Hao, Y., & Kocíncová, D. (2011). Genetic and functional diversity of *Pseudomonas aeruginosa* lipopolysaccharide. *Frontiers in Microbiology, 2*, 118. https://doi.org/10.3389/fmicb.2011.00118

Lam, M. M. C., et al. (2018a). Genetic diversity, mobilisation and spread of the yersiniabactin-encoding mobile element ICE*Kp* in *Klebsiella pneumoniae* populations. *Microbial Genomics*. https://doi.org/10.1099/mgen.0.000196

Lam, M. M. C., et al. (2018b). Population genomics of hypervirulent *Klebsiella pneumoniae* clonal group 23 reveals early emergence and rapid global dissemination. *Nature Communications, 9*, 2703.

Lam, M. M. C., Wick, R. R., Watts, S. C., et al. (2021). A genomic surveillance framework and genotyping tool for *Klebsiella pneumoniae* and its related species complex. *Nature Communications, 12*, 4188. https://doi.org/10.1038/s41467-021-24448-3

Laux, C., Peschel, A., & Krismer, B. (2019). Staphylococcus aureus colonization of the human nose and interaction with other microbiome members. Microbiology spectrum, 7(2), 10-1128.

Leavis, H. L., Bonten, M. J., & Willems, R. J. (2006). Identification of high-risk enterococcal clonal complexes: Global dispersion and antibiotic resistance. *Current Opinion in Microbiology, 9*(5), 454–460.

<span class="mark">Long, S. W. et al. Whole-genome sequencing of human clinical *Klebsiella pneumoniae* isolates reveals misidentification and misunderstandings of *Klebsiella pneumoniae*, *Klebsiella variicola*, and *Klebsiella quasipneumoniae*. *mSphere* **2**, e00290–e00317 (2017).</span>

Madsen, K. T., Skov, M. N., Gill, S., & Kemp, M. (2017). Virulence factors associated with *Enterococcus faecalis* infective endocarditis: A mini review. *The Open Microbiology Journal, 11*, 1.

Malaure, C., Geslain, G., Birgy, A., Bidet, P., Poilane, I., Allain, M., ... & Bonacorsi, S. (2024). Early-onset infection caused by *Escherichia coli* sequence type 1193 in late preterm and full-term neonates. *Emerging Infectious Diseases, 30*(1), 20.

Maldonado-Barrueco, A., Rubio-Mora, E., Bloise, I., Cacho-Calvo, J., Hernández-Rivas, L., Dahdouh, E., ... & Lázaro-Perona, F. (2025). Genomic analysis of carbapenem resistant *Acinetobacter baumannii* outbreak in a burn intensive care unit of a tertiary-care hospital in Madrid, Spain. *Antimicrobial Resistance & Infection Control, 14*(1), 124.

Matsumura, Y., Yamamoto, M., Gomi, R., Tsuchido, Y., Shinohara, K., Noguchi, T., & Nagao, M. (2025). Integrating whole-genome sequencing into antimicrobial resistance surveillance: Methodologies, challenges, and perspectives. *Clinical Microbiology Reviews, 38*(4), Article e00140-22. https://doi.org/10.1128/cmr.00140-22

Murray, C. J., Ikuta, K. S., Sharara, F., Swetschinski, L., Aguilar, G. R., Gray, A., ... & Tasak, N. (2022). Global burden of bacterial antimicrobial resistance in 2019: A systematic analysis. *The Lancet, 399*(10325), 629–655. https://doi.org/10.1016/S0140-6736(21)02724-0

Mylotte, J. M., & Tayara, A. (2000). *Staphylococcus aureus* bacteremia: Predictors of 30-day mortality in a large cohort. *Clinical Infectious Diseases, 31*(5), 1170–1174.

Nicolas-Chanoine, M.-H., Bertrand, X., & Madec, J.-Y. (2014). *Escherichia coli* ST131, an intriguing clonal group. *Clinical Microbiology Reviews, 27*(3), 543–574. https://doi.org/10.1128/CMR.00125-13

NIHR Global Health Research Unit on Genomic Surveillance of AMR. (2020). Whole-genome sequencing as part of national and international surveillance programmes for antimicrobial resistance: A roadmap. *BMJ Global Health, 5*(11), e002244. https://doi.org/10.1136/bmjgh-2019-002244

Odih, E. E., Abdulahi, J. A., Amulele, A. V., Bates, M., Heinz, E., Hu, W., & Holt, K. E. (2026). Contribution of nosocomial transmission to *Klebsiella pneumoniae* neonatal sepsis in Africa and South Asia: An observational study of infection clusters inferred from pathogen genomics and temporal data. *PLOS Medicine, 23*(5), Article e1005077. https://doi.org/10.1371/journal.pmed.1005077

Oliver, A., Mulet, X., López-Causapé, C., & Juan, C. (2015). The increasing threat of *Pseudomonas aeruginosa* high-risk clones. *Drug Resistance Updates, 21*, 41–59. https://doi.org/10.1016/j.drup.2015.08.002

Opperman, C. J., Moodley, C., Lennard, K., Smith, M., Ncayiyana, J., Vulindlu, M., ... & Centner, C. M. (2022). A citywide, clonal outbreak of *Pseudomonas aeruginosa*. *International Journal of Infectious Diseases, 117*, 74–86.

Pearse, O., Zuza, A., Tewesa, E., Siyabu, P., Fraser, A. J., Cornick, J., ... & Heinz, E. (2025). High diversity of *Escherichia coli* causing invasive disease in neonates in Malawi poses challenges for O-antigen based vaccine approach. *Communications Medicine, 5*(1), 298. [<u>https://www.nature.com/articles/s43856-025-01007-</u>](https://www.nature.com/articles/s43856-025-01007-1)1

Pedersen, T., Løvestad, A. H., Ingebretsen, A., Skutlaberg, D. H., Ås, C. G., Blomfeldt, A., ... & Skjærvik, A. (2026). Molecular epidemiology of a nationwide *Pseudomonas aeruginosa* outbreak in Norway reveals multiple distinct clusters, including high-risk clone ST244. *Journal of Hospital Infection, 168*, 70–79.

Pirnay, J. P., Bilocq, F., Pot, B., Cornelis, P., Zizi, M., Van Eldere, J., Deschaght, P., Vaneechoutte, M., Jennes, S., Pitt, T., & De Vos, D. (2009). *Pseudomonas aeruginosa* population structure revisited. *PLOS ONE, 4*(11), e7740. https://doi.org/10.1371/journal.pone.0007740

Poole, K. (2011). *Pseudomonas aeruginosa*: Resistance to the max. *Frontiers in Microbiology, 2*, 65. https://doi.org/10.3389/fmicb.2011.00065

Price, V., Dunn, S. J., Moran, R. A., Swindells, J., & McNally, A. (2022). Whole-genome sequencing enhances existing pathogen and antimicrobial-resistance surveillance schemes within a neonatal unit. *Microbial Genomics, 8*(6), Article 000841. https://doi.org/10.1099/mgen.0.000841

Robertson, J., & Nash, J. H. E. (2018). MOB-suite: Software tools for clustering, reconstruction and typing of plasmids from draft assemblies. *Microbial Genomics, 4*(8), e000206. https://doi.org/10.1099/mgen.0.000206

Rudd, K. E., Johnson, S. C., Agesa, K. M., Shackelford, K. A., Tsoi, D., Kievlan, D. R., ... & Naghavi, M. (2020). Global, regional, and national sepsis incidence and mortality, 1990–2017: Analysis for the Global Burden of Disease Study. *The Lancet, 395*(10219), 200–211. https://doi.org/10.1016/S0140-6736(19)32989-7

Sarkar, S. N., & Das, S. (2026). Parallel evolutionary trajectories of extensively drug-resistant *Klebsiella pneumoniae* ST258 and ST307 pandemic clones: A systematic review. *Canadian Journal of Microbiology, 72*, 1–12.

Sarowska, J., Futoma-Koloch, B., Jama-Kmiecik, A., Frej-Madrzak, M., Ksiazczyk, M., Bugla-Ploskonska, G., & Choroszy-Krol, I. (2019). Virulence factors, prevalence and potential transmission of extraintestinal pathogenic *Escherichia coli* isolated from different sources: Recent reports. *Gut Pathogens, 11*(1), 10.

Schembri, M. A., Ben Zakour, N. L., Phan, M. D., Forde, B. M., Stanton-Cook, M., & Beatson, S. A. (2015). Molecular characterization of the multidrug resistant *Escherichia coli* ST131 clone. *Pathogens, 4*(3), 422–430.

Shaver, C. M., & Hauser, A. R. (2004). Relative contributions of *Pseudomonas aeruginosa* ExoU, ExoS, and ExoT to virulence in the lung. *Infection and Immunity, 72*(12), 6969–6977. https://doi.org/10.1128/IAI.72.12.6969-6977.2004

Song, X., Sun, Z., Ding, B., Jin, M., Xu, J., & Yang, B. (2025). Investigation and control of a suspected outbreak of carbapenem-resistant *Acinetobacter baumannii* nosocomial infections in the cardiovascular surgical ICU based on whole-genome sequencing. *Frontiers in Public Health, 13*, 1730647.

Strateva, T., & Yordanov, D. (2009). *Pseudomonas aeruginosa*: A phenomenon of bacterial resistance. *Journal of Medical Microbiology, 58*(9), 1133–1148. https://doi.org/10.1099/jmm.0.009142-0

Strysko, J., Thela, T., Feder, A., Thubuka, J., Machiya, T., Mkubwa, J., ... & Planet, P. J. (2025). Carbapenem-resistant *Acinetobacter baumannii* at a hospital in Botswana: Detecting a protracted outbreak using whole genome sequencing. *Microbiology Spectrum, 14*(1), e01768-25.

Thrane, S. W., Taylor, V. L., Lund, O., Lam, J. S., & Jelsbak, L. (2016). Application of whole-genome sequencing data for O-specific antigen analysis and in silico serotyping of *Pseudomonas aeruginosa* isolates. *Journal of Clinical Microbiology, 54*(7), 1782–1788. https://doi.org/10.1128/JCM.00349-16

Van Hal, S. J., Jensen, S. O., Vaska, V. L., Espedido, B. A., Paterson, D. L., & Gosbell, I. B. (2012). Predictors of mortality in *Staphylococcus aureus* bacteremia. *Clinical Microbiology Reviews, 25*(2), 362–386.

Wilkinson, M. D., Dumontier, M., Aalbersberg, I. J., Appleton, G., Axton, M., Baak, A., Blomberg, N., Boiten, J.-W., da Silva Santos, L. B., Bourne, P. E., Bouwman, J., Brookes, A. J., Clark, T., Crosas, M., Dillo, I., Dumon, O., Edmunds, S., Evelo, C. T., Finkers, R., … Mons, B. (2016). The FAIR Guiding Principles for scientific data management and stewardship. *Scientific Data, 3*, Article 160018. [<u>https://doi.org/10.1038/sdata.2016.18</u>](https://doi.org/10.1038/sdata.2016.18)

<span class="mark">Whitfield C. Biosynthesis and assembly of capsular polysaccharides in Escherichia coli . Annu Rev Biochem. 2006;75:39–68. doi: 10.1146/annurev.biochem.75.103004.142545</span>

Wohl, S., Lee, E. C., DiPrete, B. L., & Lessler, J. (2023). Sample size calculations for pathogen variant surveillance in the presence of biological and systematic biases. *Cell Reports Medicine, 4*(5). https://doi.org/10.1016/j.xcrm.2023.101022

World Health Organization. (2020). *Whole-genome sequencing for surveillance of antimicrobial resistance*. https://www.who.int/docs/default-source/antimicrobial-resistance/glass_wgs_report_v8_web.pdf

World Health Organization. (2022a). *Global genomic surveillance strategy for pathogens with pandemic and epidemic potential, 2022–2032*. https://www.who.int/publications/i/item/9789240046979

World Health Organization. (2022b). *WHO guiding principles for pathogen genome data sharing*. https://www.who.int/publications/b/65924

World Health Organization. (2024). *WHO bacterial priority pathogens list, 2024: Bacterial pathogens of public health importance to guide research, development and strategies to prevent and control antimicrobial resistance*. https://www.who.int/publications/i/item/9789240093461

World Health Organization. (2025, October 13). *WHO warns of widespread resistance to common antibiotics worldwide*. https://www.who.int/news/item/13-10-2025-who-warns-of-widespread-resistance-to-common-antibiotics-worldwide

Wyres, K. L., Lam, M. M. C., & Holt, K. E. (2020). Population genomics of *Klebsiella pneumoniae*. *Nature Reviews Microbiology, 18*, 344–359. https://doi.org/10.1038/s41579-019-0315-1

Zerbato, V., Pol, R., Sanson, G., Suru, D. A., Pin, E., Tabolli, V., ... & Di Bella, S. (2024). Risk factors for 30-day mortality in nosocomial enterococcal bloodstream infections. *Antibiotics, 13*(7), 601.

Zhu, S., Zhang, K., Zhang, M., Xiao, J., Wang, L., & Zhao, C. (2026). Genomic epidemiology and antimicrobial resistance prevalence of *Staphylococcus aureus* isolated from bloodstream infections in a tertiary hospital in central China: A 5-year retrospective study. *Frontiers in Public Health, 14*, 1807676.

# 

# Appendix

**Supplementary table 1: Standalone Tools**

<table style="width:100%;">
<colgroup>
<col style="width: 20%" />
<col style="width: 15%" />
<col style="width: 13%" />
<col style="width: 14%" />
<col style="width: 13%" />
<col style="width: 21%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Analysis Step</strong></th>
<th><strong>Universal Tools</strong></th>
<th><strong><em>K. pneumoniae</em> Specific</strong></th>
<th><strong><em>E. coli</em> Specific</strong></th>
<th><strong><em>S. aureus</em> Specific</strong></th>
<th><strong>Purpose</strong></th>
</tr>
<tr class="odd">
<th><strong>Base calling</strong></th>
<th><p>Dorado</p>
<p>Guppy</p>
<p>Bcl-convert</p></th>
<th></th>
<th></th>
<th></th>
<th>Convert raw file in FASTQ</th>
</tr>
<tr class="header">
<th><strong>Raw QC</strong></th>
<th>FastQC, MultiQC</th>
<th>-</th>
<th>-</th>
<th>-</th>
<th>Quality assessment</th>
</tr>
<tr class="odd">
<th><strong>Trimming</strong></th>
<th><p>fastp, Trimmomatic</p>
<p>Porechop</p>
<p>Nanofilt</p></th>
<th>-</th>
<th>-</th>
<th>-</th>
<th>Adapter removal, filtering</th>
</tr>
<tr class="header">
<th><strong>Contamination Check</strong></th>
<th>ConFindr, Kraken2</th>
<th>-</th>
<th>-</th>
<th>-</th>
<th>Detect mixed cultures</th>
</tr>
<tr class="odd">
<th><strong>Species Confirmation</strong></th>
<th>Bactinspector</th>
<th>Kleborate (species module)</th>
<th>-</th>
<th>-</th>
<th>Verify pathogen identity</th>
</tr>
<tr class="header">
<th><strong>Assembly and polishing</strong></th>
<th><p>Shovill, SPAdes</p>
<p>Flye</p>
<p>Unicycler</p>
<p>Medaka</p></th>
<th>-</th>
<th>-</th>
<th>-</th>
<th>Genome assembly</th>
</tr>
<tr class="odd">
<th><strong>Assembly QC</strong></th>
<th>QUAST, CheckM2, BUSCO</th>
<th>-</th>
<th>-</th>
<th>-</th>
<th>Assembly quality metrics</th>
</tr>
<tr class="header">
<th><strong>MLST</strong></th>
<th>mlst (PubMLST)</th>
<th>Included in Kleborate</th>
<th></th>
<th>spaTyper</th>
<th>Sequence typing</th>
</tr>
<tr class="odd">
<th><strong>AMR Detection</strong></th>
<th>ABRicate (ResFinder, CARD), AMRFinderPlus</th>
<th>Kleborate</th>
<th><p>ABRicate</p>
<p>AMRFinderplus(Implemented in Kleborate)</p></th>
<th><p>ABRicate</p>
<p>AMRFinderPlus</p></th>
<th>Resistance gene detection</th>
</tr>
<tr class="header">
<th><strong>Virulence Detection</strong></th>
<th>ABRicate (VFDB), AMRFinderPlus</th>
<th>Kleborate (hypervirulence markers)</th>
<th>Implemented in Kleborate</th>
<th>PVL detection</th>
<th>Virulence factor profiling</th>
</tr>
<tr class="odd">
<th><strong>Plasmid Detection</strong></th>
<th>ABRicate PlasmidFinder, MOB-suite</th>
<th>ABRicate</th>
<th>ABRicate</th>
<th>ABRicate</th>
<th>Plasmid replicon typing</th>
</tr>
<tr class="header">
<th><strong>Serotype or Capsule</strong></th>
<th>-</th>
<th>Kleborate (K/O loci), Kaptive, KlebSeroEpi</th>
<th><p>ECTyper (O:H)</p>
<p>Implemented in Kleborate</p></th>
<th>spaTyper (spa type), SCCmecFinder</th>
<th>Strain typing</th>
</tr>
<tr class="odd">
<th><strong>SNP Calling and core genome alignment</strong></th>
<th>Snippy</th>
<th>Snippy</th>
<th>Snippy</th>
<th>Snippy</th>
<th>Variant detection and alignment</th>
</tr>
<tr class="header">
<th><strong>Phylogeny</strong></th>
<th>IQ-TREE, FastTree</th>
<th>IQ-TREE</th>
<th>IQ-TREE</th>
<th>IQ-TREE</th>
<th>Tree construction</th>
</tr>
<tr class="odd">
<th><strong>Visualization</strong></th>
<th>iTOL, FigTree,</th>
<th>Microreact,</th>
<th>Microreact</th>
<th>Microreact</th>
<th>Result visualization</th>
</tr>
</thead>
<tbody>
</tbody>
</table>

**Supplementary table 2 : Integrated Workflows**

Specialized workflows that stitch together multiple standalone bioinformatics tools for specific analysis stages.

<table>
<colgroup>
<col style="width: 24%" />
<col style="width: 16%" />
<col style="width: 15%" />
<col style="width: 13%" />
<col style="width: 14%" />
<col style="width: 15%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Workflow</strong></th>
<th><strong>Purpose</strong></th>
<th><strong>Input</strong></th>
<th><strong>Outputs</strong></th>
<th><strong>Key Features</strong></th>
<th><strong>Pathogen Support</strong></th>
</tr>
<tr class="odd">
<th>Snippy</th>
<th>Rapid SNP calling</th>
<th>Raw reads + reference</th>
<th>VCF, alignment,</th>
<th>Fast, automated, handles multiple samples</th>
<th>Most bacteria</th>
</tr>
<tr class="header">
<th>Snippy-core</th>
<th>Multi-sample comparison</th>
<th>Snippy outputs</th>
<th>Core SNP alignment</th>
<th>Combines individual Snippy runs</th>
<th>Most bacteria</th>
</tr>
<tr class="odd">
<th>SRST2</th>
<th>AMR gene detection + MLST</th>
<th>Raw reads</th>
<th>Gene presence, ST</th>
<th>Uses read mapping, not assembly</th>
<th>Most bacteria</th>
</tr>
<tr class="header">
<th>AbritAMR</th>
<th>AMR and virulence detection workflow</th>
<th>Assemblies</th>
<th>AMR reports</th>
<th>Standardized, lab-validated</th>
<th>Most bacteria</th>
</tr>
<tr class="odd">
<th>nf-core/bacass</th>
<th>Assembly pipeline</th>
<th>Raw reads</th>
<th>Assemblies, QC</th>
<th>Community-validated, reproducible</th>
<th>Most bacteria</th>
</tr>
<tr class="header">
<th>Nullarbor or Bohra</th>
<th>Complete analysis</th>
<th>Raw reads</th>
<th>HTML report, phylogeny</th>
<th>Mature, well-documented</th>
<th>Most bacteria</th>
</tr>
<tr class="odd">
<th>Kleborate</th>
<th><p>Kpsc</p>
<p>E.coli</p></th>
<th>Assembly</th>
<th>Full report</th>
<th>Species, MLST, AMR, virulence, serotype</th>
<th><em>K. pneumoniae and E. coli</em></th>
</tr>
<tr class="header">
<th>ECTyper</th>
<th>E. coli typing</th>
<th>Assembly</th>
<th>Serotype, phylogroup</th>
<th>O:H antigen prediction</th>
<th><em>E. coli</em> only</th>
</tr>
<tr class="odd">
<th>spaTyper + SCCmecFinder</th>
<th>S. aureus typing</th>
<th>Assembly</th>
<th>spa type, SCCmec type</th>
<th>MRSA characterization</th>
<th><em>S. aureus</em> only</th>
</tr>
</thead>
<tbody>
</tbody>
</table>

**Supplementary table 3:** All-in-One Pipelines - Workflows for complete analysis of bacteria genomes

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 27%" />
<col style="width: 17%" />
<col style="width: 28%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Pipeline</strong></th>
<th><strong>Strengths</strong></th>
<th><strong>Pathogen Support</strong></th>
<th><strong>Best For</strong></th>
</tr>
<tr class="odd">
<th><p>Bactopia</p>
<p><a href="https://bactopia.github.io/latest/"><u>https://bactopia.github.io/latest/</u></a></p></th>
<th>Most flexible, actively developed, extensive tool integration</th>
<th>Most bacteria + pathogen-specific modules</th>
<th>Users wanting maximum flexibility</th>
</tr>
<tr class="header">
<th>nf-core/bactmap</th>
<th>Community-validated, nf-core standards, excellent docs</th>
<th>Most bacteria</th>
<th>Community-validated, nf-core standards, excellent docs</th>
</tr>
<tr class="odd">
<th><p>TheiaProk</p>
<p>Via Terra platform</p></th>
<th>Public health focused, Theiagen</th>
<th>Most bacteria</th>
<th>Public health labs/institutes using Terra</th>
</tr>
<tr class="header">
<th>ASA3P</th>
<th>User-friendly, great HTML reports</th>
<th>Most bacteria</th>
<th>Docker-friendly users, beginners</th>
</tr>
<tr class="odd">
<th>CGE Bacterial Analysis Pipeline (BAP)</th>
<th>Process Illumina reads, Nanopore reads, or assembled contigs</th>
<th>Most bacteria</th>
<th></th>
</tr>
<tr class="header">
<th>BacSeq</th>
<th>for both short-read and long-read sequencing data and the visualization and reports</th>
<th>Most bacteria</th>
<th>Hybrid assembly</th>
</tr>
</thead>
<tbody>
</tbody>
</table>

**Supplementary table 4 : Web-based tools**

For all level users with or without command-line access or in low-resource settings, the following web-based tools provide similar functionality

<table>
<colgroup>
<col style="width: 19%" />
<col style="width: 38%" />
<col style="width: 17%" />
<col style="width: 23%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Tool</strong></th>
<th><strong>URL</strong></th>
<th><strong>Purpose</strong></th>
<th><strong>Pathogens</strong></th>
</tr>
<tr class="odd">
<th>Pathogenwatch</th>
<th><a href="https://pathogen.watch/"><u>https://pathogen.watch/</u></a></th>
<th>Comprehensive analysis</th>
<th><em>K. pneumoniae, E. coli, S. aureus</em>, more</th>
</tr>
<tr class="header">
<th>NCBI Pathogen Detection</th>
<th><u>https://www.ncbi.nlm.nih.gov/pathogens/</u></th>
<th>Surveillance, Outbreak investigation, AMR &amp; Virulence Gene detection</th>
<th><em>K. pneumoniae, E. coli, S. aureus, A. baumanii, Candida auris,</em> <a href="https://www.ncbi.nlm.nih.gov/pathogens/organisms/"><u>more</u></a></th>
</tr>
<tr class="odd">
<th>Galaxy</th>
<th><a href="https://usegalaxy.eu/"><u>https://usegalaxy.eu/</u></a></th>
<th>General purpose workflows</th>
<th>All bacteria</th>
</tr>
<tr class="header">
<th>ResFinder</th>
<th><a href="https://genepi.food.dtu.dk/resfinder"><u>https://genepi.food.dtu.dk/resfinder</u></a></th>
<th>AMR gene detection</th>
<th>All bacteria</th>
</tr>
<tr class="odd">
<th>CARD</th>
<th><a href="https://card.mcmaster.ca"><u>https://card.mcmaster.ca</u></a></th>
<th>AMR analysis</th>
<th>All bacteria</th>
</tr>
<tr class="header">
<th>KlebSeroEpi</th>
<th><a href="https://klebsiella.shinyapps.io/neonatal/"><u>https://klebsiella.shinyapps.io/neonatal/</u></a></th>
<th>Serotype epidemiology</th>
<th><em>K. pneumoniae</em></th>
</tr>
<tr class="odd">
<th>Transmission estimator</th>
<th><p><a href="https://github.com/klebgenomics/transmission_estimator"><u>https://github.com/klebgenomics/transmission_estimator</u></a></p>
<p><a href="https://klebsiella.shinyapps.io/transmission_estimator/"><u>https://klebsiella.shinyapps.io/transmission_estimator/</u></a></p></th>
<th>Neonatal cluster detection</th>
<th><em>K. pneumoniae, E. coli</em></th>
</tr>
</thead>
<tbody>
</tbody>
</table>

**Databases for AMR, virulence genes, MLST, and CgMLST**

- Comprehensive Antimicrobial Resistance Database (CARD) - [<u>https://card.mcmaster.ca</u>](https://card.mcmaster.ca)

- ResFinder - [<u>http://genepi.food.dtu.dk/resfinder</u>](http://genepi.food.dtu.dk/resfinder)

- Enterobase [<u>https://enterobase.warwick.ac.uk/</u>](https://enterobase.warwick.ac.uk/)

- PubMLST –[<u>http://pubmlst.org/</u>](http://pubmlst.org/)

- <span class="mark">BIGSdb - [<u>https://bigsdb.pasteur.fr/</u>](https://bigsdb.pasteur.fr/)</span>

- <span class="mark">Antibiotic Resistance Gene-ANNOTation - ARG-ANNOT</span>

- Beta-Lactamase Data Resources - [<u>http://www.bldb.eu/</u>](http://www.bldb.eu/)

- VFDB

- AMRFinderPlus / NDARO - https://www.ncbi.nlm.nih.gov/pathogens/antimicrobial-resistance/resources/

**Shinny apps for Neonatal sepsis**

- Transmission estimator [<u>https://github.com/klebgenomics/transmission_estimator</u>](https://github.com/klebgenomics/transmission_estimator)

> <span class="mark">Identify transmission clusters among neonatal sepsis bacterial isolates using genomic (genetic distance) and epidemiological (spatiotemporal) data.</span>

- KlebSeroEpi- <span class="mark">explore the distribution of predicted K and O serotypes for *Klebsiella pneumoniae - [<u>https://klebsiella.shinyapps.io/neonatal/</u>](https://klebsiella.shinyapps.io/neonatal/)*</span>

## 

## Genome resources for sepsis 

Neonatal sepsis isolates - [<u>https://pathogen.watch/collection/klebnet-neonatal-sepsis</u>](https://pathogen.watch/collection/klebnet-neonatal-sepsis)

Bacteria isolates available in the public collection - [<u>https://github\`\`\`.com/klebgenomics/KlebRef</u>](https://github.com/klebgenomics/KlebRef)

## 

## AMR data resources

Public sources of pathogen genomics data relevant to AMR surveillance

- NCBI Pathogen Detection – [<u>http://ncbi.nlm.nih.gov/pathogens</u>](http://ncbi.nlm.nih.gov/pathogens)

- Resistome Tracker – [<u>http://fda.gov/animal-veterinary/national-antimicrobial-resistance-monitoring-system/global-resistome-data</u>](http://fda.gov/animal-veterinary/national-antimicrobial-resistance-monitoring-system/global-resistome-data)

- CARD Prevalence - [<u>card.mcmaster.ca/prevalence</u>](http://card.mcmaster.ca/prevalence)

- PubMLST –[<u>http://pubmlst.org/</u>](http://pubmlst.org/)

- Pathogenwatch - [<u>https://pathogen.watch/</u>](https://pathogen.watch/)

## Data Submission Workflow

**Pathogen Data Object Model (DOM)**

The Pathogen Data Object Model (DOM) is a standardized framework for structuring and sharing genomic pathogen data and associated contextual metadata in public health databases. It ensures that genomic surveillance data is globally consistent, FAIR (Findable, Accessible, Interoperable, and Reusable), and ready for rapid public health intervention. The Pathogen DOM is the recommended standard relational framework for all pathogen submissions. It decouples sample-level metadata from sequence-level data, allowing multiple assays to reference a single isolate record. The model consists of four interconnected components:

1.  **BioProject:** A study-level "container" that groups related genomic submissions under a single administrative or funding initiative. Stores high-level study information and links all associated data submissions together.

2.  **BioSample:** Provides crucial contextual information about the sample and pathogen (e.g., collection date, host, geographical location, and specimen type).

3.  **Raw Reads (SRA/ENA/DRA):** The primary high-throughput sequencing data necessary for verifying published results and allowing future pipeline re-computation. It allows other scientists to double-check or validate the original study's conclusions and re-analyze the genetic data using newer, more advanced software in the future.

4.  **Assembly/Consensus (Optional):** Structured contiguous sequences representing reconstructed genomes, typically used for rapid downstream alignment and lineage profiling.

The standard INSDC submission workflow consists of three linked registration steps, each of which receives a unique accession number. Using NCBI’s Submission Portal ([<u>https://submit.ncbi.nlm.nih.gov/</u>](https://submit.ncbi.nlm.nih.gov/)) as an example, this process is described step-by-step below, incorporating metadata standards and quality control (QC) tags.

**Step 1: Register a BioProject (Study)**

A BioProject is an umbrella record for all data submissions from a single initiative, such as a sepsis genomic surveillance programme or an outbreak investigation.

- **Information required**: Project title, a clear description, the list of target organisms, funding source (required if NIH-funded), and the intended data release date.

- **Where to register**: The NCBI Submission Portal (submit.ncbi.nlm.nih.gov/subs/bioproject), ENA, or DDBJ.

- Describe the project scope using the purpose_of_sampling vocabulary from the sepsis metadata specification (e.g., outbreak_investigation, routine_genomic_surveillance, AMR_monitoring).

**Step 2: Register BioSamples (Sample Metadata)**

A BioSample describes the biological source material for each sequence, typically a single bacterial isolate from a patient specimen. BioSamples can be created as part of the SRA submission process or registered independently.

- **Select a Package:** During submission, you must choose the metadata ‘package’ that best fits your samples (e.g., “Pathogen: clinical or host-associated”). Each package has a distinct set of required attributes.

- **Information required:** Organism name (NCBI Taxonomy), collection date, geographic location, specimen source, and host information (age, sex, disease status). Each sample must have a unique set of attributes.

- **Where to register**: The NCBI Submission Portal (submit.ncbi.nlm.nih.gov/subs/biosample), ENA Webin, or DDBJ.

- Use the PHA4GE sepsis metadata fields to populate BioSample attributes. Required fields (sample_id, organism, collection_date, geographic_location, specimen_source) must be present. Strongly recommended fields (host_age, host_sex, infection_type, antimicrobial_susceptibility) substantially improve the epidemiological value.

**Step 3: Submit Sequence Data to the SRA**

The Sequence Read Archive (SRA) is the primary repository for minimally-processed raw read data from high-throughput sequencing platforms. Submission is handled through the NCBI Submission Portal, which guides you through a multi-step wizard to link your reads to your BioProject and BioSamples.

**1. Prepare Library Metadata:** For each set of sequence files, you must provide:

- A link to the corresponding BioSample accession.

- The library construction protocol (e.g., Illumina DNA Prep, Ligation).

- Additional metadata including a unique library name, the sequencing platform (e.g., Illumina NovaSeq), and file type (e.g., fastq).

**2. Upload Sequence Files:**

> **Accepted formats:** Fastq files, which can be compressed using gzip or bzip2 only (.gz or .bz2). Do not use standard zip (.zip) compression.
>
> **File naming:** All file names must be unique, contain no sensitive information, and use only ASCII plain text (letters A-Z, numbers 0-9, hyphens, and underscores). The file names in your metadata table must be an exact match to your uploaded files, including the extension.

**3.** **Choose an Upload Method:**

> **Web Browser (HTTP/Aspera Connect):** Recommended for small to medium datasets. You can browse for files or drag-and-drop them. The Aspera Connect plugin can be installed for faster transfer speeds and is launched directly from the web interface.
>
> **Command-Line (FTP or Aspera):** Required for high-volume data submissions or individual files approaching the 5 TB limit. Files must be uploaded to a single, dedicated preload folder. This folder is active for 30 days, after which it and its contents are automatically deleted.
>
> **Cloud Upload:** Data can be transferred directly from an Amazon S3 or Google Cloud Platform bucket.

**4. Human Sequence Screening:** It is the submitter’s responsibility to ensure they have appropriate consent for human sequence data to be distributed publicly. Submitters are strongly encouraged to screen for and remove contaminating human reads from files before submission. NCBI also offers a human contamination screening service upon request (contact sra@ncbi.nlm.nih.gov).

**Step 4: Submit Assembled Genomes to GenBank**

Genome assemblies (FASTA), optionally with annotation files (GFF, GBK), can be submitted to GenBank. This submission must include the assembly method (assembler, version, parameters) and estimated coverage depth. INSDC requires assemblies to meet minimum quality thresholds. Assemblies that have been flagged with QC tags should still be deposited but must be annotated accordingly to alert users to their limitations.

#### Step by Step Data Submission and Sharing Checklist

The following checklist consolidates the key actions required for sharing sepsis pathogen genomic data in a manner that is FAIR, Accord compliant, and technically sound. It is designed to be used as a point of use reference by laboratory staff preparing a data submission.

| **Phase**                             | **Action**                                                                                                                                                               | **Tool or Resource**                               |
|---------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------|
| **Before sequencing**                 | Obtain ethics approval and determine appropriate consent model for data sharing.                                                                                         | Institutional IRB; Accord Clause 4                 |
| **After sequencing, before analysis** | Perform host read subtraction (for clinical specimens containing human DNA).                                                                                             | Kraken2, Bowtie2, or BBSplit with GRCh38           |
| **After assembly**                    | Quality‑control assemblies (coverage, contiguity, contamination). Apply PHA4GE QC tags where thresholds are not met.                                                     | QUAST, CheckM2; PHA4GE QC tag repository           |
| **Before submission**                 | Curate metadata using PHA4GE sepsis fields; validate with DataHarmonizer. Export in INSDC‑compatible format.                                                             | DataHarmonizer                                     |
| **Submission to INSDC**               | Register BioProject → Register BioSamples → Submit raw reads to SRA/ENA/DRA and assemblies to GenBank/ENA.                                                               | NCBI Submission Portal, ENA Webin‑CLI              |
| **Supplementary sharing**             | Upload assemblies (or raw reads) to specialised public health platforms for additional analysis and global context comparison.                                           | Pathogenwatch, EnteroBase, NCBI Pathogen Detection |
| **Upon publication**                  | Lift embargo; confirm data are publicly accessible. Notify data‑generating laboratories before submitting any secondary analysis for publication.                        | Repository dashboard; direct communication         |
| **Ongoing**                           | Monitor for requests from secondary users; respond to collaboration invitations; maintain the linkage file between de‑identified study IDs and patient records securely. | Institutional data custodian                       |

Supplementary table 5 : Computing infrastructure options for sepsis pathogen genomics

| **Infrastructure Tier**                        | **Specifications**                                                                                                                                                                                                | **Best For**                                                                                                                           | **Suitable Tools and Platforms**                                                                                                                                           |
|------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Standard laptop**                            | 16-32 GB RAM, 4-8 cores, 500 GB–1 TB storage                                                                                                                                                                      | Ad‑hoc analysis, small batches, training                                                                                               | Web‑based platforms (Pathogenwatch, EnteroBase, Galaxy), lightweight local tools (Kleborate, mlst, ABRicate), ONT MinION Mk1C integrated laptop sequencing and basecalling |
| **Workstation or local server**                | 64-256 GB RAM, 16-64 cores, 10-50 TB storage                                                                                                                                                                      | Routine surveillance (\>100 isolates per batch), local installation of curated pipelines                                               | Nextflow/Snakemake with Singularity, Bactopia, nf‑core pipelines, custom analysis scripts                                                                                  |
| **Institutional HPC cluster**                  | Shared memory, hundreds to thousands of CPU cores, parallel file system                                                                                                                                           | High‑throughput surveillance (1,000+ isolates per batch), compute‑intensive phylogenetics (BEAST2, IQ‑TREE)                            | Nextflow with SLURM/PBS executor, Snakemake with cluster profile, BEAST2 with GPU acceleration                                                                             |
| **Cloud computing (AWS, Google Cloud, Azure)** | Elastic; scale on demand. AWS EC2, Google Compute Engine, or Microsoft Azure                                                                                                                                      | Burst capacity for large projects, international collaboration, laboratories without local HPC                                         | Nextflow with cloud executor, nf‑core pipelines (tested on AWS), Terra.bio platform (Google Cloud)                                                                         |
| **Terra.bio (Broad Institute)**                | Free for public health users; built on Google Cloud; graphical workspace interface                                                                                                                                | Public health laboratories seeking an accessible, supported cloud platform for pathogen genomic analysis                               | TheiaProk, PHB workflows, Jupyter notebooks, integrated data management (Dockstore, workflow versioning)                                                                   |
| **Galaxy (public servers)**                    | Free, web‑based GUI; servers hosted in Europe ([<u>usegalaxy.eu</u>](https://usegalaxy.eu)), USA ([<u>usegalaxy.org</u>](https://usegalaxy.org)), Australia ([<u>usegalaxy.org.au</u>](https://usegalaxy.org.au)) | Laboratories with limited command‑line expertise or no local Linux environment; training. Supports direct upload and INSDC submission. | \>315 tool suites, 115 curated workflows; ABRicate, AMRFinderPlus, ResFinder, Kleborate, assembly, phylogenetics                                                           |

**Supplementary Table 6: PHA4GE Microbial Data-Sharing Accord Clauses**

The full text of the PHA4GE Microbial Data-Sharing Accord (Version 1.0) is reproduced below for reference. The Accord was developed by the PHA4GE Ethics and Data Sharing Working Group to establish baseline consensus norms for the sharing and secondary use of microbial genomic datasets.

**Purpose:** To establish baseline consensus norms for the sharing and secondary use of microbial genomic datasets, providing a common set of standards for data producers and consumers.

| **Principle**                                         | **Description**                                                                                                                                                                                                                                                                                                                                                                                                                                  |
|-------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **1. Attribution**                                    | The Methods section of any type of publication using the data will explicitly describe the source of data, with links/citation where appropriate.                                                                                                                                                                                                                                                                                                |
|                                                       | The Acknowledgements section of any type of publication using the data will explicitly describe the source of data, with links/citation where appropriate.                                                                                                                                                                                                                                                                                       |
|                                                       | Where there are very many data generators they may be listed in a supplementary table for a publication, or an online accessible list, e.g. a webpage or GitHub repo, for oral presentations and other media. In these cases, if feasible, a publication may include a list of contributing institutions.                                                                                                                                        |
| **2. Overview of outputs prior to their publication** | An email or alert will be sent to data generators with a confidential copy of a publication to review prior to publication.                                                                                                                                                                                                                                                                                                                      |
|                                                       | A standard two-week window will be provided for data generators to review the publication and raise any serious concerns that create a real risk for the data generators. No response within the two-week window equates to no concerns raised.                                                                                                                                                                                                  |
|                                                       | The duration of this review window may be increased by data generators but should not be decreased without very good cause.                                                                                                                                                                                                                                                                                                                      |
| **3. Onward sharing of data**                         | There will be no onward sharing of data to third parties unless there is explicit documented agreement from the data generator for onward sharing, or the data are already available for use as unrestricted open data.                                                                                                                                                                                                                          |
| **4. Host and phenotype data**                        | For human hosts, clinical data attached to sequence data will always be anonymised and de-identified such that they cannot be re-linked to individuals under any circumstances.                                                                                                                                                                                                                                                                  |
|                                                       | Genomic data will always be cleaned of contaminating human sequence by data generators prior to sharing, unless specific agreements and ethical clearance is in place for the onward use of these data.                                                                                                                                                                                                                                          |
|                                                       | For other species, genomic data will always be cleaned of contaminating host sequence (for example animal and plant sequence data) to ensure compliance with trade and national resource laws and treaties.                                                                                                                                                                                                                                      |
| **5. Geospatial data**                                | Heat maps will be used with aggregate data areas to plot geospatial data, to ensure individuals or specific communities cannot be identified.                                                                                                                                                                                                                                                                                                    |
|                                                       | Individual sample geocoordinates representing humans infected with pathogens will not be presented as dots on maps, in order to prevent re-identification and/or stigma for individuals and communities affected by infectious diseases. Heat maps will ensure that counts per aggregate data area and the area covered are sufficiently high that they cannot be used to infer the identity of individuals, households or specific communities. |
| **6. Intellectual Property**                          | Intellectual property does not transfer to the data user unless specifically and explicitly agreed by the data generator and supported by valid IP transfer agreement documentation.                                                                                                                                                                                                                                                             |
|                                                       | Unless there is a valid written agreement documenting a different arrangement, IP remains with the data generator.                                                                                                                                                                                                                                                                                                                               |
| **7. Opportunity for collaboration**                  | A reasonable attempt must be made by the data consumer to collaborate with the data generator where feasible, except where the data generator has provided an explicit waiver of this requirement.                                                                                                                                                                                                                                               |
