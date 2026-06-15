# ৪. ডেটা স্প্লিট (Train / Validation / Test)

## স্প্লিট রেশিও

```
মোট ডেটা
├── ৮০% → ট্রেন সেট
├── ১০% → ভ্যালিডেশন সেট
└── ১০% → টেস্ট সেট
```

## কোড

```python
from sklearn.model_selection import train_test_split

# ৮০% ট্রেন, ২০% টেম্প
train_text, temp_text, train_labels, temp_labels = train_test_split(
    df['text'], df['label'],
    test_size=0.2, random_state=42,
    stratify=df['label']
)

# ১০% ভ্যাল, ১০% টেস্ট
val_text, test_text, val_labels, test_labels = train_test_split(
    temp_text, temp_labels,
    test_size=0.5, random_state=42,
    stratify=temp_labels
)
```

## ফাইল স্ট্রাকচার

```
data/
├── train.csv      (৬০-৭০%)
├── validation.csv (১৫-২০%)
└── test.csv       (১৫-২০%)
```
