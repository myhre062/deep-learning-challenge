# deep-learning-challenge

# Module 21 Challenge

## Overview

The purpose of this analysis is to develop and optimize a deep learning model to predict the success of charity funding applications. The analysis involves preprocessing the data, building a neural network model, and optimizing the model to improve its performance. The optimized model aims to accurately classify applications as successful or unsuccessful based on various features.

## Results

### Data Preprocessing

- The Target Variable(s) for my model were the `IS_SUCCESSFUL` variable.

- The Feature Variable(s) for my model were: `APPLICATION_TYPE`, `AFFILIATION`, `CLASSIFICATION`, `USE_CASE`, `ORGANIZATION`, `STATUS`, `INCOME_AMT`, `SPECIAL_CONSIDERATIONS`, `ASK_AMT`

- The Variable(s) removed from the input data were: `EIN`, `NAME`

### Compiling, Training, and Evaluating the Model

- How many neurons, layers, and activation functions did you select for your neural network model, and why?
    - In the initial and optimized model I used 3 layers because it provides enough complexity to capture non-linear relationships in the data without overfitting. I used ReLU activation for the first 2 layers and Sigmoid activation for the last layer.
    - In the initial neural network used 80 neurons for layer 1, 30 neuron for layer 2, then 1 neurons for layer 3. I used 80 neurons, this layer has enough capacity to learn a wide variety of patterns from the input data. In the second layer I used 30 because it helps in progressively narrowing down the complexity, making the network more focused and reducing the risk of overfitting. In the third layer I used 1 neuron because the task is binary classification (predicting whether a charity application is successful or not).
    - In the optimization neural network I used 50-150 neurons where the optimal is 130 neurons in the first layer, with ReLU activation. I did this range so the model could find the optimal number of nuerons to use so I didn't have to decide. I did the same for the second layer where I gave the model a range of 20-80 neurons where it found that the optimal number of neurons is 30. I also used ReLU activation for the second layer. Same as the inital model, I used 1 nueron because the model needs to predict whether or not a chartity is successful or not. 

- Were you able to achieve the target model performance:
    - I was not able to achieve the 75% accuracy performace with my optimization methods.
    - Initial model had an accuracy of ~72%
    - Optimized model had an accuracy of ~73%

- What steps did you take in your attempts to increase model performance?: 
    - I tried to use these 3 methods: 
        1. Hyperparameter tuning using keras-tuner, for hyperparameter optimization. Configured RandomSearch for hyperparameter tuning.
        2. Adding a Dropout layer to reduce overfitting.
        3. Experimented with different learning rates by using the tuner.search(). Once that was completed, I used the best hyperparameters, including the optimal learning rate. 

## Summary

The overall results of the deep learning model indicate that the initial model achieved an accuracy of approximately 72%, while the optimized model achieved an accuracy of approximately 73%. Despite the optimization efforts, the performance improvement was not the best. A potential recommendation for further improvement is to explore different model architectures such like Random Forest or Gradient Boosting, which might capture complex patterns in the data more effectively than a single neural network model.