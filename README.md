# Explainable Inference for Hybrid Transfer Learning in Infodemic Misinformation Detection

This repository is the working project space for experiments around the paper:

**Explainable Inference for Hybrid Transfer Learning in Infodemic Misinformation Detection**

**Authors:** Deepak Kanneganti, Sajib Mistry, Aneesh Krishna, Mufti Mahmud, and Monowar Bhuyan

## Paper at a glance

If you are opening this repository for the first time, this is the story of the project in one paragraph.

The paper studies how to make strong transformer-based misinformation detection models more interpretable during infodemic events such as pandemics, elections, and crises. The central idea is that hybrid transfer learning models built on top of architectures such as BERT and BART can be very effective for prediction, but they are harder to explain using standard post hoc XAI tools. The paper therefore introduces an explainable inference mechanism that makes it possible to attach methods such as SHAP and ELI5 to hybrid transformer pipelines without redesigning the underlying model architecture.

In short, this repository contains the practical notebook trail behind that research story: data cleaning notebooks, BERT-based explainability notebooks, BART-based explainability notebooks, and experimental notebooks that appear to evaluate the approach across multiple misinformation datasets.

## Read this repository like a script

Think of the repository as a narrated workflow rather than as a packaged software library.

1. We begin with raw or semi-processed misinformation datasets.
2. We clean and reshape the data so that it can be used for transformer pipelines.
3. We train or fine-tune BERT and BART based models for misinformation detection.
4. We attach explainability methods such as SHAP and ELI5 to the prediction pipeline.
5. We compare behavior across datasets and experimental settings.

This is why most of the work here lives in notebooks instead of Python modules. The notebooks capture the progression of the research.

## Repository structure

There are **no nested project folders** in the current repository snapshot. Everything is stored at the top level. So instead of describing folder-by-folder navigation, the best way to understand the layout is by logical groups of files.

### 1. Core documentation

- `README.md`
  - The main guide to the repository.

### 2. Experimental notebooks for BERT-based explainability

- `Experiment_1_Enabling_Explainability_in_BERT_based_infodemic_misinformation_detection.ipynb`
  - An experiment notebook centered on BERT-based misinformation detection with explainability components.
  - Uses signals related to `bert-base-uncased`, SHAP, ELI5, and mixed-domain or COVID-style data sources.

- `Experiment_2_Enabling_Explainability_in_BERT_based_infodemic_misinformation_detection.ipynb`
  - A second BERT-focused experiment that appears to extend the first setup to additional validation and test splits.
  - References `kd_dataset.csv`, `mixed_domain_godamit.csv`, `covid_kd_val.csv`, and `covid_kd_test.csv`.

- `Experiment_3_Enabling_Explainability_in_BERT_based_infodemic_misinformation_detection.ipynb`
  - A third BERT-based experiment, again combining misinformation classification and explanation workflow.

- `Enabling_Explainability_in_BERT_AAAI.ipynb`
  - A BERT notebook that appears to be a polished or presentation-oriented version of the explainability workflow.
  - Includes explainability-related tooling such as SHAP, ELI5, and text explanation components.

- `Enabling_Explainability_in_BERT_Kaggle.ipynb`
  - A BERT explainability notebook tailored toward a Kaggle fake news style dataset or setup.

- `Cross_Domain_Text_Classification_Capsatone_Bert (3).ipynb`
  - A cross-domain BERT notebook that appears to train or test on mixed-domain misinformation data and then evaluate on COVID-related splits.
  - Likely useful when studying generalization across domains.

### 3. Experimental notebooks for BART-based explainability

- `BART_infodemic_misinformation_detection_Fakenews_FNIR1.ipynb`
  - A BART-based misinformation notebook with explainability tooling.
  - Uses BART model signals and explanation libraries such as SHAP and ELI5.

- `BART_infodemic_misinformation_detection_Fakenews_aa1.ipynb`
  - Another BART notebook, likely a variation of the misinformation detection pipeline under a different dataset or evaluation setting.

- `BART_infodemic_misinformation_detection_Fakenews_kaggle.ipynb`
  - A BART-based notebook that appears to target a Kaggle fake news configuration while keeping the XAI workflow.

