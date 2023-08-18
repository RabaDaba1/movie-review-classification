# Movie Review Classification

This repository contains code for predicting if a movie review is positive or negative using TensorFlow and word embeddings. The goal is to build a binary classifier that can accurately classify the sentiment of a movie review based on the text.

## Data

The training [dataset is from Kaggle](https://www.kaggle.com/datasets/lakshmi25npathi/imdb-dataset-of-50k-movie-reviews), which contains 50,000 movie reviews from IMDB. The dataset is balanced, meaning there are 25,000 positive and 25,000 negative reviews. The reviews are preprocessed and each one is encoded as a sequence of word indexes.

## Model

The model is a simple neural network that consists of an embedding layer, a global average pooling layer, and a dense layer with sigmoid activation. The embedding layer maps each word index to a vector of 10 dimensions. The global average pooling layer computes the average of the embeddings for each review. The dense layer outputs a probability between 0 and 1, indicating how likely the review is positive.

## Training

The model is trained using the Adam optimizer and binary cross-entropy loss. The training set is split into 80% for training and 20% for validation. The model is trained for 20 epochs. The performance of the model is evaluated using accuracy score.

## Results

The model achieves an accuracy of 87.5% on the test set. The model also performs well on some example reviews, as shown below:

| Review | Prediction | Probability |
|--------|------------|-------------|
| I loved this movie. It was so funny and entertaining. | Positive | 0.79 |
| This movie was terrible. The plot was boring and the acting was awful. | Negative | 0.00 |
| Funny movie but not an amazing one. Best to watch with your friends. | Positive | 0.55 |
