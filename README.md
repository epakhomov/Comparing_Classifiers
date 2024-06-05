# Comparing_Classifiers

## Introduction

This README file provides a summary of findings for Practical Application Assignment III: Comparing_Classifiers.

The accompanying Jupyter notebook can be [found here](). 

## The objective and the data

The objective of this assignment is to compare the performance of the classifiers (dummy classifier, k-nearest neighbors, logistic regression, decision trees, and support vector machines). The dataset for this assignment could be found [here](https://archive.ics.uci.edu/dataset/222/bank+marketing).


## The business objective 

The business objective is to find a machine learning model that would predict whether a customer would open a long term deposit or not. The model will help improve the efficiency of marketing campaings by adjusting the campaign's parameters according to the model

## The methods

The methodology for this assignment was based on CRISP_DM framework and included standard ML stages like Business and Data understanding, Data preparation, etc. 

## Models evaluation metrics

The dataset is highly imbalanced, so the standard accuracy score is not a good metric for this case. Given the business problem, the **precision score** seems to be more appropriate. The precision is intuitively the ability of the classifier not to label as positive a sample that is negative. In this context, it means the customer does not open long term deposit, but the model predicts the opposite. This type of error would impact revenue forecast negatively and everybody hates when it happens.


## Data quality and data preparation highlights

The data had no missing values. The categorical variables were target encoded. Standard scaled was applied.

## Models performance with the default parameters.

The accuracy scores and train times for each model can be found in Table 1.

|  Model  | Train score | Test score| Train times, s| 
|---------|-------------|-----------|---------------|
| Dummy   | 0.0         | 0.0       | 0.004         |
| Logistic| 0.664	    | 0.667     | 0.0990        |       
| KNN     | 0.745       | 0.575     | 0.0151        |       
| D. Tree | 1.0         | 0.49      | 0.1478        |  
| SVM     | 0.749       | 0.664     | 5.0280        |


## Hyperparameters tuning

GridSearchCV was applied to each model to find the best hyperparameters. The comparison of precision scores for the **test data** for models with default hyperparameters and best hyperparameters can be found in Table 2.

|  Model  | Default     | Best      | 
|---------|-------------|-----------|
| Logistic| 0.667       | 0.665     |
| KNN     | 0.575	    | 0.602     | 
| D. Tree | 0.49        | 0.593     | 
| SVM     | 0.664       | 0.691     |

Best parameters for the SVM were: C=0.1, gamma='scale', kernel='poly'

## Feature selection 

To further improve the performance, Sequential Feature Selector was used to remove (backward selection) features to form a feature subset for SVM with the best parameters found earlier with GridSearchCV.


## Results and discussion

### Precision score interpretation

Precision is a metric used in machine learning to measure how often a model's positive predictions are correct. The higher the score, the better model performed. According to various sources, precision needs to be at minimum 70-80% (0.7-0.8) for a model to be useful. 

## Next steps

We can try improving the model performance by the following:
- Improving data preparation and cleaning stages
- Acquiring more data from the original dataset
- Applying non-linear models

## Non-technical recommendation to a dealership

Dear sellers,

I'd like to discuss what factors or properties of a used car make it less or more expensive from a buyer's perspective and what you can do it about it. As we all know, different buyers value different things in a car. For example, someone who likes music will be looking at an acoustic system and properties of a car, someone who doesn't like music, wouldn't really care about it that much. Therefore, we will be looking at properties of a car that are important to the vast majority of the buyers. This information should increase sales of the inventory.

According to the analysis, the two most important properties are current mileage and year when the car was made. The bigger value of the odometer is, the lower price a customer is willing to pay for a car. The opposite is also true, customers are willing to pay more money for the cars with lower mileage. 

Regarding the year of a car, the older car is, less valuable the car becomes from a buyer perspective. The condition of a car doesn't seem to be a strong factor. That is most likely due to the fact (unless the body is visibly damaged), that a true condition of internal important parts of the car(engine, brakes, etc.) is unknown most of the time.

Based on this analysis, we recommend the following: 

1) Don't let the original sellers to leverage any other properties of a car to get a better deal with you. Remember, the most important properties are current mileage and the year when the car was made. As an example, If a car was manufactured many years ago and has a lot of miles on it, it doesn't really matter if it has an unusual color. 

2) In order to maximize the revenue, our recommendation is to focus on buying (from the original owners) cars manufactured in recent years and that have low odometer values. The ROI from buying newer cars from owners should be higher than ROI from buying any cars.