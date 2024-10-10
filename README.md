# LIVER-PATIENT-PREDICTION
# Business Problem 
### Problem Context
Patients with Liver disease have been continuously increasing because of excessive consumption of alcohol, inhale of harmful gases, intake of contaminated food, pickles and drugs. This dataset was used to evaluate prediction algorithms in an effort to reduce burden on doctors.

### Content
This data set contains 416 liver patient records and 167 non liver patient records collected from North East of Andhra Pradesh, India. The "Dataset" column is a class label used to divide groups into liver patient (liver disease) or not (no disease). This data set contains 441 male patient records and 142 female patient records.

Any patient whose age exceeded 89 is listed as being of age "90".

### Features:

* Age of the patient
* Gender of the patient
* Total Bilirubin
* Direct Bilirubin
* Alkaline Phosphotase
* Alamine Aminotransferase
* Aspartate Aminotransferase
* Total Protiens
* Albumin
* Albumin and Globulin Ratio
* Dataset: field used to split the data into two sets (patient with liver disease, or no disease)
# Data Analysis Report
## **1. Introduction**
The purpose of the analysis is to predict if the patient is suffering from Liver disease or not . 


## **2. Data Overview**
- Number of rows: 582
- Number of columns: 11
- Featues:'Age', 'Gender', 'Total Bilirubin', 'Direct Bilirubin','Alkaline Phosphotase', 'Alamine Aminotransferase','Aspartate Aminotransferase', 'Total Protiens', 'Albumin','Albumin and Globulin Ratio', 'Target' . 
- Target Variable : Target (defines liver disease positive or negative) .


#### **3. Data Preprocessing and Feature Engineering**
- **Handling Missing Values** : The dataset contains 4 missing values in Albumin and Globulin_Ratio feature contain 4 NaN values .

- **Handling categorical data** : For the categorical features like Gender ,we have converted the Categorical values of Male as 1 and Female as 0 .

- **Outliers** : Handling outliers was crucial for improving model accuracy, but in some cases, extreme values might change the report , so after careful analysis. from above boxplot and data we can see in "Aspartate Aminotransferase" there is huge diff b/w min,mean and max value . so we can consider long gap values as an outlier . 

- **Feature Transformation**: There is no need of Standardization and Normalization of our dataset, as we using Ensemble Technique.
### **4. Exploratory Data Analysis (EDA)**
- **Age vs Target** : Age between 40 and 60 are more prone to liver disease, as liver function deteriotes with age.
- **Gender vs Target** : Males exhibit a higher prevalence of liver disease compared to females, as the count of males with liver disease is larger than that of females.
- **TotalBilirubin vs Target** :Patients with liver disease generally have higher count bilirubin levels compared to those without liver disease.
The maximum bilirubin levels in liver disease patients are significantly elevated, which indicates a strong relationship between bilirubin levels and liver function.
- **Direct Bilirubin vs Target** :Patients without liver disease have lower direct bilirubin levels, usually concentrated around the normal range.
Patients with liver disease exhibit a wider distribution of direct bilirubin levels, with a significant number of cases where Direct Bilirubin is elevated, confirming its association with liver dysfunction.
- **Alkaline Phosphates vs Target** :Patients with liver disease typically show higher ALP levels than those without liver disease.
The distribution of ALP in liver disease patients is wider, suggesting more variability in this enzyme's levels.
- **Alamine Aminotransferase vs Target** :Higher ALT levels are seen in patients with liver disease.
There are outliers among liver disease patients, showing extremely elevated ALT, which might indicate more severe liver injury.
- **Aspartate Aminotransferase vs Target**:Elevated AST levels are common in liver disease patients.
AST levels are typically higher in liver disease patients, with more extreme cases exhibiting high outliers.
- **Total Protiens vs Target**:Patients with liver disease have lower total protein levels compared to those without liver disease.
The distribution is indicating that most liver disease patients have relatively low total proteins.
- **Albumin	Albumin vs Target** :Patients with liver disease showed lower levels of albumin compared to those without liver disease, which is consistent with impaired liver function.
The median albumin levels are distinctly lower in liver disease patients.
- **Albumin	Albumin and Globulin Ratio vs Target** : Patients with liver disease have a lower A/G ratio, indicating an imbalance in protein production due to liver dysfunction.
The distribution of A/G ratio for liver disease patients is skewed towards the lower side, with some outliers reflecting severely reduced ratios.

## **Overview of Models Evaluated**
#### Logistic Regression

Performance Metrics:
- Accuracy Score: 0.61
- Precision: 0.57
- Recall : 0.82
- F1 Score: 0.67
  

#### Random Forest Classifier

Performance Metrics:
- Accuracy Score: 0.92
- Precision: 0.95
- Recall: 0.94
- F1 Score: 0.87

