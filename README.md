# Predict Concrete Strength Using ANN

## Overview

This project explores using Artificial Neural Networks (ANNs) to predict the compressive strength of concrete based on its ingredients and age. The dataset used is the "Concrete Compressive Strength Data Set" sourced from [https://cocl.us/concrete_data](https://cocl.us/concrete_data).

The project investigates the impact of different factors on the model's performance:

- **Data Normalization:** Comparing models trained on raw vs. normalized data.
- **Number of Epochs:** Evaluating the effect of training for different numbers of epochs.
- **Network Architecture:** Experimenting with different numbers of hidden layers.

## Dataset

The dataset contains 1030 instances, each representing a different concrete mixture. The features include:

- Cement  – kg in a m3 mixture
- Blast Furnace Slag  – kg in a m3 mixture
- Fly Ash  – kg in a m3 mixture
- Water  – kg in a m3 mixture
- Superplasticizer  – kg in a m3 mixture 
- Coarse Aggregate  – kg in a m3 mixture
- Fine Aggregate  – kg in a m3 mixture
- Age – Day (1~365)

The target variable is:

- Concrete compressive strength – MPa 

## Project Structure

- `concrete_strength_prediction.ipynb`: Jupyter Notebook containing the code and experiments.
- `README.md`: This file, providing a project overview and results.

## Experiments and Results

The notebook details four main experiments:

**A. Baseline Model:**
   - Single hidden layer (10 nodes, ReLU activation).
   - Adam optimizer, Mean Squared Error (MSE) loss.
   - 50 epochs.
   - **Mean MSE:** [404.26]
   - **Standard Deviation of MSEs:** [468.49] 

**B. Data Normalization:**
   - Same architecture as Part A but using normalized data (standardization).
   - **Mean MSE:** [378.51] 
   - **Standard Deviation of MSEs:** [105.54]
   - **Observation:** Data normalization significantly improved performance, reducing the mean MSE.

**C. Increased Epochs:**
   - Same as Part B but training for 100 epochs.
   - **Mean MSE:** [168.62]
   - **Standard Deviation of MSEs:** [27.07]
   - **Observation:** Increasing epochs further decreased the mean MSE, suggesting longer training can be beneficial.

**D. Increased Hidden Layers:**
   - Using normalized data and three hidden layers (each with 10 nodes and ReLU activation).
   - **Mean MSE:** [130.28]
   - **Standard Deviation of MSEs:** [13.41]
   - **Observation:** Adding more layers [significantly improved performance, reducing the mean MSE compared to Part B].

## Conclusion

This project demonstrates the effectiveness of ANNs for predicting concrete compressive strength.  Key findings include the importance of data normalization and the impact of training epochs and network architecture on model performance. 

Further improvements could involve:

- Exploring different optimizers, activation functions, and loss functions.
- Implementing techniques like early stopping and dropout for better generalization.
- Hyperparameter tuning to find the optimal network configuration.

