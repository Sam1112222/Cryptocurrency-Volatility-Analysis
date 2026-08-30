# Cryptocurrency-Volatility-Analysis
# 📈 Cryptocurrency Volatility Prediction

<p align="center">
  <b>An End-to-End Machine Learning Project for Predicting Cryptocurrency Volatility</b>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.12-blue?style=for-the-badge&logo=python"/>
  <img src="https://img.shields.io/badge/Pandas-Data%20Processing-150458?style=for-the-badge&logo=pandas"/>
  <img src="https://img.shields.io/badge/Scikit--Learn-Machine%20Learning-F7931E?style=for-the-badge&logo=scikit-learn"/>
  <img src="https://img.shields.io/badge/Streamlit-Deployment-FF4B4B?style=for-the-badge&logo=streamlit"/>
  <img src="https://img.shields.io/badge/NumPy-Scientific%20Computing-013243?style=for-the-badge&logo=numpy"/>
</p>

---

## 🚀 Project Overview

Cryptocurrency markets are highly dynamic and are known for significant price fluctuations. Understanding and forecasting market volatility can help in **risk analysis, portfolio management, and data-driven decision making**.

This project builds an **end-to-end Machine Learning pipeline** to predict the **7-day volatility of cryptocurrencies** using historical market data.

The project covers the complete workflow:

**Raw Data → Data Cleaning → Feature Engineering → EDA → Model Training → Evaluation → Prediction → Streamlit Deployment**

---

## 🎯 Objectives

* Analyze historical cryptocurrency market data
* Clean and preprocess raw financial data
* Generate meaningful time-series features
* Calculate rolling cryptocurrency volatility
* Train a Machine Learning regression model
* Evaluate model performance using standard regression metrics
* Save the trained model and preprocessing scaler
* Build an interactive Streamlit prediction interface

---

## 🧠 Machine Learning Approach

The project predicts **7-day rolling volatility** using historical market and trading information.

### Target Variable

```text
vol_7d
```

The target represents the rolling standard deviation of daily returns over a 7-day period.

### Daily Return

```text
daily_return = (close - open) / open
```

### 7-Day Volatility

```text
vol_7d = Standard Deviation of Daily Returns over 7 Days
```

---

## 🛠️ Features Used

The model uses the following features:

| Feature           | Description                            |
| ----------------- | -------------------------------------- |
| `open`            | Opening cryptocurrency price           |
| `high`            | Highest price during the day           |
| `low`             | Lowest price during the day            |
| `close`           | Closing cryptocurrency price           |
| `volume`          | Daily trading volume                   |
| `market_cap`      | Cryptocurrency market capitalization   |
| `daily_return`    | Daily percentage return                |
| `liquidity_ratio` | Trading volume relative to market cap  |
| `ma7`             | 7-day moving average of closing price  |
| `ma30`            | 30-day moving average of closing price |

---

## 🔄 Project Workflow

```text
                 ┌──────────────────────┐
                 │   Historical Data    │
                 │     dataset.csv      │
                 └──────────┬───────────┘
                            ↓
                 ┌──────────────────────┐
                 │ Data Preprocessing   │
                 │ • Cleaning           │
                 │ • Date Conversion    │
                 │ • Missing Values     │
                 │ • Sorting            │
                 └──────────┬───────────┘
                            ↓
                 ┌──────────────────────┐
                 │ Feature Engineering  │
                 │ • Daily Returns      │
                 │ • 7D Volatility      │
                 │ • Liquidity Ratio    │
                 │ • MA7 / MA30         │
                 └──────────┬───────────┘
                            ↓
                 ┌──────────────────────┐
                 │ Feature Scaling      │
                 │ StandardScaler       │
                 └──────────┬───────────┘
                            ↓
                 ┌──────────────────────┐
                 │ Random Forest        │
                 │ Regressor            │
                 └──────────┬───────────┘
                            ↓
                 ┌──────────────────────┐
                 │ Model Evaluation     │
                 │ MAE • RMSE • R²      │
                 └──────────┬───────────┘
                            ↓
                 ┌──────────────────────┐
                 │ Streamlit Application│
                 │ Interactive Predict  │
                 └──────────────────────┘
```

---

## 📊 Dataset

The project uses historical daily cryptocurrency market data.

### Main Columns

```text
date
open
high
low
close
volume
market_cap
crypto_name
```

The preprocessing pipeline standardizes column names, converts dates, sorts records by cryptocurrency and date, and handles missing values.

---

## 🤖 Model

### Random Forest Regressor

The project uses a **Random Forest Regression** model with:

```text
n_estimators = 200
random_state = 42
```

Before training, numerical features are standardized using:

```text
StandardScaler
```

The trained model and scaler are saved using `joblib`.

---

## 📈 Model Evaluation

The model is evaluated using three regression metrics:

| Metric       | Purpose                                                      |
| ------------ | ------------------------------------------------------------ |
| **MAE**      | Measures average absolute prediction error                   |
| **RMSE**     | Penalizes larger prediction errors                           |
| **R² Score** | Measures how well the model explains variation in the target |

### Current Results

| Metric |     Result |
| ------ | ---------: |
| MAE    | `0.035549` |
| RMSE   | `0.142268` |
| R²     |  `-7.5304` |

> ⚠️ The current R² score indicates that the model requires further improvement before it can be considered reliable for real-world volatility forecasting.

