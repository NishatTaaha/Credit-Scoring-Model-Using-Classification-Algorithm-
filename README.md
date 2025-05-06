
# 🧾 Credit Scoring Model - Code Overview

## 🔹 2. Feature Engineering

### 🔸 Categorical Features
The model includes the following categorical variables, which are encoded using **OneHotEncoder**:
* `CheckingAccountStatus`
* `CreditHistory`
* `Purpose`
* `SavingsAccount`
* `EmploymentSince`
* `PersonalStatusSex`
* `OtherDebtors`
* `Property`
* `OtherInstallmentPlans`
* `Housing`
* `Job`
* `Telephone`
* `ForeignWorker`

### 🔸 Numerical Features
These features are scaled using **StandardScaler**:
* `Duration`
* `CreditAmount`
* `InstallmentRate`
* `PresentResidenceSince`
* `Age`
* `NumberExistingCredits`
* `NumberPeopleLiable`

## 🔹 3. Methodology

### 🔸 Step 1: Data Loading
* Load the credit dataset using `pandas`.

### 🔸 Step 2: Preprocessing
* Identify categorical and numerical columns.
* Build separate transformers:
  * `OneHotEncoder` for categorical columns.
  * `StandardScaler` for numerical columns.
* Combine them using `ColumnTransformer`.

### 🔸 Step 3: Pipeline Construction
* Create a pipeline combining the preprocessing steps and the classifier:
  ```python
  Pipeline([
      ('preprocessor', ColumnTransformer(...)),
      ('classifier', LogisticRegression())
  ])
  ```
  
### 🔸 Step 4: Model Training
* Split data into training and testing sets (80% training, 20% testing).
* Train the pipeline on the training data.

### 🔸 Step 5: Model Evaluation
* Predict on the test set.
* Generate:
  * **Confusion Matrix**
  * **Classification Report** (Precision, Recall, F1-score)
  * **ROC Curve** and **AUC Score**

## 🔹 4. Final Output & Insights
* The model predicts whether a credit applicant is **low-risk (good)** or **high-risk (bad)**.
* Evaluated using AUC and classification metrics to judge its ability to separate good vs. bad credit applicants.


