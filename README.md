# pypsa-zm-data

This repository mainly hosts data required to run energy system planning scenarions for Zambia within [PyPSA-Earth](https://github.com/pypsa-meets-earth/pypsa-earth). Hence, it is not a standalone repository, and needs to be executed in conjunction with PyPSA-Earth.

 It also contains customised pieces of code to run those scenarios, instructions on how to run them, and validation notebooks for Zambia.

![d](image/README/1679077012057.png)

# Repository Structure

## `configs` folder

The `configs` folder contains `config.yaml's` for all scenarios. These are the option files that allow `pypsa-earth` to create model outputs.

## `data` folder

The `data` folder contains any extra data or data deletion requirements.

## `image` folder

The `image` folder contains all images used in this repository.

## `scripts` folder

The `scripts` folder contains the source code required to execute Snakemake rules that are specific for Zambia. The execution of these rules is controlled by the Snakefile `zm.smk` (see below).

## `validation` folder

The `validation` folder contains all the resources used to validate the PyPSA-Earth in Zambia. It is divided in two subfolders:

1. `notebooks` contains modified versions of the validation notebook template given in the [pypsa-earth/documentation](https://github.com/pypsa-meets-earth/documentation/tree/main/notebooks/validation) for Zambia.

2. `report` contains a report, written in paper format, of the model validation for Zambia. It is inspired in section 4 of the PyPSA-Earth paper ([Parzen et al. (2023)](https://doi.org/10.1016/j.apenergy.2023.121096)). For now, the most updated version of the report is stored in Overleaf, and can be edited through the following [link](https://www.overleaf.com/9955214172jymhghfymjrx). The version in this repository will be updated regularly from Overleaf.

Beyond the templates used, the validation of PyPSA-Earth in Zambia focuses on key features of the Zambian electricity system (e.g., hydro).

## Snakefile `zm.smk`

The Snakefile `zm.smk` defines the Snakemake rules that are specific for Zambia.

Note that the code to execute those rules should be stored in the `scripts` folder, and called as a script in the Snakefile `zm.smk`. 

# User Instructions

TBD. This [issue](https://github.com/pypsa-meets-earth/pypsa-zm-data/issues/1) needs to be solved/ tested.

# Acknowledgement

Both projects are funded by the Climate Compatible Growth for the following projects:

- [Macroeconomic implications of the Green Growth Strategy in Zambia](https://drive.google.com/file/d/1n9l50KhCGH4l07Kqsu1wiRGweubw0TYj/view?usp=sharing)
- [Energy System Chef – The energy system implications of transitions to clean cooking in Zambia](https://drive.google.com/file/d/1Sgr3NXm2F5gEFea_qEvJ-OWaNmSAjHMx/view?usp=sharing)
