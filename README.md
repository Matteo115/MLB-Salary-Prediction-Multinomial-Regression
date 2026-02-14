# MLB Salary Prediction using Multinomial Logistic Regression

![R](https://img.shields.io/badge/Language-R-blue) ![Status](https://img.shields.io/badge/Status-Completed-success)

## 📌 Project Overview
This project focuses on predicting the salary levels of Major League Baseball (MLB) players based on their performance statistics. Using the **Hitters** dataset, the objective was to classify players into three salary categories (**Low, Medium, High**) using **Multinomial Logistic Regression**.

This analysis was conducted as part of an academic project at **LUISS Guido Carli University**.

## 📊 Dataset
The analysis uses the `Hitters.csv` dataset, which contains statistics and salaries for baseball players.
* **Observations:** 322 players (reduced to 259 after cleaning missing values).
* **Target Variable:** `SalaryLevel` (Created by binning the continuous `Salary` variable into tertiles).
* **Predictors:** Various performance metrics (e.g., `AtBat`, `Hits`, `HomeRuns`, `Years`, etc.).

## ⚙️ Methodology

The project follows a structured Data Science pipeline:

### 1. Exploratory Data Analysis (EDA)
* Data cleaning (handling missing values in the `Salary` column).
* Factorization of categorical variables (`League`, `Division`).
* Analysis of distributions and correlations (detected right-skewness in salary and multicollinearity among career stats).

### 2. Modeling Strategy
We implemented a **Multinomial Logistic Regression** model using the `nnet` package. The training process involved:
* **Data Partitioning:** Stratified splitting (70% Train, 30% Test).
* **Validation Methods:** Comparison between **Vanilla Validation Set** and **K-Fold Cross-Validation (K=5)** to ensure robustness.

### 3. Model Optimization
* **Baseline Model:** Included all predictors.
* **Feature Selection:** Removed statistically insignificant variables (high p-values).
* **Stepwise Selection:** Applied Backward Stepwise Selection to minimize AIC.

## 📈 Key Results

We compared the Full Model against an Improved (Reduced) Model. The optimization process successfully increased accuracy while reducing model complexity.

| Metric | Full Model | Improved Model (Final) |
| :--- | :---: | :---: |
| **Validation Accuracy** | 72.2% | **72.2%** |
| **Test Set Accuracy** | 61.8% | **64.5%** |
| **5-Fold CV Accuracy** | 59.2% | **64.7%** |
| **AIC** | 264.13 | **255.02** |

The final model generalizes better to unseen data, demonstrating that removing noisy variables (like `Hits`, `RBI`, `Runs`) improved the predictive power.

## 🛠️ Technologies & Libraries
* **Language:** R
* **Libraries:**
    * `nnet` (Multinomial Regression)
    * `caret` (Machine Learning workflow & Cross-Validation)
    * `ggplot2` (Data Visualization)
    * `dplyr` / `tidyr` (Data Manipulation)
    * `corrplot` (Correlation analysis)

## 🚀 How to Run
1. Clone the repository:
   ```bash
   git clone [https://github.com/YOUR_USERNAME/MLB-Salary-Prediction-Multinomial-Regression.git](https://github.com/YOUR_USERNAME/MLB-Salary-Prediction-Multinomial-Regression.git)
