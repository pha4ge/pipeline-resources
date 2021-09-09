# **Informing Public Health Action from SARS-CoV-2 Genomic Analysis**

PHA4GE Bioinformatics Pipelines &amp; Visualization Working Group <br/>
Southgate J, Libuit KG, van Heusden P, Ambrosio F, Kapsak CJ, Maturure P, Etienne G, 


# Overview

Genomic analysis of SARS-CoV-2 (SC2) samples has aided global genomic surveillance in response to COVID-19 outbreaks. The visualization of such datasets has led to the identification and characterization of SARS-CoV-2, monitoring geographic spread and evaluating transmission routes or clusters. This has had a profound impact on the formation of appropriate public health responses.

In an attempt to assist in the development of visualization tools and platforms, the Bioinformatics Pipelines and Visualization Working Group of the Public Health Alliance for Genomic Epidemiology (PHA4GE) has drafted this living document to highlight the potential of SARS-CoV-2 genomic surveillance and listed various open-source resources and case studies which are freely available .  

Please note that the bioinformatics resources listed in this document are simply an attempt to highlight the most accessible solutions as per the opinions of our working group and in no way represent a comprehensive list of all available SC2 visualization resources. If this document fails to include a valuable public health resource or in some way mischaracterizes a resource mentioned, we encourage community collaboration through pull-requests and/or raised GitHub issues.


# SARS-CoV-2 Genomic Analysis to inform Public Health Action

The PHA4GE bioinformatics pipeline and visualization working group has defined key genomic surveillance which can be used in public health decision making: 

1. **Detection of known variants** 
      * Variant Definitions
      * Use-cases

2. **Early detection of novel and emergent variants** 
      * Targeted Sampling
      * Use-cases
      * Wastewater monitoring

3. **Monitoring Variant Prevalence** 

# Community Resources

## 1. Detection of known variants

<!---blurb here-->

<details>
 <summary>Variant Definitions (VOC and VOI)</summary>

