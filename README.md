# Comparing_Classifiers

## Introduction

This README file provides a summary of findings for Practical Application Assignment III: Comparing_Classifiers.

The accompanying Jupyter notebook can be [found here](). 

## The objective and the data

The objective of this assignment is to compare the performance of the classifiers (dummy classifier, k-nearest neighbors, logistic regression, decision trees, and support vector machines). The data for this assignment could be found [here](https://archive.ics.uci.edu/dataset/222/bank+marketing).


## The business objective 

The business objective is to find a machine learning model that would predict whether a customer would open a long term deposit or not. The model will help improve the efficiency of marketing campaings by adjusting the campaign's parameters according to the model

## The methods

The methodology for this assignment was based on CRISP_DM framework and included standard ML stages like Business and Data understanding, Data preparation, etc. 

## Models evaluation metrics

The dataset is highly imbalanced, so the standard accuracy score is not a good metric for this case. Given the business problem, the **precision score** seems to be more appropriate. The precision is intuitively the ability of the classifier not to label as positive a sample that is negative. In this context, it means the customer does not open long term deposit, but the model predicts the opposite. This type of error would impact revenue forecast negatively and everybody hates when it happens.


## Data quality and data preparation highlights

The data had no missing values. The categorical variables were target encoded. Standard scaled was applied.

## Models performance with the default parameters.

The accuracy scores and train times for each model can be found in table 1.

|  Model  | Train score | Test score| Train times, s| 
|---------|-------------|-----------|---------------|
| Dummy   | 0.0         | 0.0       | 0.004         |
| Logistic| 0.664	    | 0.667     | 0.0990        |       
| KNN     | 0.745       | 0.575     | 0.0151        |       
| D. Tree | 1.0         | 0.49      | 0.1478        |  
| SVM     | 0.749       | 0.664     | 5.0280        |
|---------|-------------|-----------|---------------|



## Feature importance

In order to assess feature importance, coefficients for the linear model were examined (Fig.7.) as well as the SHAP values (Fig.8.).

<img src="/images/7.png" alt="Fig.7" class="center" style="width:600px;height:auto;">

<img src="/images/8.png" alt="Fig.8" class="center" style="width:600px;height:auto;">

## Results and discussion

We can see that there is only one independent variable, "odometer", that has a strong negative relationship with the price target. Which makes sense, the more miles car had driven, the less valuable it becomes.

In terms of effect sizes of the variables, we can see that aside from the odometer variable, there are six more variable that display sizeable effect. 

We get similar results from Shap. As we can see from the Shap plot, the higher odometor values negatively impact the price. While lower values of year also negatively impact the price which also makes sense.

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