#  SpaceX Falcon 9 Landing Prediction

> An end-to-end data science project analyzing SpaceX Falcon 9 launches and predicting first-stage landing success using machine learning.

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat-square&logo=pandas&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat-square&logo=scikitlearn&logoColor=white)
![Plotly](https://img.shields.io/badge/Plotly-3F4F75?style=flat-square&logo=plotly&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=flat-square&logo=jupyter&logoColor=white)

##  Overview

SpaceX's ability to recover and reuse the first stage of its Falcon 9 rocket is a major part of its launch strategy.

This project explores historical Falcon 9 launch data and builds machine learning models to answer a simple question:

> **Can we predict whether a Falcon 9 first stage will successfully land?**

The project follows a complete data science workflow:

**Data Collection → Data Wrangling → EDA → Interactive Visualization → Machine Learning → Model Evaluation**

Data was collected through the SpaceX API and web scraping, explored using Python and SQL, visualized with Plotly and Folium, and ultimately used to train several classification models.

---

##  Project Workflow

###  1. Data Collection

Falcon 9 launch data was collected using two approaches:

- SpaceX REST API
- Web scraping with BeautifulSoup

Launch information included variables such as:

- Payload mass
- Orbit
- Launch site
- Booster flight history
- Grid fins
- Reuse status
- Landing legs
- Booster block
- Booster serial
- Latitude & longitude
- Landing outcome

---

###  2. Data Wrangling

The raw launch data was cleaned and transformed for analysis.

This included:

- Handling missing values
- Filtering the dataset to Falcon 9 launches
- Converting landing outcomes into a binary target
- Preparing categorical features
- One-hot encoding features for machine learning

The prediction target was represented as:

```text
0 → Unsuccessful landing
1 → Successful landing
```

---

###  3. Exploratory Data Analysis

Exploratory analysis was performed to investigate relationships between launch characteristics and landing success.

The analysis examined factors such as:

- Flight number vs. launch success
- Payload mass vs. launch outcome
- Launch site performance
- Orbit type
- Booster characteristics
- Changes in success rate over time

Both Python-based visualization and SQL queries were used to explore the dataset.

---

###  4. Geospatial Analysis

Launch sites were analyzed geographically using **Folium**.

Interactive maps were created to explore:

- SpaceX launch site locations
- Successful and unsuccessful launches
- Nearby infrastructure
- Geographic relationships around launch facilities

This added a spatial dimension to the exploratory analysis.

---

###  5. Interactive Dashboard

An interactive dashboard was built using **Plotly Dash** to make the launch data easier to explore.

The dashboard includes:

- Launch-site filtering
- Success/failure visualization
- Payload range filtering
- Payload vs. landing outcome analysis
- Booster category visualization

Users can dynamically explore how launch conditions relate to successful first-stage recovery.

---

##  Machine Learning

The final stage of the project treats landing prediction as a **binary classification problem**.

After preprocessing and standardization, the dataset contained:

**90 launch observations**  
**83 model features**

The data was split into training and testing sets and several classification algorithms were evaluated.

`GridSearchCV` was used to tune model hyperparameters.

### Models Evaluated

| Model | Cross-Validation Score | Test Accuracy |
|---|---:|---:|
| Logistic Regression | 84.64% | 83.33% |
| Support Vector Machine | 84.82% | 83.33% |
| **Decision Tree** | **87.50%** | **94.44%** |
| K-Nearest Neighbors | 84.82% | 83.33% |

###  Best Result

The **Decision Tree classifier** produced the highest test-set accuracy:

# **94.44%**

This experiment demonstrates how launch characteristics can be used to model historical Falcon 9 first-stage landing outcomes.

> **Note:** The dataset is relatively small, so the 94.44% test accuracy should be interpreted as the result of this experiment rather than an estimate of real-world predictive performance.

---

##  Tech Stack

### Data & Analysis

`Python` • `Pandas` • `NumPy` • `SQL`

### Machine Learning

`scikit-learn` • `GridSearchCV` • `Logistic Regression` • `SVM` • `Decision Trees` • `KNN`

### Visualization

`Matplotlib` • `Seaborn` • `Plotly` • `Folium`

### Data Collection

`REST APIs` • `Requests` • `BeautifulSoup`

### Application

`Plotly Dash` • `Jupyter Notebook`

---

##  Repository Structure

```text
spacex-landing-prediction/
│
├── Data Collection API.ipynb
│   └── Collect Falcon 9 launch data through the SpaceX API
│
├── Data Collection with Web Scraping.ipynb
│   └── Extract historical launch information from the web
│
├── Data Wrangling.ipynb
│   └── Clean and prepare launch data
│
├── EDA.ipynb
│   └── Exploratory data analysis
│
├── EDA with Data Visualization.ipynb
│   └── Visual exploration of launch characteristics
│
├── Interactive Visual Analytics with Folium lab.ipynb
│   └── Geographic launch-site analysis
│
├── Machine Learning Prediction.ipynb
│   └── Train, tune, and evaluate classification models
│
├── spacex_dash_app.py
│   └── Interactive Plotly Dash application
│
├── Final Assignment.ipynb
│
└── README.md
```

---

##  Skills Demonstrated

This project combines several stages of the data science lifecycle:

- REST API integration
- Web scraping
- Data cleaning & preprocessing
- Exploratory data analysis
- SQL querying
- Feature engineering
- Categorical encoding
- Data standardization
- Interactive visualization
- Geospatial analysis
- Dashboard development
- Supervised machine learning
- Hyperparameter tuning
- Classification model comparison
- Model evaluation

---

##  Key Takeaways

The project demonstrates how raw external data can be transformed into a complete predictive analytics workflow.

Rather than focusing only on model training, the project covers the full process:

```text
Raw Data
   ↓
Collection
   ↓
Cleaning
   ↓
Exploration
   ↓
Visualization
   ↓
Feature Preparation
   ↓
Model Training
   ↓
Evaluation
```

The strongest result in the saved experiment came from the **Decision Tree model with 94.44% test accuracy**.

---

## Project Background

This project was completed as part of the **IBM Data Science Professional Certificate's Applied Data Science Capstone**.

The IBM coursework provided the project framework and guided lab structure. I completed the data collection, preprocessing, exploratory analysis, visualization, dashboard development, and machine learning exercises contained in this repository.

I maintain the project here as a portfolio demonstration of the end-to-end data science techniques developed throughout the certificate.

---

##  Author

**Aristotelis Theocharoulas**

Computer Science graduate interested in **Applied AI, Data Science, and Software Engineering**.

[![GitHub](https://img.shields.io/badge/GitHub-aristostheo-181717?style=flat-square&logo=github)](https://github.com/aristostheo)

---

*Educational data science project based on historical SpaceX launch data. Not affiliated with or endorsed by SpaceX.*
