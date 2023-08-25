# Movie Review Classifier

This repository contains code for predicting if a movie review is positive or negative using TensorFlow. The goal is to build a binary classifier that can accurately classify the sentiment of a movie review.

## Data

The training [dataset is from Kaggle](https://www.kaggle.com/datasets/lakshmi25npathi/imdb-dataset-of-50k-movie-reviews), which contains 50,000 movie reviews from IMDB. The dataset is balanced, meaning there are 25,000 positive and 25,000 negative reviews. The reviews are preprocessed and each one is encoded as a sequence of word indexes.

## Model

### Baseline
The baseline model is a simple neural network that consists of an embedding layer, a global average pooling layer, and a dense layer with sigmoid activation. The embedding layer isn't pre-trained and maps each word index to a vector of 10 dimensions.

### Final model
Final model is a single Bidirectional LSTM layer with 64 units. The model uses pre-trained GloVe 100D embeddings to improve its performance. Model file couldn't be uploaded to GitHub due to its size, but it can be downloaded from [here](https://drive.google.com/file/d/1ETyYk8NZlcWjNMmfrvTAId4PJJhNl4pT/view?usp=sharing).

## Training

The model was trained using the Adam optimizer with a learning rate of 0.001 and binary cross-entropy loss. The model was trained for 10 epochs on 49k examples and tested on 1k.

## Results

Final model achieved **95.0%** accuracy on the training set and **90.3%** accuracy on the test set. There was no validation set as there was no hyperparameter tuning.

| Review | Prediction | Probability |
|--------|------------|-------------|
| The movie was great. I enjoyed every second of it although actors play wasn't perfect but plot made up for it. I would recommend it to others. | Positive | 0.94 |
| I loved this movie. It was so funny and entertaining. | Positive | 0.88 |
| This movie was terrible. The plot was boring and the acting was awful. | Negative | 0.00 |
| Funny movie but not an amazing one. Best to watch with your friends. | Positive | 0.91 |
| Not a good movie. I wasn't satisfied with the actors play. I wouldn't recommend it to others. | Negative | 0.17 |
| A good movie. I was satisfied with the actors play. I would recommend it to others. | Positive | 0.67 |
