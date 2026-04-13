<div align="center">

# 🛡️ Network Security Prediction

> Classify network requests as **safe or unsafe** using NLP — with 84% accuracy across both BoW and TF-IDF models.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python](https://img.shields.io/badge/Python-3.12-3776AB?logo=python&logoColor=white)](https://www.python.org/)
[![Jupyter](https://img.shields.io/badge/Notebook-Jupyter-F37626?logo=jupyter&logoColor=white)](https://jupyter.org/)
[![scikit-learn](https://img.shields.io/badge/ML-scikit--learn-F7931E?logo=scikit-learn&logoColor=white)](https://scikit-learn.org/)
[![GitHub Stars](https://img.shields.io/github/stars/Malaydoshi711/Network-Security-Prediction?style=social)](https://github.com/Malaydoshi711/Network-Security-Prediction)

</div>



## 📖 About

Network Security Prediction is a machine learning project that uses **Natural Language Processing (NLP)** to detect whether an incoming network request is malicious or safe. By analyzing the textual content of request bodies — specifically note titles and descriptions — the project trains classifiers using two proven text-vectorization strategies: **Bag of Words (BoW)** and **TF-IDF**. Both models achieve **84% accuracy** on the held-out test set.

The dataset contains 1,000 labeled network requests (572 safe, 428 unsafe) sourced from Kaggle. Unsafe requests are identified by the presence of malicious language patterns in their body content, making this a practical application of NLP to cybersecurity.



## ✨ Key Features

- 🔍 **Malicious language detection** — Identifies unsafe requests by analyzing textual patterns in request body descriptions
- 🧹 **NLP preprocessing pipeline** — Includes stopword removal, Porter stemming, lowercasing, and punctuation filtering
- 📊 **Two vectorization strategies** — BoW (CountVectorizer) and TF-IDF compared head-to-head
- 🤖 **Bernoulli Naive Bayes classifier** — Lightweight, interpretable model well-suited for binary text classification
- 📈 **Exploratory data analysis** — Class distribution visualization, safe vs. unsafe malicious word corpus analysis
- ⚙️ **Feature engineering** — Description length added as a supplementary numeric feature
- 🎯 **84% accuracy** — Consistent across both BoW and TF-IDF approaches on a 20% test split



## 🗂️ Dataset

| Field | Details |
|---|---|
| **Source** | [Kaggle — Network Requests Data](https://www.kaggle.com/datasets/nandinibagga/network-requests-data/data) |
| **File** | `monoxor.csv` |
| **Total Samples** | 1,000 network requests |
| **Safe Requests** | 572 (57.2%) |
| **Unsafe Requests** | 428 (42.8%) |
| **Features Used** | `req/body/note/title`, `req/body/note/desc`, `isSafe` (label) |

Download the dataset from the Kaggle link above and place `monoxor.csv` in the project root before running the notebook.



## 🏗️ Project Structure

```
Network-Security-Prediction/
├── Network Security Prediction.ipynb   # Main analysis & modeling notebook
├── monoxor.csv                         # Dataset (download from Kaggle)
├── README.md                           # Project documentation
└── LICENSE                             # MIT License
```



## 🚀 Getting Started

### Prerequisites

- Python 3.8+
- Jupyter Notebook or JupyterLab

### Installation

```bash
# 1. Clone the repository
git clone https://github.com/Malaydoshi711/Network-Security-Prediction.git
cd Network-Security-Prediction

# 2. Install dependencies
pip install numpy pandas matplotlib scikit-learn nltk tqdm

# 3. Download NLTK stopwords (run once)
python -c "import nltk; nltk.download('stopwords')"

# 4. Download the dataset from Kaggle and place monoxor.csv in the project root
```

### Quick Start

```bash
# Launch the notebook
jupyter notebook "Network Security Prediction.ipynb"
```

Run all cells top-to-bottom. The notebook will load the dataset, preprocess text, train both models, and report accuracy.



## 🔬 Methodology

The pipeline follows these stages:

**1. Data Loading & EDA** — Load `monoxor.csv`, inspect distributions, and visualize the safe vs. unsafe class split with a pie chart.

**2. Feature Selection** — Retain only `req/body/note/title`, `req/body/note/desc`, and the `isSafe` label. Add `desc length` as an engineered numeric feature.

**3. Text Preprocessing** — For each description: lowercase, split, remove stopwords (NLTK English), apply Porter stemming, and reconstruct the cleaned token list.

**4. Vectorization** — Two strategies are compared:
- **Bag of Words**: `CountVectorizer` with `max_features=100`, unigrams
- **TF-IDF**: `TfidfVectorizer` with equivalent settings

**5. Classification** — `BernoulliNB` trained on an 80/20 train-test split (`random_state=0`).

**6. Evaluation** — Both models achieve **84% accuracy** on the test set.



## 📊 Results

| Model | Vectorizer | Accuracy |
|---|---|---|
| Bernoulli Naive Bayes | Bag of Words (BoW) | **84%** |
| Bernoulli Naive Bayes | TF-IDF | **84%** |



## 🛠️ Tech Stack

![Python](https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?logo=numpy&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?logo=pandas&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?logo=scikit-learn&logoColor=white)
![NLTK](https://img.shields.io/badge/NLTK-NLP-green)
![Matplotlib](https://img.shields.io/badge/Matplotlib-Visualization-blue)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?logo=jupyter&logoColor=white)



## 📋 Requirements

```
numpy
pandas
matplotlib
scikit-learn
nltk
tqdm
```

Install all with:

```bash
pip install numpy pandas matplotlib scikit-learn nltk tqdm
```



## 📄 License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.



## 👤 Author

**Malay Doshi**

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Malay_Doshi-0A66C2?logo=linkedin&logoColor=white)](https://www.linkedin.com/in/malaydoshi/)
[![X / Twitter](https://img.shields.io/badge/X-@Malay60814567-000000?logo=x&logoColor=white)](https://x.com/Malay60814567)
[![GitHub](https://img.shields.io/badge/GitHub-Malaydoshi711-181717?logo=github&logoColor=white)](https://github.com/Malaydoshi711)



<div align="center">

If you found this project useful, consider giving it a ⭐ on [GitHub](https://github.com/Malaydoshi711/Network-Security-Prediction)!

</div>
