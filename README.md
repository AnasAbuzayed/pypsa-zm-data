# pypsa-zm-data

This repository mainly hosts data required to run energy system planning scenarions for Zambia within [PyPSA-Earth](https://github.com/pypsa-meets-earth/pypsa-earth). Hence, it is not a standalone repository, and needs to be executed in conjunction with PyPSA-Earth.

 It also contains customised pieces of code to run those scenarios, instructions on how to run them, and validation notebooks for Zambia.

# Model Execution

## Combining pypsa-earth and pypsa-zm-data repositories

The provided workflow builds on [PyPSA-Earth](https://github.com/pypsa-meets-earth/pypsa-earth). Therefore, first, the PyPSA-Earth repository must be forked and the fork should then be cloned. A fork can be created by navigating to the [PyPSA-Earth](https://github.com/pypsa-meets-earth/pypsa-earth) website. By clicking on the fork-symbol in the upper right corner, a fork is created and linked to the specific user.

Next, we also need to fork the [pypsa-zm-data](https://github.com/pypsa-meets-earth/pypsa-zm-data) repository. A fork can be created by navigating to the [pypsa-zm-data](https://github.com/pypsa-meets-earth/pypsa-zm-data) website and clicking the fork symbol in the upper right corner.

To clone both forks to the correct locations on a local machine, the following commands can be used using the local machines shell:
```bash
git clone https://github.com/<user-name>/pypsa-earth
```
`<user-name>` must be replaced with your personal github-username.

After that, one must change to the freshly created pypsa-earth repository.
```bash
cd pypsa-earth/
```
and repeat the cloning, this time for the pypsa-zm-data repository.
```bash
git clone https://github.com/<user-name>/pypsa-zm-data
```
Again, `<user-name>` must be replaced with your personal github-username. At the end of this process, the following folder structure should have been created (where `<user-name>` is your personal github-username):

- `../<user-name>/pypsa-earth` that contains the pypsa-earth repository.

- `../<user-name>/pypsa-earth/pypsa-zm-data` that contains the pypsa-zm-data repository. Note that this is inside the directory of the pypsa-earth repository.

In order to install the pypsa-earth environment, instructions are provided in the pypsa-earth [documentation](https://pypsa-earth.readthedocs.io/en/latest/installation.html), see `Install dependencies` and `Python dependencies`. Note that you should be in the directory `../<user-name>/pypsa-earth` at the beginning this process.
After installing the environment, activate it using
```bash
conda activate pypsa-earth
```
Before the whole workflow can be executed, the databundle must be retrieved. This can be done via:
```bash
snakemake -j 1 retrieve_databundle_light
```
This step can optionally be skipped if the `data/` folder with all relevant subfolders already exists.

## Feeding pypsa-earth with customized data from pypsa-zm-data

Work in progress. See the [pypsa-kz-data](https://github.com/pypsa-meets-earth/pypsa-kz-data) repository for an example on how to do this.


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

# Acknowledgements

This projects is funded by the Climate Compatible Growth through the following projects:

- [Macroeconomic implications of the Green Growth Strategy in Zambia](https://drive.google.com/file/d/1n9l50KhCGH4l07Kqsu1wiRGweubw0TYj/view?usp=sharing)
- [Energy System Chef – The energy system implications of transitions to clean cooking in Zambia](https://drive.google.com/file/d/1Sgr3NXm2F5gEFea_qEvJ-OWaNmSAjHMx/view?usp=sharing)
