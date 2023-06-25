# Emotion Analysis Project

This project focuses on emotion analysis in text data using various datasets and models. It consists of three main directories: `emotion-annotation`, `emotion-prediction`, and `emotion-role-labeling`.

## emotion-annotation

The `emotion-annotation` directory contains annotation guidelines for instances of the UCI ML Drug Review dataset with Eckman’s 6 fundamental emotions. These guidelines provide instructions and standards for annotating emotions in the dataset, facilitating consistent and accurate labeling.

## emotion-prediction

The `emotion-prediction` directory includes scripts for predicting emotions in text from three different datasets using two different models: LSTM and BERT-based models. The datasets used for emotion prediction are as follows:

1. ISEAR Dataset: A dataset of labeled texts containing emotional statements, available at [https://aclanthology.org/C18-1179/](https://aclanthology.org/C18-1179/).
2. Tales Dataset: A dataset of emotional narratives, also available at [https://aclanthology.org/C18-1179/](https://aclanthology.org/C18-1179/).
3. DAIR-AI Dataset: A dataset from Hugging Face's DAIR-AI repository, which includes labeled texts for emotion analysis.

By leveraging LSTM and BERT-based models, the scripts aim to accurately predict emotions in the provided text datasets.

## emotion-role-labeling

The `emotion-role-labeling` directory comprises human and automatic annotations of emotion role labels. These annotations assign specific roles to emotions found in the text data, providing further insights into the context and expression of emotions.

## Usage

1. Navigate to the respective directories (`emotion-annotation`, `emotion-prediction`, `emotion-role-labeling`) to access the relevant materials and scripts.
2. Follow the instructions in each directory to perform annotation, emotion prediction, or explore emotion role labeling.
3. Refer to the documentation provided within each directory for detailed usage guidelines and script explanations.

## Acknowledgements

- UCI ML Drug Review dataset: [link](https://archive.ics.uci.edu/ml/datasets/Drug+Review+Dataset+%28Drugs.com%29)
- ISEAR and Tales datasets: [link](https://aclanthology.org/C18-1179/)
- Hugging Face DAIR-AI repository: [link](https://huggingface.co/datasets/dair_ai/emotion)

For more information, refer to the documentation and files within each directory.