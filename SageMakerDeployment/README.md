# Deploying Sentiment Analysis Model on SageMaker

In this project, we demonstrate how we can delopy sentiment analysis model on AWS SageMaker. A simple LSTM based model is used for the sentiment analysis. Together with Lambda function and API gateway,

## Data

We use [IMDb dataset](http://ai.stanford.edu/~amaas/data/sentiment/)

## Steps

1. Download or otherwise retrieve the data.
2. Process / Prepare the data.
3. Upload the processed data to S3.
4. Train a chosen model.
5. Test the trained model (typically using a batch transform job).
6. Deploy the trained model.
7. Use the deployed model.

## Model

## Deploying Web App

We create

<img src="https://github.com/yukiteb/Deep-Learning-Nanodegree/blob/master/SageMakerDeployment/web_app.PNG" width=800 height=200>

## Result
The example of the review and result is below:

<b>Review</b>: The movie was great and I really liked it. From the beginning to the end, I was never bored and the time really flies when I was watching the movie.

<b>Result</b>: Your review was POSITIVE! 

