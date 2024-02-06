# Disease Prediction using Microbiome Data

In this project, I focus on utilizing microbiome data to predict the likelihood of various diseases. By analyzing the composition of microbiomes, my aim is to develop machine learning models capable of accurately predicting disease outcomes based on microbiome data.

## Introduction

Microbiome data contains valuable information about the abundance of microorganisms present in a particular environment, such as the human gut. These microorganisms have been linked to various health conditions and diseases. Through this project, I explore how microbiome data can be leveraged for disease prediction.

## Project Cycle

### 1. Data Acquisition and Preprocessing

I began by acquiring microbiome abundance data from [GMrepo](https://evolgeniusteam.github.io/gmrepodocumentation/usage/downloaddatafromgmrepo/), a repository of gut microbiota data. This data includes abundance measurements for microbial taxa across different samples.

### 2. Data Cleaning and Exploration

Next, I cleaned the metadata associated with the samples to remove any irrelevant or duplicated entries. I also preprocessed the microbiome abundance data, filtering out samples that do not have corresponding metadata and performing any necessary standardization.

I then conducted exploratory data analysis (EDA) to gain insights into the distribution of phenotypes (disease categories) and perform dimensionality reduction using Principal Component Analysis (PCA) to visualize patterns in the data.

### 3. Feature Selection

Features were selected based on significance results obtained from the Kruskal-Wallis test; if a feature was found significantly different between the healthy and disease categories, it was deemed as important and preserved for model training.

### 5. Machine Learning Model Training, Evaluation and Selection

For each disease, models were trained using the Pycaret library, and various metrics such as accuracy, AUC, recall, precision, F1-score, kappa, and MCC were used for evaluation. I select the best-performing model for each disease based on these evaluation metrics.
