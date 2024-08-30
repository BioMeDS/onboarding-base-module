# Folder structure

Standard folder structure for data analysis projects in the BioMeDS group.

## Basic structure

This is the basic high level folder structure. All these folders can and should contain sensible sub-folders. If you have different experiments or sub-tasks, try to use consistent sub-folder structures for `data`, `code`, `results`, etc.

```
.
├── code                    ← all script and notebook files
├── data
│   ├── processed           ← any transformations of the raw data (scaling, normalization, ...)
│   └── raw                 ← raw data as received, read only
├── documents               ← abstracts, papers, posters, grant proposals, talks, ...
│   └── references          ← .bib file
├── envs                    ← compute environments (e.g. conda .yml or renv folder)
├── .git
├── .gitignore              ← used to exclude temporary files and large files
├── LICENCE                 ← defaults: data: CC0, documents/figures: CC-BY, code: MIT
├── README.md               ← high level documentation, links to analyses and summary of results
└── results
    ├── figures
    ├── final
    └── intermediate
```

## Extended structure

If you use tools for large data handling (datalad or dvc), containers (apptainer or docker), a workflow language (Snakemake), develop machine learning models or develop a software package (possibly with nbdev) as part of your project, the folder structure is extended accordingly

```
.
├── apptainer|docker         ← container definition (.def or Dockerfile) and image (.sif)
├── code
├── data
│   ├── processed
│   └── raw
├── .datalad|.dvc            ← handled by datalad or dvc
├── documents
│   ├── paper
│   ├── poster
│   └── references
├── envs
├── .git
├── .gitignore
├── LICENCE
├── <pkgname>                ← subfolder for your package
│   ├── doc
│   ├── src
│   └── tests
├── README
├── results
│   ├── figures
│   ├── final
│   ├── intermediate
│   └── models               ← exported model weights, code for loading the model in the `code` folder
└── workflow                 ← Snakefile(s) and config for Snakemake
    └── Snakefile

```