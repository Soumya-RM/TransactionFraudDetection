The project focuses on detecting fraudulent credit card transactions using machine learning. The dataset contains over 550,000 transactions, including various features such as transaction amount, timestamp, merchant details, and customer demographics. The target variable, is_fraud, indicates whether a transaction is fraudulent.

* Data Cleaning and Preprocessing:
Date Parsing: The trans_date_trans_time column was split into separate columns for date, hour, and day of the week to facilitate analysis.
Categorical Encoding: Categorical variables like merchant, category, and job were encoded using appropriate techniques such as one-hot encoding or label encoding.
Handling Missing Data: Missing or null values were handled by imputing with mean values or dropping rows where data was critical.
Anonymization: Personal identifiers like first, last, cc_num, and dob were either anonymized or removed for privacy concerns.

* Exploratory Data Analysis (EDA):
Transaction Amount Distribution: The distribution of transaction amounts for both fraud and non-fraud cases was visualized to understand the variance in transaction sizes.
Fraud Distribution by Category: The most common merchant categories and states associated with fraud were identified to understand patterns in fraudulent activity.
Demographic Analysis: The fraud rate was analyzed based on the customer's job, gender, and transaction hour to identify any significant trends.
Fraud Hotspots: Geographic hotspots of fraud were visualized by mapping merchant locations and overlaying fraud occurrence using the merchant’s latitude and longitude.

* Feature Engineering:
Transaction Hour: A new feature was created for transaction_hour, which extracted the hour of the transaction from the timestamp.
Night Transaction: A binary feature, is_night_transaction, was added to indicate if the transaction occurred at night (after 6 PM).
Age Calculation: The age of the customer was derived from the dob column to understand if age played a role in fraud detection.
Distance to Merchant: The distance between the customer’s location and the merchant was calculated using the Haversine formula based on geographic coordinates.
Log Transformation: A log transformation was applied to the amt feature to reduce skewness and better model the distribution of transaction amounts.
Binned Transaction Amount: The amt feature was binned into categories for grouped analysis to examine transaction behavior in specific ranges.

* Model Building:
The dataset was split into training and testing sets (80/20 ratio) to train the machine learning models.
Several binary classification models were trained and evaluated:
Logistic Regression
Random Forest
XGBoost / Gradient Boosting

* Model Evaluation:
The models were evaluated using various performance metrics such as accuracy, precision, recall, and F1 score.
Cross-validation was implemented to ensure the models' robustness and generalization.
Hyperparameter tuning was performed to optimize model performance and improve accuracy.
The final models were compared to determine the best-performing algorithm for fraud detection.
