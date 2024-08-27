# Protocol Guidelines

If you complete this module as part of an official practical in the BioMeDS group at the University of Würzburg (typically a master f1 practical in Biosciences or similar), you need to write a protocol as part of your examination.

Here, we provide some guidelines to write your protocol, because bioinformatics protocols in general and the protocol for this onboarding module in particular differ from standard protocols in other disciplines.

## General hints

- include what's necessary, but keep the protocol concise — there is no page limit (in neither direction)
- use the standard structure:
    - Introduction
    - Material and Methods (MM)
    - Results
    - Discussion
- some things that belong to MM in other disciplines are Results in bioinformatics (e.g. if the purpos of your work is the development of an analysis pipeline, the final pipeline is a result)
- in the introduction, almost every statement needs a reference
- in MM cite all software and packages with version number, cite the package as requested by the authors (if applicable), else look for a publication, unless available reference the website
- source code should
  - only be included in the main text, if it contains an essential innovation (e.g. an algorithm you developed, or the high-level steps of the analysis pipeline you designed)
  - other code can be shown in the appendix (if you specifically reference some of it) 
  - irrespective of the amount of code included in the document, a git repository with all the code should additionally be provided

## Specific hints

In this onboarding base module, the main goal was to learn and apply computational techniques but also generic methods regarding project structure, version control, documentation, etc.
The aim of the protocol is also more on training, how to write a bioniformatics protocol, rather than documenting your learning step-by-step.

Therefore, try to frame it as a biologically motivated story:
You want to analyze the spatial expression pattern of certain genes in the mouse brain. Specifically, you want to know the number of cells and the count for each gene per field of view. In order to achieve that, you need to develop an analysis pipeline for a public in-situ sequencing dataset.

Think of some potential underlying biological question, why you might want to know the spatial expression pattern of these genes. You can make something up here, it does not need to match the specific selection of genes.

The content of the separate sections could be roughly as follows:
- **Introduction**: Give the reader enough biological background to understand the motivation and aim for this project. What is the biological system? What is the experimental methods? What kind of data do you have available? What is your specific goal, addressed in the remainder of the protocol?
- **Material and Methods**: Describe the dataset. List the used software and packages with version numbers, briefly mentioning the purpose of each. If you use specific generic algorithms or measures (e.g. gaussian filter, morphological closing, Otsu threshold) briefly describe and cite them here.
- **Results**: The computational steps to count nuclei and detect and decode spots are part of your results. So describe these steps (show relevant code if necessary) and the results (e.g. the mean number of cells per fov or a histogram of cells per fov). Describe the expression pattern of the genes across fovs (you can use text, figures, images, tables)
- **Discussion**: Reflect on how well your pipeline is doing, is it detecting all the spots, does it decode most of the spots, ...? How can it be further improved? Is there anything notable in the expression pattern of the genes? How might this relate to your (made-up) biological question?

Don't stick too strictly to these suggestions. This module is framed qutie openly, so you might have done different kinds of analyses or focused on a certain part. Your protocol should reflect that.