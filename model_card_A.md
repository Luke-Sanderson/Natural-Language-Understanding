---
{}
---
language: en
license: cc-by-4.0
tags:
- text-classification
repo: https://github.com/Luke-Sanderson/Natural-Language-Understanding/

---

# Model Card for m78355ls-t02231ss-AV

<!-- Provide a quick summary of what the model is/does. -->

This is a classification model that was trained to
      detect whether two pieces of text were written by the same author.


## Model Details

### Model Description

<!-- Provide a longer summary of what this model is. -->


This model is feature extraction model with a Multi Layer Perceptron (MLP) 
prediction layer that was trained on 30K pairs of texts. The features extracted 
include comparisons in length, number of words, average word length, compression
size, capitalisation, punctuation, and vocabulary richness. The MLP is formed a
an input layer for the 10 features, 2 hidden layers of size 64 and 32, and a 
single node output layer

- **Developed by:** Luke Sanderson and Sarah Saad
- **Language(s):** English
- **Model type:** Supervised
- **Model architecture:** Multi Layer Perceptron
- **Finetuned from model [optional]:** GLAD

### Model Resources

<!-- Provide links where applicable. -->

- **Repository:** [More Information Needed]
- **Paper or documentation:** [More Information Needed]

## Training Details

### Training Data

<!-- This is a short stub of information on the training data that was used, and documentation related to data pre-processing or additional filtering (if applicable). -->

30K pairs of texts drawn from emails, news articles and blog posts.

### Training Procedure

<!-- This relates heavily to the Technical Specifications. Content here should link to that section when it is relevant to the training procedure. -->

#### Training Hyperparameters

<!-- This is a summary of the values of hyperparameters used in training the model. -->


      - learning_rate: 1e-03
      - train_batch_size: 8
      - eval_batch_size: 8
      - seed: 42
      - num_epochs: 50

#### Speeds, Sizes, Times

<!-- This section provides information about how roughly how long it takes to train the model and the size of the resulting model. -->


      - overall training time: 10 minutes
      - duration per training epoch: 10 seconds
      - model size: 64KB

## Evaluation

<!-- This section describes the evaluation protocols and provides the results. -->

### Testing Data & Metrics

#### Testing Data

<!-- This should describe any evaluation data used (e.g., the development/validation set provided). -->

The full development set provided, amounting to 6K pairs.

#### Metrics

<!-- These are the evaluation metrics being used. -->


      - Precision 0.596
      - Recall 0.518
      - F1-score 0.554
      - Accuracy 0.583
      - MCC 0.165
      - Cohen's Kappa 0.164

### Results

The model obtained an F1-score of 55% and an accuracy of 58%.

## Technical Specifications

### Hardware


      - RAM: at least 12.7 GB
      - Storage: at least 32GB,
      - GPU: None

### Software


      - Tensorflow 2.15.0

## Bias, Risks, and Limitations

<!-- This section is meant to convey both technical and sociotechnical limitations. -->

No bias related to input length.

## Additional Information

<!-- Any other information that would be useful for other people to know. -->

The hyperparameters for the MLP were determined by manual experimentation
      with different values. Similarly, the combination of features used was found through experimentation.
