# ৭. ইভ্যালুয়েশন (Evaluation)

## মেট্রিক্স

| মেট্রিক | বিস্তারিত |
|---------|-----------|
| **Accuracy** | মোট প্রেডিকশনের কতটি সঠিক |
| **Precision** | Positive বলাগুলোর কতটি সত্যিই Positive |
| **Recall** | প্রকৃত Positive-এর কতটি শনাক্ত করেছে |
| **F1-score** | Precision + Recall-এর কম্বিনেশন |

## কোড

```python
from sklearn.metrics import (classification_report,
                              confusion_matrix, accuracy_score)
import seaborn as sns
import matplotlib.pyplot as plt

predictions = trainer.predict(test_dataset)
pred_labels = predictions.predictions.argmax(axis=1)

# Accuracy
acc = accuracy_score(test_labels, pred_labels)
print(f"Accuracy: {acc:.4f}")

# Classification Report
print(classification_report(test_labels, pred_labels,
      target_names=['Negative', 'Neutral', 'Positive']))

# Confusion Matrix
cm = confusion_matrix(test_labels, pred_labels)
sns.heatmap(cm, annot=True, fmt='d', cmap='Blues',
            xticklabels=['Negative', 'Neutral', 'Positive'],
            yticklabels=['Negative', 'Neutral', 'Positive'])
plt.show()
```

## তুলনা টেবিল (প্রত্যাশিত)

| মডেল | Accuracy | F1-Score |
|------|----------|----------|
| TF-IDF + Logistic Regression | ~৭৫% | ~০.৭৪ |
| BanglaBERT | ~৮৮% | ~০.৮৭ |
| **ইমপ্রুভমেন্ট** | **+১৩%** | **+০.১৩** |
