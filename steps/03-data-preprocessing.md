# ৩. ডেটা প্রিপ্রসেসিং (Data Cleaning)

## অপারেশন টেবিল

| অপারেশন | বিবরণ | কোড |
|----------|--------|------|
| ইমোজি রিমুভ | ইমোজি সরানো | `re.sub(r'[^\w\s।,।?!]', '', text)` |
| স্পেশাল ক্যারেক্টার রিমুভ | @, #, $ সরানো | `re.sub(r'[#@$%^&*()]', '', text)` |
| অতিরিক্ত স্পেস রিমুভ | মাল্টিপল স্পেস → একটিতে | `re.sub(r'\s+', ' ', text).strip()` |
| ডুপ্লিকেট রিমুভ | একই রিভিউ একাধিকবার থাকলে | `df.drop_duplicates(subset=['text'])` |
| ছোট টেক্সট ফিল্টার | ৩ শব্দের কম বাদ | `df[df['text'].str.split().str.len() >= 3]` |

## সম্পূর্ণ কোড

```python
import pandas as pd
import re

df = pd.read_csv('raw_reviews.csv')

# ক্লিনিং
df['text'] = df['text'].apply(lambda x: re.sub(r'[^\w\s।,।?!]', '', str(x)))
df = df.drop_duplicates(subset=['text'])
df = df[df['text'].str.split().str.len() >= 3]
df = df.dropna(subset=['text'])

df.to_csv('cleaned_reviews.csv', index=False)
```
