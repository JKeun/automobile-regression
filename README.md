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
    - Inner CV = 5
    - train: 80%
    - validation: 20%
- test set: 20%

**3. Preprocessing**
- Missing values: impute (knn)
- Real variables: scaling
- Categorical variables: dummies

**4. Modeling**
- Linear Models
    - Rdige
    - Lasso
    - Elastic Net
    - Polynomial
- Non-Linear Models
    - Kernel Ridge
    - SVR
    - Ensemble
    - Neural Network
    - Nearest Neighbors

**5. Grid Search & Model Selection (train & validation)**
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
- scaling (https://datascienceschool.net/view-notebook/f43be7d6515b48c0beb909826993c856/)
- linear models (https://datascienceschool.net/view-notebook/83d5e4fff7d64cb2aecfd7e42e1ece5e/)
