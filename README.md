# Understanding Emission Profiles


[![DOI](https://zenodo.org/badge/433461032.svg)](https://zenodo.org/badge/latestdoi/433461032)


Companion repository for the paper: 

 **Whose house is on fire? Identifying socio-demographic and housing characteristics driving differences in the UK household CO2 emissions**

*Antonia Schuster, Michael Lindner, Ilona M. Otto*

## Data set

We use the Understanding Society dataset, Wave 9, available only here: https://www.understandingsociety.ac.uk/documentation/data-releases.

In order for the code to work, the datafiles `i_hhresp.sav` and `i_indresp.sav` are needed. The suffix `i_` denotes Wave 9 of the survey. The file `hhresp` contains substantive data from responding households, while `indresp` contains substantive data for responding adults (16+), incl. proxies. Both datafiles should be downloaded in the `.sav` format and placed in the project directory within the folder `data/raw/`


## Repository structure

The repository is structured as follows:

```
.
├── data
│    └── raw
│         ├── i_hhresp.sav (save to this location)
│         ├── i_indresp.sav 
│         └── ...
├── plots
├── renv
└── src
```

* `data` contains preprocessed data frames and survey, the subfolder `raw` contains energy prices and CO2 conversion factors. The downloaded survey data should be place here as well.
* `plots` holds the figures used in the publication
* `src` holds `.Rmd` files for reproducing our analysis, and `.html` files that render code, output and results in an easily accesible format.


If you want to familiarize yourself with the code we recommend starting by viewing the `.html` files in `src` in a web browser.

## Preliminaries: Version control

For exact reproducibility of our results we use the package manager `renv` to keep track of the versions of all packages used in a so called lockfile.

To reproduce our analysis, install `renv` then use `renv::activate()` to activate the environment specified in the lockfile. You might have to use `renv::hydrate()` to install required packages as well. Afterwards you can run the R code as you would normally do.

You can call `renv::project()` and ``renv::status()` to check whether the correct project is activated and whether it is synchronized with the lockfile.

## Preliminaries: Working directory

All scripts assume that the working directory of your R session is the root directory of this repository. If you are using Rmarkdown and knitr you might need to change the working directory in a setup cell with the command:
```
knitr::opts_knit$set(root.dir = "PATH_TO_DIR")
```
Where `PATH_TO_DIR` might either be an absolute file system path, or a path relative to your default working directory. If you are using RStudio you might also want to change your default working directory if is not set correctly.

## Prelimnaries: R version

All scripts have been tested with R version 4.1.0. If you are should be seeing unexpected behaviour with another R version, try switching.
