# Omicron Resource

{authors list}

# Overview

The [World Health Organization (WHO) has classified the SARS-CoV-2 B.1.1.529 variant as a Variant of Concern (VOC)](https://www.who.int/news/item/26-11-2021-classification-of-omicron-(b.1.1.529)-sars-cov-2-variant-of-concern) under the advice of the [Technical Advisory Group on SARS-CoV-2 Virus Evolution (TAG-VE)](https://www.who.int/groups/technical-advisory-group-on-sars-cov-2-virus-evolution)—an independent group of experts that periodically monitors and evaluates the evolution of SARS-CoV-2 and assess if specific mutations and combinations of mutations alter the behavior of the virus. The WHO has assigned the B.1.1.529 VOC the label Omicron as per the [their greek-letter key variant assignment system](https://www.who.int/news/item/31-05-2021-who-announces-simple-easy-to-say-labels-for-sars-cov-2-variants-of-interest-and-concern).  The elevation of Omicron to a WHO-designated VOC was based on the TAG-VE's assessment of the variant’s large number of genomic mutations and plausible impact on COVID-19 epidemiology. 

The PHA4GE Pipelines and Visualization Working Group has created this document as an attempt to highlight critical open-source/accesses resources to aid in the understanding and further analysis of the Omicron variant. 

In no way does this document represent a comprehensive list of all available SC2 bioinformatics resources. If this document fails to include a valuable public health resource or in some way mischaracterizes a resource mentioned, we encourage community collaboration through pull-requests and/or raised GitHub issues.

## Contents

{links to sections}

# General Information on the Omicron Variant

## Educational Material
- [Nature News Article - Heavily mutated Omicron variant puts scientists on alert](https://www.nature.com/articles/d41586-021-03552-w): {info blurb}
- [Theiagen Genomics Primer the Omicron Variant (Video)](https://www.youtube.com/watch?v=xhyWjPgdP9U): To assist public health scientists' understanding of the Omicron Variant, Frank Ambrosio recorded a small primer on the Omicron variant that includes an overview of the Nature news article that by Ewen Callaway and visual depictions of key Omicron mutations and the genetic diversity of Omicron relative to other SARS-CoV-2 variants using MicrobeTrace. 

## Public Health Announcements
- CDC
- WHO
- ECDC Threat Assessment Brief (December 02, 2021)

## 
## Lineage Technical Details
- [Pango-designation proposed new lineage](https://github.com/cov-lineages/pango-designation/issues/343) and the [associated twitter thread](https://twitter.com/PeacockFlu/status/1463176821416075279) Tom Peacock
- [COV-Lineages B.1.1.529 Description](https://cov-lineages.org/global_report_B.1.1.529.html) & [Outbreak.info Omicron Variant Report](https://outbreak.info/situation-reports/omicron) for information and visualizations on defining mutations, countries identified, and trends over time
- [Galaxy EU Omicron Public Analysis](https://galaxyproject.eu/posts/2021/11/29/omicron-and-galaxy/): View of the Omicron lineage’s mutational pattern derived transparently and fully reproducibly from raw sequencing reads using the Galaxy Project bioinformatics platform.
    
# Potential impacts of Spike Protein Mutations

The spike protein of the SARS-CoV-2 Omicron variant contains approximately 32 mutations, many of which have not been observed in previous VOCs. However, based on their location, several of these mutations have the potential to impact immune escape, transmissibility, and detection. Spike mutations found in the Omicron VOC can be analyzed in detail using the [Stanford University Coronavirus Antiviral & Resistance Database](https://covdb.stanford.edu/sierra/sars2/by-patterns/).

![Omicron S-gene mutations](./images/omicron_standford.svg)

- Up to 15 mutations have been observed within the receptor binding domain (RBD). The RBD region of the Spike protein interacts directly with the human receptor ACE2 and mutations in this region may have a direct impact on how well SARS-CoV-2 viral particles attach to a host cell. 

- Approximately 8 mutations have been observed within the N-terminal domain (NTD). The NTD of the Spike protein aids in virus attachment and mutations in this region could also impact virus infectivity. 

- Both the RBD and NTD are surface exposed areas of the Spike protein that are targeted by antibodies. Mutations in these regions have the potential to evade immunity by antibodies acquired through previous infection or vaccination.

- Three mutations occur near the furin cleavage site, the region of the Spike protein responsible for viral-host membrane fusion. Mutations in this region have the potential to affect viral entry into host cells.

## Spike Mutations and Diagnostic/Sequencing Assays

PCR-based diagnostic assays that target the Spike gene can also be impacted by mutations in the SARS-CoV-2 genome. Specifically, the ThermoFisher TaqPath probe targeting the Spike gene is known to result in S-gene target failure (SGTF) when the SARS-CoV-2 genome contains the deletion resulting in a loss of amino acids 69-70 of the NTD. When coupled with a positive amplification of other SARS-CoV-2 genetic regions, the SGTF has been used as a diagnostic indicator of VOC presence (SGF Deletion Assay). This has previously been the case for VOC Alpha.

- The Omicron variant contains the NTD deletion at amino acids 69/70 and results in SGTF by the TaqPath PCR assay (∆69-70 TaqPath S dropout). 

- To monitor registered primer sets for overlapping sequence variants in Omicron, visit [NEB’s Primer Monitor Tool](https://primer-monitor.neb.com/lineages).

- [SARS-CoV-2 Artic V4.1 update for Omicron variant](https://community.artic.network/t/sars-cov-2-v4-1-update-for-omicron-variant/342): Ten mutations in the Omicron VoC affect the Artic V4 primer scheme. The Artic Network has designed 11 new primers to account for these mutations. 

 
# Bioinformatics Resources and Considerations

## Reference Sequences
- BioProject
- 

