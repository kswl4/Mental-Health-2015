# Mental-Health-2015
# 🧠 Mental Health in America: 2015 Analysis

## 📌 Overview
Using CDC survey data from over 330,000 Americans, this project explores what factors are most associated with poor mental health outcomes — including age, income, and exercise habits.

**🔗 [View Live Tableau Dashboard](https://public.tableau.com/app/profile/kiasha.williams/viz/MentalHealthonAmerica2015/Dashboard1)**

---

## ❓ Questions Explored

1. Which age group reports the most poor mental health days?
2. Does exercise frequency affect mental health outcomes?
3. Does income level impact mental health?

---

## 🔍 Key Findings

- **18–24 year olds** report the highest average number of poor mental health days per month
- **People who don't exercise** report significantly more poor mental health days than those who do
- **Lower income (under $10k/year)** is strongly associated with worse mental health outcomes — with a clear improvement as income rises

---

## 🛠️ Tools Used

![Python](https://img.shields.io/badge/Python-9B59B6?style=for-the-badge&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-7D3C98?style=for-the-badge&logo=pandas&logoColor=white)
![Tableau](https://img.shields.io/badge/Tableau-A569BD?style=for-the-badge&logo=tableau&logoColor=white)

---

## 📂 Files

| File | Description |
|---|---|
| `mental_health.ipynb` | Full analysis notebook — cleaning, exploration, and visualizations |
| `2015_cleaned.csv` | Cleaned dataset (332,938 rows, 9 columns) |
| `mental_health_by_age.png` | Chart — avg poor mental health days by age group |
| `mental_health_by_exercise.png` | Chart — avg poor mental health days by exercise habit |
| `mental_health_by_income.png` | Chart — avg poor mental health days by income level |

---

## 🧹 Data Cleaning Steps

- Selected 9 relevant columns from 330 total
- Replaced coded value `88` (meaning zero days) with `0`
- Removed unknown/refused response codes (77, 99)
- Dropped rows with missing values
- Final dataset: **332,938 rows**

---

## 💡 Business Recommendations

Based on the findings, here are 3 actionable recommendations:

**1. Target Youth Mental Health Programs (18–24)**
Young adults report the highest number of poor mental health days. Companies in wellness, insurance, and healthcare should prioritize this age group through affordable therapy apps, campus partnerships, and mental health benefits for entry-level workers.

**2. Incentivize Exercise as a Mental Health Intervention**
The data shows a clear link between exercise and better mental health outcomes. Employers and insurers could offer gym membership subsidies, step challenges, or wellness stipends as low-cost mental health interventions.

**3. Address the Income-Mental Health Gap**
Poor mental health days spike sharply at the lowest income level. Policy recommendations include expanding Medicaid mental health coverage, investing in community mental health centers in low-income areas, and offering sliding-scale therapy services.

---

## 📊 Data Source

[CDC Behavioral Risk Factor Surveillance System (BRFSS) 2015](https://www.kaggle.com/datasets/cdc/behavioral-risk-factor-surveillance-system) via Kaggle

---

*This is my first data analytics project as part of my portfolio. Built using Python and Tableau.*
