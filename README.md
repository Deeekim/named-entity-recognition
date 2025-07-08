# Named Entity Recognition

A list of machine learning models designed to analyze industry-specific datasets using various transformer models from hugging face. 

## Datasets

conll2003: General dataset
finer-ord: Dataset primarily trained on financial reports

## Models

General NER models
- bert-base-cased

NER pretrained on financial datasets
- Finbert by Prosus AI

## Methodologies
- **Model Training**: Variations of BERT models were employed on different kinds of datasets. Of particular interest is the Finbert variation, which was specifically designed to output sentiment rather than as a classification use for tokens. The model was repurposed for its finance-domain specific knowledge.
- Notebooks are run through google colab for access to available free GPU. 

## Results

The token tags in the following datasets are heavily imbalanced, with an emphasis for the outside entity. Because of this, the f1 score was used to identify the success of these models. Across 3 epochs, the f1 score increased from 0.861 to 0.881.

| Epoch |  Acuracy  |     F1    |
|-------|-----------|-----------|
|   1   | 0.979722  | 0.861279  |
|   2   | 0.981958  | 0.878493  |
|   2   | 0.982150  | 0.881010  |

The high scores are attributed to the cleanliness and structure of the finer-ord dataset.

Among the mismatched, ticker symbols stand out as the most frequently tagged token. Because of their highly specific nature, manual imputation of their tags may be required. Other models trained on stock market specific data may improve the detection of ticker symbols within reports.

### Requirements:
- Python 3.x
- pandas
- numpy
- transformers
- seqeval
- torch
- datasets