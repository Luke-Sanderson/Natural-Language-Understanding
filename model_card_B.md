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


This model is Siamese Bi-GRU model that was trained on 30K pairs of texts. The 
model architecture consists of a shared embedding layer, followed by a shared 
Bi-GRU. The outputs of the Bi-GRU are concatenated together and fed into a 
Batch Normalisation layer and then a dense layer of 64 neurons. Finally there is
a single neuron output layer with a sigmoid activation function for binary 
classification

- **Developed by:** Luke Sanderson and Sarah Saad
- **Language(s):** English
- **Model type:** Supervised
- **Model architecture:** Siamese Bi-GRU
- **Finetuned from model [optional]:** [More Information Needed]

### Model Resources

<!-- Provide links where applicable. -->

- **Repository:** [More Information Needed]
- **Paper or documentation:** Deep Learning based Authorship Identification

## Training Details

### Training Data

<!-- This is a short stub of information on the training data that was used, and documentation related to data pre-processing or additional filtering (if applicable). -->

30K pairs of texts drawn from emails, news articles and blog posts.

### Training Procedure

<!-- This relates heavily to the Technical Specifications. Content here should link to that section when it is relevant to the training procedure. -->

#### Training Hyperparameters

<!-- This is a summary of the values of hyperparameters used in training the model. -->


      - learning_rate: 1e-04
      - train_batch_size: 32
      - eval_batch_size: 32
      - seed: 42
      - num_epochs: 100

#### Speeds, Sizes, Times

<!-- This section provides information about how roughly how long it takes to train the model and the size of the resulting model. -->


      - overall training time: 1 hour 31 minutes
      - duration per training epoch: 55 seconds
      - model size: 162.1MB

## Evaluation

<!-- This section describes the evaluation protocols and provides the results. -->

### Testing Data & Metrics

#### Testing Data

<!-- This should describe any evaluation data used (e.g., the development/validation set provided). -->

The full development set provided, amounting to 6K pairs.

#### Metrics

<!-- These are the evaluation metrics being used. -->


      - Precision 0.519
      - Recall 0.584
      - F1-score 0.550
      - Accuracy 0.520
      - MCC 0.038
      - Cohen's Kappa 0.039

### Results

The model obtained an F1-score of 55% and an accuracy of 52%.

## Technical Specifications

### Hardware


      - RAM: at least 12.7 GB
      - Storage: at least 32GB,
      - GPU: V100

### Software


      - Tensorflow 2.15.0

## Bias, Risks, and Limitations

<!-- This section is meant to convey both technical and sociotechnical limitations. -->


Maximum input length of 512 tokens is enforced for this model. This could
introduce a bias to the start of sequences as any tokens after 512 are 
truncated.

## Additional Information

<!-- Any other information that would be useful for other people to know. -->

The hyperparameters for the MLP were determined by manual experimentation
      with different values. Similarly, the combination of features used was found through experimentation.
