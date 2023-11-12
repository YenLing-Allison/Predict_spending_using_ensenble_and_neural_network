# Predict_spending_using_ensenble_and_neural_network
https://github.com/YenLing-Allison/Predict_spending_using_ensenble_and_neural_network

# Business Question
Use numeric prediction techniques to build a predictive model for the spending dataset. This dataset is provided on the course website and contains data about whether or not different consumers made a purchase in response to a test mailing of a certain catalog and, in case of a purchase, how much money each consumer spent.

# Action
1. Build numeric prediction models that predict Spending based on the other available customer information (obviously, not including the Purchase attribute among the inputs!). Use linear regression, k-NN, regression tree, SVM regreesion and Neural Network and ensembling models.
2. As a variation on this exercise, create a separate “restricted” dataset (i.e., a subset of the original dataset), which includes only purchase records (i.e., where Purchase = 1). Build numeric prediction models to predict Spending for this restricted dataset. 

# Data Resource
Dataset: HW3.xlsx 
This dataset has two possible outcome variables: Purchase (0/1 value: whether or not the purchase was made) and Spending (numeric value: amount spent).

# Analysis Process
1. Input
   * Processed model hyperparameters  
   * Scaling method
2. Inner loop   
   * Tune hyperparameters  
   * Searching optimal hyperparameters  
3. Outer loop  
   * Retrain on training set
   * Predict on testing set
4. Build six models
   * Linear regression 
   * K-NN
   * Regression tree 
   * SVM regression
   * Neural Network
   * Ensembling models - Random forest, Stacking, Gradient Boosting
5. Rebuild models again using optimal model  
   * Train-test split and build the model
   * Make prediction
6. Summarize performance  
   * Confusion matrix, predictive accuracy, precision, recall, f-measure
   * ROC and Lift curve


# Model comparison without 'purchase' vs with 'purchase' = 1   
| Model | MSE without 'purchase' | MSE with 'purchase' = 1 |
| --- | --- | --- |
| Regression Tree | 17047 | 32329 |
| Linear Regression | 16387 | 26908 |
| KNN | 21404 | 34003 |
| SVR | 18279 | 29163 |
| Stacking Regressor | 15862 | 26655 |
| Baging Regressor | 16364 | 26585 |
| ***GradientBoosting Regressor*** | ***15852*** | ***25269*** |
| Neural Network | 30937 | 50317 |

# Discuss
Overall, **models without column 'purchase' perform well than models with column 'purchase' = 1**.  
This is because with column 'purchase' = 1, it only has half of whole dataset and the spending variation will be larger than the data without column 'purchase', which has whole dataset. Therefore, sample data size influence predictive results and have different variations on other columns such as sources, frequence, days_ago and so on.

