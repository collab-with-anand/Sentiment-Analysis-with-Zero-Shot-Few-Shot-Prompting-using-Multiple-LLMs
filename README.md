# 💬🤖 Sentiment Analysis with Zero-Shot & Few-Shot Prompting using Multiple LLMs

## 🎯 Project Overview

This project investigates how **large language models (LLMs)** perform on **sentiment analysis** tasks under different prompting paradigms — **Zero-Shot**, **Few-Shot**, and **Cross-Model Evaluation**.
Using a subset of the *Yelp Restaurant Review Dataset*, the notebook compares performance across multiple LLMs (e.g., Claude 3 Sonnet, LLaMA) and evaluates their ability to classify sentiment accurately **without explicit retraining**.

---

## 🧠 Objectives

* 🧩 Evaluate **Zero-Shot learning**: direct classification using plain prompts.
* 🧩 Evaluate **Few-Shot learning**: provide limited labeled examples within prompts.
* 🤝 Compare **multiple LLMs** (Claude vs LLaMA) under identical conditions.
* 📊 Quantify model accuracy, precision, recall, and F1-score.
* 🔍 Reflect on strengths, weaknesses, and misclassification patterns.

---

## 🧾 Dataset

* Source: *restaurant_reviews_az.csv* (subset of Yelp reviews)
* Selected 100 samples → 50 **positive** and 50 **negative** reviews.
* Each review is labeled and used for evaluation across methods.

---

## 🧩 Methodology

| Step                           | Description                                                                    |
| :----------------------------- | :----------------------------------------------------------------------------- |
| **1. Data Loading & Cleaning** | Imported libraries → Loaded dataset → Randomly sampled 50+50 labeled reviews.  |
| **2. Zero-Shot Prompting**     | Used Claude 3 Sonnet to classify sentiment *without any examples*.             |
| **3. Few-Shot Prompting**      | Provided 2 positive & 2 negative examples in prompt for guided classification. |
| **4. Multi-Model Comparison**  | Re-ran both setups with **Claude 3 Sonnet** and **LLaMA 2** models.            |
| **5. Evaluation**              | Computed **Precision, Recall, F1, Accuracy** across approaches.                |
| **6. Reflection**              | Discussed model behavior, prompt sensitivity, and interpretability.            |

---

## 📊 Results

### 🔹 Zero-Shot (Claude 3 Sonnet)

| Metric    | Score |
| :-------- | :---: |
| Accuracy  | ~80 % |
| Precision |  0.79 |
| Recall    |  0.82 |
| F1-Score  |  0.80 |

### 🔹 Few-Shot (Claude 3 Sonnet)

| Metric    | Score |
| :-------- | :---: |
| Accuracy  | ~88 % |
| Precision |  0.87 |
| Recall    |  0.89 |
| F1-Score  |  0.88 |

### 🔹 Cross-Model Comparison (Few-Shot)

| Model           | Accuracy | F1-Score | Notes                                                  |
| :-------------- | :------: | :------: | :----------------------------------------------------- |
| Claude 3 Sonnet |   0.88   |   0.88   | Highly consistent with human labels.                   |
| LLaMA 2         |   0.83   |   0.82   | Slightly lower; sensitive to phrasing and punctuation. |

---

## 💡 Key Observations

* 🧩 **Few-Shot learning** significantly improves sentiment accuracy over zero-shot.
* ⚡ **Prompt phrasing** heavily affects smaller models (LLaMA).
* 🧠 **Claude 3 Sonnet** exhibits stronger reasoning and contextual grasp.
* 🔍 **Misclassifications** often stem from sarcasm or mixed-tone reviews.
* 🤖 Each LLM displays distinct linguistic bias — useful for ensemble decision making.

---

## ⚙️ Environment Setup

```bash
git clone https://github.com/<your-username>/llm-sentiment-prompting.git
cd llm-sentiment-prompting
pip install pandas numpy scikit-learn openai anthropic transformers matplotlib
```

## 🔍 Key Takeaways

* **Few-Shot > Zero-Shot** for nuanced sentiment tasks.
* **Prompt engineering** is critical — clarity improves reproducibility.
* **Model diversity** enhances overall understanding through ensemble thinking.
* **LLMs can classify effectively without retraining**, making them powerful tools for rapid NLP prototyping.

---

## 🧾 References

* Anthropic Claude 3 Sonnet API Documentation
* Meta LLaMA 2 Whitepaper
* Yelp Review Dataset (public subset)

---
