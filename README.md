# Week 3 — Data Visualization & Feature Engineering

**Student:** Adina Zafar | SP24-BSE-006
**Internship:** AI/ML — Week 3 of 8
**Instructor:** Zain Ul Abideen

 **Dataset**
House Prices — Advanced Regression Techniques
Source: Kaggle | 1460 rows, 81 columns | Target: SalePrice

**What I did this week**
built a full visualization dashboard using matplotlib and seaborn, then did feature engineering to get the dataset ready for ML in week 4. this was honestly the most work-heavy week so far — 81 columns is a lot to go through.

**5 Key Findings**
1. OverallQual had the strongest correlation with SalePrice at 0.79 — the quality rating basically drives the price more than anything else
2. TotalSF (feature i engineered by combining all floor areas) came in at 0.76 correlation, which actually beat GrLivArea (0.709) that was already in the original data
3. SalePrice skewness dropped from 1.88 to 0.12 after log transform — the before/after difference is very visible in the dashboard
4. 47.6% of numerical features were highly skewed — more than i expected, almost half the dataset needed treatment
5. went from 174 features after encoding down to 26 after correlation filter + variance threshold + multicollinearity removal

**Top 3 Engineered Features**
| Feature | Formula | Correlation |
|---|---|---|
| TotalSF | TotalBsmtSF + 1stFlrSF + 2ndFlrSF | 0.76 |
| PricePerSF | SalePrice / TotalSF | 0.64 |
| TotalBaths | FullBath + 0.5×HalfBath + BsmtFullBath + 0.5×BsmtHalfBath | 0.63 |

TotalSF was the most impactful one — buyers care about total usable space, not individual floor measurements separately. combining all three floors into one feature gave a stronger signal than any of them alone.

**Tools**
Python, Pandas, NumPy, Matplotlib, Seaborn, Scikit-learn, SciPy

**Dashboard Preview**

![Dashboard](week3_dashboard.png)
