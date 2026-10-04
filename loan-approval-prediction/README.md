# Loan approval prediction

Binary classification of loan approval, comparing a Random Forest on the original data with Logistic Regression and a Decision Tree trained after SMOTE oversampling.

The dataset is `loan_approval_dataset.csv` (4,269 applicants, 13 columns, no missing values), the Kaggle loan approval prediction dataset. It is not included; place it next to the notebook. Education, self-employment and the label are label-encoded, the data is split 80/20 (stratified, `random_state=42`, 854 test rows), and SMOTE balances the training set from 2,125 vs 1,290 to 2,125 each. Test results: Random Forest (no SMOTE) accuracy 0.980, F1 0.973; Decision Tree (SMOTE) accuracy 0.980, F1 0.974; Logistic Regression (SMOTE) accuracy 0.813, F1 0.748. SMOTE is applied only to the two models trained on it, so the comparison also mixes model type with resampling, and `loan_id` is not dropped, so the identifier is used as a feature.
