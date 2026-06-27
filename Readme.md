<div align="center">

# 📱 Spam SMS Classifier

### A Natural Language Processing (NLP) project that classifies SMS messages as **Spam** 🚫 or **Ham** ✅ using Machine Learning.

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.8%2B-blue?style=for-the-badge&logo=python&logoColor=white" alt="Python"/>
  <img src="https://img.shields.io/badge/scikit--learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white" alt="scikit-learn"/>
  <img src="https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white" alt="Jupyter"/>
  <img src="https://img.shields.io/badge/NLP-Text%20Classification-00C7B7?style=for-the-badge" alt="NLP"/>
  <img src="https://img.shields.io/badge/Accuracy-97.76%25-success?style=for-the-badge" alt="Accuracy"/>
</p>

<p align="center">
  <img src="https://img.shields.io/github/stars/nomanpathan485/spam-sms-classifier?style=social" alt="Stars"/>
  <img src="https://img.shields.io/github/forks/nomanpathan485/spam-sms-classifier?style=social" alt="Forks"/>
  <img src="https://img.shields.io/github/watchers/nomanpathan485/spam-sms-classifier?style=social" alt="Watchers"/>
</p>

<p align="center">
  <a href="#-overview">Overview</a> •
  <a href="#-features">Features</a> •
  <a href="#-tech-stack">Tech Stack</a> •
  <a href="#-installation">Installation</a> •
  <a href="#-usage">Usage</a> •
  <a href="#-results">Results</a> •
  <a href="#-roadmap">Roadmap</a> •
  <a href="#-author">Author</a>
</p>

</div>

---

## 🔍 Overview