#### AdaBoost Classifier:

Performance Metrics:
- Accuracy Score: 0.75
- Precision: 0.86
- Recall: 0.76
- F1 Score: 0.81


#### Gradient Boosting Classifier: 

Performance Metrics:
- Accuracy Score: 0.82
- Precision: 0.91
- Recall: 0.84
- F1 Score: 0.87

## Model Performance Comparison

#### Best Model: 

After creating multiple classification models, Both RandomForest and GradientBoosting performed well in their base models, achieved overall scores as below.

1.RandomForest Classifier:
- Precision (Class 1): 0.95
- Recall (Class 1): 0.95
- Accuracy: 0.93
- F1 Score: 0.88
 
2.GradietBoosting Classifier:
- Precision (Class 1): 0.92
- Recall (Class 1): 0.85
- Accuracy: 0.82
- F1 Score: 0.88

## **Model Tuning Summary**
The primary goal of model tuning was to enhance the performance of the Random Forest (RF) and Gradient Boosting (GB) models.
In this tuning process, 
### **RandomForest** :
- Before Tuning: - Accuracy of 68%, with a clear imbalance between Class 1 (recall = 85%) and Class 2 (recall = 29%).
- After Tuning: Major improvement with accuracy jumping to 93%, and more balanced performance for both classes (precision, recall, and F1 all around 95% for Class 1 and 88% for Class 2).

### **Gradient Boosting**:
- Before Tuning: Reasonable performance with 74% accuracy. Class 2 recall is relatively low at 35%.
- After Tuning: Significant improvement with accuracy at 93%, similar to Random Forest, with high precision, recall, and F1 scores (95% for Class 1 and 88% for Class 2).

## **Conclusion** 
Random Forest and Gradient Boosting are the best-performing algorithms after tuning, both achieving 93% accuracy with balanced precision, recall, and F1 scores for both classes.

## Challenges Faced in the Liver Disease Prediction Project
- The liver disease prediction project presents a variety of challenges throughout different stages, ranging from data collection to model building.
- Here s a detailed breakdown of the major obstacles encountered during this project:

**1. Data Quality Issues**
**Missing Values**
- One of the common issues in healthcare datasets is missing values, which can lead to biased or inaccurate results if not handled properly.

- Challenges: Certain column Albumin Albumin and Globulin Ratio had missing  data.
- Solution: Applied various techniques like median imputation to handle missing values
**2. Outliers**
- Outliers were present in several biochemical markers like Aspartate Aminotransferase (AST) and Alanine Aminotransferase (ALT), which could potentially distort the analysis and model performance.

- Challenges: High variability in liver enzyme levels could skew results, making model training less effective.
- Solution: Applied  IQR methods to detect and either cap or remove outliers. However, deciding on the appropriate thresholds for outliers was challenging because some extreme values might reflect real cases of severe liver disease.

**3. Feature Selection and Importance**
- Liver disease is influenced by multiple biochemical markers, but not all features contribute equally to the prediction model.

- Challenges: Determining which features were most important for predicting liver disease was difficult. Features like Total Proteins and Albumin correlated with each other, leading to potential multicollinearity.
- Solution:
Conducted correlation analysis and used techniques like Recursive Feature Elimination (RFE) and Random Forest feature importance to select the most relevant features.
Dimensionality reduction was applied, but striking a balance between maintaining feature significance and reducing complexity was challenging.

  **Model Selection**
- Choosing the best machine learning model for liver disease prediction posed several challenges, especially in balancing between model complexity and interpretability.
Several algorithms were considered, including Logistic Regression, Random Forest, Gradient Boosting Classifier, Adaboost Classifier , K-NN classifier

- Challenges: Simpler models like Logistic Regression and Decision Trees failed to capture the complex relationships between biochemical markers and liver disease.
- Solution: Conducted a comparative analysis of various models using cross-validation and performance metrics such as AUC-ROC, accuracy, precision, and recall.

**4.Evaluation Metrics Confusion**:
- Challenges : The reliance on accuracy as a metric was misleading due to the imbalanced nature of the dataset. This necessitated a shift in focus toward metrics like precision, recall, and F1-score to better assess model performance, particularly in correctly identifying the minority class.
- Solution : Establishing a consistent evaluation framework centered on precision, recall, and F1-score ensured a comprehensive assessment of model effectiveness, particularly for the minority class.
  
**5.Computational Resource Limitations**:
- Challenges : Some models, particularly ensemble methods like Gradient Boosting, AdaBoost required substantial computational resources, resulting in longer training times and kernel crashes. This created bottlenecks in the model development process.
- Solution : To address computational resource limitations, I relied solely on local resources without utilizing cloud computing or distributed systems. This approach led to longer training times, requiring patience while the kernel executed the model training processes.
