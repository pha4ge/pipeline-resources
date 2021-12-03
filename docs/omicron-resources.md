# Omicron Resource

{authors list}

# Overview

The [World Health Organization (WHO) has classified the SARS-CoV-2 B.1.1.529 variant as a Variant of Concern (VOC)](https://www.who.int/news/item/26-11-2021-classification-of-omicron-(b.1.1.529)-sars-cov-2-variant-of-concern) under the advice of the [Technical Advisory Group on SARS-CoV-2 Virus Evolution (TAG-VE)](https://www.who.int/groups/technical-advisory-group-on-sars-cov-2-virus-evolution)—an independent group of experts that periodically monitors and evaluates the evolution of SARS-CoV-2 and assess if specific mutations and combinations of mutations alter the behavior of the virus. The WHO has assigned the B.1.1.529 VOC the label Omicron per [their greek-letter key variant assignment system](https://www.who.int/news/item/31-05-2021-who-announces-simple-easy-to-say-labels-for-sars-cov-2-variants-of-interest-and-concern).  The elevation of Omicron to a WHO-designated VOC was based on the TAG-VE's assessment of the variant’s large number of genomic mutations and plausible impact on COVID-19 epidemiology. 

The PHA4GE Pipelines and Visualization Working Group has created this document as an attempt to highlight critical open-source/accesses resources to aid in the understanding and further analysis of the Omicron variant. 

In no way does this document represent a comprehensive list of all available SC2 bioinformatics resources. If this document fails to include a valuable public health resource or in some way mischaracterizes a resource mentioned, we encourage community collaboration through pull-requests and/or raised GitHub issues.

## Contents
- [General Information on the Omicron Variant](#general-information-on-the-omicron-variant)
	- [Educational Material](#educational-material)
	- [Public Health Announcements and Publications](#public-health-announcements-and-publications)
	- [Technical Details and Discussions](#technical-details-and-discussions)
	- [Data Reporting and Sharing](#data-reporting-and-sharing)
- [Potential impacts of Spike Protein Mutations](#potential-impacts-of-spike-protein-mutations)
    - [Spike Mutations and Diagnostic/Sequencing Assays](#spike-mutations-and-diagnostic-/-sequencing-assays)
- [Bioinformatics Resources and Considerations](#bioinformatics-resources-and-considerations)
    - [Reference Sequences](#reference-sequences)

# General Information on the Omicron Variant

## Educational Material
- [Nature News Article - Heavily mutated Omicron variant puts scientists on alert](https://www.nature.com/articles/d41586-021-03552-w): Overview of the identified variant and its potential public health impacts.
- [Theiagen Genomics Primer the Omicron Variant (Video)](https://www.youtube.com/watch?v=xhyWjPgdP9U): To assist public health scientists' understanding of the Omicron Variant, Frank Ambrosio recorded a small primer on the Omicron variant that includes an overview of the Nature news article by Ewen Callaway, visual depictions of key Omicron mutations, and the genetic diversity of Omicron relative to other SARS-CoV-2 variants using MicrobeTrace. 

## Public Health Announcements and Publications
- [Classification of Omicron (B.1.1.529): SARS-CoV-2 Variant of Concern (World Health Organization)](https://www.who.int/news/item/26-11-2021-classification-of-omicron-(b.1.1.529)-sars-cov-2-variant-of-concern)
- [CDC Statement on B.1.1.529 (Omicron variant)](https://www.cdc.gov/media/releases/2021/s1126-B11-529-omicron.html)
- [SARS-CoV-2 variants of concern as of 3 December 2021 (ECDC)](https://www.ecdc.europa.eu/en/covid-19/variants-concern)
- [Implications of the further emergence and spread of the SARS-CoV-2 B.1.1.529 variant of concern (Omicron) for the EU/EEAECDC (December 02, 2021)](https://www.ecdc.europa.eu/sites/default/files/documents/threat-assessment-covid-19-emergence-sars-cov-2-variant-omicron-december-2021.pdf)
- [SARS-CoV-2 variants of concern and variants under investigation in England (UK Health Security Agency)](https://assets.publishing.service.gov.uk/government/uploads/system/uploads/attachment_data/file/1036501/Technical_Briefing_29_published_26_November_2021.pdf)
- [Genomic surveillance of SARS-CoV-2 in Belgium ( National Reference Laboratory (UZ Leuven & KU Leuven))](https://assets.uzleuven.be/files/2021-11/genomic_surveillance_update_211126.pdf)

## Technical Details and Discussions
- [Pango-designation proposed new lineage](https://github.com/cov-lineages/pango-designation/issues/343) and the [associated twitter thread](https://twitter.com/PeacockFlu/status/1463176821416075279) Tom Peacock
- [COV-Lineages B.1.1.529 Description](https://cov-lineages.org/global_report_B.1.1.529.html) & [Outbreak.info Omicron Variant Report](https://outbreak.info/situation-reports/omicron) for information and visualizations on defining mutations, countries identified, and trends over time
- [Galaxy EU Omicron Public Analysis](https://galaxyproject.eu/posts/2021/11/29/omicron-and-galaxy/): View of the Omicron lineage’s mutational pattern derived transparently and fully reproducibly from raw sequencing reads using the Galaxy Project bioinformatics platform.

## Data Reporting and Sharing
- [PHA4GE Resource on Data Sharing](https://github.com/pha4ge/SARS-CoV-2-Contextual-Data-Specification): Sharing of sample read and assembly data through internationally accessible databases allows insights to be drawn about how the virus is spreading and mutating across the globe; the more freely available these data are to international researchers and public health scientists, the stronger our decision making can be.
- [PHA4GE Resource on Data Submission](https://github.com/pha4ge/pipeline-resources/blob/main/docs/bioinfo-solutions.md#2-submitting-raw-sequence-data-fastq-consensus-assemblies-fasta-and-relevant-sample-metadata-to-internationally-accessible-databases): Resources developed to assist in the preparation and submission of raw NGS read data (fastq files), SC2 consensus assemblies (fasta files), and contextual sample metadata to internationally-accessible databases such as NCBI, ENA, and GISAID

    
# Potential impacts of Spike Protein Mutations

The spike protein of the SARS-CoV-2 Omicron variant contains approximately 32 mutations, many of which have not been observed in previous VOCs. However, based on their location, several of these mutations have the potential to impact immune escape, transmissibility, and detection. Spike mutations found in the Omicron VOC can be analyzed in detail using the [Stanford University Coronavirus Antiviral & Resistance Database](https://covdb.stanford.edu/sierra/sars2/by-patterns/).

![Omicron S-gene mutations](./images/omicron_standford.svg)

- Up to 15 mutations have been observed within the receptor binding domain (RBD). The RBD region of the Spike protein interacts directly with the human receptor ACE2 and mutations in this region may have a direct impact on how well SARS-CoV-2 viral particles attach to a host cell. 

- Approximately 8 mutations have been observed within the N-terminal domain (NTD). The NTD of the Spike protein aids in virus attachment and mutations in this region could also impact virus infectivity. 

- Both the RBD and NTD are surface exposed areas of the Spike protein that are targeted by antibodies. Mutations in these regions have the potential to evade immunity by antibodies acquired through previous infection or vaccination.

- Three mutations occur near the furin cleavage site, the region of the Spike protein responsible for viral-host membrane fusion. Mutations in this region have the potential to affect viral entry into host cells.

## Spike Mutations and Diagnostic/Sequencing Assays

Mutations in the SARS-CoV-2 genome can affect PCR-based diagnostic assays and genomic sequencing. For example, the ThermoFisher TaqPath probe targeting the Spike gene is known to result in S-gene target failure (SGTF) when amplifying nucleic acid preparations from VOC Alpha. This occurs when the SARS-CoV-2 genome contains a deletion resulting in the loss of amino acids 69-70 of the NTD. When coupled with the positive amplification of other SARS-CoV-2 genetic regions, the SGTF has been used as a diagnostic indicator of VOC presence [SGF Deletion Assay](https://www.biorxiv.org/content/10.1101/2021.10.25.465706v1.full). 

- [Thermo Fisher Scientific Confirms Detection of SARS-CoV-2 in Samples Containing the Omicron Variant with its TaqPath COVID-19 Tests](https://thermofisher.mediaroom.com/2021-11-29-Thermo-Fisher-Scientific-Confirms-Detection-of-SARS-CoV-2-in-Samples-Containing-the-Omicron-Variant-with-its-TaqPath-COVID-19-Tests): The Omicron variant contains the NTD deletion at amino acids 69/70 and results in SGTF by the TaqPath PCR assay. 

- [NEB's Primer Monitor Tool](https://primer-monitor.neb.com/lineages): Monitor registered primer sets for overlapping sequence variants in Omicron.

- [SARS-CoV-2 Artic V4.1 update for Omicron variant](https://community.artic.network/t/sars-cov-2-v4-1-update-for-omicron-variant/342): Ten mutations in the Omicron VOC affect the Artic V4 primer scheme for whole genome sequencing. The Artic Network has designed 11 new primers to account for these mutations. 

 
# Bioinformatics Resources and Considerations

## Reference Sequences
- BioProject
- 

