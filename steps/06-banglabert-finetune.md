# ৬. BanglaBERT ফাইন-টিউনিং

## মডেল ইনফো

- **মডেল:** `csebuetnlp/banglabert`
- **লাইব্রেরি:** Hugging Face Transformers
- **ক্লাস:** AutoModelForSequenceClassification (৩ লেবেল)

## ইম্পোর্ট ও লোড

```python
from transformers import AutoTokenizer, AutoModelForSequenceClassification

model_name = "csebuetnlp/banglabert"
tokenizer = AutoTokenizer.from_pretrained(model_name)
model = AutoModelForSequenceClassification.from_pretrained(
    model_name, num_labels=3
)
```

## টোকেনাইজেশন

```python
train_encodings = tokenizer(
    train_text.tolist(),
    truncation=True, padding=True,
    max_length=128, return_tensors="pt"
)
```

## ট্রেইনিং কনফিগারেশন

| প্যারামিটার | ভ্যালু |
|-------------|--------|
| learning_rate | 2e-5 |
| batch_size | 16 |
| num_epochs | 4 |
| optimizer | AdamW |
| max_length | 128 |

## Trainer API

```python
from transformers import Trainer, TrainingArguments

training_args = TrainingArguments(
    output_dir='./results',
    num_train_epochs=4,
    per_device_train_batch_size=16,
    per_device_eval_batch_size=16,
    evaluation_strategy='epoch',
    save_strategy='epoch',
    logging_dir='./logs',
)

trainer = Trainer(
    model=model,
    args=training_args,
    train_dataset=train_dataset,
    eval_dataset=val_dataset,
)

trainer.train()
```

## Google Colab টিপস

- Runtime → Change runtime type → **T4 GPU** সিলেক্ট করুন
- মডেল লোড হতে ২-৩ মিনিট সময় লাগতে পারে
- ১৫০০-৩০০০ ডেটা দিয়ে ট্রেইন করতে ১৫-৩০ মিনিট সময় লাগে
