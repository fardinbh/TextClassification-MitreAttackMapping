# MITRE ATT&CK Incident Mapping

This repository provides a Python script for mapping descriptive text of an incident to relevant MITRE ATT&CK Enterprise techniques. The script uses Python 3.9.15 and several libraries listed below. It employs the SecBERT model, based on BERT architecture and trained on cybersecurity text, for the mapping process.

## Requirements

To run this script, you need to have the following libraries installed:

- Python 3.9.15
- ipywidgets 8.0.4
- transformers 4.31.0
- ipython 8.12.2
- iocextract 1.16.0
- lime 0.2.0.1
- pandas 2.0.3
- torch 2.0.1
- tqdm 4.66.1
- scikit-learn 1.3.0

You can install these libraries using `pip`:

```bash
pip install ipywidgets==8.0.4 transformers==4.31.0 ipython==8.12.2 iocextract==1.16.0 lime==0.2.0.1 pandas==2.0.3 torch==2.0.1 tqdm==4.66.1 scikit-learn==1.3.0
```

The pretrained SecBERT model is used for the training step, which can be found at [SecBERT Model](https://huggingface.co/jackaduma/SecBERT). This model has its own wordpiece vocabulary (secvocab) tailored to match the cybersecurity training corpus effectively.

## Data Preparation

The main dataset used for training is the TRAM Training Dataset, which is the Threat Report ATT&CK Mapping (TRAM) created by The MITRE Corporation. TRAM is designed to advance research into automating the mapping of CTI reports to ATT&CK. Furthermore, another comprehensive dataset based on all the techniques and subtechniques of Enterprise Techniques was created and merged with the TRAM dataset.

The `technique_dictMitre.pkl` file includes all the MITRE ATT&CK techniques and sub-techniques.

## Training Code

The training code is provided in the Jupyter Notebook cells below. It includes data loading and preprocessing, model loading, training data splitting, and model training. The notebook consists of several code cells to load data, preprocess it, tokenize text, and train a SecBERT-based model for incident mapping.

## Model Prediction and IOC Extraction

After training, you can use the trained model to predict MITRE ATT&CK techniques for an incident summary and extract indicators of compromise (IoCs). The provided Jupyter Notebook cells load the trained model and tokenizer, and allow you to input incident summaries for prediction. The model can provide predictions for multiple techniques, and you can set a confidence threshold to filter the results.

## Model Explainability

The script also offers model explainability using the LIME (Local Interpretable Model-Agnostic Explanations) method. You can enable model explainability to gain insights into how the model made its predictions.

## How to Use

1. Install the required libraries.
2. Run the training code to train the SecBERT model.
3. Use the provided code to load the trained model and perform incident mapping and IoC extraction.
4. Utilize model explainability if needed.

The provided Jupyter Notebook cells guide you through the process.

**Note:** Ensure you have the necessary data and files for training and prediction.

For more details, refer to the Jupyter Notebook and the provided Python scripts.
