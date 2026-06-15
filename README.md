# Sentiment-of-Bangla-NLP

> 🇧🇩 বাংলা ই-কমার্স সেন্টিমেন্ট অ্যানালাইসিস

Daraz, Rokomari, GorerBazarBD-এর কাস্টমার রিভিউ নিয়ে সেন্টিমেন্ট অ্যানালাইসিস প্রজেক্ট।

---

## 📑 প্রকল্প ওভারভিউ

- **লক্ষ্য:** বাংলা ই-কমার্স রিভিউ → Positive / Negative / Neutral ক্লাসিফিকেশন
- **প্ল্যাটফর্ম:** Daraz, Rokomari, GorerBazarBD
- **মডেল:** TF-IDF + Logistic Regression (Baseline) vs BanglaBERT (Fine-tuned)

---

## 📚 ডকুমেন্টেশন স্ট্রাকচার

| # | ফাইল | বিষয়বস্তু |
|---|------|------------|
| ১ | [`steps/01-data-collection.md`](./steps/01-data-collection.md) | ডেটা সংগ্রহ — স্ক্র্যাপিং ও ম্যানুয়াল কালেকশন |
| ২ | [`steps/02-data-labeling.md`](./steps/02-data-labeling.md) | লেবেলিং গাইডলাইন ও ফরম্যাট |
| ৩ | [`steps/03-data-preprocessing.md`](./steps/03-data-preprocessing.md) | টেক্সট ক্লিনিং ও প্রিপ্রসেসিং |
| ৪ | [`steps/04-data-split.md`](./steps/04-data-split.md) | Train/Val/Test স্প্লিট |
| ৫ | [`steps/05-baseline-model.md`](./steps/05-baseline-model.md) | TF-IDF + Logistic Regression বেসলাইন |
| ৬ | [`steps/06-banglabert-finetune.md`](./steps/06-banglabert-finetune.md) | BanglaBERT ফাইন-টিউনিং |
| ৭ | [`steps/07-evaluation.md`](./steps/07-evaluation.md) | ইভ্যালুয়েশন ও মেট্রিক্স |
| ৮ | [`steps/08-publication.md`](./steps/08-publication.md) | পাবলিকেশন রাইটিং গাইড |

---

## 🛠️ প্রয়োজনীয় লাইব্রেরি

```txt
pandas
numpy
scikit-learn
transformers
torch
datasets
beautifulsoup4
selenium
matplotlib
seaborn
jupyter
```

## ✅ চেকলিস্ট

- [ ] ১. Daraz, Rokomari, GorerBazarBD থেকে রিভিউ সংগ্রহ
- [ ] ২. রিভিউ লেবেলিং
- [ ] ৩. ডেটা প্রিপ্রসেসিং
- [ ] ৪. Train/Val/Test স্প্লিট
- [ ] ৫. TF-IDF + Logistic Regression বেসলাইন
- [ ] ৬. BanglaBERT ফাইন-টিউনিং
- [ ] ৭. ইভ্যালুয়েশন
- [ ] ৮. পাবলিকেশন রাইটিং

---

## 👨‍💻 কন্ট্রিবিউটর

**নাম:** [আপনার নাম] · **ইউনিভার্সিটি:** [ইউনিভার্সিটি] · **ইমেইল:** [ইমেইল]
