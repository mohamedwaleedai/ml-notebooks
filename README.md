# ml-notebooks

Exploratory and educational machine learning notebooks: data preprocessing, customer segmentation, loan approval classification, student score regression and sales forecasting.

## Contents

| Folder | What it covers | Tech | Headline result |
|---|---|---|---|
| [data-preprocessing](data-preprocessing/) | Teaching notebooks on missing values, outliers, encoding, scaling, pipelines and data leakage, on synthetic football data | pandas, scikit-learn, category_encoders, seaborn | None (educational) |
| [mall-customer-segmentation](mall-customer-segmentation/) | K-Means (k = 5) and DBSCAN on income and spending score | scikit-learn, pandas, seaborn | 5 K-Means clusters; DBSCAN gives 2 clusters and 8 noise points |
| [loan-approval-prediction](loan-approval-prediction/) | Random Forest vs SMOTE-balanced Logistic Regression and Decision Tree | scikit-learn, imbalanced-learn | Test accuracy 0.980 (Random Forest, Decision Tree) and 0.813 (Logistic Regression) |
| [student-performance-regression](student-performance-regression/) | Multiple linear regression on study habits | scikit-learn, pandas | Test R-squared 0.989 |
| [walmart-sales-forecast](walmart-sales-forecast/) | Linear Regression, XGBoost and LightGBM on lagged weekly sales | XGBoost, LightGBM, pandas | Training-set R-squared 0.92 / 0.97 / 0.97 (not held-out) |

Each folder has its own README with the dataset, technique and caveats. Several of these results are measured on a single split or on training data, and the folder READMEs say where.

## Getting Started

The notebooks were executed end to end with nbconvert on Python 3.11 using the pinned versions below.

```bash
python -m venv .venv
# Windows: .venv\Scripts\activate    macOS/Linux: source .venv/bin/activate
pip install -r requirements.txt
```

Open a notebook in Jupyter, VS Code or Colab. The datasets are third-party and are not included in this repository (`*.csv` is gitignored). Each folder README names the file it expects; download it from Kaggle and place it next to the notebook. The two data-preprocessing notebooks need no download.

`pandas` is pinned below 3 because the Walmart notebook uses `fillna(method="ffill")`, which pandas 3 removed.

## License

MIT. See [LICENSE](LICENSE).
