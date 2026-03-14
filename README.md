# ml_project_credit_risk_model

🏦 Credit Risk Modeling & Scoring System

A machine learning based credit risk scoring system that predicts the probability of loan default, converts it into a credit score, and assigns a risk rating.

The project includes a Streamlit web application where users can enter borrower details and instantly receive a default probability, credit score, and rating.

📊 Project Overview

Financial institutions must evaluate whether a borrower is likely to default on a loan.

This project builds a credit risk model that:

1️⃣ Predicts Probability of Default (PD)
2️⃣ Converts PD into a Credit Score (300–900)
3️⃣ Assigns a Risk Rating

The system replicates a typical credit scoring pipeline used in fintech and banking.

⚙️ Project Architecture
User Input (Streamlit UI)
        ↓
Feature Engineering
        ↓
Data Preprocessing
        ↓
Model Prediction
        ↓
Probability of Default
        ↓
Credit Score Calculation
        ↓
Risk Rating
📂 Project Structure
credit-risk-project/

│
├── main.py                  # Streamlit user interface
├── prediction_helper.py     # Data preprocessing & prediction logic
│
├── artifacts/
│   └── model_data.joblib    # Saved model, scaler, and feature metadata
│
└── README.md
📈 Dataset & Preprocessing

Several preprocessing steps were performed before training the model.

Data Cleaning

Invalid values in loan purpose were replaced using mode imputation.

Feature Engineering

Example features used:

Age

Loan tenure

Credit utilization ratio

Delinquency ratio

Average DPD per delinquency

Loan-to-income ratio

Number of open accounts

Feature Selection

Feature selection was performed using:

Information Value (IV) – measures predictive power of variables

Variance Inflation Factor (VIF) – removes multicollinearity

Domain Knowledge – ensures financial relevance

Feature Scaling

Numeric features were scaled using:

MinMaxScaler

This ensures features are in the same range and improves model performance.

🔀 Train Test Split

The dataset was split into training and testing sets.

Typical splits used in modeling:

Train : 70%
Test  : 30%

During project discussions or model reviews, business teams may ask questions such as:

"Why didn’t you use an 80–20 split?"

These discussions help ensure the modeling approach is aligned with business requirements and technical standards.

🤖 Model Training

Multiple machine learning models were tested:

Logistic Regression

Random Forest

Gradient Boosting / XGBoost (if applicable)

Hyperparameter tuning was performed using:

RandomizedSearchCV

Optuna

This helps find the best combination of model parameters.

📊 Model Evaluation

Several evaluation metrics were used:

Metric	Purpose
AUC	Measures model discrimination
KS Statistic	Separation between good and bad borrowers
Gini Coefficient	Credit scoring performance
Classification Report	Precision, recall, F1-score

These metrics are commonly used in credit risk modeling.

🧠 Credit Score Generation

The trained model predicts probability of default using logistic regression.

The probability is converted into a credit score using:

Credit Score = 300 + (Non-Default Probability × 600)

Score Range:

300 → 900

Higher scores indicate lower risk.

🏷️ Risk Rating

Borrowers are classified into risk categories:

Score Range	Rating
300–499	Poor
500–649	Average
650–749	Good
750–900	Excellent
💻 Streamlit Web Application

The Streamlit application allows users to input borrower details and obtain predictions instantly.

User Inputs

Age

Income

Loan amount

Loan tenure

Credit utilization

Delinquency ratio

Residence type

Loan purpose

Loan type

Output

The app displays:

Default Probability

Credit Score

Risk Rating

🚀 Running the Application
Install dependencies
pip install -r requirements.txt
Run the Streamlit app
streamlit run main.py
🧰 Technologies Used

Python

Pandas

NumPy

Scikit-learn

Optuna

Streamlit

Joblib
