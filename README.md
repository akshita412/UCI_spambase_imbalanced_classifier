# Project Overview
This project repository is created to classify if an email is spam or not on the basis of 2 approaches.

## Key Question
The upsurge in the volume of unwanted emails called spam has created an intense need for the development of more dependable and robust antispam filters. How can we utilise ML models to flag spam messages?
Additionally, can we incorporate a different leg of evaluation? For instance, generic model evaluation is the go-to method but can we also build a cost-sensitive classification model?


## Dataset
The dataset is from UCI machine learning repository. Specifically, 
(i) file “spambase.data” contains the actual data, and 
(ii) files “spambase.names” and “spambase.DOCUMENTATION” contain the description of the data.

This dataset has 4601 records, each record representing a different email message. Each record is described with 58 attributes (indicated in the aforementioned .names file): attributes 1-57 represent various content-based characteristics already extracted from each email message (related to the frequency of certain words or certain punctuation symbols in a message as well as to the usage of capital letters in a message), and the last attribute represents the class label for each message (spam or non-spam).

Dataset link: http://archive.ics.uci.edu/ml/datasets/Spambase


## Approach
- Some initital EDA and anomaly detection checks are performed, correlation was checked.
- Different models performances were observed. The models were:
    - Logistic
    - KNN
    - SVC

## Results
- Model Performance based: The best performance is achieved by SVM classifier out of Logistic Regression, KNN and SVM classifiers that were tried. Not only, it has hugher base metrics like accuracy, precision, fscore. But, it also has higher MCC & kappa. This signifies that it has better, effectively distinguishable performance for the imbalanced classes.

- Cost analysis based: For the cost analysis, the minimal costs come up for 3 values at different thresholds. For the KNN classifier, the threshold should be 0.2 to achieve minimum cost For, Logistic and SVM classifiers, it should be 0.3 Logistic and SVM have pretty similar performances pertaining to cost. This is also because they have similar performance. The cost matrix has been designed in such a way that for every correctly identified spam, the company is able to save USD5000 and for every incorrect identification of a correct mail, the company loses USD1000, or that is the cost company has to bear. For every spam that is not identified, the company loses USD100

- Based on the above statements and analysis on both cost and model performance, a SVM classifier should be chosen as it would render best results in terms of both.
