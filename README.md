Heart Disease Classification: Comprehensive ML Algorithm Comparison

Project Overview
This project implements a complete machine learning pipeline to predict heart disease, comparing individual algorithms (Decision Tree, KNN, Naive Bayes, SVM, ANN, Logistic Regression) and ensemble methods (Bagging, Random Forest, AdaBoost, Gradient Boosting, etc.) to identify the best performing model.

-Key Achievements
Best Individual Model: ANN with 82.84% accuracy and 0.8900 AUC
Best Ensemble Model: Extra Trees with 84.31% accuracy and 0.9145 AUC
Most Stable Model: Logistic Regression with only 1.14% train-test gap
Comprehensive Analysis: 14 models trained, tuned, and evaluated with detailed comparison

-Dataset
Total Samples: 920 (from 4 databases: Cleveland, Hungarian, Switzerland, VA Long Beach)
Features: 14 clinical attributes (age, sex, chest pain type, blood pressure, cholesterol, etc.)
Target: Binary classification (0 = No disease, 1 = Disease)
After Preprocessing: 918 samples (removed duplicates)
After SMOTE: 1,016 balanced samples (508:508)

-Preprocessing Pipeline
1. Data Loading → Combine 4 data sources
2. Data Cleaning → Remove duplicates (920 → 918 samples)
3. Missing Value Imputation → Median imputation (0 missing values)
4. Target Encoding → Binary encoding (0/1)
5. SMOTE Resampling → Balance classes (508:508)
6. Train-Test Split → 80/20 stratified split
7. Feature Scaling → StandardScaler (in pipeline)


-Results & Analysis
Key Findings
1️.Ensemble Methods Outperform Individual Models
Extra Trees achieved the highest accuracy (84.31%) and AUC (0.9145), surpassing the best individual model (ANN: 82.84%, AUC: 0.8900) by:

+1.47% in accuracy
+0.0245 in AUC (significant improvement in discriminative power)

2️.Linear vs Non-Linear Models
Non-Linear Models (KNN, ANN, SVM-RBF) generally achieved higher accuracy:

Best Non-Linear: ANN (82.84%)
Best Linear: Logistic Regression & SVM-Linear (81.37%)

Trade-off: Linear models showed superior stability (LR gap: 1.14% vs ANN gap: 11.98%)
3️.Overfitting Analysis
Models with Good Generalization (Train-Test Gap < 5%):

- Logistic Regression: 1.14%
- Naive Bayes: 2.61%
- SVM: 2.62%
- KNN: 2.87%

Models Prone to Overfitting (Gap > 10%):

- ANN: 11.98%
- Gradient Boosting: 16.42%
- Voting: 18.14%
- Stacking: 18.63%

4️. Why Ensemble Methods Excel

-Variance Reduction (Bagging/Random Forest/Extra Trees):

Averaging predictions from multiple trees reduces variance
Extra randomization in Extra Trees further improves generalization


-Bias Reduction (Boosting methods):

Sequential learning focuses on hard-to-classify samples
AdaBoost showed excellent balance (81.86% accuracy, 6.44% gap)


-Diversity of Predictors:

Combining different perspectives leads to more robust predictions
Stacking and Voting leverage multiple algorithm strengths



Clinical Significance
With AUC of 0.9145, Extra Trees demonstrates:

Excellent discriminative power for medical screening
High sensitivity for identifying at-risk patients
Reliable ranking of patient risk levels
Production-ready performance for clinical decision support systems

-Technologies & Tools
Core Libraries

Python 3.8+
scikit-learn 1.3+: ML algorithms, pipelines, evaluation
imbalanced-learn: SMOTE implementation
pandas: Data manipulation
NumPy: Numerical computing
Matplotlib & Seaborn: Data visualization

-ML Techniques

Pipeline Integration
GridSearchCV for hyperparameter tuning
Stratified Cross-Validation
SMOTE for class imbalance
StandardScaler for feature normalization


Contact
Rozak Mulya Limbong
Email: jakskuy6@gmsil.com
LinkedIn: https://www.linkedin.com/in/rozak-limbong-181a35317/