This provides an opportunity for future experimentation with better time-series validation, feature selection, hyperparameter tuning, and sequence-based models.

---

## 📁 Project Structure

```text
Cryptocurrency-Volatility-Prediction/
│
├── 📂 app/
│   └── streamlit_app.py
│
├── 📂 data/
│   └── dataset.csv
│
├── 📂 models/
│   └── scaler.pkl
│
├── 📂 notebook/
│   └── crypto_volatility_prediction_colab.ipynb
│
├── 📂 reports/
│   ├── EDA_Report.md
│   ├── Final_Report.md
│   ├── HLD.md
│   ├── LLD.md
│   └── Pipeline.md
│
├── 📂 src/
│   ├── data_preprocessing.py
│   ├── feature_engineering.py
│   └── model_training.py
│
└── README.md
```

---

## 💻 Technologies Used

### Programming & Data

* 🐍 Python
* 🐼 Pandas
* 🔢 NumPy

### Machine Learning

* Scikit-learn
* Random Forest Regression
* StandardScaler
* Joblib

### Visualization & Analysis

* Matplotlib
* Exploratory Data Analysis

### Deployment

* Streamlit

### Development

* Jupyter Notebook
* Google Colab
* Git & GitHub

---

## ⚙️ Installation

### 1. Clone the Repository

```bash
git clone <YOUR_REPOSITORY_URL>
```

### 2. Navigate to the Project

```bash
cd Cryptocurrency-Volatility-Prediction
```

### 3. Create a Virtual Environment

```bash
python -m venv venv
```

### 4. Activate the Environment

#### Windows

```bash
venv\Scripts\activate
```

#### Linux / macOS

```bash
source venv/bin/activate
```

### 5. Install Dependencies

```bash
pip install pandas numpy scikit-learn matplotlib streamlit joblib
```

---

## ▶️ Running the Project

### Train the Model

Run the model training script:

```bash
python src/model_training.py
```

This performs:

```text
Data Loading
      ↓
Data Cleaning
      ↓
Feature Engineering
      ↓
Feature Scaling
      ↓
Model Training
      ↓
Model Evaluation
      ↓
Model Saving
```

The trained model and scaler are stored in the `models/` directory.

---

## 🌐 Run the Streamlit Application

Start the application with:

```bash
streamlit run app/streamlit_app.py
```

The application provides an interactive interface where users can enter:

* Open Price
* High Price
* Low Price
* Close Price
* Trading Volume
* Market Capitalization

The application then generates a predicted **7-day volatility value**.

---

## 📸 Application Preview

Add your Streamlit screenshot here:

```markdown
![Streamlit Application](images/streamlit_app.png)
```

Recommended folder:

```text
images/
└── streamlit_app.png
```

---

## 📊 Exploratory Data Analysis

The project includes an EDA report covering:

* Cryptocurrency price distributions
* Trading volume analysis
* Market capitalization
* Daily returns
* Volatility behavior
* Moving averages
* Relationships between market variables

Detailed analysis is available in:

```text
reports/EDA_Report.md
```

---

## 📚 Documentation

The repository contains additional technical documentation:

| Document          | Description               |
| ----------------- | ------------------------- |
| `EDA_Report.md`   | Exploratory Data Analysis |
| `HLD.md`          | High-Level Design         |
| `LLD.md`          | Low-Level Design          |
| `Pipeline.md`     | ML Pipeline Documentation |
| `Final_Report.md` | Final Project Report      |

---

## 🔮 Future Improvements

The current implementation provides a foundation for cryptocurrency volatility prediction. Several improvements can make the system more robust.

### 📌 Model Improvements

* Hyperparameter tuning using GridSearchCV / RandomizedSearchCV
* Compare Random Forest with XGBoost and Gradient Boosting
* Experiment with LightGBM
* Use ensemble approaches

### ⏱️ Time-Series Improvements

* Use proper chronological train/test splitting
* Implement walk-forward validation
* Add lag features
* Add rolling statistical features
* Experiment with LSTM / GRU networks

### 📡 Real-Time Prediction

Future versions could integrate live cryptocurrency market APIs to provide:

```text
Live Market Data
       ↓
Automatic Feature Engineering
       ↓
Trained ML Model
       ↓
Real-Time Volatility Prediction
```

### 📊 Dashboard Improvements

The Streamlit application can be extended with:

* Historical volatility charts
* Cryptocurrency comparison
* Interactive price charts
* Prediction history
* Risk-level classification
* Real-time market data

---

## ⚠️ Disclaimer

This project is developed for **educational and research purposes only**.

Cryptocurrency markets are highly volatile, and machine learning predictions are not guaranteed to be accurate.

This project should **not be considered financial or investment advice**.

---

## 👨‍💻 Author

### Sambhav Saini

**Computer Science Engineering Graduate | AI & Data Analytics Enthusiast**

Interested in:

* 🤖 Artificial Intelligence
* 📊 Data Analytics
* 🧠 Machine Learning
* 🔗 Generative AI & RAG
* 🐍 Python
* 🗄️ SQL

---

## ⭐ If You Found This Project Useful

If you found this project interesting or useful:

⭐ **Star the repository**

🍴 **Fork the repository**

💡 **Explore the code and reports**

📌 **Feel free to suggest improvements**

---

<p align="center">
  <b>Built with Python, Machine Learning & Data Analytics 🚀</b>
</p>
