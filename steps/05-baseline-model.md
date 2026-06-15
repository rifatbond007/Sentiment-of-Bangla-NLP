# ৫. বেসলাইন মডেল (Baseline)

BanglaBERT-এর পারফরম্যান্স তুলনার জন্য ক্লাসিক্যাল ML বেসলাইন প্রয়োজন।

## TF-IDF + Logistic Regression

```python
from sklearn.feature_extraction.text import TfidfVectorizer
from sklearn.linear_model import LogisticRegression
from sklearn.pipeline import Pipeline

pipeline = Pipeline([
    ('tfidf', TfidfVectorizer(max_features=5000, ngram_range=(1,2))),
    ('clf', LogisticRegression(max_iter=1000))
])

pipeline.fit(train_text, train_labels)
accuracy = pipeline.score(test_text, test_labels)
```

## অপশনাল বেসলাইন মডেল

| মডেল | লাইব্রেরি | ইম্পোর্ট |
|-------|-----------|----------|
| SVM | scikit-learn | `from sklearn.svm import SVC` |
| Naive Bayes | scikit-learn | `from sklearn.naive_bayes import MultinomialNB` |
| Random Forest | scikit-learn | `from sklearn.ensemble import RandomForestClassifier` |

## রেজাল্ট সেভ

```python
import json

results = {
    'model': 'TF-IDF + Logistic Regression',
    'accuracy': accuracy,
    'f1_score': f1
}

with open('results/baseline_results.json', 'w') as f:
    json.dump(results, f)
```
