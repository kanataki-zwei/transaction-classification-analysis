# transaction-classification-analysis

## Classification of Financial Transactions in Python    

This project focuses on classifying financial transactions using both Regex-based and Machine Learning techniques.     

The classification process follows a structured approach:    

Workflow Steps:    
- Data Quality Checks     
    - Checking data types and handling missing values.
    - Converting dates and times into datetime format.    
    - Identifying and handling duplicate transactions.
    - Standardizing classification tags.
- Exploratory Data Analysis (EDA)   
- Classification Approaches
    - Regex-based Classification: Using rule-based matching for predefined categories.
    - Machine Learning Classification: Training models to predict classification tags.
    - Stacked Approach: Combining Regex and ML for enhanced accuracy.

**Performance Evaluation & Summary**

- Evaluating classification models using accuracy, precision, and recall.
- Comparing models and identifying misclassified transactions.
- Summarizing the pros and cons of different approaches.

### Step 1: Data Quality Checks

- Duplicate Transaction Analysis
- Duplicate Rows: Checked for exact duplicate rows in the dataset.
- Duplicate Transaction IDs: Some transactions had duplicate IDs with different customers, amounts, and statuses.
- Decision: Kept the duplicates in the dataset for training purposes but flagged them for potential fraud or data entry errors.
- Classification Tag Standardization
- Standardized variations such as Bill_Payments, BillPayments, and Bill-Payments into a single format: Bill Payments.
- Ensured consistency in classification to prevent data contamination.

#### Step 2: Exploratory Data Analysis (EDA)

- Transaction Trends Over Time: Visualized daily transaction patterns.
- Transaction Amount Distributions: Identified anomalies in transaction amounts.
- Transaction Status Analysis: Explored the distribution of completed, refunded, and failed transactions.
- Classification Tag Distribution: Analyzed how frequently each classification tag appeared.
- Identifying Outliers: Highlighted transactions with unusually high amounts or odd transaction times.

#### Step 3: Transaction Classification

We implemented and compared three approaches:

**Regex-Based Classification**      
Used predefined patterns to classify transactions based on keywords in descriptions.     
Two regex strategies:      
- General Regex Matching: Simple keyword-based rules.     
- Granular Regex Matching: More refined regex patterns.    

Performance:     
- General regex performed better, but regex alone lacks adaptability to new patterns.     
- Some transactions had ambiguous descriptions that were hard to classify using rules alone.

**Machine Learning-Based Classification**     
Trained Logistic Regression and Random Forest models using TF-IDF vectorization.     
