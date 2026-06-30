# 👋 Hi, I'm Xingyu Shi 

🎓 Graduate student in **Quantitative Methods in the Social Sciences (QMSS)** at Columbia University  
💼 Data Scientist · Machine Learning Researcher · Applied NLP + Finance  
📍 New York, USA  

I focus on **data-driven decision-making**, **predictive modeling**, and **AI techniques applied to real-world problems**—from medical image classification to financial-market analytics and global socioeconomic indicators.

---

## 🔍 About Me

- 🌐 Interested in **Machine Learning**, **Financial Econometrics**, **NLP for Markets**, **Deep Learning**, and **Data-Driven Product Strategy**  
- 🤖 Experience building **neural networks** (CNN, ResNet, VGG, LSTM), **classical ML models**, and **end-to-end data pipelines**  
- 📊 Passionate about transforming data into insights that directly inform policy, finance, or product development  
- 🧠 Currently expanding skills in **MLOps**, **model interpretability**, and **large-scale sentiment analysis**  

---

## 🚀 Featured Data Science Projects

### 🩺 **1. Medical Image Classification — Deep Learning for COVID / Pneumonia Detection**  
🔗 *Project Repo:* https://github.com/Yifan-Zang/GR5074_Project2_MedicalImageClassification  

Using a dataset of **15,153 radiography images**, we built and compared:  
- ✔ **Baseline CNN**  
- ✔ **ResNet50**  
- ✔ **VGG16**  
- ✔ **DenseNet121**  
- ✔ **InceptionV3**

**Key Highlights:**
- Achieved **96.28% test accuracy** with **VGG16** (best-performing model)  
- Implemented **GPU-accelerated training**, **data augmentation**, and **transfer learning**  
- Evaluated models using **confusion matrices, learning curves, and loss analysis**  
- Applicable to real clinical triage pipelines and medical AI systems


---


### 📈 **2. Master Thesis — News Sentiment & Next-Day Return Predictability in U.S. Tech Stocks (2021–2024)**
🔗 *Project Repo:* https://github.com/xingyushi1119/masterthesis
**Research Question:**  
> Does sector-level news sentiment (macro + industry + firm-level) predict next-day excess returns for U.S. technology stocks?

**Methods & Data:**
- Daily CRSP returns  
- RavenPack Event Sentiment Score (ESS)  
- Fama–French 6-factor model  
- Panel regressions with fixed effects  
- Leave-one-out (LOO) sentiment construction  
- Robustness checks + heterogeneity tests (size, volatility, liquidity)

**Key Findings (Short Summary):**
- Sector sentiment has **no broad next-day predictive power**, consistent with fast information assimilation  
- **Significant heterogeneity:** smaller firms react more strongly to aggregate sentiment  
- Results robust to FF6 controls, alternate clustering, and weekly aggregation  

---
### 📈 **3.ETF Tracker (Group project) **
🔗 *Project Repo:* 
A full-stack web application that lets users browse ETFs, stocks, sectors, and
market indices, explore the relationships between them, and get sector-based
ETF recommendations. Built as a database systems course project (group of 3) on
a PostgreSQL backend with a Flask front end.

> **Note:** This is a group project. My primary contributions were the
> relational schema design, the Python data-ingestion pipeline, and the
> SQL analytics behind the recommendation and exposure features.

---

## What it does

- **Browse & search** ETFs, stocks, sectors, and indices, with detail pages
  showing how entities relate (e.g. which ETFs hold a given stock and at what
  weight).
- **User accounts** with registration, login, password hashing, and sessions.
- **Favorites & personalized dashboard** for logged-in users.
- **Sector-similarity ETF recommendations** based on the sectors of the ETFs a
  user has liked.
- **Comments** on ETF pages, with comment counts maintained automatically by a
  database trigger.

---

## Data model

A normalized relational schema centered on funds and their constituents:

- **Core entities:** `ETF`, `Stock`, `Sector`, `market_index`, `Fund_Family`
- **Weighted many-to-many relationships:**
  - `Stock_in_ETF` (stock ↔ ETF, with position weight)
  - `ETF_has_Sector` (ETF ↔ sector, with sector weight)
  - `Stock_in_Index` (stock ↔ index, with weight)
  - `Fund_has_ETF` (fund family ↔ ETF)
- **User tables:** `Users`, `User_Likes_ETF`
- Referential integrity enforced with primary and foreign key constraints.

---

## Interesting database operations

**Sector-similarity recommendations.** For each ETF a user likes, the query
finds its sectors, then finds other ETFs sharing those sectors, counts the
shared sectors as a similarity score, ranks, and de-duplicates across the
user's liked set. Implemented with CTEs and multi-table joins.

**Stock cross-holding view.** Joins `Stock`, `Sector`, `Stock_in_ETF`, and
`ETF` to show, for any stock, every ETF that holds it ordered by position
weight — surfacing where a stock has the most exposure across the ETF universe.

**Automatic comment counts.** A PL/pgSQL trigger (`update_comment_count()`)
increments a stored comment count on each ETF whenever a new comment is added.

---

## Stack

Python (Flask), PostgreSQL (with PL/pgSQL), HTML/Bootstrap. Data was loaded
from a curated source spreadsheet via a pandas + psycopg2 ingestion script that
validated foreign keys against existing dimension tables before loading.

---

## Repo layout

```
app.py                  Flask app (routes, queries, auth)
templates/              Jinja/Bootstrap templates
create_user_tables.sql  User & favorites tables
SQLSetup/               Schema setup, import scripts, analytical queries
```

## Running locally

```bash
pip install -r requirements.txt
# set your PostgreSQL connection details (host, db, user, schema)
python3 app.py
```

The app expects a populated PostgreSQL database; see `SQLSetup/` for the
schema and import scripts.

## 🛠️ Tech Stack

### **Languages**
- Python (NumPy, Pandas, Scikit-Learn, TensorFlow, Keras, Statsmodels)  
- SQL  
- R (Econometrics + Data Analysis)  

### **Tools & Frameworks**
- TensorFlow / Keras  
- Scikit-Learn  
- GridSearchCV  
- Jupyter Notebook  
- Git & GitHub  
- WRDS, RavenPack, CRSP / Compustat  

### **Specialties**
- Machine Learning  
- Deep Learning for Imaging  
- Feature Engineering  
- NLP-based sentiment analysis  
- Econometrics (panel models, factor models)  
- Data Visualization  

---

## 📬 Get in Touch

📫 Email: xs2557@columbia.edu/ shixingyuemily@gmail.com / xs2048@nyu.edu
🔗 LinkedIn: *www.linkedin.com/in/xingyu-shi-02734b325*  
📦 GitHub: https://github.com/xingyushi1119 

Looking for **Data Science / Machine Learning / Quantitative Analyst** roles.

Thanks for stopping by!  
✨ *Let’s build something impactful together.*


