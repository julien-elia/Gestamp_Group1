# Gestamp_Group1

This project contains two notebooks:
- "Open_Files.ipynb" has only been used for the initial data exploration purpose only. 
- "Capstone_Final.ipynb" contains all the steps of our project.

You can find below the executive summary.

## Title: Automotive Industry Machine Learning for Quality Control

## By: Maria Botello, Hassan El Mokdad, Julien Elia, Yara Hoteit, and Walid Mneymneh.

## Executive Summary 

Gestamp, a Spanish multinational company specialized in manufacturing of components for world leading automobile manufacturers, faces the challenge of efficiently identifying defects in their cold stamping process. This process consists of four main steps: washing the metal piece, pressing it with dies, imprinting a specific pattern, and manually inspecting for defects. Therefore, we are presenting the development of a machine learning model aimed at automating the quality detection process.

The objective of this project was to leverage machine learning techniques, enabling automated quality detection and reducing the reliance on manual inspection. To achieve this, we started by analyzing hundreds of files provided by the company. Out of all those files, we estimated that only the files containing actual values were necessary for our analysis. Indeed, other files such as the parameters or the asset numbers were removed from the analysis. Thanks to this data selection process, we have reduced the number of features to 77. 

To further reduce the dataset’s size, we proceeded with feature engineering. We started by dropping variables that were null, consistent or duplicated. The next step was to encode the date and time features as cyclical variables, representing the day of the month and time of the day. We then analyzed the correlations between variables, or the logical relationships between them, to create new features. This helped us reduce our dataset size to obtain a more robust and efficient model. Our final dataset consists of 47 features, including the Traceability Code. 

To clean the data, we added a binary variable to verify whether a defect was detected. Out of the 143,994 instances in the dataset, only 528 rows were associated with defects, indicating a class imbalance problem. We then divided our defect detection into two problems. The first one, a binary classification problem, consists of analyzing all parts and classifying them as “defective” or “not defective”. The second problem is a multiclass classification problem, where we separated the defects in 4, the 3 most frequent defects and “Other defects”. 
The binary classification task was solved using a Random Forest classifier, with undersampling, stratification and 10 folds cross validation. This model achieved a good performance, with an AUC of 0.87, precision of 0.98 and recall of 0.84. Even though other models were tested, they were either overfitting or did not offer significant performance improvements. We therefore decided to keep this model as it shows great results in fast computing times.

The multiclass classification task was attacked using a similar approach. The chosen model is again a Random Forest model, this time with randomized search. For the multiclass problem, we can only look at the weighted average precision, which is 0.52. Even though this model does not achieve a great score, it is a good benchmark to keep for once the company collects more defective data.

The implementation of this machine learning model offers several key benefits for Gestamp. Firstly, it significantly reduces the reliance on manual inspection, allowing for faster and  efficient production processes with less human error. By automating the quality detection, the company can improve overall productivity by enabling timely interventions and corrective actions to be taken by having predictions for possible defects. Although this work shows great promise, it can always be improved by adding more data or trying computer vision or deep learning techniques, keeping in mind that the latter will result in a loss of interpretability.

In conclusion, while Gestamp collected a huge amount of data, it was deemed unnecessary to use everything for this defect classification. After analyzing all available data, we have decided to use only the values emitted by the machines to run our models. For the binary classification task, a random forest model was able to predict the defects with an AUC of 0.87, ensuring that the company can now capture a big part of defects before they even happen, thus having a more reliable cold stamping process. 
