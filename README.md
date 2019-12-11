# Prediction of Adult Income based on Census Data

## Contributors:
- Ramachandra Gopal Posina
- Akhil Morampudi
- Mahanth Mukesh Dadisetty
- Bharadwaj Aryasomayajula
- Dinesh Deshi

## Domain:
Income of US Citizes, Census Bureau
  
## Objective:
The goal of this project is to predict if an individual’s income exceeds 50K or not using machine learning classification algorithms and also finding patters in the dataset using Association rules. This helps us to determine various things such as lucrativeness of setting up a business in a city based on average income of the people, Real Estate preferences and bank loan eligibility for a particular person. In addition, we can also figure out what type of tourist places a particular strata of people would like to visit and whether that person’s children would prefer a public or private college in future.

## Data and Source Description
#### Dataset : Adult Census Income from Kaggle
#### Source of the Data :  
https://www.kaggle.com/uciml/adult-census-income

This data was extracted from the 1994 Census bureau database by Ronny Kohavi and Barry Becker (Data Mining and Visualization, Silicon Graphics). The prediction task is to predict whether income exceeds $50k per year based on the provided. census data provided above. The Datasets consists of a list of records , each of which explains various features of a person along with his income per year. 

<b>A brief description of the features are as follows:</b>  
<b>Target:</b>  
income : >50K, <=50K  
  
<b>Predictors:</b>  
age: continuous
workclass: Private, Self-emp-not-inc, Self-emp-inc, Federal-gov, Local-gov, State-gov, Without-pay, Never-worked  
fnlwgt: continuous  
education: Bachelors, Some-college, 11th, HS-grad, Prof-school, Assoc-acdm, Assoc-voc, 9th, 7th-8th, 12th, Masters, 1st-4th, 10th, Doctorate, 5th-6th, Preschool  
education-num: continuous  
marital-status: Married-civ-spouse, Divorced, Never-married, Separated, Widowed, Married-spouse-absent, Married-AF-spouse  
occupation: Tech-support, Craft-repair, Other-service, Sales, Exec-managerial, Prof-specialty, Handlers-cleaners, Machine-op-inspct, Adm-clerical, Farming-fishing, Transport-moving, Priv-house-serv, Protective-serv, Armed-Forces  
relationship: Wife, Own-child, Husband, Not-in-family, Other-relative, Unmarried  
race: White, Asian-Pac-Islander, Amer-Indian-Eskimo, Other, Black  
sex: Female, Male  
capital-gain: continuous  
capital-loss: continuous
hours-per-week: continuous
native-country: United-States, Cambodia, England, Puerto-Rico, Canada, Germany, Outlying-US(Guam-USVI-etc), India, Japan, Greece, South, China, Cuba, Iran, Honduras, Philippines, Italy, Poland, Jamaica, Vietnam, Mexico, Portugal, Ireland, France, Dominican-Republic, Laos, Ecuador, Taiwan, Haiti, Columbia, Hungary, Guatemala, Nicaragua, Scotland, Thailand, Yugoslavia, El-Salvador, Trinadad&Tobago, Peru, Hong, Holand-Netherlands 
  
## Application of the CRISP-DM Process
   - Data Understanding Phase
   - Data Preparation Phase
   - Modeling Phase
   - Evaluation Phase
   - Deployment Phase

## Data Understanding and Data Preparation

Data Pre-Processing and Exploratory Data Analysis has been performed on the data and below are the observations


#### Bias in the data:
AI Fairness 360 by IBM implements several pre-processing mitigation algorithms. We will choose the Optimized Preprocess algorithm, which is implemented in “OptimPreproc” class in the “aif360.algorithms.preprocessing” directory. This algorithm will transform the dataset to have more equity in positive outcomes on the protected attribute for the privileged and unprivileged groups.

<b>Bias in original dataset:</b> Difference in mean outcomes between unprivileged and privileged groups = -0.104553  
<b>Bias after mitigation:</b> Difference in mean outcomes between unprivileged and privileged groups = -0.051074


#### Preliminary Observations:
1. The no of records having income less than 50k dollars is more than the no of records having income more than 50k dollars income. The dataset needs to be balanced with the    target values so that the models do not overfit the data.
2. The capital.gain and capital.loss values contain zeroes, so these columns can be dropped.  
3. Scatter plots and bar plots are plotted to find the distribution of various values of categorical values.  
4. Hours.per.week has a value of 40 in most of the records, so this field can be dropped.
5. The fnlwgt values are mostly in the range of 0-40,000 and are of age 20 to 40.
6. The outliers are present in some of the continuous variables which need to the handled properly.
    
    
## Machine Learning

  1.Performed Logistic Regression on the model and calculated the performance metrics of the model and computed the scores   
  2.Association Rules(For finding patters in the Dataset)  
  3.K-Fold Cross Validation  
  4.Applying CART algorithms to choose the best algorithm based on the metrics obtained.  
  5.Using ensemble learning implemented neural networks
    
## Evaluation

Model evaluation metrics are required to quantify model performance. The choice of evaluation metrics depends on a given machine learning task (such as classification, regression, ranking, clustering, topic modeling, among others). Some metrics, such as precision-recall, are useful for multiple tasks. 

Classification Metrics include the following scores

1.Classification Accuracy

2.Confusion Matrix

3.F1 score on test 

4.Precision

5.Specificity 

6.Recall 

1.Classification Accuracy:
Accuracy is a common evaluation metric for classification problems. It’s the number of correct predictions made as a ratio of all predictions made. We use sklearn module to compute the accuracy of a classification task

2.Confusion Matrix
A confusion matrix provides a more detailed breakdown of correct and incorrect classifications for each class.The diagonal elements represent the number of points for which the predicted label is equal to the true label, while anything off the diagonal was mislabeled by the classifier. Therefore, the higher the diagonal values of the confusion matrix the better, indicating many correct predictions.

3.Area under Curve (AUC)
Area under ROC Curve is a performance metric for measuring the ability of a binary classifier to discriminate between positive and negative classes.

4.F-Measure
F-measure (also F-score) is a measure of a test’s accuracy that considers both the precision and the recall of the test to compute the score. Precision is the number of correct positive results divided by the total predicted positive observations.

5.Recall, 
Itis the number of correct positive results divided by the number of all relevant samples (total actual positives).

<b>Evaulation scores & Performance metrics obtained in our model:</b>

Accuracy on test: 0.8019891500904159 

F1 score on test: 0.49

Precision : 0.7720364741641338 

Specificity : 0.9697824335213537 

Recall : 0.580

## Future Scope
- Design a machine learning pipeline and feed the ensemble learning

## Conclusion
Finally from the dataset we predict whether a person makes over $50K a year or not.  
Find Patters in the dataset  
K-Fold cross validation
