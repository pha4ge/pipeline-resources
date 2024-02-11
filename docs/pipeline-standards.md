# **Best Practices for Public Health Bioinformatics Pipelines**

**PHA4GE Bioinformatics Pipelines &amp; Visualization Working Group <br/>**
Libuit KG, Guthrie J, Ambrosio F, Kapsak C, Unal Gultekin, Holmes J, Wright S, Nguinkal J, Doughty E, Southgate J, O'Cathail C, Carleton H, Kingwara L, Khan W, Baker K, Diallo A, Connor T, Kanwar S, Maturure P, James S, Cuesta I, Dyster V, Gaskin A, Williams C, Smith E, Rokney A, Petkau A, Varona S, Gnimpieba E, Rey S, Macori G, & Mboowa G
<details>
 <summary> Document Changelog</summary>

- 2023-07-05:
    - Commit to main
 - 2023-12-03:
    - Adding max duration for commitments to maintain (2  years)
- 2024-02-11:
    - Adding descriptions of meeting and verifying proposed standards
</details>

## Overview

The field of public health bioinformatics relies heavily on the development and sustainability of high-quality software to support efforts in disease surveillance, outbreak investigation, and genomic research. Bioinformatics pipelines, also known as bioinformatics workflows, play a critical role in facilitating the routine analysis of genomic data by orchestrating the flow from raw data through various processing stages to final analysis. 

Despite their critical role, the absence of guidelines and best practices specific to public health pathogen genomics has hindered progress towards accessible, reproducible, interoperable, and standardized bioinformatics analysis in public health.

To support both pipeline developers and analysts who rely on these pipelines to inform critical public health decision making, the Bioinformatics Pipelines and Visualization Working Group of the Public Health Alliance for Genomic Epidemiology (PHA4GE) has proposed a set of best practices for bioinformatics pipelines, tailored for public health applications. These best practices aim to provide a framework for the development, testing, and maintenance of bioinformatics pipelines, enhancing the quality, reliability, and sustainability of these resources and facilitating their impact on public health.

## 10 Best Practices for Public Health Bioinformatics Pipelines

### 1. Publicly-Accessible Repository
_Is the source code for this pipeline available at a publicly-accessible repository URL?_

Publicly-accessible software bolsters collaboration and expedites innovation in public health bioinformatics, empowering worldwide public health communities to address critical challenges. By enhancing accessibility, publicly available software enable interoperability and reproducibility across public health investigations, crucial for well-informed decision-making and policy creation. Popular code repositories such as GitHub, GitLab, Bitbucket, and SourceForge offer platforms for developers to share their work. 

**To adhere to this best practice:** Host the bioinformatics pipeline on an open code repository platform.

**To verify adherence to this best practice:** The reviewer should confirm existence and functionality of the repository.

### 2. Open-Source License
_Does the repository contain a plain-text LICENSE file with the contents of an OSI-approved software license?_

