# Student performance regression

Predicts a student's Performance Index from study habits with multiple linear regression.

The dataset is `Student_Performance.csv` (10,000 rows: hours studied, previous scores, extracurricular activities, sleep hours, sample question papers practised, performance index), the Kaggle "Student Performance (Multiple Linear Regression)" file. It is not included; place it next to the notebook. Rows outside the IQR bounds of the target are removed, the extracurricular flag is label-encoded, and an 80/20 split (`random_state=42`) feeds scikit-learn's `LinearRegression`. On the test set: MSE 4.083 and R-squared 0.989 (train R-squared 0.9887, test 0.9890). The IQR filter is applied to the target before the split.
