# onboarding-base-module

A certain organization and structure is important in order to work cleanly. To help with this, there is this onboarding, which is intended to convey the following basic concepts:

- **I**ntegrated **D**evelopment **E**nvironment (IDE)
- Project directory structure (group specific)
- Version control with [git](https://git-scm.com/)
- Documentation
- Code environments

Essentially, this workflow should be applied:

```mermaid
    graph LR
        id1(Working on project) ---> id2(Push to git)
        id2 ---> id3(Update documentation)
        id3 ---> id1
        id3 -.-> id2
```
The [Python](https://www.python.org/) programming language is used for this onboarding.

### Tasks
#### 1. Read through the instruction repository and understand the task
T O   D O

#### 2. Install the IDE [Visual Studio Code](https://code.visualstudio.com/)
It is advisable to use an IDE, as these have useful features such as debugging or autocompletion in the editor as well as version control. They can also indicate potential errors in the code. Things like this are especially useful when you are just starting out with programming. More information about IDEs can be found in the [CCTB Wiki](http://10.87.174.31/mediawiki/index.php/Beginner%27s_Guide_to_Programming#Integrated_Developer_Environments). For this onboarding the use of the IDE "Visual Studio Code" (VS Code) is recommended. A short tutorial about the download and installation can also be found in the [CCTB Wiki](http://10.87.174.31/mediawiki/index.php/Beginner%27s_Guide_to_Programming#Download_.26_Installation_2).

#### 3. Install the VS Code Extension "Jupyter" for Jupyer Notebook support
The use of the Jupyter extension in VS Code combines the versatility of both "VS Code" and "Jupyter Notebook"

#### 4. Create a repository based on the basic structure provided
| Folder | Explanation |
| -------- | -------- |
| data     | Your data is stored here     |
| code     | Your code is stored here     |
| communication     | Any images/posters etc. that can be used for publications and such are stored here     |
| results     | Your results are stored here. This included your results and end results     |

#### 5. Start using git on your project
To start using git, open your Terminal (Linux) or your Command prompt (Windows) and go to your repository. For this you can use ```cd PATH```. Then write ```git init```and hit enter. This initializes the use of git in the repository. To add files to git you have to use the command ```git add FILE``` and to commit the files that were added you have to use the command ```git commit -m "MESSAGE"```, where "MESSAGE" should be a short message about what you commited or what updates you did. If you want to check what files have been added or what changes were made you can use ```git status```. A history of commits can be found via ```git log```.

#### 6. Create a README for your project and write a short introduction
T O   D O

#### 7. Download the data provided by this [realistic dataset](https://www.ebi.ac.uk/biostudies/bioimages/studies/S-BSST700)
T O   D O

#### 8. Use ```.gitignore``` on the downloaded data to prevent it from being committed to git
Create a file called ```.gitignore``` and input the names/paths of files and/or folders that should not be included in the git commit. This ```.gitignore``` file has to be in your repository.

#### 9. Update your README with details about the data
T O   D O

#### 10. Inspect the data visually using ***program***
T O   D O

#### 11. Install [mamba](https://mamba.readthedocs.io/en/latest/installation/mamba-installation.html) (mamba - miniforge)
T O   D O

#### 12. Create the project environment and install the required packages. Create the `environment.yml` with the content below as reference.

```yml
dependencies:
  - numpy
  - pandas=2.0.1
```
For this base module you need the packages ```matplotlib``` in version 3.1 and ```scikit-image```.

#### 13. Create a figure that incorporates all runs (c1 - c4) as subplots.
T O   D O
