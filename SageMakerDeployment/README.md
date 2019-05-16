# Deploying Sentiment Analysis Model on SageMaker

In this project, we demonstrate how we can delopy sentiment analysis model on AWS SageMaker. A simple LSTM based model is used for the sentiment analysis. Together with Lambda function and API gateway, we build a web app which tells whether the sentiment of the user-given movie review is positive or negative.

## Data

We use [IMDb dataset](http://ai.stanford.edu/~amaas/data/sentiment/) for the set of labeled movie reviews.

## File structure
The files are structured as follows:
```

| - SageMaker Project.ipynb # main notebokk which contains all the analysis
| - index.html  # main page of web app
| - predict.py  # contains functions related to prediction/inference
| - train.py  # contains functions related to training

```

## Steps

1. Download or otherwise retrieve the data.
2. Process / Prepare the data.
3. Upload the processed data to S3.
4. Train a chosen model.
5. Test the trained model (typically using a batch transform job).
6. Deploy the trained model.
7. Use the deployed model.

## Model

The model has the following structure:

- Embedding layer -> LSTM layer -> FC Layer

We used 32 dimensions for embedding layer and 100 hidden units in the LSTM layer.

## Deploying Web App

To delopy a web app, we need to set up

- <b>Lambda function</b>: This Lambda function will be executed whenever our public API has data sent to it. When it is executed it will receive the data, perform any sort of processing that is required, send the data (the review) to the SageMaker endpoint we've created and then return the result.
- <b>API Gateway</b>: API Gateway triggers the Lambda function created above

The interface of the web app looks like below:

<img src="https://github.com/yukiteb/Deep-Learning-Nanodegree/blob/master/SageMakerDeployment/web_app.PNG" width=800 height=250>

## Result
The example of the review and result is below:

<b>Review</b>: The movie was great and I really liked it. From the beginning to the end, I was never bored and the time really flies when I was watching the movie.

<b>Result</b>: Your review was POSITIVE! 

