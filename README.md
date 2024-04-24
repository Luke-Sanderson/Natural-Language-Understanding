
# NLU - Author Verification
This project aims to classify pairs of text into pairs that are written by the same author or different authors.

## Structure
There are 3 Jupyter notebook files in this repo:
- `NLU Model A.ipynb`
- `NLU Model B.ipynb`
- `NLU Demo.ipynb`

`NLU Model A.ipynb` can be viewed or ran to train a feature based multi-layer perceptron model on a given training dataset, outputting the model as a `.keras` or `.h5` file. It will also output some metrics on a provided validation dataset. 

`NLU Model B.ipynb` does the same as A but with a siamese Bidirectional GRU model.

`NLU Demo.ipynb` can be run to evaluate the two produced models on a provided dataset and then run a prediction on another dataset. This will produce a set of metrics along with an outputted CSV of predictions 

There are also 2 model files for Model A and Model B along with multiple CSVs. Note that due to the size of Model B this is not included in the blackboard submission and can be found in the following google drive 

https://drive.google.com/drive/folders/1TLztHNaWegNXCizsUSubCCxGrG_C-A2R?usp=sharing

## Code attribution
### Model A
Modified the punctuation, compression_based_dissimilarity, char_ngram_similarity, and entropy feature extraction methods found in GLAD: Groningen Lightweight Authorship Detection by Manuela Hürlimann in 2015. Repo can be found:

https://github.com/pan-webis-de/huerlimann15

Only the punctuation method was used in the final model but the other methods are written in the codebase and were used in testing

### Model B 
The weights of the embedding layer are pretrained GloVe embeddings.

Jeffrey Pennington, Richard Socher, and Christopher D. Manning. 2014. GloVe: Global Vectors for Word Representation. URL: https://nlp.stanford.edu/pubs/glove.pdf





