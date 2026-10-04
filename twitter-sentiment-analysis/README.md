# Twitter sentiment analysis

Classic NLP baselines for four-class tweet sentiment: spaCy preprocessing, TF-IDF features and four scikit-learn classifiers.

The dataset is `twitter_training.csv` (the Kaggle Twitter entity sentiment analysis training file; labels Positive, Negative, Neutral and Irrelevant; 14,937 test rows after an 80/20 split). It is not included; place it next to the notebook, and install the spaCy model with `python -m spacy download en_core_web_sm`. Text is lemmatised with stop words and punctuation removed, split 80/20 (stratified, `random_state=42`), vectorised with TF-IDF fitted on the training split, and classified with k-NN (k = 4), Logistic Regression, a Decision Tree and a Random Forest (100 trees). Saved test results: Random Forest accuracy 0.91, k-NN 0.90, Decision Tree 0.81, Logistic Regression 0.79.

**Limitations.** The notebook also defines a small Keras network, but those cells were never run, so there is no neural-network result. The saved outputs come from the original Kaggle run; the Kaggle file is not on the machine used to prepare this repository, so the notebook was re-executed end to end only on a small synthetic stand-in CSV, which confirms the code runs but says nothing about the scores. It was also not checked whether duplicate tweets fall on both sides of the train/test split, which would inflate the k-NN and tree-based scores.
