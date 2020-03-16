# Loan-Prediction

Step 1:
Clean and prepare the data: There are several entries where values have been deleted to simulate dirty data. 


Step 2:
Build  models: 


All the models work relatively well and among them Gradient Boosting Regressor returned the most robust result with the lowest RMSE. I fit the models by each subgrade since the grades and subgrades are extremally important features, they might overshadow other features. However, I tried fitting model by subgrades or otherwise, the results are not that different.
Model 1: Linear regression
Linear regression is the least complex model among all of them. Easy to fit and fast to run. With 0.79 train error and 0.8 testing error without tuning, linear regression does not tend to over-fit. However, the result is not the best among all the models.
Model 2: Random Forest
Although testing error of random forest is only 0.39, the training error is up to 0.77. definitely over fitting. I tried to tune the parameters but cannot resolve the situation. Apart from that, we can extract feature importance from random forest models to help with feature selection.
Model 3: Support Vector Regressor
Tried to fit the model using linear, polynomial regressor and find out the result from kernel=linear is pretty much the same as our linear model and polynomial took too much time to run. In the end, settle for rbf, the result shows no-overfitting with 0.84 testing and training error.
Model 4: Gradient Boosting Regressor
Gradient Boosting Regressor gave the best result (training error 0.77 and testing error 0.79) with a little bit tuning (learning rate from 0.1 to 0.05, n_estimators from 100 to 500)
Model 5: StackingRegressor (RF and GBR)
Tried to stack random forest and gradient boosting regressor. The result shows overfitting with 0.13 training error and 0.82 testing error. Besides, it took a while to run.