- [Tracking SARS-CoV-2 variants - WHO](https://www.who.int/en/activities/tracking-SARS-CoV-2-variants/)
  - **Brief Description:** Working Definitions of variants and actions taken upon discovery
  - **Developed/supported by:** WHO Virus Evolution Working Group, COVID-19 reference laboratory network, representatives from GISAID, Nextstrain, Pango and additional experts
- [Standardised Variant Definitions - Public Health England](https://github.com/phe-genomics/variant_definitions)
  - **Brief Description:** Repository containing the up-to-date lineage definitions for variants of concern (VOC) and variants of interest (VOI) as curated by Public Health England
  - **Developed/supported by:** Public Health England
  - **Other Links:** [COVID-19 variants: genomically confirmed case numbers](https://www.gov.uk/government/publications/covid-19-variants-genomically-confirmed-case-numbers)

- [SARS-CoV-2 variants of concern - ECDC](https://www.ecdc.europa.eu/en/covid-19/variants-concern)
  - **Brief Description:** ECDC surveillance VOC, VOI and variant under monitoring tables
  - **Developed/supported by:** ECDC/WHO Regional Office for Europe’s joint virus characterisation working group

- [SARS-CoV-2 (hCoV-19) Mutation Reports - Outbreak.io](https://outbreak.info/situation-reports)
  - **Brief Description:** Epidemiological info including PANGO lineage prevalence
  - **Developed/supported by:** [Su](http://sulab.org/), [Wu](http://wulab.io/), and [Andersen](https://andersen-lab.com/) labs at Scripps Research

- [SARS-CoV-2 Variant Classifications and Definitions - US CDC](https://www.cdc.gov/coronavirus/2019-ncov/variants/variant-info.html)
  - **Brief Description:** US Government VOI/VOC definitions. US Department of Health and Human Services (HHS) established a SARS-CoV-2 Interagency Group (SIG) to improve coordination among the Centers for Disease Control and Prevention (CDC), National Institutes of Health (NIH), Food and Drug Administration (FDA), Biomedical Advanced Research and Development Authority (BARDA), and Department of Defense (DoD).
  - **Developed/supported by:** US HHS SARS-CoV-2 Interagency Group (SIG)

- [PANGO cov-lineages - cov-lineages.org](https://cov-lineages.org/lineage_list.html)
  - **Brief Description:** Website documenting all current Pango lineages and their spread using latest GISAID data.
  - **Developed/supported by:** Pangolin Network

- [ecdc_virology](https://github.com/erikalmecdc/ecdc_virology)
  - **Brief Description:** Algorithm that takes a full GISAID metadata dump and detects and ranks variants
  - **Developed/supported by:** European Centre for Disease Prevention and Control (ECDC)

- [Grinch](https://github.com/cov-lineages/grinch)
  - **Brief Description:** Generates reports for the international distribution of PANGO lineages that can be viewed in a web browser.
  - **Developed/supported by:** PANGO, cov-lineages
  - **User-interface:** command-line tool

</details>

## 2. Early detection of novel and emergent variants

 <!---blurb here-->

<details>
 <summary>Targeted Sampling Resources</summary>
 
- [Guidance for representative and targeted genomic SARS-CoV-2 monitoring - ECDC](https://www.ecdc.europa.eu/en/publications-data/guidance-representative-and-targeted-genomic-sars-cov-2-monitoring)
  - **Brief Description:** Guidance for EU/EEA Member States on implementing genomic SARS-CoV-2 surveillance. Includes advice on how to estimate the number of sequenced samples needed to achieve various objectives, including the early detection of novel variants.
  - **Developed/supported by:** European Centre for Disease Prevention and Control (ECDC)
 
- [Guidance for surveillance of SARS-CoV-2 variants - WHO](https://www.who.int/publications/i/item/WHO_2019-nCoV_surveillance_variants)
  - **Brief Description:** A minimum set of surveillance activities recommended at the national level to detect and monitor the relative prevalence of SARS-CoV-2 variants and outline a set of activities for the characterization and assessment of risk posed by these variants
  - **Developed/supported by:** WHO
</details>

<details>
 <summary>Phylogenetic Tree Visualization</summary>
 
- [Microreact](http://microreact.org)
  - **Brief Description:** Microreact allows you to upload, visualise and explore any combination of clustering (trees), geographic (map) and temporal (timeline) data. Other metadata variables are displayed in a table. You can specify colours and/or shapes to display on the map, tree and/or timeline. A permanent URL is produced for you to share your Microreact.
  - **Developed/supported by:** Centre for Genomic Pathogen Surveillance at Imperial College London and the Wellcome Genome Campus (Anthony Underwood)

- [Nextstrain](https://nextstrain.org/)
  - **Brief Description:** Nextstrain is an open-source project to harness the scientific and public health potential of pathogen genome data. It provides continually-updated view of publicly available data with powerful analyses and visualizations showing pathogen evolution and epidemic spread.
  - **Developed/supported by:** Ivan Aksamentov, Richard Neher

- [Cov2Tree](https://cov2tree.org/)
  - **Brief Description:** Phylogenetic tree with more than a million SARS-Cov-2 sequences sourced from INSDC databases, the China National Center for Bioinformation and COG-UK using a custom-developed open-source library called [Taxodium](http://github.com/theosanderson/taxodium) 
  - **Developed/supported by:** Theo Sanderson

- [CoVizu](https://filogeneti.ca/covizu/)
    - **Brief Description:** CoVizu is an [open source project](https://github.com/PoonLab/CoVizu) endeavouring to visualize the global diversity of SARS-CoV-2 genomes, which are provided by the [GISAID Initiative](https://gisaid.org/).
    - **Developed/supported by:** [Poon Laboratory](https://www.schulich.uwo.ca/pathol/people/bios/faculty/poon_art.html) of Western University

- [MicrobeTrace](https://microbetrace.cdc.gov/MicrobeTrace/)
  - **Brief Description:** The Visualization Multitool for Molecular Epidemiology and Bioinformatics
  - **Developed/supported by:** US CDC
  - **Documentation:** https://github.com/CDCgov/MicrobeTrace
  - **User-interface:** offlineable browser-based web app

- [Auspice](https://auspice.us/)
  - **Brief Description:** Allows interactive exploration of phylogenomic datasets by simply dragging & dropping them onto this page.
  - **Developed/supported by:** Fred Hutch/Basel (Nextstrain team)
  - **Documentation:** [Technical documentation (GitHub README)](https://github.com/nextstrain/auspice#readme), [NextStrain discussion Forum](https://discussion.nextstrain.org/)
  - **User-interface:** offlineable browser-based web app

- [UShER](https://genome.ucsc.edu/cgi-bin/hgPhyloPlace)
  - **Brief Description:** Places user provided sequences on very large reference trees, extracts the relevant subtree, and provides a visualization
  - **Developed/supported by:** UCSC
  - **User-interface:** offlineable browser-based web app

</details>


<details>
 <summary>Wastewater Dashboards</summary>
 
- [Wastewater Surveillance - SAMRC](https://www.samrc.ac.za/wbe/)
  - **Brief Description:** Dashboard monitoring SC2 RNA signal in wastewater collected at facilities in South Africa. 
  - **Developed/supported by:** SAMRC

- [Ottawa covid-19 wastewater surveillance](https://613covid.ca/wastewater/)
  - **Brief Description:** Wastewater monitoring dashboard in Ottawa, Canada
  - **Developed/supported by:** Warsame Yusuf, Rostyslav Vyuha, Yulric Sequeira, Andrew Fitches, and others on Big Life Lab team


- [Wastewater Surveillance Programme - Queensland Gov](https://www.qld.gov.au/health/conditions/health-alerts/coronavirus-covid-19/current-status/wastewater)
  - **Brief Description:** Dashboard monitoring SC2 prevalence in wastewater in Queensland, Australia
  - **Developed/supported by:** Queensland Government / University of Queensland / CSIRO

- [COVID-19: Wisconsin Coronavirus Wastewater Monitoring Network - Wisconsin Department of Health Sciences](https://www.dhs.wisconsin.gov/covid-19/wastewater.htm)
  - **Brief Description:** Wastewater monitoring dashboard as part of SC2 surveillance in Wisconsin
  - **Developed/supported by:** Wisconsin Department of Health Services, Wisconsin State Lab of Hygiene, and the University of Wisconsin-Milwaukee


</details>



## 3. Monitoring variant prevalence

 <!---blurb here-->

<details>
 <summary>Variant Prevalence Visualization</summary>
 
- [Covariants](https://covariants.org/)
    - **Brief Description:** Track global prevalence of Nextclade-annotated lineages
    - **Developed/supported by:** Emma B. Hodcroft, Ivan Aksamentov

- [Covidtag](http://covidtag.paseq.org/)
  - **Brief Description:** Variant prevalence and monitoring dashboard in Spain 
  - **Developed/supported by:** Francesc Català Moll and Marc Noguera i Julia, IrsiCaixa AIDS Research Institute

- [Covid Data Tracker -Variant Proportions - US CDC](https://covid.cdc.gov/covid-data-tracker/#variant-proportions)
  - **Brief Description:** Dashboard displaying estimated proportion of VOHC, VOC and VOI circulating in the US
  - **Developed/supported by:** US CDC supported by APHL and National SARS-CoV-2 Strain Surveillance (NS3) program 


- [covSPECTRUM](https://ngdc.cncb.ac.cn/ncov/variation)
    - **Brief Description** : Interactive tool to analyze and discover variants of SARS-CoV-2
    - **Developed/supported by:** [Computational Evolution group at ETH Zurich](https://bsse.ethz.ch/cevo)
    - **Documentation:** https://github.com/cevo-public/cov-spectrum-website

- [Genome Variations - CNCB/NGDC](https://ngdc.cncb.ac.cn/ncov/variation)
    - **Brief Description** : Range of tools for visualization, annotation and statistics.
    - **Developed/supported by:** China National Center for Bioinformation (CNCB)

</details>


## 4. Genomic Dashboards 

<!---Blurb here-->

<details>
 <summary>National Dashboards</summary>
 
- [CovInce](https://github.com/theosanderson/covince)
    - **Brief Description:** CovInce is an application built in React for visualising numbers and proportions of lineages for cases of SARS-CoV2. It is currently used primarily for the spatiotemporal displays at https://covid19.sanger.ac.uk/ and https://covglobe.org/.

    - **Developed/supported by:** Theo Sanderson, Richard Goater and Harald Vöhringer

- [US CDC Covid Data Tracker](https://covid.cdc.gov/covid-data-tracker/#published-covid-sequences)
    - **Brief Description:** Dashboard displaying variant proportion and sequences and global variant reporting

    - **Developed/supported by:** US CDC


- [Indian COVID-19 Surveillance](https://clingen.igib.res.in/covid19genomes/)
    - **Brief Description:** Dashboard displaying national and state level pango lineage frequencies and proportions incorporating data from the Indian SARS-CoV-2 Genomics Consortium (INSACOG), GENESCoV2 Kerala, Maharashtra State Genomic Surveillance

    - **Developed/supported by:** CSIR Institute of Genomics & Integrative Biology (CSIR-IGIB)

- [ECDC SARS-CoV-2 variants dashboard](https://gis.ecdc.europa.eu/portal/apps/opsdashboard/index.html#/25b6e879c076412aaa9ae7adb78d3241)
    - **Brief Description:** The dashboard provides an overview of the proportion of variants of concern and variants of interest in EU/EEA Member States together with sequencing volumes. Data are sourced from TESSy or the GISAID EpiCoV database

    - **Developed/supported by:** ECDC

- [COVID-⁠19 Switzerland Dashboard](https://www.covid19.admin.ch/en/epidemiologic/virus-variants)
    - **Brief Description:** Dashboard reporting that monitors variant prevalence in Switzerland and Liechtenstein. Laboratories report the results of the so-⁠called case-⁠specific variant analysis to us via the reporting system. These include the targeted examination of individual mutations or the partial or complete sequencing of the genome. The systematic monitoring of circulating virus variants, on the other hand, involves the targeted, complete sequencing of the genome from a representative sample.


    - **Developed/supported by:** Federal Office of Public Health FOPH

</details>


<details>
 <summary>District/Local level Dashboards</summary>
 
- [Seattle Flu Study](https://seattleflu.org/pathogens)
    - **Brief Description:** Monitoring influenza and other respiratory illnesses since 2017 in the Seattle area with the aim to find new and better ways to detect, prevent, and respond to respiratory illnesses
    - **Developed/supported by:** Brotman Baty Institute for Precision Medicine

- [Wisconsin SARS-CoV-2 (hCoV-19) Genomic Dashboard](https://dataportal.slh.wisc.edu/sc2dashboard)
    - **Brief Description:**  Dashboard reporting sequencing and variant prevalence in Wisconsin using data obtained from GISAID and Wisconsin Department of Health Services (DHS) SARS-CoV-2 dashboard.

    - **Developed/supported by:** Kelsey Florek, Wisconsin State Laboratory of Hygiene (WSLH)
    - **Code Repository:** https://github.com/wslh-data/sc2-data-dashboard

</details>
 
## 5. Training Resources

<!-- Blurb-->


<details>
<summary>Genomic Dashboard Resources</summary>

- [CDC Toast](https://github.com/ells/testWikiFunctionality/wiki)
    - **Brief Description:** Wiki document identifying commonly used dashboard elements to improve situational awareness and provide a better understanding of geospatial and temporal patterns arising from SARS-CoV-2 genomic data sources. This document serves as an introduction to elements, focusing on SARS-CoV-2 genomic data, with simple examples using open source technologies.
    - **Developed/supported by:** US CDC, Ellsworth Campbell

- [R figures - Training Video](https://www.youtube.com/watch?v=HHHMon4k7XM)
    - **Brief Description:** Training webinar titled - ‘How to make publication ready professional looking Figures’ - presented by Houriiyah Tegally, PhD candidate at KRISP using R to produce figures to convey scientific findings of SARS-CoV-2 Genomic Surveillance

    - **Developed/supported by:** University of KwaZulu-Natal (UKZN) KwaZulu-Natal Research Innovation and Sequencing Platform (KRISP), Houriiyah Tegally
    
- [Rshiny resource materials](https://shiny.rstudio.com/tutorial/)
    - **Brief Description:** Training videos and materials

    - **Developed/supported by:**  Rstudio

- [GISAID Processing](https://github.com/pvanheus/GISAID_processing)
    - **Brief Description:** Open-source repository containing python scripts to process GISIAD data into frequency graphs
    - **Developed/supported by:** Peter van Heusden (University of Western Cape)
    - **Documentation:** [Technical Documentation (GitHub README)](https://github.com/pvanheus/GISAID_processing/blob/main/README.md)
    - **Accessibility:** [Python-Scripts](https://github.com/krisp-kwazulu-natal/africa-covid19-genomics#readme)

</details>



