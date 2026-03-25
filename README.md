# IEEE-CIS-Fraud-Detection System
📌 Project Overview

This project focuses on detecting fraudulent transactions using the IEEE-CIS Kaggle Fraud Detection dataset. The goal is to build a machine learning model that can identify fraud patterns and provide insights into risky transaction behavior.

The project includes:

Data preprocessing and merging
Exploratory Data Analysis (EDA)
Feature engineering
Model training using LightGBM
Visualization through a Streamlit dashboard
🎯 Objectives
Detect fraudulent transactions accurately
Handle imbalanced data effectively
Identify key factors contributing to fraud
Visualize patterns for business insights
📂 Project Structure
project/
│
├── src/
│   ├── config.py
│   ├── data_loader.py
│   ├── eda.py
│   ├── features.py
│   ├── train.py
│   ├── predict.py
│   ├── utils.py
│
├── data/
│   ├── raw/
│   ├── processed/
│
├── outputs/
│   ├── plots/
│   ├── submission/
│
├── app.py
├── main.py
├── requirements.txt
📊 Dataset
Source: Kaggle IEEE-CIS Fraud Detection
Files used:
train_transaction.csv
train_identity.csv
test_transaction.csv
test_identity.csv

Each transaction includes:

Transaction amount
Product category
Device information
Card details
Email domains
Time-based features
🔍 Exploratory Data Analysis

The following key visualizations were created:

Fraud vs Legitimate Transactions
Transaction Amount Distribution
Transaction Amount Distribution by Fraud Class
Fraud Amount Distribution (Boxplot)
Fraud Rate by Amount Range
Fraud Rate by Product Category
Fraud Rate by Device Type
Top Email Domains Associated with Fraud
Fraud Activity Heatmap
Card Usage Frequency
Model Feature Importance
Key Findings:
Fraud is highly imbalanced
Most transactions are small (right-skewed data)
Fraud occurs in specific transaction ranges
Device, email, and time strongly influence fraud
⚙️ Feature Engineering

New features were created to improve model performance:

Time Features
Hour, day, week extracted from TransactionDT
Amount Features
Log transformation (log(1 + TransactionAmt))
Rounded values and decimal components
Behavioral Features
Email match (sender vs receiver)
Missing value count
Frequency Features
Card usage frequency
Email/domain frequency
Device frequency
🤖 Model
Model Used: LightGBM (LGBMClassifier)
Why LightGBM?
Handles large datasets efficiently
Works well with missing values
Captures complex feature interactions
Strong performance on tabular data
📈 Evaluation Metric
ROC-AUC Score

Typical performance:

Validation ROC-AUC: ~0.93 – 0.96

This metric measures how well the model distinguishes between fraud and non-fraud transactions.

📤 Submission File

The final submission file contains:

TransactionID → Unique transaction identifier
isFraud → Predicted probability of fraud (0 to 1)

The model outputs probabilities instead of binary labels, allowing better ranking of risky transactions.

📊 Streamlit Dashboard

The project includes an interactive dashboard displaying:

All EDA visualizations
Model insights
Fraud patterns
Run the app:
streamlit run app.py
🚀 How to Run the Project
1. Install dependencies
pip install -r requirements.txt
2. Run full pipeline
python main.py
3. Run dashboard
streamlit run app.py
💡 Key Insights
Fraud is rare but follows clear patterns
Certain transaction ranges are riskier
Mobile devices show higher fraud rates
Email mismatches increase fraud probability
Fraud activity varies by time
Repeated card usage indicates suspicious behavior
🔮 Future Improvements
Use advanced models (XGBoost, CatBoost)
Apply anomaly detection techniques
Deploy real-time fraud detection system
Add explainability (SHAP values)
📌 Conclusion

This project demonstrates that combining EDA + feature engineering + machine learning can effectively detect fraud. The model successfully identifies patterns and provides actionable insights for improving fraud detection systems.
