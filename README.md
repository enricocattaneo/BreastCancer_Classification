# Breast Cancer Classification

**OBJECTIVE**: Use the Breast Cancer Wisconsin (Diagnostic) Database and compare different classification models to help diagnose patients.

## Table of Contents

- [Data Description](#datadescription)
- [Data Preparation](#datapreparation)
- [Classification Models](#classificationmodels)
- [Results](#results)


<a id='datadescription'></a>
## Data Description
This is a copy of UCI ML Breast Cancer Wisconsin (Diagnostic) datasets. (https://goo.gl/U2Uwz2)

**Number of Instances**: 569

**Number of Attributes**: 30 numeric, predictive attributes and the class

**Attribute Information**:
* radius (mean of distances from center to points on the perimeter)
* texture (standard deviation of gray-scale values)
* perimeter
* area
* smoothness (local variation in radius lengths)
* compactness (perimeter^2 / area - 1.0)
* concavity (severity of concave portions of the contour)
* concave points (number of concave portions of the contour)
* symmetry
* fractal dimension ("coastline approximation" - 1)
* class (WDBC-Malignant - 0, WDBC-Benign - 1)

(The mean, standard error, and "worst" or largest (mean of the three worst/largest values) of these features were computed for each image, resulting in 30 features.  For instance, field 0 is Mean Radius, field 10 is Radius SE, field 20 is Worst Radius).

Features are computed from a digitized image of a fine needle aspirate (FNA) of a breast mass. They describe characteristics of the cell nuclei present in the image.


<a id='datapreparation'></a>
## Data Preparation
Preliminary data analysis. We also split the data into training and test sets.

![output](https://user-images.githubusercontent.com/80990030/182133835-2c2720ea-2b5d-4db4-b33f-38ba4a54caec.png)

<a id='classificationmodels'></a>
## Classification Models
The use of accuracy, the most common metric for evaluating classification models, may bring some issues. When addressing this classification problem, an important consideration has to be made. The accuracy of an ML model describes how many data points were detected correctly and is formally defined as: 

$Accuracy = \frac{True Positive + True Negative}{True Positive + True Negative + False Positive + False Negative}$

This metric weights both false positive and false negative observations the same. Since, in this particular study, we are considering the classification of breast cancer, we have to be cautious when considering such a metric. The misclassification of a person with cancer carries more dangerous implications than that of a healthy patient. What if a patient has cancer, but no treatment is given because our model predicted so? (That is a situation we would like to avoid!)

Once we make this important consideration, the use of the recall (or sensitivity), which is another metric for the evaluation of classification models, makes more sense. The recall describes how many true positives were recalled (found) by the model. It is calculated by dividing the true positives by the total actual positive. 

$Recall = \frac{True Positive}{True Positive + False Negative}$

Recall should be the model metric we use to select our best model when there is a high cost associated with False Negative (as in this case). 

So we conduct a parallel analysis considering either accuracy or recall for multiple Machine Learning models: 
* K-nearest neighbors
* Naive Bayes 
* Logistic regression
* Decision tree
* Random forest
* AdaBoost
* Gradient boosting
* Artificial neural network


<img width="1338" alt="Schermata 2022-08-01 alle 13 06 21" src="https://user-images.githubusercontent.com/80990030/182135341-9474b312-668d-42b9-948b-f016f19ccb50.png">


<a id='results'></a>
## Results
The performance is the same between Gradient Boosting and Logistic Regression in terms of accuracy. The former has higher precision, while the latter has a better recall. Since, as we highlighted before, recall is the most appropriate metric in this study, we prefer the Logistic model.

<img width="600" alt="Schermata 2022-08-01 alle 13 23 22" src="https://user-images.githubusercontent.com/80990030/182138090-91bf3093-80e1-4a27-9cfa-66f95c5c977f.png">

<img width="400" alt="Schermata 2022-08-01 alle 13 22 58" src="https://user-images.githubusercontent.com/80990030/182138111-574276ee-c73e-4c87-9aa4-9aeec2ece386.png">

<img width="400" alt="Schermata 2022-08-01 alle 13 23 08" src="https://user-images.githubusercontent.com/80990030/182138126-9c39d235-43b9-4876-8527-3df5cfbce5fe.png">
