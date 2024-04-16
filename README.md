Table of Contents    
----------------
* [Introduction](#introduction)         
* [Data Description](#data-description)   
* [Methodology](#methodology)         
* [Models Evaluated](#models-evaluated)     
* [Getting started](#getting-started)     
* [Installation](#installation)        
* [Running the project](#running-the-project) 
* [Results](#results)            
* [Comparative Analysis](#comparative-analysis) 
* [Conclusion](#conclusion)          

Introduction
-----------------
The datasets contain transactions made by credit cards in September 2013 by European cardholders. This dataset presents transactions that occurred over two days, including 492 frauds out of 284,807 transactions. The dataset is highly unbalanced, with the positive class (frauds) accounting for 0.172% of all transactions.

Data Description
-----------------
The data comes from credit card transactions in September 2013 by European cardholders. The dataset is highly unbalanced and has undergone PCA transformation, resulting in numerical input variables V1 to V28. The "Time" and "Amount" features have not been transformed, providing additional context for the transactions. The "Class" feature indicates whether a transaction is fraudulent.

Methodology
-----------------
The project involves several key steps to address the problem of credit card fraud detection:
* **Exploratory Data Analysis**: Analyze and understand the data to identify patterns, relationships, and trends in the data by using Descriptive Statistics and Visualizations. 
* **Data Cleaning**: This might include standardization, handling the missing values and outliers in the data. 
* **Dealing with Imbalanced data**: This data set is highly imbalanced. The data should be balanced using the appropriate methods before moving onto model building.
* **Feature Engineering**: Create new features or transform the existing features for better performance of the ML Models. 
* **Model Selection**: Choose the most appropriate model that can be used for this project. 
* **Model Training**: Split the data into train & test sets and use the train set to estimate the best model parameters. 
* **Model Validation**: Evaluate the performance of the model on data that was not used during the training process. The goal is to estimate the model's ability to generalize to new, unseen data and to identify any issues with the model, such as overfitting. 
* **Model Deployment**: Model deployment is the process of making a trained machine learning model available for use in a production environment.

Models Evaluated
-----------------
* Random Forest Classifier
* AdaBoost Classifier
* CatBoost Classifier
* XGBoost
* LightGBM

Getting Started
-----------------
_Prerequisites_
Ensure you have Python 3.8+ installed. The following libraries are required:
* numpy
* pandas
* scikit-learn
* matplotlib
* seaborn
* lightgbm
* xgboost
* catboost

Installation
-----------------
```python
pip install -r requirements.txt
```

Running the Project
-----------------
Run the credit-card-fraud-detection.ipynb notebook and run all cells to reproduce the analysis and results.

Results
-----------------
In our quest to develop a robust solution for credit card fraud detection, we evaluated several machine learning models, focusing on their ability to predict fraudulent transactions accurately. Our primary metric for comparison was the Area Under the Receiver Operating Characteristic Curve (AUC), which provides a comprehensive measure of model performance across different threshold settings. Here's a summary of our findings:

* **Random Forest Classifier**: This model served as our baseline, achieving an AUC score of 0.85 on the test set. Its performance establishes a solid foundation, highlighting the potential of ensemble methods in detecting fraudulent activities.

* **AdaBoost Classifier**: Subsequent experimentation with AdaBoost resulted in a slightly lower AUC score of 0.83 for the test set predictions. This indicates that while AdaBoost contributes to reducing bias, it might not capture the complexity of fraudulent transaction patterns as effectively as needed.

* **CatBoost Classifier**: Advancing our exploration, the CatBoost model showed improvement with an AUC score of 0.86 after training for 500 iterations. This model's ability to handle categorical features and reduce overfitting likely contributed to its enhanced performance.

* **XGBoost**: A significant leap in performance was observed with the XGBoost model. Using the validation set for tuning, we achieved a remarkable validation AUC score of 0.984. When applied to the test set, the model demonstrated superior predictive power with an AUC score of 0.974, indicating its efficacy in distinguishing between fraudulent and legitimate transactions with high confidence.

* **LightGBM**: The LightGBM model was evaluated using both a train-validation split and cross-validation methods. For the validation set, we achieved an AUC score of approximately 0.974, consistent with the high performance seen in other models. On the test set, the AUC score reached 0.94, and through cross-validation, we further validated the model's robustness with an AUC score of 0.97. These results underscore LightGBM's efficiency and effectiveness in fraud detection scenarios, benefiting from its gradient-based learning and ability to handle large data volumes.

Comparative Analysis
-----------------
Our investigation reveals a clear trend: gradient boosting models, particularly XGBoost and LightGBM, outperform traditional ensemble methods in detecting credit card fraud. The superior AUC scores of XGBoost (0.974) and LightGBM (up to 0.97) on the test set highlight their capability to capture the nuances of fraudulent transactions more effectively than AdaBoost (0.83) and even our baseline Random Forest model (0.85).
The high performance of XGBoost and LightGBM can be attributed to their sophisticated handling of imbalanced data, feature interactions, and their ability to minimize overfitting while maximizing predictive accuracy. These attributes make them particularly suited for the complexities of fraud detection tasks, where the cost of false negatives (failing to detect fraud) is high.

Conclusion
-----------------
The exploration of various machine learning models in our credit card fraud detection project underscores the critical role of model selection in predictive performance. The standout performance of XGBoost and LightGBM, with their respective AUC scores on the test set, suggests that gradient boosting models hold significant promise for enhancing fraud detection systems. Future work will focus on further optimizing these models and exploring the integration of additional features and data sources to improve detection rates.




