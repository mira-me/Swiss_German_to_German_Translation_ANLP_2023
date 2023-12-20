# German_to_Swiss_Translation_ANLP_2023
Swiss German to German translation project for the course Advances Natural Language Processing at the IT University of Copenhagen.

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

## Data

The dataset is optained from the Eidgenössische Technische Hochschule (ETH) Zürich.
The dataset includes around 3 hours of high-quality audio per dialect together with Swiss German and High German transcripts.
The reduced raw dataset, containing only the Swiss German and High German transcripts can be found in the folder data/raw_data/sentences_ch_de_transcribed.json.



## Notebook Files

To reproduce the results of this project, the notebooks in the folder code can be used. We used Google Colab to execute the notebooks. 

**data_preperation.ipynb**:
* Preprocess the raw data file, generate the training and test set and store the resulting csv files in the folder /data.

**Training.ipynb**:
* This notebook is run to add a new language to the model and finetune it on the SwissDial training dataset. This notebook is executed with a T4 GPU in Google Colab. The model-used in this project is the [facebook/nllb-200-distilled-600M](https://huggingface.co/facebook/nllb-200-distilled-600M) from huggingface. 

**apply_model.ipynb**:
* Notebook to generate the translations between the source language (BE) and the target language (DE) using the five different models (trained on different embedding strategies). The finetuned models for the Swiss German dialects can be found [here](https://drive.google.com/drive/folders/1Vfe1fAmGQdUWecqt2HKNxUkObRbRqfFo?usp=sharing).

**evaluation_statistics.ipynb**: 

***

## Installation & Requirements

The code is run on Google Colab with the following additional requirements:

```bash
pip install sentencepiece transformers==4.33 datasets wandb sacremoses sacrebleu -q
```

## Instructions