This project tackles the classic **SMS Spam Classification** problem in NLP. Using the [SMS Spam Collection Dataset](https://www.kaggle.com/datasets/uciml/sms-spam-collection-dataset), I built a machine-learning pipeline that:

1. Cleans raw SMS text
2. Converts messages into numerical features using a **Bag-of-Words** representation (`CountVectorizer`)
3. Trains a **Logistic Regression** classifier
4. Achieves **97.76% accuracy** on the held-out test set

> **Why this project?** It's a great entry point into text classification — small dataset, fast training, and immediately interpretable results. Perfect for showcasing the end-to-end ML workflow: data prep → vectorization → training → evaluation → serialization.

---

## ✨ Features

- 🧹 **End-to-end text preprocessing** — lowercase, punctuation removal, stop-word handling
- 🧮 **Bag-of-Words vectorization** with `CountVectorizer`
- 🎯 **Logistic Regression classifier** — fast, interpretable, strong baseline
- 📊 **Comprehensive evaluation** — Accuracy, Precision, Recall, F1, Confusion Matrix
- 💾 **Model serialization** — Pickle-based persistence for both model and vectorizer
- 📓 **Fully reproducible** — Single Jupyter Notebook with the complete pipeline

---

## 🛠️ Tech Stack

<p align="left">
  <img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white" alt="Python"/>
  <img src="https://img.shields.io/badge/Pandas-150458?style=flat-square&logo=pandas&logoColor=white" alt="Pandas"/>
  <img src="https://img.shields.io/badge/NumPy-013243?style=flat-square&logo=numpy&logoColor=white" alt="NumPy"/>
  <img src="https://img.shields.io/badge/scikit--learn-F7931E?style=flat-square&logo=scikit-learn&logoColor=white" alt="scikit-learn"/>
  <img src="https://img.shields.io/badge/Jupyter-F37626?style=flat-square&logo=jupyter&logoColor=white" alt="Jupyter"/>
  <img src="https://img.shields.io/badge/Pickle-Persistence-808080?style=flat-square" alt="Pickle"/>
</p>

| Category       | Tools                           |
|----------------|---------------------------------|
| Language       | Python 3.8+                     |
| Data Handling  | Pandas, NumPy                   |
| ML Framework   | Scikit-learn                    |
| Vectorization  | CountVectorizer (Bag-of-Words)  |
| Model          | Logistic Regression             |
| Serialization  | Pickle                          |
| Environment    | Jupyter Notebook                |

---

## 📂 Project Structure

```
spam-sms-classifier/
│
├── 📓 notebook.ipynb          # End-to-end pipeline (data → evaluation)
├── 📄 README.md               # You are here
├── 📦 requirements.txt        # Python dependencies
├── 🤖 spam_model.pkl          # Trained Logistic Regression model
├── 🔤 vectorizer.pkl          # Fitted CountVectorizer
│
└── 📁 data/
    └── 📊 spam.csv            # SMS Spam Collection Dataset
```

---

## ⚙️ Installation

### 1️⃣ Clone the repository

```bash
git clone https://github.com/nomanpathan485/spam-sms-classifier.git
cd spam-sms-classifier
```

### 2️⃣ Create a virtual environment (recommended)

```bash
python -m venv venv
source venv/bin/activate        # macOS / Linux
venv\Scripts\activate           # Windows
```

### 3️⃣ Install dependencies

```bash
pip install -r requirements.txt
```

---

## 🚀 Usage

### Option A — Run the notebook

```bash
jupyter notebook notebook.ipynb
```

Walk through each cell to see the full pipeline: data loading → preprocessing → vectorization → training → evaluation.

### Option B — Use the pre-trained model directly

```python
import pickle

# Load artifacts
model = pickle.load(open("spam_model.pkl", "rb"))
vectorizer = pickle.load(open("vectorizer.pkl", "rb"))

# Classify a message
sample = ["Congratulations! You won a $1000 Walmart gift card. Click here to claim now!"]
vectorized = vectorizer.transform(sample)
prediction = model.predict(vectorized)

print("🚫 Spam" if prediction[0] == 1 else "✅ Ham (Not Spam)")
```

---

## 📊 Results

### Overall Performance

| Metric         | Score     |
|----------------|-----------|
| **Accuracy**   | **97.76%** |
| Spam Precision | 0.99      |
| Spam Recall    | 0.84      |
| Spam F1-Score  | 0.91      |

### Confusion Matrix

|                  | Predicted Ham | Predicted Spam |
|------------------|---------------|----------------|
| **Actual Ham**   | ✅ TN         | ⚠️ FP          |
| **Actual Spam**  | ⚠️ FN         | ✅ TP          |

> 💡 **High precision (0.99) means**: when the model says *Spam*, it's almost always right. **Lower recall (0.84)** means a small number of spam messages slip through — a typical trade-off when optimizing to avoid false alarms.

---

## 🧠 What I Learned

- ✅ How machines convert raw text into numerical features (Bag-of-Words)
- ✅ Practical use of `CountVectorizer` for text vectorization
- ✅ Why **Logistic Regression** is a strong baseline for binary text classification
- ✅ Reading **classification reports** — Precision vs Recall trade-offs
- ✅ **Model serialization** with Pickle for reuse without retraining
- ✅ Structuring an end-to-end NLP pipeline inside a Jupyter Notebook

---

## 🗺️ Roadmap

Planned improvements for this project:

- [ ] 🔄 **TF-IDF Vectorization** for better feature weighting
- [ ] 🧪 **Naive Bayes comparison** (MultinomialNB is the classic spam baseline)
- [ ] 🌐 **Streamlit web app** — paste an SMS, get instant classification
- [ ] 🤗 **Transformer-based models** (BERT / DistilBERT) for state-of-the-art accuracy
- [ ] 📈 **ROC-AUC & PR curves** visualization
- [ ] 🐳 **Dockerize** the inference pipeline
- [ ] 🧪 Add a small unit-test suite for the preprocessing pipeline

---

## 🤝 Contributing

Contributions, issues, and feature requests are welcome!

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 🙏 Acknowledgments

- 📚 Dataset: [SMS Spam Collection Dataset](https://www.kaggle.com/datasets/uciml/sms-spam-collection-dataset) — UCI Machine Learning Repository
- 💡 Inspiration: Classic NLP workflows taught in introductory ML courses

---

## 👤 Author

**Noaman Ayub Pathan**

<p>
  <a href="https://github.com/nomanpathan485"><img src="https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white" alt="GitHub"/></a>
  <a href="https://www.linkedin.com/in/noaman-ayub-pathan/"><img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn"/></a>
</p>

<p align="left">
  <img src="https://komarev.com/ghpvc/?username=nomanpathan485&label=Profile%20views&color=0e75b6&style=flat" alt="Profile views"/>
</p>

---

<div align="center">

### ⭐ If you found this useful, drop a star — it helps a lot!

</div>
