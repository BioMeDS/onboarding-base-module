# Quantitative biomedical image analysis methods

- Course: 
- Student: 
- Supervisor: Markus Ankenbrand
- Start: 
- Duration: 4-8 weeks

## Motivation

Established transcriptomics techniques can be used to get insights into gene expression profiles of tissues or single cells.
Recent advances enable to further track the spatial localization and dynamics of transcripts at sub-cellular resolution [1].
Raw data of spatial transcriptomics experiments (e.g. in-situ-sequencing) are complex and diverse.
In order to extract biologically meaningful insights from this data, they need to be computationally processed.

## Current situation

Lots of different spatial transcriptomic methods exist [1].
All of them produce different raw data with their own ideosyncracies.
They each require specialized analysis approaches and tools.
Most of the computational method development efforts are scattered in different repositories and packages tackling specific sub-tasks.
An effort has been made by Axelrod et al. to develop `starfish`, a comprehensive toolset with a unified interface [2].
Sadly, development of that package has stalled since 2021, therefore it is incomplete and outdated.
In order to develop new approaches and consolidate existing ones, it is essential to understand basic image analysis techniques and how they are used in state of the art methods.

## Research aims

Learn and apply basic quantitative image analysis techniques for spatial transcriptomics on a publically available in-situ sequencing dataset from the mouse brain [3].
Beside the technical skills, also learn foundations and tools to work in a structured way, that promotes rigorous and reproducible research.

## Action

Getting familiar with (fluorescence microscopic) imaging data.
Learning how to use python and specialized packages to load, display, transform, and quantitatively analyze these images.

### Work plan

1. Work through the project description
2. Follow the steps of the [online onboarding repository](https://github.com/BioMeDS/onboarding-base-module/) [4]. This includes
   - setting up the project
   - acquiring the raw data
   - exploratory data analysis
   - counting nuclei
   - decoding transcripts
3. Upload the repository to [GitHub](https://github.com/), [GitLab](https://git.physik.uni-wuerzburg.de/) or [Codeberg](https://codeberg.org/) and share the repository (privately if you want) with Markus

### When are you successful?

1. You know how to properly setup a project (including folder structure, version control, compute environments)
2. You properly documented and version control all steps of your work
3. You have ideas how to further improve your code

## What could come next?

1. Detailed comparison with published decoding results
2. Analysis of cell heterogeneity and clustering into cell types
3. Visualization of spatial distribution of cell types
4. Differences in sub-cellular localization of transcripts

## Literature and Links

1. Moses and Pachter, (2022). *Museum of spatial transcriptomics*. Nat Methods 19, 534–546. https://doi.org/10.1038/s41592-022-01409-2
2. Axelrod et al., (2021). *starfish: scalable pipelines for image-based transcriptomics*. Journal of Open Source Software, 6(61), 2440, https://doi.org/10.21105/joss.02440
3. Gataric et al., (2021). *PoSTcode: Probabilistic image-based spatial transcriptomics decoder*. bioRxiv 2021.10.12.464086. https://doi.org/10.1101/2021.10.12.464086
4. https://github.com/BioMeDS/onboarding-base-module/
