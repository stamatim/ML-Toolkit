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

## SVR Intuition