Open-source licenses in public health bioinformatics encourage the widespread adoption and sharing of valuable tools and resources, fostering a collaborative environment for research and innovation. These licenses also support the unrestricted improvement and customization of software, enabling researchers to tailor solutions to specific public health challenges and enhance overall outcomes. Without a license, the code author retains all rights to the work, and others are not allowed to use, copy, distribute, or modify it without permission. This means that the code is effectively unusable by the research community as a whole. A license grants this permission and allows others to use, copy, distribute, or modify the work under certain conditions. Popular license types for open-source bioinformatics software include GNU General Public License (GPL), MIT License, and Apache License 2.0. For helpful information regarding open-source licenses, we recommend the ARS Technica Article “[Open source licenses: What, which, and why]([url](https://arstechnica.com/gadgets/2020/02/how-to-choose-an-open-source-license/))”. 

**To adhere to this best practice:** Choose an open-source license (e.g., MIT) for the pipeline, providing legal permissions for users to modify and share the code.

**To verify adherence to this best practice:** The reviewer should confirm the presence of a clearly defined open-source license in the pipeline repository.

### 3. Version Controled Software 
_Are stable releases that follow semantic versioning of the pipeline available for implementation in public health laboratories?_

Utilizing stable software releases with semantic versioning in public health bioinformatics ensures consistent functionality and compatibility, minimizing disruptions in research workflows. This approach also simplifies version tracking and communication, facilitating seamless collaboration among researchers and reducing the likelihood of errors due to software discrepancies. Maintaining a detailed changelog is also highly recommended to track software updates, bug fixes, and feature additions, ensuring transparency and ease of understanding for users.

**To adhere to this best practice:** Implement semantic versioning (e.g., MAJOR.MINOR.PATCH).

**To verify adherence to this best practice:** The reviewer should check for version tags in the repository, ensuring that versioning follows semantic versioning principles and accurately reflects the pipeline's development history.

### 4. Workflow Management System
_Does the pipeline utilize a workflow management system for its development and execution??_ 

Implementing workflow management systems in public health bioinformatics pipelines ensures efficient, scalable, and reproducible analyses. These systems automate complex data processing tasks, facilitating seamless integration and execution of diverse bioinformatics tools. By standardizing workflow execution, they enhance data analysis consistency across different computational environments, contributing significantly to the reliability and reproducibility of public health research findings.

Additionally, the use of workflow management systems facilitates maintainability. The shared knowledge and use of these systems by a community of developers ensure that pipelines can be more readily supported and updated, significantly enhancing long-term usability and stability. Common workflow management systems adopted acorss public health pathogen genomics include [NextFlow](https://www.nextflow.io/), [WDL](https://openwdl.org/), [SnakeMake](https://snakemake.readthedocs.io/en/stable/), and [CWL](https://www.commonwl.org/). 

**To adhere to this best practice:** Choose a workflow management system that supports scalability, is compatible with common bioinformatics tools, and integrates easily with existing infrastructure. Document the workflow configuration and dependencies clearly.

**To verify adherence to this best practice:** The reviwer should assess the pipeline source code to identify the use of a workflow management system.

### 5. Containerized/Packaged Software
_Does the pipeline utilize containerized (e.g. Docker) or packaging (e.g. conda) software software to enhance interoperable pipeline distribution?_ 

Using software packages and/or containerization within public health bioinformatics pipeline enhances interoperability by enabling seamless integration and deployment across different platforms and environments. This approach simplifies pipeline distribution and installation, promotes reproducibility, and facilitates collaboration among researchers, contributing to the development of more accessible and interoperable tools and resources.

Containers are essential for modern bioinformatics development and pipeline distribution, as the ability to replicate results is a fundamental principle of the scientific method. This is true for public health, as any lab should be able to easily install and maintain pipeline and reproduce/verify results from another lab. Containers should be packaged with one or a combination of the following methods:
- conda environments
- venv environments
- Singularity containers
- Docker containers.

There should be a clear summary in the Git README pointing to which containerisation method has been chosen and instructions for how a lab can install this pipeline and/or where docker images are available, e.g. dockerhub and quay for containers; and where conda packages are available, e.g. anaconda and bioconda (cross-referenced with Installation Instructions).

When bioinformatics software is containerised, there should be a supplementary document justifying, where appropriate, why a particular version was chosen for analysis. Reasons for choosing specific pipeline versions include but are not limited to ensuring functionality by selecting compatible dependencies and major differences in functionality and features between pipeline versions.
Similarly, if a pipeline version within the container changes, this should be appropriately version-controlled, outlining any expected effects on results, documented in a CHANGELOG. This could also provide a useful way for prompting improvements during the code review process, e.g. questioning why pipeline with an upcoming end-of-life was chosen during development.

**To adhear this best practice:** Implement pipeline components within Docker containers or distribute them as Conda packages.

**To verify adherence to this best practice:** The reviewer should inspect the pipeline source code and review analyatical steps (e.g. NextFLow processes or WDL tasks) to ensure use of containerized or packaged softare.

### 6. Common File Formats
_Does the pipeline accept as input and generate as output common file format utilized in public health pathogen genomics?_

Accepting and generating common file formats for public health bioinformatics pipeline enhances interoperability and data exchange between different tools and platforms. This approach facilitates data sharing, promotes consistency, and enables researchers to leverage a wide range of pipeline solutions, contributing to the development of more comprehensive and effective solutions for addressing critical public health challenges. These files include: .fasta, .fastq(.gz), .sam, .bam, .bai, .bed, .vcf, .gff, .gtf, .txt, .log, .tsv, .csv, .nwk, and .json.

**To adhere to this best practice:** The pipeline should accept as input and generate as output common file formats utilized in public health pathogen genomics, enhancing interoperability and data exchange between different tools and platforms.

**To verify adherence to this best practice:** The reviewer should check the documentation or repository for explicit information on the common file formats supported by the pipeline, ensuring compatibility with widely used formats in public health bioinformatics.

### 7. Software Testing
_Are there automated and/or manual tests described so that the functionality of the pipeline can be assessed?_

Including software tests for public health bioinformatics pipeline ensures the reliability and accuracy of the tools, enhancing user confidence and promoting consistent research outcomes. These tests also facilitate early detection and resolution of potential issues, contributing to the overall stability and robustness of the pipeline in a rapidly evolving public health landscape. At a minimum, pipeline being implemented for public health pathogen genomics should include: 
- Smoke tests to ensure that the basic functionality of the program is working correctly
- Unit tests to test individual code units
- System tests/end-to-end tests to assess the overall functionality of the program, with a focus on common and important paths
- Regression tests to ensure that changes to the code do not break existing functionality (note: system tests can be utilized to implement regression tests)

When appropriate, inclusion of additional testing strategies may also enhance the robustness of pipeline, e.g.
- Acceptance tests to ensure that the program meets a project’s fundamental requirements
- Runtime tests to evaluate the pipeline's behavior, performance, and stability during its operation to ensure that it meets the required standards and functions correctly in real-world scenarios
- Testing frameworks, e.g. use of GitHub Actions to automate defined software tests, provide a consistent and organized structure for writing and running test cases, enabling developers to efficiently validate the correctness, performance, and reliability of their pipeline

The description of functionality and performance testing should be made accessible via the code repository where the pipeline is made available.

**To adhere to this best practice:** Provide a description of both automated and/or manual tests that assess the functionality of the pipeline, ensuring reliability and accuracy.

**To verify adherence to this best practice:** The reviewer should check the documentation for a description of tests, both automated and manual, that evaluate the functionality of the pipeline, contributing to user confidence and consistent research outcomes.

### 8. Benchmark/Validation Datasets
_Is there a publically available set of inputs with known outputs that can be used to test successful installation and benchmark against other tools?_ 

Including a benchmark or validation dataset for public health bioinformatics pipeline provides researchers with a standard reference for evaluating and comparing the performance of different tools, promoting transparency and consistency in the evaluation of pipeline. By establishing a common reference point, benchmarking enables researchers to identify the strengths and weaknesses of various pipeline solutions and promotes the development of more accurate, reliable, and effective tools. Authors should make benchmark and/or validation datasets publicly available and well-documented, allowing others to reproduce the experiments and validate the results.

A benchmark dataset is a standardized set of inputs with known outputs that is used to compare the performance of different bioinformatics tools on the same set of data. The benchmark dataset is typically designed to be representative of the types of data that the tool is likely to encounter in real-world scenarios and covers a range of use cases.

A validation dataset, on the other hand, is used to validate the accuracy and reliability of a specific bioinformatics tool. The validation dataset is designed to test the tool's performance on a range of input data types and sizes and evaluate its ability to correctly identify the target sequences and distinguish them from non-target sequences.

**To adhere to this best practice:** Include a benchmark or validation dataset for public health bioinformatics pipeline, promoting transparency and consistency in the evaluation and comparison of different tools. 
**To verify adherence to this best practice:** The reviewer should check the documentation or repository for information on the availability and accessibility of a benchmark and/or validation dataset for the public health bioinformatics pipeline.

### 9. Reference Data Requirements
_Are required reference data and/or databases clearly documented, publicly accessible, and maintained?_

Documenting any external reference data or database requirements for public health bioinformatics pipeline enhances the usability and reproducibility of the pipeline by providing clear and comprehensive information on the necessary data sources and dependencies. This documentation promotes transparency, facilitates replication, and enables researchers to more effectively integrate the pipeline into their workflows, contributing to the development of more reliable and impactful tools and resources.

If an external reference data or database is required, the following standards should be met: static versioning, open-access, and clear instructions to install/access database; database versioning and date of most recent update – version control and compatibility 
- Identify what aspects of the database need to be documented, such as the database schema, table structure, and stored procedures. Identify the format the documentation should take, such as technical documentation, user guides, and reference manuals.
- Clearly document the sources of data used to construct the database, including information on how the data was acquired, processed, and validated.
- Specify the format of the data, including any file formats, parameters used, and other relevant information.
- Describe the process of data curation, including any quality control measures, data cleaning, and data integration.
- Describe any taxonomy and annotation used in the database, including any reference standards or guidelines that were followed.
- Specify the terms of use and any restrictions on the use of data from the database, including any attribution or citation requirements.
- Mention any community or website, such as a help forum or feedback mechanism, that are in place for the database.
- Ensure that the database is compatible with the pipeline that it is being used with. Make sure that the documentation clearly states the versions of pipeline and systems that the database is compatible with.

The format of open-access downloadable should be defined, ideally in compressed format, and in such a format that will be best suited for downstream usage/analysis.

**To adhere to this best practice:** Tthe required reference data and/or databases for public health bioinformatics pipeline should be clearly documented, publicly accessible, and maintained. If an external reference database is required, it should also adhere to standards such as static versioning, open-access, and clear instructions for installation/access. Clearly document aspects of the database, such as the schema, table structure, and stored procedures, in a format suitable for users, such as technical documentation, user guides, and reference manuals.

**To verify adherence to this best practice:** The reviewer should check the documentation or repository for comprehensive information on external reference data or database requirements, ensuring transparency, usability, and reproducibility.

### 10. Pipeline Documentation
_Is the pipeline documentation clearly written and publicly accessible?_

Having clearly written and publicly-accessible pipeline documentation enhances user understanding, facilitates adoption, and promotes efficient usage of the pipeline. It provides comprehensive instructions, usage examples, and explanations of key functionalities, enabling public health scientists to effectively utilize the pipeline for their specific bioinformatics needs. Best practices for pipeline documentation include:
- Defining the documentation scope: Identify what aspects of the tool's core functionality need to be documented and what format the documentation should take. This can include things like user guides, reference manuals, and API documentation.
- Establishing documentation guidelines: Develop a set of guidelines or standards for documenting the tool's core functionality. 
- Creating a documentation template: Develop a template or set of templates that can be used to create consistent and accurate documentation..
- Reviewing and update the documentation: Regularly review and update the documentation to ensure that it is accurate and up to date. This can be done by gathering feedback, monitoring usage data, and making adjustments as necessary.
- Keeping it accessible: Make the documentation easily accessible to users by providing it in different formats like HTML, PDF, and user-friendly formats.

Effective pipeline documentation encompasses a broad range of practices, each targeting specific aspects of usability, transparency, and collaboration. These documentation practices ensure that users and contributors have a clear understanding of the pipeline's development, usage, and governance. By incorporating these elements, documentation becomes a comprehensive resource that supports the pipeline's integrity, facilitates community contribution, and enhances user engagement, making it an indispensable part of best practices in bioinformatics pipeline development.

**To adhere to this best practice and verify adherence to this best practice:**Refer to the documentation practices listed below.

#### 10a. Statement of Need with Respect to Public Health Pathogen Genomics
_Have the authors clearly stated the challenges in public health pathogen genomics that this pipeline aims to address?_

A clear statement of need for public health bioinformatics pipeline highlights the significance and relevance of the tool within the public health landscape, facilitating its adoption by the target user base. This practice also helps to align development efforts with pressing public health challenges, ensuring that resources are directed towards addressing the most critical issues. For instance, the tool could address the challenge of integrating multiple types of genomic data analysis, such as variant calling, phylogenetic reconstruction, and outbreak investigation, into a single platform. The pipeline could also incorporate machine learning algorithms to provide automated classification and identification of pathogens, reducing the need for manual curation. The type of organization or researcher that the tool is intended for should be made clear, and it is helpful to provide information regarding the level of computational expertise needed.

Users are more likely to adopt a new tool if they can see how it addresses existing limitations or provides new and innovative features that are not available in current tools. The authors should explain how their tool is different from existing tools and how it improves upon established methods, if there are any. For example, the tool might provide more accurate and reliable results due to the incorporation of new algorithms or statistical models. It might also be more user-friendly and accessible to users with varying levels of computational expertise, allowing a wider range of end-users to take advantage of the tool's capabilities.

**To adhear to this documentation practice:** Clearly state the significance and relevance of public health bioinformatics pipeline and explain how the tool differs from existing ones and/or improves established methods.
- To verify adherence to this documentation practice,the reviewer will ensure that the documentation includes a statement highlighting the pipeline's purpose and its alignment with pressing public health challenges.

#### 10b. Pipeline Functionality
_Has the function of this software as it pertains to public health bioinformatics been clearly articulated?_

Including a clear indication of software function in public health bioinformatics enables researchers to easily identify the most suitable tools for their specific needs, enhancing productivity and the overall quality of their work. This practice also fosters informed decision-making, ensuring that the software is applied effectively and appropriately to address public health challenges.

The intended use of the software in the context of public health pathogen genomics should be clearly stated, accompanied by the means to confirm this functionality, e.g. through the provision of a validation dataset with information detailing expected outputs and, if appropriate, how these outputs can be compared to a benchmark standard. Standardizing the documentation of the core functionality of a tool can help to ensure that it is clear, accurate, and easy to understand. Limitations of the software that may affect use of the results for clinical or epidemiological purposes and decisions should also be indicated with clarification of which organisms, species and subspecies have been validated for use, and where limitations and discrepancies may occur.

**To adhear to this documentation practice:** Clearly indicate the function, intended use, and limitations of the software.

**To verify adherence to this documentation practice:** The reviewer should check for explicit documentation that clearly communicates the software's functionality, intended use, limitations, validated organisms, and potential discrepancies.


#### 10b. Contribution, Authorship, and Verified Point of Contact
_Does the full list of authors seem appropriate and include a verified point of contact?_

Clearly listing authorship and credit in public health bioinformatics acknowledges the contributions of individual researchers, fostering a sense of ownership and responsibility for their work. This practice also promotes transparency, collaboration, and recognition within the scientific community, enhancing career development opportunities and encouraging the sharing of expertise. We would recommend using the [CRedIT system](https://credit.niso.org/) adopted by the Natural Sciences field to acknowledge contributions to bioinformatic tools. Contributors to the pipeline must be acknowledged as a co-author if they have contributed by: programming, pipeline development; designing computer programs; implementation of the computer code and supporting algorithms; testing of existing code components.

A verified point of contact must include a working email address of an individual or organization that is most likely to maintain the bioinformatic tool in the long term. Ideally, email addresses for multiple individuals should be provided and these should not be organizational email addresses (e.g. joe.bloggs@phag4e.org), as they could lose access to that email when they leave that organization. 

**To adhear to this documentation practice:** Clearly list authorship and credit for the bioinformatics tool, acknowledging individual contributions and following the CRedIT system for appropriate recognition based on specific contributions.

**To verify adherence to this documentation practice:** The reviewer should check the documentation and repository for a clear and comprehensive list of authors, ensuring adherence to the CRedIT system and appropriate acknowledgment of contributors based on their roles in programming, pipeline development, design, implementation, and testing.

#### 10c. Conflict of Interest Statement
_Have all potential conflicts of interest been disclosed?_

Stating potential conflicts of interest regarding pipeline authors in public health bioinformatics promotes transparency and integrity in scientific research. This practice enables users to make informed decisions about the pipeline they utilize, ensuring unbiased results and fostering trust within the research community. Conflict of interest is defined as any factor which renders an author, co-author, or collaborative team unable to (potentially or otherwise) perform an independent peer review or evaluation pertaining to a study. Examples of conflict of interest include but are not limited to commercial, personal, political, or religious interests. When developing bioinformatics (for public health) pipelines, any conflict of interest should be disclosed by the responsible authors to ensure independent peer review and testing of code has been carried out prior to publication. Some conflict of interest statements may be waived if an author can demonstrate they are able to perform an impartial code review. For example, JOSS suggests that if two co-authors did not ever truly collaborate, this might mean a co-author is a suitable selection for code review. 

**To adhear to this documentation practice:** Authors of public health bioinformatics pipeline, pipelines, or methods should transparently disclose any potential conflicts of interest, such as commercial, personal, political, or religious affiliations, to promote transparency and integrity in scientific research.

**To verify adherence to this documentation practice:** The reviewer should assess the presence of a clear conflict of interest statement in the documentation or repository, ensuring that responsible authors have openly disclosed any factors that may impact their ability to perform an unbiased peer review or evaluation.

#### 10d. Community Guidelines for Contribution and Support
_Are there clear guidelines for third parties wishing to 1) contribute to the pipeline 2) report issues or problems with the pipeline and 3) seek support?_

Including community guidelines for contribution and support in public health bioinformatics pipeline promotes open and transparent communication channels between developers, users, and the broader scientific community. These guidelines foster an environment of shared knowledge and expertise, enabling individuals to provide feedback, report issues, and contribute to the improvement and sustainability of essential tools and resources and can include repository style guides, issue templates, and/or guidelines for providing support to users, including how to report issues, how to troubleshoot common problems, and how to escalate issues that cannot be resolved through standard support channels.

**To adhear to this documentation practice:** Include community guidelines for contribution and support on the code repository where the pipeline is made available. Ensure that community guidelines foster an environment of shared knowledge and expertise, enabling individuals to contribute feedback, report issues, and actively participate in the improvement and sustainability of essential tools and resources.

**To verify adherence to this documentation practice:** The reviewer should confirm the presence of well-documented community guidelines in the documentation or repository, encompassing aspects such as repository style guides, issue templates, and guidelines for providing user support.

#### 10e. Documentation for Local Installation and/or Remote Access (e.g. Web Server or Galaxy/Terra Workflow)
_Does installation and/or access to the pipeline proceed as outlined in the documentation?_

Providing clear local installation and/or remote access instructions for public health bioinformatics pipeline streamlines the user experience, enabling researchers to efficiently deploy and utilize essential tools. This practice also minimizes potential technical barriers, fostering accessibility and promoting widespread adoption within the scientific community. The pipeline installation guide should be clear, concise, and easy to follow. The system requirements for the pipeline should be outlined with a clearly-stated list of all prerequisites and dependencies that are necessary to install the pipeline correctly. Ideally, dependencies are handled with an automated package management solution. The necessary pipeline should be defined with the required minimum version and release.

Installation instructions should include a step-by-step list. Configuration settings should be detailed and need to be clear as to the expected outcome and result. A method for verification of a successful installation should be described, and any typical problems that might occur during the installation along with methods for troubleshooting. Where there are manual post-installation / cleanup-tasks it is necessary to provide details of necessary tasks. If there are any software license terms, these should be listed. 
Methods to update the pipeline should also be described within the installation instructions.

If the resources have been made available via a web application (e.g. Galaxy or Terra.Bio), instructions on how to access and utilize the pipeline through the web application should be clearly indicated. 

**To adhear to this documentation practice:** Authors of public health bioinformatics pipeline should offer clear local installation and/or remote access instructions, ensuring a streamlined user experience and facilitating efficient deployment of essential tools. Installation instructions should include detailed configuration settings with clear expected outcomes, step-by-step lists, and verification methods for successful installation, along with troubleshooting guidance for common issues. If resources are available via a web application (e.g., Galaxy or Terra.Bio), clear instructions on how to access and utilize the pipeline through the web application should be provided.

**To verify adherence to this documentation practice:** The reviewer should check for a well-documented installation guide with clear, concise, and easy-to-follow step-by-step instructions, including system requirements, dependencies, and automated package management solutions, as well as information on software versioning.

#### 10f. Example Usage
_Do the authors include examples of how to use this pipeline?_

Documenting an example usage for public health bioinformatics pipeline provides researchers with practical guidance on how to effectively apply the tool in real-world scenarios, enhancing their understanding of its potential applications. This practice promotes successful integration of the pipeline into research workflows, ensuring that it is utilized to its full capacity and ultimately advancing public health outcomes. An example usage for a command-line interface (CLI) tool in public health bioinformatics might illustrate the required input data, command syntax, and expected output, providing a tangible demonstration of the tool's application. For instance, a tool analyzing genomic variants could have an example usage like:

```
Input files:
- sample.vcf (Variant Call Format file containing genomic variants)

Command:
$ analyze_variants.py -i sample.vcf -o output.txt -p population_data.csv

Output:
- output.txt (file containing the filtered and annotated genomic variants relevant to public health)
```

This example usage showcases the necessary input files, command options, and the output generated, helping researchers to better understand the tool's functionality and how to incorporate it into their own analyses.

**To adhear to this documentation practice:** Provide practical guidance by documenting an example usage for public health bioinformatics pipeline, offering researchers clear instructions on how to effectively apply the tool in real-world scenarios. Ensure that the example usage enhances researchers' understanding of the pipeline, facilitating successful integration into research workflows and maximizing its utility for advancing public health outcomes.

**To verify adherence to this documentation practice:** The reviewer should check for comprehensive documentation that includes an example usage, illustrating the required input data, command syntax, and expected output, enhancing researchers' understanding of the tool's potential applications.


