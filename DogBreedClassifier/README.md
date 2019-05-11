# Classifying Dog Breed with CNN
In this project, we build a dog-breed classifier using CNN (Convolutional Neural Network). We build CNN from scratch, as well as pre-trained VGG-16-based CNN using transfer learning. Finally, we build an app (function) which tells whether a given picture of whether it is a human, a dog, or something else. If the app identifies picture as a dog then it tells you the breed, but if the picture is human, it tells you the most resembling breed of dogs.

## Project Steps
1. Build a human face-detector using OpenCV.
2. Build a dog detector using pre-trained VGG-16. It is trained on ImageNet (1000 image categories).
3. Build a dog breed classifier from scratch.
4. Build a dog breed classifier using transfer learning with VGG-16.
5. Combine the above to create an app. Given a picture, the app tells 1) if the picture is a dog, then what breed it is, 2) if the picture is a human, what breed it most resembles to, 3) the picture is neither a human nor a dog

## Network Structure
We built 2 network 1) one from scratch, 2) one with pre-trained model (VGG-16). Below are the structure of both networks:

### Network from Scratch
- Input Image (224 x 224 x 3)
- Convolution layer with 16 filters (224 x 224 x 16) -> Relu -> MaxPooling layer (112 x 112 x 16) -> Batch Norm
- Convolution layer with 32 filters (112 x 112 x 32) -> Relu ->MaxPooling layer (56 x 56 x 32) -> Batch Norm
- Convolution layer with 64 filters (56 x 56 x 64) -> Relu ->MaxPooling layer (28 x 28 x 64) -> Batch Norm
- DropOut Layer -> FC Layer (1000) -> Relu -> DropOut -> FC Layer (500) -> Relu -> DropOut -> FCLayer (133)

### Network with pre-trained model
- Pre-trained VGG -> Dropout -> FC1 (500) -> Relu -> Dropout -> FC2 (133) -> Logsoftmax

## Model Performance
The model from scratch achieved accuracy of <b>16%</b>, and the pre-trained model achieved the accuracy of <b>73%</b>.


## Examples
Below is  the some examples of app.

![Example](https://github.com/yukiteb/Deep-Learning-Nanodegree/blob/master/DogBreedClassifier/dog_app_example.PNG)
