# 📘 NLU Assignment 2: Learning Word Embeddings from IIT Jodhpur Data

## 👨‍🎓 Author

**Naman Jain (B22BB027)**
Indian Institute of Technology Jodhpur

---

## 📌 Overview

This project focuses on building **Word2Vec models (CBOW and Skip-gram)** from scratch using textual data collected from IIT Jodhpur sources. The goal is to learn meaningful word embeddings and analyze semantic relationships between academic terms.

---

## 📂 Dataset Creation

### 🔍 Data Sources

The dataset was collected from:

* IIT Jodhpur official website
* Academic regulations
* Research and academics pages
* Course-related content

### 🤖 Intelligent Data Collection Pipeline

A hybrid system was built combining:

* **Web scraping (BeautifulSoup + Requests)**
* **LLM-based filtering and cleaning (Mistral-Nemotron via NVIDIA API)**

### ⚙️ Pipeline Steps

1. Crawl IITJ webpages using BFS
2. Extract links using BeautifulSoup
3. Filter relevant academic links using LLM
4. Extract meaningful text from HTML using LLM
5. Convert structured content into paragraph format
6. Remove noise and non-English content

👉 Result: Clean academic corpus in paragraph form

---

## 📊 Dataset Statistics

| Metric          | Value |
| --------------- | ----- |
| Total Tokens    | 2724  |
| Vocabulary Size | 1019  |

---

## 🧠 Models Implemented

### 1. CBOW (Continuous Bag of Words)

* Predicts target word from context
* Faster but less expressive

### 2. Skip-gram

* Predicts context from target word
* Better for semantic understanding

---

## ⚙️ Hyperparameters Explored

* Embedding Dimensions: 50, 100
* Context Window Size: 5, 8
* Negative Sampling: 5, 10

---

## 🔍 Results

### 📌 Nearest Neighbors (Best Models)

#### CBOW

* Weak semantic structure for rare words
* Good for frequent terms

#### Skip-gram

* Strong semantic relationships
* Captures academic hierarchy (PhD, MTech, etc.)

---

## 🔁 Analogy Results

### CBOW

* computer - engineering + science → *performance* (0.28)
* undergraduate - bachelor + master → *course* (0.47)
* study - student + faculty → *skill* (0.33)

👉 Weak relational understanding

---

### Skip-gram

* computer - engineering + science → *technology* (0.70)
* undergraduate - bachelor + master → *postgraduate* (0.83)
* study - student + faculty → *application* (0.68)

👉 Strong semantic + hierarchical relationships

---

## 📉 Visualization

* t-SNE used for dimensionality reduction
* Clear clustering of:

  * Academic terms
  * Degree programs
  * Institutional concepts

---

## 🧠 Key Insights

* Skip-gram significantly outperforms CBOW
* Captures:

  * Semantic similarity
  * Academic hierarchy
  * Contextual relationships
* CBOW struggles with rare and domain-specific words

---

## ⚠️ Limitations

* Small dataset size
* Limited context diversity
* Some noisy embeddings for rare words

---

## 🚀 Future Work

* Use larger corpus
* Compare with pre-trained embeddings (GloVe, FastText)
* Explore transformer-based embeddings (BERT)

---

## 📁 Project Structure

```
├── notebook.ipynb
├── corpus.txt
├── embedding_plot_sg.png
├── embedding_plot_cbow.png
├── report.tex
└── README.md
```

---

## ✅ Conclusion

This project demonstrates how word embeddings can be learned from domain-specific data. The use of a hybrid scraping + LLM pipeline significantly improves corpus quality, leading to better semantic representations, especially with the Skip-gram model.

---

## ⭐ Note

This project was implemented from scratch without using pre-built Word2Vec libraries, ensuring a deep understanding of embedding learning mechanisms.
