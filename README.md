# 📈 Tesla Stock Price Prediction & Buy/Sell Signal Dashboard

This project applies **machine learning** on historical **Tesla (TSLA)** stock data to predict short-term price direction and generate **Buy/Sell trading signals**. The final dataset is visualized using **Tableau** to build an interactive dashboard showing price trends, signal markers, volume spikes, and model accuracy.

---

## 📁 Dataset

- **Source:** [Yahoo Finance – Tesla (TSLA) Historical Data](https://finance.yahoo.com/quote/TSLA/history)
- **File Used:** `stock_data_cleaned.csv`
- **Duration:** Multiple years of daily TSLA stock data
- **Fields:**
  - `Date`, `Open`, `High`, `Low`, `Close`, `Volume`
  - `MA5`, `MA10`, `Return`, `Volume_Change`
  - `Target` (actual price direction)
  - `Predicted` (model output)
  - `Position` (Buy/Sell/Hold signal)

---

## 🎯 Objectives

- Perform exploratory data analysis (EDA) on Tesla’s price trends
- Engineer technical features like moving averages and return %
- Train a machine learning model to predict next-day price movement
- Generate Buy/Sell signals based on model predictions
- Visualize results in Tableau as an investor dashboard

---

## 🧰 Tools & Libraries

- **Python (Jupyter Notebook):**
  - `pandas`, `matplotlib`, `seaborn`, `scikit-learn`
- **Machine Learning Model:**
  - Logistic Regression
- **Visualization:**
  - Tableau Desktop / Tableau Public

---

## 📊 Key Visualizations (Built in Tableau)

- 📉 **Tesla Close Price with MA5 & MA10 lines**
- 🔼 **Buy/Sell Signal markers** (green ▲ for Buy, red ▼ for Sell)
- 📦 **Volume area chart** to visualize trading volume spikes
- 📈 **Actual vs Predicted** price direction chart
- 🧠 **KPI card showing model prediction accuracy**

---

## 🧠 Machine Learning Pipeline

- **Target:** `1` if tomorrow’s `Close` > today’s, else `0`
- **Features Used:**
  - Moving Averages (MA5, MA10)
  - Price Return %
  - Volume Change %
- **Model:** Logistic Regression (baseline)
- **Evaluation:**
  - Accuracy Score
  - Confusion Matrix
- **Signal Logic:**
  - `Position = 1` → Buy
  - `Position = -1` → Sell
  - `Position = 0` → Hold

---

## 📌 Insights

- 📈 Strong prediction accuracy in upward trends
- 🔁 Moving average crossovers align with model decisions
- 💰 Signal markers provide potential entry/exit points
- 📊 Dashboard makes it easy to interpret market movement

---

## 🏁 How to Use

### ⚙️ Python Side
- Open `tesla_stock_ml.ipynb`
- Run all cells to:
  - Load and clean Tesla stock data
  - Engineer features and target
  - Train ML model and generate predictions
  - Export final CSV using:
    ```python
    df.to_csv('stock_data_cleaned.csv', index=False)
    ```

### 📈 Tableau Side
- Import `stock_data_cleaned.csv` into Tableau
- Create:
  - Line chart: `Close`, `MA5`, `MA10` over `Date`
  - Signal markers using `Position` → Shape + Color
  - Volume Area chart
  - Accuracy KPI using:
    ```sql
    (SUM(IF [Target] = [Predicted] THEN 1 ELSE 0 END) / COUNT([Predicted])) * 100
    ```

---

## 🔮 Future Work

- Add advanced models (e.g., Random Forest, XGBoost)
- Include technical indicators (RSI, MACD)
- Simulate profit/loss based on signal strategy
- Deploy in Streamlit or Flask as a live web app

---

## 🙌 Special Thanks

This project was guided with the help of **ChatGPT by OpenAI**, which assisted in:
- ML pipeline design
- Feature engineering strategy
- Tableau dashboard structure
- Python debugging and improvements

---

## 📬 Contact

Created by **Aryan Gaikwad**  
📧 aryangaikwad3986@gmail.com | 🔗 www.linkedin.com/in/aryan-gaikwad-9bb560285

