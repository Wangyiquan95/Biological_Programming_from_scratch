# Guideline of Programming for Biologists

## Contents
* [1 Programming languages](#1-Programming-languages)   
* [2 Important envirnment management Software](#2-Important-envirnment-management-Software)   
* [3 Important packages](#3-Important-packages)   
* [4 Applications](#4-Applications)
* [5 Quick references](#5-quick-references)
* [6 Tools](#6-tools)

## 1 Programming languages
```
###---Main goal---###
Learn the basic usage of each language
- understand data types,variables,loop,
- learn to use terminal

Python Programming:
- Basics:
Variables, Data Types, and Operators
Control Flow (if statements, loops)
Functions and Modules
- Intermediate:
Lists, Dictionaries, and Sets
File Handling
Exception Handling
- Advanced:
Object-Oriented Programming (OOP)
Decorators and Generators
Virtual Environments

```
## Programming languages

- Python
- R
- shell


## Recommendation books and websites
```
I would highly recommend to read "Computing Skills for Biologists A Toolbox"
```
- Python Programming website (https://www.w3schools.com/python/python_variables.asp)
- R Programming Website (https://daviddalpiaz.github.io/appliedstats/introduction-to-r.html)
- [Computing Skills for Biologists A Toolbox](./text_book/Computing_Skills_for_Biologists_A_Toolbox.pdf)

## 2 Important envirnment management Softwares

```
###---Main goal---###
- learn to use programming supportive platform
- learn to manage environments and packages
- learn to version control
```
### 2-1 programming packages management Software

- Anaconda(https://www.anaconda.com/products/individual)
- learn to use conda (https://docs.conda.io/projects/conda/en/latest/user-guide/getting-started.html)

```
comments: anaconda is useful tool for  python packages and enviroments management
```
### 2-2 Integrated development environment(IDE) Software

- Pycharm (https://www.jetbrains.com/pycharm/)
- learn to create first project (https://www.jetbrains.com/help/pycharm/creating-and-running-your-first-python-project.html)
- learn to create conda env on pycharm (https://www.jetbrains.com/help/pycharm/conda-support-creating-conda-virtual-environment.html#conda-requirements)

```
comments: pycharm is a powerful IDE for different programming languages (support Python, R, etc.). It is used for code writing, testing and debugging.
```

### 2-3 Version control

- git and github (https://product.hubspot.com/blog/git-and-github-tutorial-for-beginners)
- add VS on Pycharm (https://www.jetbrains.com/help/pycharm/version-control-integration.html)

```
comments: verson control is extremely important since it will track all changes you made to the files
```
## 3 Common packages

```
###---Main goal---###
understand the main functions of each package
```
### 3-1 python packages

- Biopython (http://biopython.org/DIST/docs/tutorial/Tutorial.html)
- Pandas
- prody
- Igblast
- PyIR
- git
- snakemake
- numpy
- scikit-learn
- pytorch
- tensorflow


```
comments: 
#1 Biopython is super helpful package for biological application, so I highly recommend go throughly its tutorial
#2 I also provide some cheatsheets on the text_book file for assisting programming
```
### 3-2 R packages

- ggplot2 (http://www.sthda.com/english/wiki/ggplot2-essentials)
- dplyr
- ggpubr


## 4 Applications

```
###---Main goal---###
run and test some toy experiments
```
### 4-1 Bioinformatics
### 4-1-1 Deep Mutational Scanning analyses
- H3N2 NA antigenic region DMS (https://github.com/Wangyiquan95/NA_EPI)
### 4-1-2 NGS analyses
- H3N2 HA egg-passaging adaptation (https://github.com/Wangyiquan95/HA_egg_passage)
- SARS-CoV-2 cell culture-adaptive mutations (https://github.com/nicwulab/SARS-CoV-2_in_vitro_adaptation)
### 4-2 Machine learning
```
###---Main goal---###
- Fundamentals:
Supervised vs. Unsupervised Learning
Types of Machine Learning Algorithms (self-supervised, generative,etc)
Training and Testing Data
- Common Models:
Transformer
GPT
BERT
GNN
Difussion
- Evaluation and Optimization:
Metrics (Accuracy, Precision, Recall)
Wanb (Visualization)
Hyperparameter Tuning
```
- An explainable language model for antibody specificity prediction (https://github.com/Wangyiquan95/HA1)
- Deep learning model for antigen identification (https://github.com/nicwulab/SARS-CoV-2_Abs)
- H3N2 NA antigenic region DMS regression (https://github.com/Wangyiquan95/NA_EPI)

## 5 QUICK REFERENCES

### ssh connection
If you've never run `ssh` before, you will need to create a `.ssh` directory. Run

```bash
mkdir -p ~/.ssh && chmod 700 ~/.ssh
```
Create `config` inside `.ssh` directory by
```
touch ~/.ssh/config
chmod 600 ~/.ssh/config
```
Add server info into `config`
```
Host wulab
    HostName nicwulab-linux.life.illinois.edu
    User id
    Port 22
```
To log in to the server, in the terminal, run

```bash
ssh wulab
```
### move files 
To copy from your computer to a (remote) server. Run(Change the path accordingly)
```
scp ~/local/path id@nicwulab-linux.life.illinois.edu:/home/server/path
```
or download files from server. Run
```
scp -r id@nicwulab-linux.life.illinois.edu:/home/server/path ~/local/path
```
### install miniconda
Download [`miniconda`](https://docs.conda.io/en/latest/miniconda.html):
```bash
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
```
Install by 
```bash
bash Miniconda3-latest-Linux-x86_64.sh
```
Create new env by
```bash
conda create --name Env_name python=3.9
conda activate Env_name
```
Remove env by
```bash
conda remove --name myenv --all
```
Create new env using yml by
```bash
conda env create -f environment.yml
```
Save conda env as yml by
```bash
conda activate my_env
conda env export > path/to/environment.yml
```
### git
git init and connect to github repo by
```bash
git init 
git add README.md
git commit -m "README.md"
git branch -M main
git remote add origin <repository-url>
```
git remove files by
```bash
git rm --cached file.csv
git commit -m "Removed files"

git push -u <remote> <branch>
```
fetch and merge from github by
```bash
git fetch <remote>
git merge <remote>/<branch>
```
### jupyter lab/notebook
Connect to server and initialize juypter lab by
```bash
ssh wulab
jupyter notebook --no-browser --port=8080
jupyter lab --no-browser --port=8080
```
Open another local terminal and connect it by
```bash
ssh -N -L 8080:localhost:8080 id@nicwulab-linux.life.illinois.edu
```
Copy the Jupyter lab URL that appears, and paste it into your web browser.

## 6 Tools
coming soon ~
### local igblast
### Somatic Hypermutation(SHM) calling
### CDRH3 clustering
### Protein clustering
### PDB renumbering
### NGS data processing-1 (DMS)
### NGS data processing-2 (Genome)
### Language modeling
### Transfer learning
