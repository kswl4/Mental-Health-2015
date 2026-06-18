# Mental-Health-2015
# 🧠 Mental Health in America: 2015 Analysis

![Python](https://img.shields.io/badge/Python-9B59B6?style=for-the-badge&logo=python&logoColor=white)
![Tableau](https://img.shields.io/badge/Tableau-A569BD?style=for-the-badge&logo=tableau&logoColor=white)

## 📚 Table of Contents
- [Project Overview](#project-overview)
- [Data Source](#data-source)
- [Data Cleaning](#data-cleaning)
- [Questions and Findings](#questions-and-findings)
- [Business Recommendations](#business-recommendations)
- [Dashboard](#dashboard)

---

## Project Overview

Using CDC survey data from over 330,000 Americans, this project explores what factors are most associated with poor mental health outcomes — including age, income, and exercise habits.

---

## Data Source

[CDC Behavioral Risk Factor Surveillance System (BRFSS) 2015](https://www.kaggle.com/datasets/cdc/behavioral-risk-factor-surveillance-system) via Kaggle

- **Raw dataset:** 441,456 rows · 330 columns
- **Columns used:** MENTHLTH, PHYSHLTH, GENHLTH, SEX, _AGEG5YR, INCOME2, EDUCA, EXERANY2, _STATE

---

## Data Cleaning

```python
cols = ['MENTHLTH', 'PHYSHLTH', 'GENHLTH', 'SEX', '_AGEG5YR', 'INCOME2', 'EDUCA', 'EXERANY2', '_STATE']
df_clean = df[cols].dropna()

df_clean = df_clean.copy()
df_clean['MENTHLTH'] = df_clean['MENTHLTH'].replace(88, 0)

df_clean = df_clean[~df_clean['MENTHLTH'].isin([77, 99])]
df_clean = df_clean[~df_clean['GENHLTH'].isin([7, 9])]
df_clean = df_clean[~df_clean['EXERANY2'].isin([7, 9])]
df_clean = df_clean[~df_clean['INCOME2'].isin([77, 99])]
```

#### Steps:
- Selected 9 relevant columns from 330 total
- Dropped rows with missing values
- Replaced coded value `88` (meaning zero days) with `0`
- Removed unknown/refused response codes (77, 99)

#### Result:
- **Final dataset:** 332,938 rows · 9 columns

---

## Questions and Findings

**1. Which age group reports the most poor mental health days?**

```python
age_mental = df_clean.groupby('AGE_LABEL')['MENTHLTH'].mean()
```

#### Answer:
- **18–24 year olds** report the highest average number of poor mental health days per month
- Poor mental health days decrease steadily as age increases

![Age Chart](https://github.com/kswl4/Mental-Health-2015/blob/main/output.png))

---

**2. Does exercise affect mental health outcomes?**

```python
exercise_mental = df_clean.groupby('EXERCISE_LABEL')['MENTHLTH'].mean()
```

#### Answer:
- People who **do not exercise** report significantly more poor mental health days
- Exercise appears to be strongly associated with better mental health outcomes

![Exercise Chart](charts/mental_health_by_exercise.png)

---

**3. Does income level impact mental health?**

```python
income_mental = df_clean.groupby('INCOME_LABEL')['MENTHLTH'].mean()
```

#### Answer:
- **Under $10k/year** has the highest average poor mental health days
- There is a clear and consistent improvement in mental health as income increases
- The jump between the lowest and highest income groups is significant

![Income Chart](charts/mental_health_by_income.png)

---

## Business Recommendations

**1. Target Youth Mental Health Programs (18–24)**
Young adults report the highest number of poor mental health days. Companies in wellness, insurance, and healthcare should prioritize this age group through affordable therapy apps, campus partnerships, and mental health benefits for entry-level workers.

**2. Incentivize Exercise as a Mental Health Intervention**
The data shows a clear link between exercise and better mental health outcomes. Employers and insurers could offer gym membership subsidies, step challenges, or wellness stipends as low-cost mental health interventions.

**3. Address the Income-Mental Health Gap**
Poor mental health days spike sharply at the lowest income level. Policy recommendations include expanding Medicaid mental health coverage, investing in community mental health centers in low-income areas, and offering sliding-scale therapy services.

---

## Dashboard

🔗 [View Live Tableau Dashboard](https://public.tableau.com/app/profile/kiasha.williams/viz/MentalHealthonAmerica2015/Dashboard1)


