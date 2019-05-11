# Predict Bike-Sharing Pattern
In this project, we build a simple neural network from scratch using numpy to predict bike-sharing pattern.

## Data
The data comes from the [UCI Machine Learning Database](https://archive.ics.uci.edu/ml/datasets/Bike+Sharing+Dataset). This dataset has the number of riders for each hour of each day from January 1 2011 to December 31 2012. Below is a plot showing the number of bike riders over the first 10 days or so in the data set.

<img src="https://github.com/yukiteb/Deep-Learning-Nanodegree/blob/master/PredictBikeSharing/bikeshare_data.png" width="500" height="350">

## Project Steps
1. Read and preprocess the data - convert categorical to numerical, standardize the scale.
2. Build a network with a single hidden layer - number of node in the hidden layer is a hyperparameter.
3. Train the network - use SGD (Stochastic Gradient Descend) for 10,000 iterations.

Here is the plot of training loss and validation loss.

<img src="https://github.com/yukiteb/Deep-Learning-Nanodegree/blob/master/PredictBikeSharing/bikeshare_train.png" width="500" height="350">

## Results
Below is the result of prediction against test set (last 21 days of data). 

<img src="https://github.com/yukiteb/Deep-Learning-Nanodegree/blob/master/PredictBikeSharing/result.PNG" width="500" height="350">

The model does a pretty good job until just before the Christmas starts. The model predicts much higher number of bike ride during the Christmas till the end of the year. This is understandable, as the model has only seen 1 Christmas/year end in the training data, and this time priod is quite different. Perhaps people do not do as much bike ride as normal time (stay home, go for vacation etc), so the model predicts much higher rides than the actual number of rides. 

