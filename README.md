# Quote-Outlier-Detection

## Description
The objective of this project is to detect outliers within auto-policy data that exhibit substantial deviations from historical data trends. The source dataset encompasses several components, including census, vehicle, and operator datasets. The project involves the design and construction of Autoencoder neural network model to identify outliers within auto quote data. The entire process is eventually deployed through an automated GitLab CI/CD pipeline. This project enables stakeholders to effectively identify emerging changes in quotes data, thereby ensuring the establishment of equitable and fair future insurance rates grounded in a comprehensive array of features.

## Workflow
#### Data Transformation
The comprehensive transformation is executed through a series of Python functions, seamlessly integrated into the dataset pipeline for automated application. The data transformation process encompasses key tasks such as constructing dictionaries for variable type identification, converting columns to their appropriate types, conducting one-hot encoding for categorical variables, implementing missing value imputation, and year-based normalization. Columns with entirely null values have been systematically excluded.

#### Autoencoder Model
An autoencoder, a neural network architecture, was utilized to condense high-dimensional data into a more compact representation, subsequently reconstructing the initial input. This method enables the encapsulation of vehicle details and policy holder information, referred to as observations, through a reduced set of encodings as opposed to the original input values. The model was trained on these observations and deployed to pinpoint outliers based on the magnitude of reconstruction error. In cases where a new observation substantially diverges from the historical dataset, a large reconstruction error is observed.
#### Identify Causes of Changes
Central to the project's objectives is the exploration of disparities between the new observations and the historical data. Observations exhibiting reconstruction errors surpassing the 90th percentile, as depicted in histograms, will be applied through a decision tree to discern feature importance. A SHAP (SHapley Additive exPlanations) is integrated following the decision tree to provide a categorical view of the significance of each feature importance individually.  This comprehensive understanding aids stakeholders in making informed decisions and deriving actionable insights from the outlier detection process, ultimately leading to more effective and targeted strategies for anomaly identification and mitigation.

## Code Files
#### All the files are in order of operation following the above workflow
#### Keys.ipynb
Dictionaries for variable type identification
#### Auto_Outlier_Detection.ipynb
Data transformation
#### Model.ipynb
Autoencoder model
#### AZPAS_Loss_Ratio_Comparison_Tree.ipynb
Identify causes of changes
