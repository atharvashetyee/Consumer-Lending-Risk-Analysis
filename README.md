# Consumer Lending Risk Analysis 📊

## 📌 Project Overview
**Consumer finance companies** often face the challenge of lending to individuals with insufficient or non-existent credit histories. This project focuses on using **Exploratory Data Analysis (EDA)** and **Statistical Hypothesis Testing** to minimize the risk of financial loss due to loan defaults.

By analyzing demographic patterns, credit history, and repayment behaviors, this analysis identifies key drivers of default and provides actionable recommendations to optimize the lending strategy.

## 🎯 Objectives
* **Analyze** customer attributes and loan characteristics to identify risk factors.
* **Discover** patterns that differentiate "defaulters" (Target=1) from "repayers" (Target=0).
* **Validate** findings using statistical hypothesis testing (T-tests, Chi-square, Z-tests).
* **Recommend** a data-driven credit policy to reduce the default rate (currently ~8.1%) towards the industry benchmark (5%).

## 📂 Dataset
The analysis uses two merged datasets:
1.  **Application Data:** Demographics, income, housing type, family status, and external credit scores.
2.  **Previous Loan History:** Historical data on prior loan applications (approvals, refusals, amounts).

*Note: The dataset contains anonymized real-world banking data.*

## 🛠️ Tech Stack
* **Language:** Python 3.x
* **Libraries:**
    * `pandas` & `numpy` (Data Manipulation)
    * `matplotlib` & `seaborn` (Visualization)
    * `scipy.stats` & `statsmodels` (Hypothesis Testing)
* **Environment:** Jupyter Notebook / Google Colab

## 🔍 Key Insights
Through rigorous EDA and statistical testing, the following drivers were identified:

### 1. Income & Affordability
* **Insight:** Lower income levels are statistically correlated with higher default rates.
* **Stat Check:** T-test (p-value < 0.05) confirmed a significant difference in income between defaulters and non-defaulters.

### 2. Previous Credit History
* **Insight:** Applicants with **prior loan refusals** are significantly more likely to default on current loans.
* **Stat Check:** Applicants with >0 refusals have a **10.3%** default rate vs. **7.0%** for those with clean histories.

### 3. Education Level
* **Insight:** Lower education levels (e.g., Secondary vs. Higher Education) are strong predictors of default.
* **Stat Check:** Chi-square test validated the dependency between education type and default risk.

### 4. External Scores
* **Insight:** `EXT_SOURCE_2` and `EXT_SOURCE_3` are the strongest numerical predictors. Defaulters consistently show lower external scores.

## 📉 Hypothesis Testing Summary
| Hypothesis | Test Used | Result | Conclusion |
| :--- | :--- | :--- | :--- |
| **H1:** Income differs by default status | T-Test | **Reject H0** | Lower income increases default risk. |
| **H2:** Gender affects default rate | Chi-Square | **Reject H0** | Gender is a significant risk factor. |
| **H3:** Education level affects default | Chi-Square | **Reject H0** | Lower education correlates with higher risk. |
| **H4:** Past refusals predict default | Z-Test | **Reject H0** | Prior rejections are a major red flag. |
| **H5:** Company Default > Industry (5%) | One-Sample Z-Test | **Reject H0** | Company risk (8.1%) is significantly higher. |

## 🚀 How to Run
1.  Clone this repository:
    ```bash
    git clone [https://github.com/yourusername/credit-risk-analysis.git](https://github.com/yourusername/credit-risk-analysis.git)
    ```
2.  Install required libraries:
    ```bash
    pip install pandas numpy matplotlib seaborn scipy statsmodels
    ```
3.  Open the notebook:
    ```bash
    jupyter notebook Final_Credit_Risk_Analysis.ipynb
    ```

## 📢 Business Recommendations
Based on the analysis, the following changes to the credit policy are recommended:
1.  **Implement DTI Caps:** Enforce stricter Debt-to-Income ratios for lower-income brackets.
2.  **"Knock-out" Rule:** Automatically flag or reject applicants with recent prior refusals.
3.  **Risk-Based Pricing:** Adjust interest rates based on Education and External Score segments.
4.  **Portfolio Rebalancing:** Tighten approval criteria to bring the portfolio default rate down from 8.1% to the 5% target.

## 🤝 Contribution
Feel free to fork this repository and submit pull requests. For major changes, please open an issue first to discuss what you would like to change.

## 📄 License
This project is open-source and available under the [MIT License](LICENSE).
