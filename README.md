# Medical Cost Prediction Project README
 
## Project Overview 
 This project aims to predict medical costs using machine learning models based on factors such as age, sex, BMI, number of children, smoking status, and region. The objectives include:
 * Building regression models to predict the actual cost of medical insurance.
 * Classifying insurance costs as "expensive" or "cheap" based on a defined threshold.

 
  **Data Exploration and Preprocessing (20 minutes)**
     * Import necessary libraries and load the dataset. 
-    * Inspect the dataset, check data types, and look for missing values.
-    * Examine descriptive statistics of the dataset.
-    * Check for null values and duplicates.
-    * Handle duplicates.
-    * Encode categorical variables (region, sex, smoker).
+    * Inspect the dataset, check data types, and look for missing values. 
+    * Examine descriptive statistics of the dataset. 
+    * Check for null values and duplicates. 
+    * Handle duplicates. 
+    * Encode categorical variables (region, sex, smoker). 
     * Conduct Exploratory Data Analysis (EDA) to understand the relationships between features and target variable.
+ **Key Findings from EDA:** 
+ * There is a moderate positive correlation between age and charges. Older individuals tend to have higher insurance charges.
+ * There is a relatively strong positive correlation between BMI and charges. A higher BMI is associated with higher charges. 
+ * There is a very strong positive correlation between smoker and charges. Smokers have significantly higher insurance charges.
+ * While the distribution of charges between males and females is nearly equal, males tend to pay more than females after the $28,000 mark. 
+ * The majority of individuals in the dataset are between the ages of 18 and 20. More elderly females were included in the data collection than males.
    
+ **Remove outliers based on the IQR of the 'charges' variable.**\
  
* **Model Building and Evaluation (10 minutes)**
     * Split the data into training, validation, and test sets. 
     * Select the best performing regression model based on the validation set performance. 
     * Evaluate the best regression model on the test set. 
     * Define a threshold for classifying charges as "expensive" or "cheap". 
-    * Train various classification models (Random Forest, Gradient Boosting, Neural Network).
+    * Train various classification models (Random Forest, Gradient Boosting, Neural Network). 
     * Evaluate classification models on the validation set using precision, recall, and F1-score. 
     * Select the best performing classification model based on the validation set performance. 
     * Evaluate the best classification model on the test set.  
 * **Model Deployment (5 minutes)**
-    * Save the best performing classification model using joblib.
+    * Save the best performing classification model using joblib.  
     * The best performing model is the Gradient Boosting Classifier.
 * **Reporting (10 minutes)**
     * Create functions for regression and classification evaluation reports.
     * **Evaluation report is inside the jupyter notebook.**
