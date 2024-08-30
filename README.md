# Alphabet Soup Funding Success Predictor

## Overview of the Analysis

This analysis uses a neural network to analyze metadata from Alphabet Soup about previously funded organizations.  The goal is to predict whether future applicants will be successful if funded.

* Purpose if future campaigns will be successful.
* Used a dataset of 34,000 previously funded organizations.
* The dataset includes the following variables:
    * EIN and NAME—Identification columns
    * APPLICATION_TYPE—Alphabet Soup application type
    * AFFILIATION—Affiliated sector of industry
    * CLASSIFICATION—Government organization classification
    * USE_CASE—Use case for funding
    * ORGANIZATION—Organization type
    * STATUS—Active status
    * INCOME_AMT—Income classification
    * SPECIAL_CONSIDERATIONS—Special considerations for application
    * ASK_AMT—Funding amount requested
    * IS_SUCCESSFUL—Was the money used effectively

## Results

* Data Preprocessing
    * The target variable: IS_SUCCESSFUL
    * The feature variables:
        * APPLICATION_TYPE
        * AFFILIATION
        * CLASSIFICATION
        * USE_CASE
        * ORGANIZATION
        * INCOME_AMT
        * SPECIAL_CONSIDERATIONS
        * ASK_AMT
    * Removed variables:
        * EIN
        * NAME
        * STATUS
* Compiling, Training and Evaluating the Model
    * The highest accuracy of 73.47% was achieved using Keras Tuner
        * Activation Functions: Tanh
        * Number of Layers: 4
        * Neurons Layer 1: 46
        * Neurons Layer 2: 3
        * Neurons Layer 3: 5
        * Neurons Layer 4: 1
    * This model's performance is slightly under the target performance of 75%
    * Steps taken to improve performance
        * Test Dropped columns.
        * Increase and decrease the cutoff point for the "Other" bin in the APPLICATION_TYPE category.
        * Added a second bin to the CLASSIFICATION category and adjusted the cutoffs higher and lower.
        * Used different activation functions.
        * Added more hidden layers.
        * Added more neurons each layer.
        * Tested added and reducing the number of Epochs.
        * Auto-Optimized with Keras Tuner.

## Summary

* The deep learning model created to predict the success of funding applications for Alphabet Soup achieved a maximum accuracy of 73.47% using Keras Tuner. This model included four layers with Tanh activation functions and a varying number of neurons per layer. Despite fine-tuning various aspects of the model—including adjusting the binning strategy, modifying the activation functions, adding more layers, and optimizing hyperparameters—the accuracy remained slightly below the target threshold of 75%.
* To improve the accuracy of the model and potentially solve this classification problem more effectively, I recommend exploring Random Forests. This model creates multiple decision trees during training and merges them to obtain a more accurate and stable prediction. It's particularly effective in handling categorical variables and managing overfitting, which might be contributing to the current model's performance ceiling.
