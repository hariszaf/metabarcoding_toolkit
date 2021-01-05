---
layout: page
title: How to run PEMA 
---

## Intro

To run PEMA you need either [Docker](https://www.docker.com/) or [Singularity](https://sylabs.io/docs/) on your computer environment. 

Singularity is the best choice especially when you are running on a HPC or a cloud environment. 


Once you have a virtualization environment set, you need to build the input directory for PEMA. Once this is ready, you will need to *mount* this directory from you local, physical machine into the container environment to allow PEMA to run. 

Here are the steps to do so! 

## Step 1: Prepare for running PEMA

Let us call the directory about to mount into the PEMA container `my_analysis`. 

PEMA needs two **madatory** input entries that **must** be included in the `my_analysis` directory: 

* a `mydata` folder including **only** the paired-end `.fastq.gz` files. If there is any README file there you need to **remove it** otherwise PEMA will return an error.

* the `parameters.tsv` file


Optionally, you might also include: 
* a `metadata.csv` file
* a `phyloseq_in_PEMA.R` script
* a `custom_ref_db` folder 

according to the needs of your analysis. 

> Here are some hints and tips about the aforementioned input data. 


### The `mydata` directory

The *name* of this file needs to be **always** as shown!
Otherwise, PEMA will return you an error.

You need to provide **paired-end `.fastq.gz` files**. Notice that your files need to be compressed. 

Furthermore, your files **have to be 

It is essential for PEMA to keep the names of the aforementioned folders and files **exactly** as they are. 

Furthermore, your files need to follow a certain format; the ENA format.

What does that mean to you? 

In the `parameters.tsv` file (see below for more) there is an option called `EnaData`. 

If your samples are already in the [ENA database](https://www.ebi.ac.uk/ena/browser/home) and you are using sequence files from there you might set this parameter to `Yes` and you are ready to go. 

Otherwise, and most likely, you need to make sure that the filenames of your sequence files have the **exact** following suffixes: 
* forward read:   `_R1_001.fastq.gz`
* reverese reads: `_R2_001.fastq.gz`

Then, you need to set the `EnaData` parameter to `No` and PEMA will make a convertion to your files and it will return a directory called `initial_data` with your own data and a `mapping_files_for_PEMA.tsv` with the new names of the files PEMA built and their corresponding names from your data.

### The `parameters.tsv` file

Like in the case of the `mydata` folder, the `parameters.tsv` file needs to **always keep its name like that**. 

> This file is rather important as it allows you to ask for PEMA exactly what you need. You may run several runs to tune the parameters included there to get the best results possible. 

In each PEMA version it is quite possible that new parameters have been added so a good practice is to always get the corresponding `parameters.tsv` file from the PEMA GitHub repo. 

As there is a great number of parameters you will be asked to fill, it is always a good practice to check on the documentation of each algorithm you are about to choose. Links to these documentation pages can be found in the `parameters.tsv` file. 


Here is an overview of the PEMA modules
![Alte text](public/pema_in_a_nutshell.jpeg)



### The `phyloseq_in_PEMA.R` script

This scirpt is an optional input file for the case that you want to run any analyses after getting the final table with the taxonomy assigned sequences and their relative abundance in each sample 


## Step 2: Running PEMA




## Step 3: PEMA output