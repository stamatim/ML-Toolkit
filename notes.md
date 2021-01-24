Note: Distinguish Categorical Variables vs. Numeric Variables

## 5 Methods of Building Models:
1. All in
  - Requires prior knowledge or 
  - It is unavoidable and you have to use it
  - Preparing for backwards elimination
  - Process:
    - Step 1. Select a criterion of goodness of fit (e.g. Akaike criterion)
    - Step 2. Construct all possible regression models: $2^n$ total combinations
    - Step 3. Select the one with the best criterion.
    - Step 4. FIN (your model is ready)
2. Backwards elimination
  - Step 1: Select a significance level to stay in the model
  - Step 2: Fit the full model with all possible predictors
  - Step 3: Consider the predictor with the highest P-value. If `P > SL`, go to Step 4, otherwise, go to FIN
  - Step 4: Remove the predictor
  - Step 5: Fit model without this variable. Go back to Step 3
3. Forward selection
  - Step 1. Select a significance level to enter the model (e.g. SL = 0.05)
  - Step 2. Fit all simple regression models **`y ~ x_n`**. Select the one with the lowest P-value
  - Step 3. Keep this variable and fit all possible methods with one extra predictor added to the one(s) you already have
  - Step 4. Consider the predictor with the lowest P-value. If `P < SL`, go to Step 3, otherwise, go to `FIN`
4. Bidirectional elimination
  - Step 1. Select a significance level to enter and to stay in the model (e.g. SLENTER = 0.05, SLSTAY = 0.05)
  - Step 2. Perform the next step of Forward Selection (new variables must have: P < SLENTER to enter)
  - Step 3. Perform ALL steps of the Backward Elimination (old veriables must have P < SLSTAY to stay). Go back to step 2.
  - Step 4. No new variables can enter and no old variables can exit
5. Score comparison

## SVR (Support Vector Regression)

Outliers not caught well with SVR model

## Decision Trees

No need for feature scaling in decision tree and random forest regression

## Random Forests

A version of ensemble learning - taking the same algorithm multiple times to get an output more powerful than the original input

Steps:
1. Pick (at random) K data points from the training set
2. Build the decision tree associated to these K data points
3. Choose the number of Ntree of trees you want to build and repeat steps 1 and 2
4. For a new data point, make each one of your Ntree trees predict the value of Y to for the data point in question, and assign the new data point the average across all of the predicted Y values.

## R Squared

What is $R^2$?
* Representative value of the best fit of a regression model. 
  * The greater the value for *R^2$, the better
* The problem with $R^2$:
  * If you keep adding independent variables to your regression model, you will not know if they are helping or not helping the model. 
* *See [this](https://www.geeksforgeeks.org/ml-r-squared-in-regression-analysis/) for more info*

$$SS_{residual} = \sum(y_i - \hat {y_i})^2$$

$$SS_{total} = \sum(y_i - \hat y_{avg})^2$$ 

Given these equations, the final equation for $R^2$ is:

$$R^2 = 1 - \frac{SS_{res}}{SS_{tot}}$$

The same concepts apply for $R^2$ for *linear* AND *multiple* linear regression.

The adjusted $R^2$ equation penalizes you for adding independent variables that DO NOT help your model.

$$Adj R^2 = 1 - (1 - R^2)\frac{n-1}{n-p-1}$$

where $p$ is the number of regressors and $n$ is the sample size.

