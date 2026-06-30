# IBM-HR-Attrition-Prediction
# 📊 Employee Attrition Prediction using Machine Learning

## 🎯 Project Overview
Every year, large companies spend vast amounts of resources trying to figure out who is likely to leave their jobs and why. This project builds an automated Machine Learning system that predicts whether an employee is likely to leave a company (attrition) based on factors like job satisfaction, salary, work-life balance, years at the company, and performance ratings.

Using the popular **IBM HR Analytics Employee Attrition Dataset (1,470 rows)**, we cleaned the data, performed Exploratory Data Analysis (EDA), and compared multiple classification models to find the best tool for HR teams to take immediate preventive action.

---

## 🛠️ Tools & Libraries Used
* **Language:** Python 3.x
* **Environment:** Jupyter Notebook / Google Colab
* **Data Manipulation:** Pandas & NumPy
* **Machine Learning:** Scikit-Learn
* **Visualization:** Matplotlib & Seaborn

---

## 📈 Key Data Insights (EDA)
* **The Overtime Burnout:** Employees who work regular overtime leave the company at nearly **triple the rate** of those who do not work extra hours.
* **High-Risk Roles:** **Sales Representatives** face an extreme systemic flight risk, exhibiting a massive **~40% attrition rate**.
* **The Critical Window:** Turnover spikes heavily during an employee's **first 1 to 2 years** at the firm. If an employee reaches a 3-year tenure, their flight risk drops dramatically.
* **Salary vs. Lifestyle:** While lower-paid employees leave more often, quality-of-life factors (like mandatory overtime and heavy business travel) carry more predictive weight in driving flight risk than salary alone.

---

## 🤖 Machine Learning Models Compared
Because the dataset is highly imbalanced (~84% stayed, ~16% left), we used the `class_weight='balanced'` technique to ensure our models didn't ignore employees who left.

| Model | Precision (Class 1) | Recall (Class 1) | F1-Score (Class 1) | ROC-AUC |
| :--- | :---: | :---: | :---: | :---: |
| **Logistic Regression (Best)** | **0.36** | **0.66** | **0.46** | **0.80** |
| **Random Forest** | 0.38 | 0.06 | 0.11 | 0.75 |
| **Gradient Boosting** | 0.41 | 0.47 | 0.44 | 0.78 |

### 🏆 Why Logistic Regression was Selected:
While Gradient Boosting had slightly higher precision, **Logistic Regression** was selected as our champion model because it achieved the highest **Recall (0.66)** and **ROC-AUC (0.80)**. For an HR department, a high Recall is vital because it ensures we flag **as many potential leavers as possible** before they quit.

---

## 📊 Visualizations (Saved in `charts/`)
Our project automatically generates and saves the following critical visual analytics:
1. **Chart 1:** Bar chart showing attrition rates broken down by Department and Job Role.
2. **Chart 2:** Box plot comparing Monthly Income distributions between employees who stayed vs. left.
3. **Chart 3:** Confusion Matrix heatmap showing accurate predictions for the Logistic Regression model.
4. **Chart 4:** Horizontal bar chart displaying the top 10 most critical features driving attrition.
5. **Chart 5:** An ROC Curve graph comparing the performance metrics of all 3 tested models.

---

## 💡 Practical HR Action Items
1. **Implement an Overtime Audit Policy:** HR should track consecutive monthly overtime hours. If an employee works excessive extra hours two months in a row, the system should trigger a workload rebalancing review.
2. **First-Year Stay Interviews:** Set up formal check-ins at the 6-month and 12-month marks specifically for new hires in high-risk groups (like Sales Representatives and Lab Technicians) to address workplace friction early.

---

## 📁 Repository Structure
```text
├── analysis.ipynb           # Complete Jupyter Notebook with code, tables, and charts
├── HR-Employee-Attrition.csv  # IBM HR Dataset
├── summary.pdf              # 1-Page Non-Technical Executive Summary for HR Directors
└── charts/                  # Directory containing exported evaluation graphs (.png)
