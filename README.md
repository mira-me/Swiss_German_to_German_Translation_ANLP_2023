# Swiss_German_to_German_Translation_ANLP_2023

This repository contains the code, data, and result files for the project "Handling Syntactical Particularities of Western Swiss German Dialects: A Study of Embedding Vector Initialization in Machine Translation" developed as a final project in the course Advances Natural Language Processing at the IT University of Copenhagen.

## Authors
Andreas Møller Belsager  
Linda Caroline Schombach  
Mira Metzger

## Folder Structure

The folders are structured as follows:

```bash
.
├── Code
│   ├── 1_data_preparation.ipynb
│   ├── 2_training.ipynb
│   ├── 3_testing.ipynb
│   └── 4_scores_test_statistics.ipynb
├── Data
│   ├── df_test.csv
│   ├── df_train.csv
│   └── raw_data
│       └── sentences_ch_de_transcribed.json
├── README.md
└── Results
    ├── Manual_Syntax_Evaluation_Synt_TestSet.xlsx
    └── df_test_Results.xlsx
```

## Code

### Installation & Requirements

The code is run on Google Colab with the following additional requirements:

```bash
pip install sentencepiece transformers==4.33 datasets wandb sacremoses sacrebleu -q
```

### Notebook Contents

To reproduce the results of this project, execute the notebooks in the folder /Code. Each notebook contains further information and instructions. 

**data_preperation.ipynb**:
* Preprocesses the raw data file, generates the training and test sets, and stores resulting CSV files in the /Data folder.

**Training.ipynb**:
* This notebook is run to add a new language to the model and finetune it on the SwissDial training dataset. This notebook is executed with a T4 GPU in Google Colab. The model-used in this project is the [facebook/nllb-200-distilled-600M](https://huggingface.co/facebook/nllb-200-distilled-600M) from huggingface. 

**apply_model.ipynb**:
* Generates translations between the source language (BE) and the target language (DE) using five different models trained on distinct embedding strategies. Find the fine-tuned models for Swiss German dialects [here](https://drive.google.com/drive/folders/1Vfe1fAmGQdUWecqt2HKNxUkObRbRqfFo?usp=sharing).

**evaluation_statistics.ipynb**: 
* Notebook to calculate evaluation scores and test statistics.


## Data

The dataset is optained from the Eidgenössische Technische Hochschule (ETH) Zürich and includes audio files together with Swiss German and High German transcripts. The reduced raw dataset, containing only the Swiss German and High German transcripts can be found in the folder Data/raw_data/sentences_ch_de_transcribed.json. Additionaly the df_test.csv and df_train.csv files are stored in this folder (ouput of the data_preperation.ipynb notebook.

## Results

There are two Excel files in the result folder. *Manual_Syntax_Evaluation_Synt_TestSet.xlsx* contains the manual evaluation of the translated sentences and scores of each model. The file *df_test_Results.xlsx* contains the translation from the source to the target language (BE-DE) for all 5 different models (5 different embedding strategies)
