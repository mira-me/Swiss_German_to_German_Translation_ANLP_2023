# German_to_Swiss_Translation_ANLP_2023
Swiss German to German translation project for the course Advances Natural Language Processing at the IT University of Copenhagen.

## Table of Contents
1. [General Info](#general-info)
2. [Installation](#installation)
4. [Instructions](#instructions)

## Data

The dataset is optained from a a dataset from the Eidgenössische Technische Hochschule (ETH) Zürich.
To get access, a form needs to be submitted https://form.jotform.com/223344961502048.
The data set includes around 3 hours of high-quality audio per dialect together with Swiss German and High German transcripts.
To reduce the size of the dataset, the audio files are removed. 

```bash
TBD code andreas
```

## Folder Structure

The folders are structured as follows:

```bash
.
├── README.md
├── code
│   ├── Training.ipynb
│   ├── apply_model.ipynb
│   ├── data_preperation.ipynb
│   └── evaluation_statistics.ipynb
├── data
│   ├── Results
│   │   ├── Manual_Syntax_Evaluation_Synt_TestSet.xlsx
│   │   ├── df_test_Results.xlsx
│   ├── df_test.csv
│   ├── df_train.csv
│   └── raw_data
│       └── sentences_ch_de_transcribed.json
```

## Installation & Requirements

The code is run on Google Colab with the following additional requirements:

```bash
pip install sentencepiece transformers==4.33 datasets wandb sacremoses sacrebleu -q
```

## Instructions

