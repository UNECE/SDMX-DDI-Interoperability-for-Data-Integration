# SDMX-DDI-Interoperability-for-Data-Integration
This activity is undertaken under the work programme of the High-Level Group for Modernisation of Official Statistics.
See original [activity proposal](https://unece.org/sites/default/files/2024-11/HLG2024%20ActivityProposal2025_SSG_Interoperability.pdf), which defines the scope of the work

## Use Cases
### [SDMX-CDI Dissemination Use Case](https://github.com/UNECE/SDMX-DDI-Interoperability-for-Data-Integration/raw/refs/heads/main/SDMX-CDI_DisseminationUseCase.docx)

### [Medadata-driven integration of dimensional data using DDI-CDI](https://github.com/UNECE/SDMX-DDI-Interoperability-for-Data-Integration/raw/refs/heads/main/Medadata-driven%20integration%20of%20dimensional%20data%20using%20DDI-CDI%20(19%20Feb%202025).docx) 

**Interoperability between SDMX to DDI-CDI - Work plan**

Concrete deliverables are centered on creating an automated data integration workflow using DDI-CDI as a central link. The primary deliverables is a set of mappings and Python scripts designed to automate the transformation of data from different source models into a unified DDI-CDI representation and vice-versa. 
These scripts will cover three specific use cases: 
1. A simplified "proto-SDMX" example
2. A full SDMX XML message from the ILO
3. An example using Google Data Commons's .mcf files (based on schema.org)

Accompanying these scripts, the working stream has produced a "DDI-CDI dimensional data integration profile" which is a subset of the full DDI-CDI classes and properties that are relevant for describing and integrating dimensional data. 

These files will serve as tangible examples of the desired DDI-CDI output for each use case, conforming to the specified DDI-CDI profile and extensions. Additionally, the project will deliver supporting documentation, including a summary document, a checklist of deliverables, and an analysis of open issues, priorities, and next steps. A key part of the work also involves identifying and brainstorming methods to codify the necessary data mappings and transformations

For more information see [Discussion on model elements and overall approach](https://docs.google.com/document/d/1t-K1CCdSJD5_Ch2LXWw6yoWZ9mEz6g0kKgP6ZSduBAc/edit?usp=sharing) and [DDI-CDI and other standards](https://docs.google.com/presentation/d/1IN9TMmocB7SPUDpPIUdtCcFODhwN9slJ/edit?usp=sharing&ouid=116774256385678898083&rtpof=true&sd=true).


###	[DDI Codebook to SDMX](https://github.com/UNECE/SDMX-DDI-Interoperability-for-Data-Integration/blob/9f96dfced17170d7cda4d2a0f7ccc45e1a4a2108/2025-03-27/DDI%20Codebook%20to%20SDMX%20(4th%20meeting%2027Mar).pdf)

**Interoperability between DDI Codebook to CDI**

- EOSC [Metadata Schema and Crosswalk Registry](https://faircore4eosc.eu/eosc-core-components/metadata-schema-and-crosswalk-registry-mscr) was not successful as it reported an error during the import of the DDI-CDI xsd file before to broke completely.
- Mapping elements for DDI-C to DDI-CDI can be found in these [two tables](https://ddi-alliance.atlassian.net/wiki/spaces/DDI4/pages/3862659092/DDI-to-DDI)
- Mapping of DDI Codebook metadata at the variable level which is suitable for producing DDI-CDI was embedded also in the [Python tools](https://github.com/DataArtifex/ddi-toolkit/blob/main/docs/copilot/codebook_to_cdif_mappings.md) developed by Pascal Heus, which were documented with Copilot, based on the [codebook_to_ddi methods](https://github.com/DataArtifex/ddi-toolkit/blob/main/src/dartfx/ddi/utils.py)
- DDI-Codebook [file](https://drive.google.com/file/d/1geLZunyiYHS4xcxeeHOL93X9_rDViE2v/view?usp=drive_link) developed by Knut Wenzig (DIW Berlin), with 2 files/datasets, each with 2 variables. One variable also has missing categories/codes.
The content was inspired by this working paper: [Publishing Fine-Grained Standardized Metadata – Lessons Learned from Three Research Data Centers - KonsortSWD](https://www.konsortswd.de/publikation/publishing-fine-grained-standardized-metadata/) This could be used with Pascals tool to produce DDI-CDI. Afterwards one would have the basis to present different snippets of DDI-C (like in the working paper above) and compare them with DDI-CDI an approach which seems to be more promising that finding 1 to 1 relations between the two standards’ elements.
- In this proof of concept by Denis, DDI codebook variables and data descriptions are transformed into SDMX structural metadata, from where SDMX mapping and target structure are used to drive an aggregation process. General study/survey information from the codebook is transferred to SDMX using a dedicated metadata structure definition, which includes also some additional information about processing. This was validated through an actual implementation to reproduce some official publications. [Video overview](https://www.youtube.com/watch?v=7Okhok4x8Tg)


### How to define mappings

**Problem statement**: [Metadata mappings for data integration](https://docs.google.com/presentation/d/15uUOylT5SLBb6oY3HfhJGM_vyMhpf325/edit?usp=sharing&ouid=116774256385678898083&rtpof=true&sd=true)

**Main proposal**: combined use of technical standards to meet different mapping needs.  This includes the use of RML to handle structural transformations (schema alignment and implicit identifiers) while SSSOM to handle semantic negotiation (value and unit alignment).

**Benefits**

- Bridges the structural gap: semantic mapping alone is insufficient for end-to-end data integration; distinguishing between "schema lifting" (RML) and "semantic alignment" (SSSOM).
- Enables machine-actionable ETL: By moving from procedural code to declarative mapping files, we pave the way for automated discovery and execution of cross-domain data integration pipelines.
- Promotes scalable interoperability: support of "data mesh" approach, allowing data providers to publish authoritative mappings that consumers can reuse, significantly reducing the manual effort required for integration.

- For more information see extensive report on [Metadata Mapping and Data Integration](https://docs.google.com/document/d/1Oz_jazfXRlqnu0D5el0TgNEQKyHhxUd2/edit?usp=drive_link&ouid=116774256385678898083&rtpof=true&sd=true)

- SDMX-XMLto DDI-CDI [structural mapping specification](https://docs.google.com/document/d/1JUXe4QiG2fbf7-2eOLKwvO1czdugp1ww/edit?usp=sharing&ouid=116774256385678898083&rtpof=true&sd=true)

## Past activities

## Presentations from the second call (20-2-2025)
- [SDMX 3 in relation to microdata, and gaps identified, focused on survey microdata](https://github.com/UNECE/SDMX-DDI-Interoperability-for-Data-Integration/raw/refs/heads/main/2025-02-20/New%20features%20in%20SDMX%203.0%20to%20support%20microdata.pptx) (30mins - Edgardo)
- [Variable cascade and microdata, at high-level](https://github.com/UNECE/SDMX-DDI-Interoperability-for-Data-Integration/raw/refs/heads/main/2025-02-20/Variable%20Cascade.pptx) (30mins - Dan)

## Presentations from the third call 6-3-2025)
-	[SDMX Content constraints](https://github.com/UNECE/SDMX-DDI-Interoperability-for-Data-Integration/raw/refs/heads/main/2025-03-06/SDMX%20ContentConstraints.pptx) (Edgardo)
-	[Use of concepts at different granularities in CDI] (conceptual variables, conceptual domains, etc.) (Dan)

## Fourth call (27-3-2025)
-	[DDI Codebook to SDMX](https://github.com/UNECE/SDMX-DDI-Interoperability-for-Data-Integration/blob/9f96dfced17170d7cda4d2a0f7ccc45e1a4a2108/2025-03-27/DDI%20Codebook%20to%20SDMX%20(4th%20meeting%2027Mar).pdf) (Edgardo)

## Fifth call (15-4-2025)
-	Data description in DDI-CDI (Flavio)

## Call 3-6-2025
-	Presentation "diagrams 2" (Luis)
-	Presentation "Recap and update" (Flavio)
-	CodeList mapping (Flavio)

## Call 26-6-2025
-	DDI products mappings (Wendy)
- Tentative SDMX-DDI fragment for data (Flavio)

## Call (8-7-2025)
-	[A proposal](https://github.com/UNECE/SDMX-DDI-Interoperability-for-Data-Integration/blob/9f96dfced17170d7cda4d2a0f7ccc45e1a4a2108/2025-07-08/SDMX-DDI%20contextual%20mapping.jpg) for attempting a mapping (Flavio)

## Presentation (29-09-2025) 
SDMX Global Conference: [Towards Practical Interoperability: Mapping SDMX and DDI for Data Integration](https://www.sdmx2025.org/plenary/SESSION_6/Session%206%20-%20Towards%20Practical%20Interoperability%20-%20Mapping%20SDMX%20and%20DDI%20for%20Data%20Integration%20%28F.%20Rizzolo%29.pdf)

## Dagstuhl workshops (9/21-11-2025)
- [2025 Metadata Models and Services Typologies in Digital Resource-Sharing Frameworks](https://ddi-alliance.atlassian.net/wiki/spaces/DDI4/pages/3837132888/2025+Metadata+Models+and+Services+Typologies+in+Digital+Resource-Sharing+Frameworks)

- [2025 The Provenance Chain: Connecting and Reusing Data, Models, and Experiments](https://ddi-alliance.atlassian.net/wiki/spaces/DDI4/pages/3837133351/2025+The+Provenance+Chain+Connecting+and+Reusing+Data+Models+and+Experiments)





