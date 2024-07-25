# Onboarding - base module

![undraw_setup_wizard_re_nday](https://github.com/BioMeDS/onboarding-base-module/assets/7403236/6df4da84-8292-43e1-a0f6-ed1b148d1308)


> [!CAUTION]  
> This onboarding base module is still a work in progress, so if you notice any errors or have any suggestions, please report them [here](https://github.com/BioMeDS/onboarding-base-module/issues) via a Github issue ([Guide](https://docs.github.com/en/issues/tracking-your-work-with-issues/creating-an-issue)).

In bioinformatic projects, beside the work on the subject, a certain organization and structure is important in order to make sure that the work is correct, reproducible, and reusable. This onboarding material guides you through a realistic project. You will analyse an in-situ sequencing dataset using the python programming language, while using tools that help following these basic principles:

- Organizing projects in a standard directory structure (group specific)
- Documentation of your work (README files and literate programming ([jupyter](https://jupyter.org/)))
- Keeping track of your work with version control ([git](https://git-scm.com/))
- Using an **I**ntegrated **D**evelopment **E**nvironment (IDE, [Visual Studio Code](https://code.visualstudio.com/))
- Creating project specific code environments ([mamba](https://mamba.readthedocs.io/en/latest/))

The general workflow consists of alternating steps of work on the project (mostly writing and executing code) and documentation.
After each logical step, the progress is committed to version control.

```mermaid
    graph LR;
        id1(Work on project) ---> id2(Commit to git)
        id2 ---> id3(Update documentation)
        id3 ---> id4(Commit to git)
        id4 ---> id1
```
The [Python](https://www.python.org/) programming language is used for this onboarding. The basics of Python are conveyed in this [course](https://github.com/SchardtS/PythonLectures) (provided by Prof. Dr. Sabine Fischer).

> [!TIP]
> If you encounter problems and cannot find any help on the linked pages, it is always wise to google your problem or look at sites such as [Stackoverflow](https://stackoverflow.com/) or [Reddit](https://www.reddit.com/). You can also try asking [ChatGPT](chat.openai.com). If you still have trouble finding a solution to your problem or if you don't understand the solution you found ask your supervisor.

### Biological background

The final goal of the analysis is to determine the spatial localization of transcripts from 50 genes within the mouse brain. 
For this purpose, a published in-situ sequencing (ISS) dataset is used, that utilizes barcodes with four rounds of sequencing.
This dataset has been used to develop a method for ISS barcode decoding, called [PoSTcode](https://www.biorxiv.org/content/10.1101/2021.10.12.464086v1.full).

### Tasks

#### 1. Read through the steps of the base module and understand your tasks

The overall task, determining spatial localization of transcripts, is broken down into sub-tasks.

#### 2. Install the IDE [Visual Studio Code](https://code.visualstudio.com/)

It is advisable to use an IDE, as these have useful features such as debugging or autocompletion in the editor as well as version control. They can also indicate potential errors in the code. Things like this are especially useful when you are just starting out with programming. More information about IDEs can be found in the [CCTB Wiki](http://10.87.174.31/mediawiki/index.php/Beginner%27s_Guide_to_Programming#Integrated_Developer_Environments). For this onboarding the use of the IDE "Visual Studio Code" (VS Code) is recommended. A short tutorial about the download and installation can also be found in the [CCTB Wiki](http://10.87.174.31/mediawiki/index.php/Beginner%27s_Guide_to_Programming#Download_.26_Installation_2).

#### 3. Install the VS Code Extension "Jupyter" for Jupyter Notebook support
The use of the Jupyter extension in VS Code combines the versatility of both "VS Code" and "Jupyter Notebook". 

#### 4. Create a repository
On your computer, create a folder for this base module. In this folder, create the subfolders listed in the following table.

| Folder | Explanation |
| -------- | -------- |
| data     | Your data is stored here     |
| code     | Your code is stored here     |
| communication     | Any images/posters etc. that can be used for publications and such are stored here     |
| results     | Your results are stored here. This includes your results and end results     |

This repository will be synchronized with a remote repository (e.g. on GitHub), later on.

#### 5. Start using git on your project
Version control of your directory and your code is possible with the help of git. VS Code has built-in version control and its functionality is explained in this [guide](https://code.visualstudio.com/docs/sourcecontrol/intro-to-git). However, before version control with git is possible, it must first be installed if you are using Windows. Click [here](https://git-scm.com/downloads) to go to the git download page.

#### 6. Create a README
Create a fille called README.md or README.txt for your project and write a short introduction. This README is used to explain what you're doing so others can understand your repository and approach to the tasks.

#### 7. Download the data provided by this [realistic dataset](https://www.ebi.ac.uk/biostudies/bioimages/studies/S-BSST700)
The dataset consists of 171 selected tiles from the right hemisphere of a mouse brain. Each tile has the dimensions 1000x1000 pixels and contains 6 imaging channels (nuclei channel, anchor channel and 4 coding channels) in which different markers were used. For each tile 4 sequencing rounds were performed.

To download all of the files, you have to manually download each file on its own if you use Windows. On Linux you can download all files together using FTP. The dataset consists of the following files:

| File | Explanation |
| ---- | ----------- |
| channel_infos.csv | Relates each image channel to its corresponding code |
| taglist.csv | Codebook of barcodes used in the experiment |
| tile_names.csv | Names (coordinates) of selected tiles |
| selected_tiles_map.png | Map of selected tiles |
| selected-tiles.zip | Registered tif images of selected tiles |
| decoding.zip | Decoding of the selected ISS tiles via different methods |

The files can then be unpacked. This should be done for the selected tiles in particular.

#### 8. Use ```.gitignore``` on the downloaded data to prevent it from being committed to git
Create a file called ```.gitignore``` and input the names/paths of files and/or folders that should not be included in the git commit. This ```.gitignore``` file has to be in your repository.

#### 9. Update your README with details about the data
Like mentioned in *6. Create a README* you should explain everything so others can understand it. Include information about your data. What is the data? What files are used? What does the data mean? and so on.

#### 10. Inspect the data visually
Now that you handled most of the organizational stuff of this base module you can finally have a look at the downloaded data. Use some image files and have a look at them in a standard image viewer on your Computer.

#### 11. Install Mamba
To start using python to analyse and visualize the data, you must first install Mamba. Mamba is a package manager that enables easy installation and handling of needed packages. Use this [link](https://github.com/conda-forge/miniforge?tab=readme-ov-file#miniforge3) to install Miniforge3 (Mamba).

#### 12. Create the project environment and install the required packages. 
Once Miniforge3 (Mamba) is installed you have to create a project environment. Create a `environment.yml` file first with the content below as reference.

```yml
dependencies:
  - numpy
  - pandas=2.0.1
```
For this base module you need the latest version of python as well as the packages ```matplotlib```, ```scikit-image``` and ```ipykernel```.

With the command ```mamba env create -f environment.yml --name NAME``` (```NAME``` = How you want to call your environment) you can create your new mamba environment based on your .yml file. If you want to install each package individually, this works with the command ```mamba install PACKAGE``` (```PACKAGE``` = The name of the package). You can also install several packages at once by including them all in the ```mamba install``` command (separated by spaces). For example: ```mamba install numpy pandas=2.0.1```. With the command ```mamba remove PACKAGE``` packages can be removed.

> [!NOTE]
> Don't forget the workflow mentioned at the top of the base module!

---

#### 13. Create a figure that incorporates all runs (c1 - c4) of one tile as subplots.
Create two files: ```Analysis.ipynb``` and ```Functions.py```. When creating the ```.ipynb``` file in VS Code it wants you to select a kernel. Here you choose the environment you created in the previous task. The ```.ipynb``` file is where you write your code. Write your code as a function that can be used to analyse any given tile of the data. You can then save the function in the ```.py``` file so that you can also use it in other ```.ipynb``` files.

As this task is about image analysis, you can read more about that [here](https://haesleinhuepf.github.io/BioImageAnalysisNotebooks/intro.html).

##### 13.1. Plot one image
Plot the following file using matplotlib.pyplot: ```out_opt_flow_registered_X10_Y10_c01_DAPI.tif```
<details>
    <summary>Help</summary>
First you have to unpack the selected-tiles.zip. Then import the needed packages (skimage, matplotlib.pyplot, glob). Now you can plot one of the images. To do this, the image must first be saved in a variable using ski.io.imread("PATH/out_opt_flow_registered_X10_Y10_c01_DAPI.tif"). This variable can then be plotted with matplotlib.pyplot. An alternative to plotting with matplotlib.pyplot would be to display the image directly with ski.io.imshow("PATH/out_opt_flow_registered_X10_Y10_c01_DAPI.tif") instead of saving the image in a variable.
</details>

##### 13.2. Create a list of files
Load all X10_Y10 images into a list.
<details>
    <summary>Help</summary>
You can use glob.glob() to save all needed files in the selected-tiles folder in a variable. To import all X_10_Y10 images and only them you have to tell glob which files it has to save. You do this with glob.glob("PATH/out_opt_flow_registered_X10_Y10_*.tif"). This nomenclature with * tells glob, that it should look for all files that have the same name (before *). You can then iterate over all the files in the glob variable and use scikit-image (ski.io.imread()) to read in the files and save them in a list. 
</details>

##### 13.3. Plot a grid of images
Create a grid of all the X10_Y10 images so that they are arranged as follows:

| | | | | | |
| -------- | -------- | -------- | -------- | -------- | -------- |
| *_c01_Alexa_488.tif | *_c01_Alexa_568.tif | *_c01_Alexa_647.tif | *_c01_Atto_425.tif | *_c01_Atto_490LS.tif | *_c01_DAPI.tif |
| *_c02_Alexa_488.tif | *_c02_Alexa_568.tif | *_c02_Alexa_647.tif | *_c02_Atto_425.tif | *_c02_Atto_490LS.tif | *_c02_DAPI.tif |
| *_c03_Alexa_488.tif | *_c03_Alexa_568.tif | *_c03_Alexa_647.tif | *_c03_Atto_425.tif | *_c03_Atto_490LS.tif | *_c03_DAPI.tif |
| *_c04_Alexa_488.tif | *_c04_Alexa_568.tif | *_c04_Alexa_647.tif | *_c04_Atto_425.tif | *_c04_Atto_490LS.tif | *_c04_DAPI.tif |

<details>
    <summary>Help</summary>
    To do this, you need to use matplotlib.pyplot.subplots() and use a for loop to iterate over the list of images you created in 13.2. The example image was plottet using the following code (ignoring the names above the tiles):

```python
fig, axs = plt.subplots(4, 6, figsize=(25, 15))
for i, ax in enumerate(axs.flatten()):
    ax.imshow(image_array[i])
plt.show()
```

Where `image_array[]` is a list of image files that was created using ski.io.imread().
    
</details>

Example for tile X10 Y2:

![Example grid of tile X10 Y2](https://github.com/BioMeDS/onboarding-base-module/blob/main/x10y2_grid.png)

#### 14. Count the number of nuclei in each field of view (fov)

##### 14.1 Develop method on a single fov

Write a jupyter notebook to explore a single field of view.
- Which channel(s) is/are most promising for nucleus segmentation?
- Which methods can you use, to distinguish between nucleus and the rest?
- How can you devide the nuclei into separate instances?
- Which problems occur, how can they be addressed?

Beside the nucleus count, also create a diagnostic figure, that helps a human to see, whether your method worked or failed.
When you have a method that works well on your selected fov, try it on some other fovs

##### 14.2 Run your method on all fovs

Write a script that applies your method to all fovs.
Write the count per fov to a csv file and save the diagnostic plots as png files in a folder.


