# Customer-Satisfaction-CSAT-Score-Prediction-using-Machine-Learning-Deep-Learning

# Project Summary
The objective of this project was to build a model to predict Customer Satisfaction (CSAT) scores based on customer interaction data. CSAT is an important metric used by companies to measure how satisfied customers are with the services they receive. Predicting CSAT scores can help organizations identify service issues and improve customer experience.

The dataset contained several features such as channel name, category, sub-category, customer remarks, agent details, tenure bucket, shift information, response time, and issue timestamps. The target variable was the CSAT Score, which ranges from 1 to 5. Since the goal was to predict a numerical value, the problem was treated as a regression task.

The first step of the project was data wrangling, where the dataset was cleaned and prepared for analysis. Missing values were handled using mode imputation, and columns with very high cardinality, such as Agent_name, were removed because they added complexity without improving model performance. Outliers in numerical features like response_time_minutes were identified using the IQR method. These steps helped make the dataset suitable for modeling.

Next, exploratory data analysis (EDA) was performed to understand the dataset and identify patterns. Various visualizations were used to analyze relationships between features and the CSAT score. It was observed that the dataset was highly skewed toward CSAT score 5, which indicates that most customers reported high satisfaction.

After EDA, feature engineering and preprocessing were performed. Categorical variables such as channel name and category were converted into numerical format using One-Hot Encoding. The Customer Remarks column contained text data, so it was processed using natural language processing techniques such as text cleaning, tokenization, stop word removal, and lemmatization. The cleaned text was then converted into numerical features using TF-IDF vectorization, which captures the importance of words in customer feedback.

Since TF-IDF created a large number of features, Principal Component Analysis (PCA) was applied to reduce the dimensionality of the dataset while preserving the most important information. Numerical features were also scaled using StandardScaler to ensure that all features were on a similar scale.

The dataset was then split into training and testing sets using an 80:20 ratio. The training data was used to build the models, while the testing data was used to evaluate their performance.

Three models were trained and compared: Artificial Neural Network (ANN), Random Forest Regressor, and XGBoost Regressor. The models were evaluated using R² Score and Mean Absolute Error (MAE). Among the three models, XGBoost performed the best, achieving the highest R² score, which indicates better predictive capability.

In conclusion, this project shows how machine learning and deep learning techniques can be used to analyze customer feedback and predict satisfaction scores. The model can help organizations understand customer experiences and make better decisions to improve service quality and customer satisfaction.

# Problem Statement

The primary object of this project is to develop a deep learning model that can accurately predict the CSAT score based on customer interactions and feedback. By doing so, we aim to provide e-commerce businesses with a powerful tool to monitor and enhance customer satisfication in real time, thereby improving service quality and fostering customer loyalty.

# Dataset Description

The dataset contains customer interaction details, agent information, and customer feedback remarks.

Key variables include:

Feature	Description
channel_name-	Communication channel used by the customer
category	-Issue category
sub-category	-Detailed issue classification
customer remarks	Text feedback provided by the customer
response_time_minutes	Time taken to respond to the customer
issue_hour	Hour when the issue was raised
issue_day	Day of the month
issue_month	Month of the issue
CSAT Score	Target variable representing customer satisfaction (1–5)

# Project Workflow

# 1 Data Wrangling

Data wrangling was performed to clean and prepare the dataset for analysis.
Steps performed:

Handling missing values
Fixing incorrect data types
Dropping irrelevant features
Creating time-based features such as issue hour, day, and month
Handling duplicated data
This step ensured that the dataset became analysis-ready and suitable for model training.

# 2 Exploratory Data Analysis (EDA)

EDA was conducted to understand the distribution of variables and identify patterns in the data.
Visualizations used:

count plot
boxplot
Correlation heatmaps
Pairplots

Key insights were identified regarding customer response time and satisfaction levels.

# 3 Hypothesis Testing

Statistical hypothesis testing was performed to evaluate relationships between variables.
hypothesis:

Null Hypothesis: Response time has no relationship with CSAT score
Alternative Hypothesis: Response time significantly affects CSAT score

Pearson correlation testing was used to evaluate the relationship between variables.

# 4 Feature Engineering and Data Preprocessing
To prepare the data for machine learning models, several preprocessing steps were applied:

Handling Missing Values
Missing values in numeric features were filled using mode imputation to preserve the data distribution.
Outlier Handling
Outliers were analyzed and managed to reduce noise in the dataset.
Categorical Encoding
Categorical variables were transformed into numerical form using One-Hot Encoding.

# Text Data Preprocessing
Customer remarks were cleaned and transformed using the following steps:

Expand contractions
Lowercase conversion
Remove punctuation
Remove URLs
Remove digits
Remove stopwords
Tokenization
Text normalization
Part-of-Speech tagging
Text Vectorization
Customer remarks were converted into numerical features using TF-IDF Vectorization.

Data Scaling
Numeric features were scaled using StandardScaler.

Dimensionality Reduction
High dimensional feature space was reduced using Principal Component Analysis (PCA).

# Machine Learning Models
Multiple machine learning and deep learning models were trained and evaluated.
Models implemented:

Random Forest Regressor
XGBoost Regressor

# Deep learning model
Artificial Neural Network (ANN)

Model Evaluation
Models were evaluated using regression metrics:

Metric	Description
R² Score	Measures how well the model explains variance in the data
MAE	Mean Absolute Error between predicted and actual CSAT score

Among the models, XGBoost showed the best overall performance, so it was selected as the final prediction model.

# Model Deployment

The final model was deployed locally using Streamlit, allowing users to interact with the model through a web interface.

The application allows users to:
Enter customer interaction details
Provide customer remarks
Predict the CSAT score in real time

This demonstrates how machine learning models can be integrated into practical applications.
