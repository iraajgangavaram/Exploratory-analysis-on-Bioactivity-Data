# Exploratory Analysis of Acetylcholinesterase Bioactivity Data

Exploratory cheminformatics analysis of ChEMBL bioactivity data for human
acetylcholinesterase (AChE), a drug target relevant to Alzheimer's disease.
The notebooks retrieve IC50 data, curate and label compounds, calculate
Lipinski descriptors with RDKit, and compare the chemical space of active
and inactive compounds.

> **Attribution:** The notebooks follow the *Computational Drug Discovery*
> tutorial series by Chanin Nantasenamat ([Data Professor](http://youtube.com/dataprofessor)),
> applied here to acetylcholinesterase.

## Notebooks

| Notebook | What it does |
|---|---|
| `CDD_ML_Part_1_Acetylcholinesterase_Bioactivity_Data_Concised.ipynb` | Searches ChEMBL for acetylcholinesterase, retrieves IC50 records, drops missing values and duplicate SMILES, and labels each compound `active` (IC50 <= 1,000 nM), `inactive` (IC50 >= 10,000 nM) or `intermediate`. |
| `CDD_ML_Part_2_Acetylcholinesterase_Exploratory_Data_Analysis.ipynb` | Keeps the largest fragment of each SMILES, computes Lipinski descriptors (MW, LogP, H-bond donors and acceptors), converts IC50 to pIC50, removes the intermediate class, and compares active vs inactive compounds with plots and Mann-Whitney U tests. |

## Workflow

```text
ChEMBL target search -> IC50 retrieval -> missing-value and duplicate removal
   -> active / inactive / intermediate labelling -> Lipinski descriptors (RDKit)
   -> IC50 to pIC50 -> box plots, scatter plots, Mann-Whitney U tests
```

## Running the notebooks

Both notebooks were written for Google Colab and install their own
dependencies in the first cells. To run locally instead:

```bash
pip install pandas numpy scipy seaborn matplotlib chembl_webresource_client
conda install -c conda-forge rdkit   # RDKit is easiest to install via conda
jupyter lab
```

Part 1 queries the live ChEMBL web service, so results can change as
ChEMBL is updated. Part 2 loads a pre-curated CSV from the tutorial author's
data repository rather than the output of Part 1.

## Technologies

Python, pandas, NumPy, SciPy, seaborn, Matplotlib, RDKit, ChEMBL web resource client, Jupyter

## Author

Iraaj Gangavaram
