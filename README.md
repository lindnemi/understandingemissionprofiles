# Understanding Emission Profiles

Companion repository for the paper: 

Shame on you? Identifying socio-demographic and housing characteristics driving differences in the UK household $CO_2$ emissions

Antonia Schuster, Michael Lindner, Ilona M. Otto

# Data set

We use the Understanding Society dataset, Wave 9, available only here: https://www.understandingsociety.ac.uk/documentation/data-releases.

In order for the code to work, the datafiles `i_hhresp.sav` and `i_indresp.sav` are needed. The suffix `i_` denotes Wave 9 of the survey. The file `hhresp` contains substantive data from responding households, while `indresp` contains substantive data for responding adults (16+), incl. proxies. Both datafiles should be downloaded in the `.sav` format and placed in the project directory within the folder `data/raw/`


# Repository structure

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


If you want to familiarize yourself with the code we recommend starting with the `.html` files in `src`.

# Preliminaries: Version control

For exact reproducibility of our results we use the package manager `renv` to keep track of the versions of all packages used.

To reproduce our analysis, install `renv` then use `renv::activate()` to activate the environment specified in the lockfile. You might have to use `renv::hydrate()` to install all required packages as well. Afterwards you can run the R code as you would normally do.
