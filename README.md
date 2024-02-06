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

### 4. Machine Learning Model Training, Evaluation and Selection

For each disease, models were trained using the Pycaret library, and various metrics such as accuracy, AUC, recall, precision, F1-score, kappa, and MCC were used for evaluation. I select the best-performing model for each disease based on these evaluation metrics.

Table 1. Diseases that yielded good ML models.

| Model                      | Accuracy | AUC    | Recall | Prec. | F1    | Kappa | MCC   | TT (Sec) | Disease                                  |
|----------------------------|----------|--------|--------|-------|-------|-------|-------|----------|------------------------------------------|
| Ada Boost Classifier       | 0.9994   | 0.9999 | 0.9467 | 1.0000| 0.9705| 0.9702| 0.9717| 0.792    | Anorexia                                 |
| Extreme Gradient Boosting | 0.9973   | 0.9998 | 0.8875 | 0.9607| 0.9207| 0.9193| 0.9211| 2.730    | CDI                                      |
| Extreme Gradient Boosting | 0.9853   | 0.9959 | 0.8034 | 0.9603| 0.8744| 0.8666| 0.8708| 6.404    | CRC                                      |
| Extreme Gradient Boosting | 0.9932   | 0.9980 | 0.8030 | 0.9633| 0.8729| 0.8695| 0.8748| 3.987    | Clostridium difficile colitis            |
| Extreme Gradient Boosting | 0.9892   | 0.9958 | 0.6758 | 0.9302| 0.7806| 0.7753| 0.7868| 3.912    | Colonic Diseases                         |
| Extreme Gradient Boosting | 0.9955   | 0.9978 | 0.8824 | 0.9777| 0.9261| 0.9238| 0.9259| 4.001    | Colorectal Neoplasms                    |
| Extreme Gradient Boosting | 0.9980   | 0.9997 | 0.9344 | 0.9866| 0.9592| 0.9581| 0.9588| 2.598    | Hematologic Neoplasms                   |
| Extreme Gradient Boosting | 0.9943   | 0.9992 | 0.9769 | 0.9615| 0.9691| 0.9659| 0.9660| 1.093    | Infant, Premature                        |
| Extreme Gradient Boosting | 0.9983   | 0.9990 | 0.8161 | 0.9690| 0.8829| 0.8820| 0.8869| 1.498    | Inflamatory Bowel Disease                |
| Extreme Gradient Boosting | 0.9969   | 0.9993 | 0.9099 | 0.9471| 0.9266| 0.9250| 0.9260| 2.460    | Liver Cirrhosis                          |
| Extreme Gradient Boosting | 0.9759   | 0.9820 | 0.7175 | 0.8725| 0.7859| 0.7733| 0.7783| 5.347    | Obesity                                  |
| Extreme Gradient Boosting | 0.9945   | 0.9994 | 0.9228 | 0.9694| 0.9444| 0.9416| 0.9425| 5.036    | Pouchitis                                |
| Ada Boost Classifier       | 0.9990   | 1.0000 | 0.9760 | 0.9886| 0.9817| 0.9812| 0.9815| 0.696    | Precursor Cell Lymphoblastic Leukemia-Lymphoma |
| Extra Trees Classifier     | 0.9947   | 0.9974 | 0.6250 | 0.9900| 0.7580| 0.7555| 0.7800| 0.332    | Small adenoma                            |
| Random Forest Classifier   | 0.9999   | 1.0000 | 0.9963 | 1.0000| 0.9981| 0.9981| 0.9981| 0.255    | Stomach Neoplasms                       |
| Extreme Gradient Boosting | 0.9945   | 0.9974 | 0.6255 | 0.8907| 0.7193| 0.7168| 0.7354| 1.459    | Uveomeningoencephalitic Syndrome         |
