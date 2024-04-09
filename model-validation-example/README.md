# model-validation-eos4tcc

## BayeshERG: hERG channel blockade

BayeshERG is a predictor of small molecule-induced blockade of the hERG ion channel.

- Input: Compound
- Input Shape: Single
- Task: Classification
- Output: Probability
- Output Type: Float
- Output Shape: Single
- Interpretation: Probability of hERG channel blockade. The cut-off used in the training set to define hERG blockade was IC50 <= 10 μM

## Repository organisation

The repository is organised in folders:

- '/notebooks' contains the jupyter notebooks where most of the work is being developed
- '/data' contains all the .csv files. Model predictions are obtained outside this repository and saved in this folder. Subfolders might be created if needed
- '/src' contains important functions I will re-use throughout the repository, to avoid typing them each time
- '/figures' contains the plots I have produced during the model validation process
- 'requirements.txt' lists all the required packages to run the notebooks in this repository. If possible I also specify the version of the package I am using.

## Installation

### Downloading Ersilia

Click [here](https://ersilia.gitbook.io/ersilia-book/ersilia-model-hub/installation) to get instructions for downloading Ersilia on your local system.

### Fetching and Serving the model

Commands are:-

- ersilia fetch eos4tcc
- ersilia serve eos4tcc
- ersilia api run -i input.csv -o output.csv

Replace 'input.csv' with the name of the input file containing standard smiles for the molecules. The output will be stored in the 'ouput.csv'. Replace the name with the name of the file where you want to store the output.

### Running predictions using the BayshERG model

Follow instructions on this [link](https://github.com/GIST-CSBL/BayeshERG) to run predictions using the BayeshERG model.

## Tasks

This repository has been created to accomplish the following tasks :-

- T1 : Model bias (check if the model is giving very high values or low values). The deatils are given in [this](https://github.com/Ashita17/Ersilia-Outreachy/blob/main/model-validation-example/notebooks/00_model_bias.ipynb) notebook.
- T2 : Reproducibility (check if we can reproduce the exact values that authors obtained when training the model in the first place). The deatils are given in [this](https://github.com/Ashita17/Ersilia-Outreachy/blob/main/model-validation-example/notebooks/01_model_reproducibility.ipynb) notebook.
- T3 : Performance (check if the model gives accurate results in external datasets). The deatils are given in [this](https://github.com/Ashita17/Ersilia-Outreachy/blob/main/model-validation-example/notebooks/02_external_validation.ipynb) notebook.

## References

- [Ersilia GitBook](https://ersilia.gitbook.io/ersilia-book/contributors/internships/outreachy-summer-2024)
- [Model Publication](https://academic.oup.com/bib/article-abstract/23/4/bbac211/6609519)
- [Model Source Code](https://github.com/GIST-CSBL/BayeshERG)
- [Chembl Dataset Source](https://www.ebi.ac.uk/chembl/web_components/explore/activities/STATE_ID:E1fWDEddf-dOwmTBnG8uWw==)

## License

All the code in this repository is licensed under a GPLv3 License.
