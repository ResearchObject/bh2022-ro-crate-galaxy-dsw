---
title: 'BioHackEU22 Report: Enhancing Research Data Management in Galaxy and Data Stewardship Wizard by utilising RO-Crates'
title_short: 'BioHackEU22 #10: RDM in Galaxy and DSW w/ RO-Crate'
tags:
  - workflow
  - Galaxy
  - RO-Crate
  - Data Management Plan
  - DMP
authors:
  - name: Ignacio Eguinoa
    orcid: 0000-0002-6190-122X
    affiliation: 1
  - name: Marek Suchánek 
    orcid: 0000-0001-7525-9218
    affiliation: 2
  - name: Vojtěch Knaisl
    orcid: 0000-0003-0103-8468
    affiliation: 2
  - name: Jan Slifka
    orcid: 0000-0002-4941-0575
    affiliation: 2
  - name: Paul De Geest
    orcid: 0000-0002-8940-4946
    affiliation: 1
  - name: Bjorn Gruning
#  - name: Nicola Soranzo
#  - name: Vojtech Knaisl
#  - name: Jan Slifka
#  - name: David Salgado
#  - name: David López
  - name: Simone Leo
    affiliation: 17
    orcid: 0000-0001-8271-5429
#  - name: Alban Gaignard
#  - name: Paulette Lieby
  - name: Stian Soiland-Reyes
    affiliation: [15, 16]
    orcid: 0000-0001-9842-9718
affiliations:
  - name: VIB-UGent Center for Plant Systems Biology, BE
    index: 1
  - name: Czech Technical University in Prague, Prague, CZ 
    index: 2
  - name: Department of Computer Science, The University of Manchester, Manchester, UK
    index: 15
  - name: Informatics Institute, University of Amsterdam, Amsterdam, NL
    index: 16
  - name: Center for Advanced Studies, Research and Development in Sardinia (CRS4), Pula (CA), IT
  - index: 17
date: 11 November 2022
cito-bibliography: paper.bib
event: BH22EU
biohackathon_name: "BioHackathon Europe 2022"
biohackathon_url:   "https://biohackathon-europe.org/"
biohackathon_location: "Paris, France, 2022"
group: '#10: Enhance RDM in Galaxy and DSW by utilising RO-Crates'
# URL to project git repo --- should contain the actual paper.md:
git_url: https://github.com/ResearchObject/bh2022-ro-crate-galaxy-dsw
# This is the short authors description that is used at the
# bottom of the generated paper (typically the first two authors):
authors_short: Ignacio Eguinoa, Marek Suchánek \emph{et al.}
---

# Background

[RO-Crate] [@citesAsDataSource:10.3233/ds-210053] is a generic packaging format containing datasets and their description using standards for FAIR Linked Data. Based on rich schema.org metadata, such datasets can be interpreted as workflow definitions, datasets, data associated with workflow invocations, inputs, outputs, etc.

The Galaxy workflow framework [@citesAsDataSource:10.1093/nar/gky379] is handling all of those objects and supports users in the daily RDM. Integrating RO-Crate deeply into Galaxy and offering import and export options of various Galaxy objects as Research Objects will greatly standardize and improve the RDM in Galaxy and smoothen the UX as well as improving interoperability with other systems.

The low hanging fruit of this proposal is to add support for import/export of RO-Crates following its Workflow profiles [@usesMethodIn:10.3897/rio.8.e95164]. Those Crates should contain as much metadata as the Galaxy framework can provide. This includes workflow metadata such as Licence, Creator, CWL-abstract description, workflow history, contextually also references (DOIs, bio.tool IDs), EDAM terms, and formats of inputs/outputs of data processing of each step of the workflow.

Exports of History and Workflow Invocations need work on the corresponding RO-Crate profile and on the Galaxy codebase. RO-Crates already can be visualized, this would add a human-readable HTML rendering of the Galaxy export and metadata. Close collaboration between RO-Crate and Galaxy developers will speed up this development; the groundwork could be completed during the Biohackathon so that both Crates will be supported by the Galaxy 23.01 release.

Data Stewardship Wizard (DSW) [@citesAsDataSource:10.5334/dsj-2019-059] is a tool for data management planning with focus on FAIR metrics, proper guidance and integration with other tools in the data stewardship domain. Thus, similarly to utilising RO-Crates in Galaxy, the import and export functionality would be highly beneficial for DSW in terms of promoting interoperability and FAIRness in general. Existing RO-Crates can be used to pre-fill specific parts of DMPs, and vice versa, RO-Crates can be created or initiated from a DMP. Such support of RO-Crates in DSW can lay a foundation for closer integration with Galaxy and potentially other ELIXIR Tools platform components.

This project benefitted largely from collaborations with other Biohackathon projects such as “#25: Scientific and technical enhancement of bioinformatics software metadata using the Tools Ecosystem open infrastructure” as they are also leveraging workflow and software metadata from the same resources,  “#22: Plant data exchange and standard interoperability” which are combining the standards MIAPPE, ISA and RO-Crate for describing plant studies and data, 

# Ambitions

_From Wed Slide_

## Updated aims

* Include improved import flow in DSW
* Plan the implementation of RO-Crate import in Galaxy.
* Implement exporting of a detailed workflow execution from Galaxy.


## Progress

* Work on the automated build pipeline for runcrate ( @Simone (remote participant)
* DSW RO-Crate mapped, export & import: project metadata, dataset metadata will follow
* Possible implementations for RO-Crate import @all
* Progress on exporting feature. @Paul and @David

# Help

Use cases: Anyone making use of RO-Crate that wants them to be imported into Galaxy and DSW.

Offtopic:
- Helm Chart (for DSW)
- DSW UI Translations

## runcrate

## Provenance export of workflow runs from Galaxy

## RO-Crate in DSW

- Mapping
- Thoughts on import/generation

## Importing RO-Crate in Galxay



# Citation Typing Ontology annotation

You can use CiTO annotations, as explained in [this BioHackathon Europe 2021 write up](https://raw.githubusercontent.com/biohackrxiv/bhxiv-metadata/main/doc/elixir_biohackathon2021/paper.md) and [this CiTO Pilot](https://www.biomedcentral.com/collections/cito).
Using this template, you can cite an article and indicate why we cite that article about DisGeNET-RDF [@citesAsAuthority:Queralt2016].


Some citations we may want to add to text: 

* RO-Crate progress [@extends:10.3897/rio.8.e93937]
* Galaxy/CWFR [@citesAsRecommendedReading:10.1162/dint_a_00136]
* Software management plans [@citesAsRecommendedReading:10.3897/rio.8.e94608]
* DSW at BH2020 [@extends:10.37044/osf.io/9mnkb]

# Results


# Discussion

...

## Acknowledgements

We acknowledge funding from European Commission under contracts [824087](https://doi.org/10.3030/824087) (EOSC-Life), [101046203](https://doi.org/10.3030/101046203) (BY-COVID), [101057388](https://doi.org/10.3030/101057388) (EuroScienceGateway). The Biohackathon was supported by [ELIXIR](https://elixir-europe.org/), the research infrastructure for life-science data.  The operation and development of Data Stewardship Wizard is supported by ELIXIR CZ research infrastructure (MŠMT Grant No.: [LM2018131](https://starfos.tacr.cz/en/project/LM2018131)).

## References
