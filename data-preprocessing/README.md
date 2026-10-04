# Data preprocessing

Two teaching notebooks that walk through the standard data preprocessing steps on synthetic football-player data, so they run with no downloads.

`notebook.ipynb` builds a 100-player dataset with deliberate problems and works through missing values, outliers (IQR), categorical encoding, scaling, feature engineering, a reusable preprocessing class, data leakage, train/test split strategies, plotting, and interview-style questions with code. `zero-to-master.ipynb` generates a messier 200-row dataset and applies the steps in order: load and inspect, missing values, visualisation, outlier capping, rare-category merging, duplicates, low-variance columns, date handling and encoding with `category_encoders`. Both are educational and produce no model metrics. Outputs are cleared; `zero-to-master.ipynb` writes `raw_football_data.csv` into the working directory when run.
