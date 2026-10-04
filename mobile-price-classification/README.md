# Mobile price classification

Classifies phones into four price ranges from their specifications with a small neural network.

The dataset is `train.csv` (2,000 phones, 20 features such as battery power, RAM, pixel resolution and connectivity flags, target `price_range` with classes 0 to 3), the Kaggle mobile price classification file. It is not included; place it next to the notebook. The notebook does a short EDA, standardises the features, one-hot encodes the target, splits 80/20 (`random_state=42`, 400 test rows) and trains a Keras MLP (128, 32 and 4 units, dropout 0.2) for 20 epochs. The original saved run reported test accuracy 0.95 with a classification report and confusion matrix; two fresh runs of this notebook gave 0.94 and 0.93, because TensorFlow is not seeded, so expect roughly 0.93 to 0.95. Outputs are cleared in the committed notebook.

**Data leakage.** `StandardScaler` is fitted on the full dataset before the train/test split, so statistics from the test rows influence the scaling. For plain standardisation the effect is probably small, but the test score is not strictly clean; fitting the scaler on the training rows only would fix it. The target is ordinal (low to very high cost) but is treated as four unordered classes.
