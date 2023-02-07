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
    orcid: 0000-0002-3079-6586
    affiliation: 6
#  - name: Nicola Soranzo
#  - name: Vojtech Knaisl
#  - name: Jan Slifka
#  - name: David Salgado
  - name: David López
    orcid: 0000-0002-9541-3961
    affiliation: 7
  - name: Simone Leo
    affiliation: 5
    orcid: 0000-0001-8271-5429
#  - name: Alban Gaignard
#  - name: Paulette Lieby
  - name: Stian Soiland-Reyes
    affiliation: [3, 4]
    orcid: 0000-0001-9842-9718
affiliations:
  - name: VIB-UGent Center for Plant Systems Biology, BE
    index: 1
  - name: Czech Technical University in Prague, Prague, CZ 
    index: 2
  - name: Department of Computer Science, The University of Manchester, Manchester, UK
    index: 3
  - name: Informatics Institute, University of Amsterdam, Amsterdam, NL
    index: 4
  - name: Center for Advanced Studies, Research and Development in Sardinia (CRS4), Pula (CA), IT
  - index: 5
  - name: Albert-Ludwigs-Universität Freiburg, Galaxy Freiburg Team, Freiburg, DE
    index: 6
  - name: Department of Computer Science, University of Freiburg, Freiburg, DE 
    index: 7
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

_From Mon Slide_

## Aims

* Use RO-Crate to enhance Research Data Management for Galaxy workflows and Data Management Plans:
  - Export detailed workflow provenance 
  - Improve RO-Crate profile for execution details
  - Explore using RO-Crate for Data Stewardship Wizard (DSW)


## Expected outcomes

* FAIR export of Galaxy history 
* Prototype Galaxy import of RO-Crate
* Conceptually mapping DSW & RO-Crate
* Support RO-Crate import / export in DSW
* Analyze DSW-Galaxy integration possibilities
* First release of runcrate command line

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

# Outcomes

_From Friday slides_

