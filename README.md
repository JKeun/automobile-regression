### Problem name: automobile
- URL: https://archive.ics.uci.edu/ml/datasets/automobile
- Target: normalized-losses
- Missing values: denoted by quotation marks ('?'). Skip data samples with missing values in the target
- Features to ignore: 'symboling'

### Data layout
- Number of Instances: 205
- Number of Attributes: 26 total
    - 15 continuous
    - 1 integer
    - 10 nominal

### Process
**1. Data Preparation**
    
- remove 'symboling' feature
- change cat values to numeric ("num-of-doors", "num-of-cylinders")
- apply "?" to NaN
- remove samples with missing values in the target("normalized-losses"): 164 samples remained
- impute missing values in features ("num-of-doors", "bore", "stroke", "horespower", "peak-rpm", "price")
- divide "numeric" & "categorical" group

**2. Data Split**
- Outer CV = 5
- modeling set: 80%
    - Inner CV = 10
    - train: 80%
    - validation: 20%
- test set: 20%

**3. Preprocessing**
- Missing values: impute (knn)
- Real variables: scaling
- Categorical variables: dummies

**4. Modeling**
- Linear Regression; Simple, Ridge, Lasso, Elastic Net, GLM
- Naive Bayes
- DT, GBM, RF
- SVM

**4. Grid Search & Model Selection (train & validation)**
- Pipeline
    - model
    - parameters range
    - scoring: neg_mean_squared_error
- Parameter Search
    - Scatter Plot (parameter X score)
    - best parameters
    - best score

**5. Evaluation (test)**
- Outer CV = 5
    - predictions
    - scores & mean score


### Reference
- how to handle missing data (https://towardsdatascience.com/how-to-handle-missing-data-8646b18db0d4)
