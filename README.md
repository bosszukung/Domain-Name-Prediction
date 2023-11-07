# Domain Name Prediction System
The Domain Name Prediction System is a machine learning project designed to predict the price labels of domain names. The dataset comprises 10,000 domain names, each labeled with a price ranging from 1 to 5. This system utilizes various machine learning algorithms to analyze domain name features and accurately predict their corresponding price labels.

## Project Overview
### 1. Install and Import Libraries
Ensure you have the necessary libraries installed to run the project. Use pip or any package manager of your choice to install required libraries.

### 2. Load Data
Load the dataset containing 10,000 domain names and their corresponding price labels (ranging from 1 to 5). You can use pandas or any suitable data loading library for this purpose.

#### 3. Features Extraction
Extract relevant features from the domain names. Features can include domain length, special characters, letters (both uppercase and lowercase), vowels, consonants, and numbers.
Perform domain WHOIS queries to extract registration, expiration, and update dates as features.
### 4. Data Pre-processing
- Handling Categorical Variables:
Use one-hot encoding to convert string columns to numeric representations.
Add the transformed categorical features to the dataset.
- Splitting Data:
Split the data into feature variables (X) and the target variable (Y), where X contains the input features and Y contains the corresponding price labels.
- Feature Selection:
Perform feature selection using GenericUnivariateSelect with mode="fpr" to select relevant features based on their importance.
- Data Splitting for Training and Testing:
Split the feature variables (X) and target variable (Y) into training and testing datasets. This step is crucial for evaluating the model's performance on unseen data.
- Standardization:
Apply feature scaling to the dataset using Standard Scaler. Standardization ensures that all features have the same scale, which is essential for algorithms that rely on distances between data points, such as K-Nearest Neighbors (KNN).
### 5. Model Training and Evaluation
Train machine learning models using the pre-processed data. Common algorithms like K-Nearest Neighbors (KNN), Random Forest, and Decision Trees can be employed.
Evaluate the models using appropriate metrics such as accuracy, precision, recall, and F1-score.
### 6. Results and Visualization
Present the results of the trained models, including accuracy scores, confusion matrices, and classification reports.
Visualize the predictions and model performance to gain insights into the system's effectiveness.