- Moved the CWLProv converter to runcrate; configured package build and CI jobs. 
- Prototype implementation of a workflow run RO-Crate from Galaxy.
- Implementation plan for a general RO-Crate import module in Galaxy
- Clarified Workflow Run profile requirements for WfExS (#29) and Sapporo (#35)
- DSW can import/export basic RO-Crates as templates

## Participation 

- DSW team: Marek, Vojtěch, Jan, Paulette (virtual)
- Galaxy export implementation: Paul and David
- runcrate lead: Simone (virtual participant)
- The brains behind RO-Crate: Stian & RO-Crate community
- Thanks to teams Bioschemas (#5 #23 #25), workflow executions (#29 #35) Galaxy-CWL (#28) and MIAPPE (#22)!


## Future work

- Galaxy: Mature export prototype
- Galaxy: Prototype RO-Crate import
- DSW: express potential future actions (e.g. submitted Grants)
- Improve RO-Crate profile documentation – what is the thinking process for extending RO-Crate?
- runcrate: refactor, expand, document – use from wf engines 
- Started draft BioHackrXiv – but when to finish it??

## runcrate

[Workflow Run RO-Crate](https://www.researchobject.org/workflow-run-crate/profiles/) is a collection of [RO-Crate profiles](https://www.researchobject.org/ro-crate/profiles.html) for capturing the provenance of the execution of computational workflows. To drive the development of the profile's specification, particularly for what concerns the internal details of each task execution, the working group developed a Python tool to convert CWLProv research object bundles [@discusses:10.3233/ds-210053] into Workflow Run RO-Crates. This tool was initially implemented as a single `cwlprov_to_crate.py` script hosted in a subfolder of the [Workflow Run RO-Crate GitHub repository](https://github.com/ResearchObject/workflow-run-crate). Though equipped with a command line interface and unit tests, the tool lacked a proper build setup and automated tests execution. Additionally, we wanted it to be ready for expansion into a generic software toolkit to manipulate Workflow Run RO-Crates, including the upcoming Galaxy history conversion feature.

Part of the work in this project consisted of turning the `cwlprov_to_crate.py` standalone script into a properly maintained Python package called `runcrate`. We created the [runcrate repository](https://github.com/ResearchObject/runcrate) and moved the code there, turning it into the `rocrate` package; added a modern build configuration using `pyproject.toml` and `setup.cfg`; added a [Sphinx](https://www.sphinx-doc.org/en/master/)-based documentation setup; configured multiple [tox](https://tox.wiki/en/latest/) environments for linting, testing, building the package and the docs; configured a GitHub CI workflow to run the tox in multiple environments.


## Provenance export of workflow runs from Galaxy

The prototype workflow provenance export [feature](https://github.com/galaxyproject/galaxy/pull/15101) in Galaxy implements the [Workflow Run Crate Profile](https://www.researchobject.org/workflow-run-crate/profiles/workflow_run_crate) while including the individual steps in preparation for lifting the export to the more detailed [Provenance Run Crate Proile](https://www.researchobject.org/workflow-run-crate/profiles/provenance_run_crate). Additionally, the export feature includes Galaxy specific workflow attributes such as [dataset collections}(https://training.galaxyproject.org/training-material/topics/galaxy-interface/tutorials/collections/tutorial.html) and [workflow parameters](https://training.galaxyproject.org/training-material/topics/galaxy-interface/tutorials/workflow-parameters/tutorial.html). Finally, this work also included setting up the necessary unit -, API - and integration tests.

## RO-Crate in DSW

- Mapping
- Thoughts on import/generation

## Importing RO-Crate in Galaxy

The proposed implementation plan for a general RO-Crate import module in Galaxy consists of four parts: 1) Drag and Drop functionality for ro-crate's to be imported in Galaxy's GUI; 2) Detection of workflows and/or datasets and decide what to do with them; 3) Detect file types (fastq, images, txt, etc); 4) Allow the user to organise detected files within Galaxy's GUI.

Questions that still need to be solved include: which datasets should be included in the import? Which datatypes do we allow (and do we validate filetypes)? Do we allow for multiple (nested) workflows and workflow runs to be imported? Do we preserve the RO-crate ID's? How do we account for missing tools in Galaxy?  

Due to these types of issues we propose an optional guidance or hint file to inform Galaxy, via the [Galaxy rule-builder](https://training.galaxyproject.org/training-material/topics/galaxy-interface/tutorials/upload-rules/tutorial.html), how to organize the RO-crate's metadata (and data). Alternatively, [Gsuite](https://github.com/gtrack) and [fairtracks](https://github.com/fairtracks/fairtracks_standard) could represent and organize the RO-crate metadata. In this case we would need some kind of conversion for Galaxy tools to be able to use this metadata.


# Citation Typing Ontology annotation

You can use CiTO annotations, as explained in [this BioHackathon Europe 2021 write up](https://raw.githubusercontent.com/biohackrxiv/bhxiv-metadata/main/doc/elixir_biohackathon2021/paper.md) and [this CiTO Pilot](https://www.biomedcentral.com/collections/cito).
Using this template, you can cite an article and indicate why we cite that article about DisGeNET-RDF [@citesAsAuthority:Queralt2016].


Some citations we may want to add to text: 

* RO-Crate progress [@extends:10.3897/rio.8.e93937]
* Galaxy/CWFR [@citesAsRecommendedReading:10.1162/dint_a_00136]
* Software management plans [@citesAsRecommendedReading:10.3897/rio.8.e94608]
* DSW at BH2020 [@extends:10.37044/osf.io/9mnkb]


# Discussion

...

## Acknowledgements

We acknowledge funding from European Commission under contracts [824087](https://doi.org/10.3030/824087) (EOSC-Life), [101046203](https://doi.org/10.3030/101046203) (BY-COVID), [101057388](https://doi.org/10.3030/101057388) (EuroScienceGateway). The Biohackathon was supported by [ELIXIR](https://elixir-europe.org/), the research infrastructure for life-science data.  The operation and development of Data Stewardship Wizard is supported by ELIXIR CZ research infrastructure (MŠMT Grant No.: [LM2018131](https://starfos.tacr.cz/en/project/LM2018131)).

## References
