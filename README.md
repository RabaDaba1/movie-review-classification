# Movie Review Classification

This repository contains code for predicting if a movie review is positive or negative using TensorFlow and word embeddings. The goal is to build a binary classifier that can accurately classify the sentiment of a movie review.

## Data

The training [dataset is from Kaggle](https://www.kaggle.com/datasets/lakshmi25npathi/imdb-dataset-of-50k-movie-reviews), which contains 50,000 movie reviews from IMDB. The dataset is balanced, meaning there are 25,000 positive and 25,000 negative reviews. The reviews are preprocessed and each one is encoded as a sequence of word indexes.

## Model

The baseline model is a simple neural network that consists of an embedding layer, a global average pooling layer, and a dense layer with sigmoid activation. The embedding layer maps each word index to a vector of 10 dimensions.

The model is a single Bidirectional LSTM layer with 32 units. The model uses pre-trained GloVe 100D embeddings to improve its performance.

## Training

The model was trained using the Adam optimizer with a learning rate of 0.001 and binary cross-entropy loss. The model was trained for 10 epochs.

## Results

Final model achieved **91.8%** accuracy on the training set and **88.5%** accuracy on the test set. There was no validation set as there was no hyperparameter tuning.

| Review | Prediction | Probability |
|--------|------------|-------------|
| The movie was great. I enjoyed every second of it although actors play wasn't perfect but plot made up for it. I would recommend it to others. | Positive | 0.92 |
| I loved this movie. It was so funny and entertaining. | Positive | 0.97 |
| This movie was terrible. The plot was boring and the acting was awful. | Negative | 0.00 |
| Funny movie but not an amazing one. Best to watch with your friends. | Positive | 0.97 |
| Not a good movie. I wasn't satisfied with the actors play. I wouldn't recommend it to others. | Negative | 0.45 |
| A good movie. I was satisfied with the actors play. I would recommend it to others. | Positive | 0.78 |