### 4. Data preparation and cleaning notebooks

- `FakeNewsPrediction_dataset_cleaning.ipynb`
  - A notebook for loading and cleaning `FakeNewsPrediction.csv`.
  - This is part of the data preparation phase before model training or explanation.

- `WELFake_Dataset_cleaning.ipynb`
  - A dataset cleaning and balancing notebook for WELFake-style fake news data.
  - Includes preprocessing, balancing, and embedding-oriented preparation steps.

### 5. CSV datasets and processed data files

- `kd_dataset.csv`
  - Main dataset file with approximately 80,417 rows.
  - Columns detected: unnamed index column, `data`, `label`.

- `covid_kd_val.csv`
  - Validation split with approximately 17,535 rows.
  - Columns detected: `index`, `data`, `label`, `idx`.

- `covid_kd_test.csv`
  - Test split with approximately 6,820 rows.
  - Columns detected: `index`, `data`, `label`, `idx`.

- `mixed_domain_godamit.csv`
  - A large mixed-domain dataset with approximately 62,882 rows.
  - Columns detected: `index`, `data`, `label`, `idx`.

- `FakeNewsPrediction.csv`
  - A fake news dataset with approximately 6,315 rows.
  - Columns detected: unnamed index column, `data`, `label`.

## What the paper contributes, in plain language

The paper argues that high-performing hybrid transformer models are useful for misinformation detection, but they can become difficult to interpret because the prediction process passes through several transformation stages. Standard XAI tools are easier to apply to simpler models than to these hybrid pipelines.

The contribution of the work is therefore not only a good classifier, but an **explainable inference pathway** that allows post hoc explanation tools to work on top of hybrid transfer learning systems. In the paper, this idea is demonstrated using BERT- and BART-centered pipelines and explanation techniques including SHAP and ELI5.

## What you should expect when opening the notebooks

Most notebooks follow a similar research rhythm:

1. Install Python libraries inside the notebook session.
2. Load a dataset from one of the CSV files.
3. Preprocess or tokenize the text.
4. Load a transformer model such as BERT or BART.
5. Train, fine-tune, or evaluate the classifier.
6. Run explanation methods such as SHAP or ELI5 `TextExplainer`.
7. Inspect prediction outputs, explanation plots, and error behavior.

Because of that, the repository feels closer to a laboratory notebook collection than to a production-ready Python package.

## Suggested reading order

If you want to understand the project in a clean sequence, read it in this order:

1. Start with the paper title and abstract to understand the research goal.
2. Open `FakeNewsPrediction_dataset_cleaning.ipynb` and `WELFake_Dataset_cleaning.ipynb` to see how data is prepared.
3. Move to the BERT notebooks, especially the `Experiment_1`, `Experiment_2`, and `Experiment_3` series.
4. Then open the BART notebooks to compare how the explainability workflow is adapted to another transformer family.
5. Finish with the cross-domain notebook to understand broader evaluation across domains.

## Environment notes

From the notebook contents, this project appears to have been developed in a notebook-first environment, likely Google Colab for at least some runs. Several notebooks install dependencies directly inside cells, including packages such as:

- `transformers`
- `eli5`
- `anchor-exp`
- SHAP-related tooling

If you plan to rerun the notebooks locally, expect to set up a Python environment with Jupyter support and the usual machine learning stack, including TensorFlow or PyTorch depending on the notebook variant.

## Important note about structure

Even though the request was to describe all folders, this repository currently does not contain separate source folders, data folders, or docs folders. Everything is stored in one flat top-level directory. For that reason, this README documents the project by **functional groups of files** instead of literal folder names.

## Closing summary

This repository documents a research workflow around explainable misinformation detection using hybrid transfer learning. The paper provides the conceptual contribution, and the notebooks provide the experimental path: clean the data, train transformer-based models, connect them to XAI tools, and study how explainability can coexist with predictive performance in infodemic settings.

If you are reading this repository as a researcher, the notebooks are the main artifact. If you are reading it as a developer, think of this repository as an experimental prototype that can later be reorganized into a cleaner package structure if needed.
