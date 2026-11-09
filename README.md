# Tabular Foundation Models for SCADA/ICS Intrusion Detection

Code for the article *Tabular Foundation Models (TFM) for SCADA Intrusion Detection Systems*.

The repository evaluates TabPFN, a tabular foundation model, as an anomaly and intrusion detector on industrial control system (ICS) datasets. It is compared against classical, deep-learning and density-based baselines, and the same pipeline is applied to every dataset. The notebooks are provided for reproducibility. Full details are given in the accompanying documentation.

## Datasets

| Dataset | Domain | Notes |
|---|---|---|
| SWaT (A1/A2) | Water treatment testbed | Normal operation plus attack scenarios |
| WADI (A1 2017 / A2 2019) | Water distribution testbed | Two acquisition campaigns |
| HAI | Boiler / turbine / water-treatment testbed | Industrial control system security dataset |
| NSL-KDD | Network intrusion | Generic tabular IDS benchmark |

The datasets are not included. Download them from their original providers and adjust the paths at the top of each notebook.

## Notebooks

### Exploration and cleaning
- `SWaT_EDA.ipynb`: exploratory analysis and cleaning of SWaT.
- `WADi_A1_2017_EDA_and_cleaning.ipynb`: exploratory analysis and cleaning of WADI A1 (2017).

### Full detection pipelines (TabPFN)
- `SWaT_A1A2-full-pipeline-v3.ipynb`: end-to-end pipeline on SWaT (preprocessing, TabPFN detector, evaluation).
- `WADi_A1_2017_full_pipeline_v1.ipynb`: same pipeline on WADI A1.
- `WADi_A2_2019_full_pipeline_v1.ipynb`: same pipeline on WADI A2.
- `HAI_full_pipeline_v1.ipynb`: same pipeline on HAI.
- `tabPFN_NSLKDD_IDS_full_pipeline_v1.ipynb`: TabPFN on the NSL-KDD network intrusion benchmark.

### Baselines
- `HAI_baselines_v1.ipynb`: baseline detectors on HAI.
- `WADI_A2_2019-baselines-v2.ipynb`: baseline detectors on WADI A2.

The baselines are compared with TabPFN using the same splits and metrics.

### Experiments
- `scada-E1-experiment.ipynb`: data-efficiency experiment. It measures how detection performance changes with the amount of normal training data.

## Environment

Python 3 with Jupyter, `tabpfn`, `scikit-learn`, `catboost`, `lightgbm`, `torch`, `pandas` and `numpy`. A GPU is recommended for TabPFN. The longer experiments, such as E1, can take many hours.

## Citation

Citation details will be added once the article is published.
