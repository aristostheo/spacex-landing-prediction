#  SpaceX Falcon 9 Landing Prediction

An end-to-end data science project exploring **SpaceX Falcon 9 launch data** and using machine learning to predict whether the first stage of a launch will successfully land.

The project covers the complete data science workflow — from collecting and cleaning raw data to exploratory analysis, interactive visualization, dashboard development, and predictive modeling.

>  Developed as the capstone project for the **IBM Data Science Professional Certificate** on Coursera.

---

##  Project Overview

SpaceX has significantly reduced the cost of orbital launches by designing Falcon 9 rockets with reusable first stages.

A major factor in the economics of a launch is therefore whether the first stage can be recovered successfully.

This project investigates historical SpaceX launch data to answer questions such as:

- How has Falcon 9 landing success changed over time?
- Which launch sites have the highest success rates?
- How do payload mass and orbit type relate to landing outcomes?
- Are certain boosters or mission characteristics associated with higher success rates?
- Can machine learning predict whether a Falcon 9 first stage will land successfully?

The final goal is to build and evaluate classification models capable of predicting **landing success** from historical launch characteristics.

---

##  Data Science Workflow

```text
        SpaceX API + Web Scraping
                   │
                   ▼
            Data Collection
                   │
                   ▼
            Data Wrangling
                   │
                   ▼
       Exploratory Data Analysis
             ┌─────┴─────┐
             ▼           ▼
            SQL     Visualization
                         │
                  ┌──────┴──────┐
                  ▼             ▼
              Plotly Dash     Folium
                  │
                  └──────┬──────┘
                         ▼
                Machine Learning
                         │
                         ▼
               Landing Prediction
```

---

##  Technologies

### Languages & Data

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-4479A1?style=for-the-badge&logo=database&logoColor=white)

### Machine Learning & Visualization

![Scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=for-the-badge&logo=scikitlearn&logoColor=white)
![Plotly](https://img.shields.io/badge/Plotly-3F4F75?style=for-the-badge&logo=plotly&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white)

**Additional tools:** Dash • Folium • BeautifulSoup • Requests • Matplotlib

---

##  Project Stages

### 1.  Data Collection — SpaceX API

Historical Falcon 9 launch data was collected using the **SpaceX REST API**.

The collected data includes information such as:

- Flight number
- Launch date
- Booster version
- Payload mass
- Orbit
- Launch site
- Landing outcome
- Flight history
- Grid fins
- Reused boosters
- Landing legs

The API responses were transformed into a structured dataset for further analysis.

📓 `Data Collection API.ipynb`

---

### 2. 🕸️ Data Collection — Web Scraping

Additional Falcon 9 launch records were collected from web-based sources using Python web scraping techniques.

The process involved:

1. Retrieving HTML content
2. Parsing launch tables
3. Extracting relevant mission information
4. Cleaning extracted values
5. Converting the results into a structured dataset

📓 `Data Collection with Web Scraping.ipynb`

---

### 3.  Data Wrangling

The collected data required preprocessing before it could be analyzed or used for machine learning.

This stage included:

- Handling missing values
- Filtering Falcon 9 launches
- Standardizing landing outcomes
- Transforming categorical variables
- Creating a binary landing-success classification target
- Preparing features for later analysis

Landing outcomes were ultimately represented as a classification problem:

```text
1 → Successful landing
0 → Unsuccessful landing
```

📓 `Data Wrangling.ipynb`

---

### 4.  Exploratory Data Analysis

Exploratory data analysis was used to investigate relationships between launch characteristics and successful landings.

The analysis explores variables including:

- Flight number
- Payload mass
- Launch site
- Orbit type
- Booster version
- Launch year
- Landing success

Visual analysis helps identify patterns that may influence the probability of recovering the Falcon 9 first stage.

📓 `EDA.ipynb`  
📓 `EDA with Data Visualization.ipynb`

---

### 5.  SQL Analysis

Structured launch data was queried using SQL to answer analytical questions about SpaceX missions.

The analysis included operations such as:

- Filtering launches by site
- Aggregating payload information
- Comparing mission outcomes
- Examining booster performance
- Identifying trends across launch records

This portion of the project demonstrates the use of **SQL for analytical querying alongside Python-based analysis**.

---

### 6.  Interactive Launch Site Analysis with Folium

An interactive map was created using **Folium** to investigate the geographic characteristics of SpaceX launch sites.

The map includes:

- Launch site markers
- Successful and unsuccessful launch outcomes
- Geographic relationships surrounding launch facilities
- Distance analysis between launch sites and nearby infrastructure

This provides a geographic perspective on the launch data that is difficult to capture through traditional charts alone.

📓 `Interactive Visual Analytics with Folium lab.ipynb`

---

### 7.  Interactive Plotly Dash Dashboard

An interactive analytics dashboard was developed with **Plotly Dash**.

The dashboard allows users to dynamically explore Falcon 9 launch performance.

### Dashboard Features

**Launch Site Selection**

Users can filter launch records by launch site or examine all sites together.

**Launch Success Visualization**

A pie chart displays the proportion of successful and unsuccessful launches for the selected site.

**Payload Analysis**

An interactive scatter plot explores the relationship between:

- Payload mass
- Booster category
- Landing success

A payload-range slider allows the dataset to be filtered dynamically.

📄 `spacex_dash_app.py`

---

##  Machine Learning

The final stage transforms the SpaceX dataset into a supervised machine learning classification problem.

The objective is:

> **Given the characteristics of a Falcon 9 launch, can we predict whether its first stage will successfully land?**

The machine learning workflow includes:

1. Feature preprocessing
2. Categorical encoding
3. Feature standardization
4. Train/test preparation
5. Hyperparameter tuning
6. Model training
7. Model comparison
8. Evaluation

Several classification algorithms were explored, including:

- Logistic Regression
- Support Vector Machine (SVM)
- Decision Tree
- K-Nearest Neighbors (KNN)

Model performance was compared to determine how effectively historical launch characteristics could predict landing outcomes.

📓 `Machine Learning Prediction.ipynb`

---

##  Repository Structure

```text
spacex-data-science/
│
├── Data Collection API.ipynb
├── Data Collection with Web Scraping.ipynb
├── Data Wrangling.ipynb
│
├── EDA.ipynb
├── EDA with Data Visualization.ipynb
│
├── Interactive Visual Analytics with Folium lab.ipynb
│
├── Machine Learning Prediction.ipynb
│
├── spacex_dash_app.py
│
├── Final Assignment.ipynb
├── DataScienceEcosystem.ipynb
│
└── README.md
```

> Some notebooks in this repository were completed as individual labs throughout the IBM Data Science Professional Certificate and support the techniques used in the final capstone.

---

##  Skills Demonstrated

This project brings together several areas of data science in one workflow:

**Data Engineering**
- REST API consumption
- Web scraping
- Data extraction
- Data cleaning and transformation

**Data Analysis**
- Pandas
- NumPy
- Exploratory data analysis
- SQL
- Feature analysis

**Data Visualization**
- Matplotlib
- Plotly
- Folium
- Interactive geographic visualization

**Application Development**
- Plotly Dash
- Interactive filtering
- Dynamic charts

**Machine Learning**
- Classification
- Feature preprocessing
- Model training
- Hyperparameter tuning
- Model evaluation and comparison

---

##  Running the Dashboard

Clone the repository:

```bash
git clone https://github.com/aristostheo/spacex-data-science.git
cd spacex-data-science
```

Install the required Python packages:

```bash
pip install pandas numpy plotly dash scikit-learn folium
```

Run the Dash application:

```bash
python spacex_dash_app.py
```

Then open the local address displayed by Dash in your browser.

---

##  Project Background

This project was completed as part of the **IBM Data Science Professional Certificate**.

The certificate provided the project structure and datasets/labs used throughout the capstone. I completed the associated data collection, analysis, visualization, dashboard, and machine-learning exercises to apply the data science techniques covered throughout the program.

The repository is maintained as a portfolio record of that work and the technical skills developed through the project.

---

##  Author

**Aristotelis Theocharoulas**

Computer Science graduate interested in **Data Science, Applied AI, and Software Engineering**.

[![GitHub](https://img.shields.io/badge/GitHub-aristostheo-181717?style=flat&logo=github)](https://github.com/aristostheo)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=flat&logo=linkedin)](www.linkedin.com/in/aristotelis-theocharoulas-a80859233)

---

⭐ If you found this project interesting, feel free to explore the notebooks and dashboard!
