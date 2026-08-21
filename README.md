# HR Attrition Analysis Dashboard 📊

## Project Overview
 
Employee attrition is expensive — replacing a mid-level employee can cost 6-9 months of their salary in hiring, onboarding, and lost productivity. This project analyzes the HR Employee Attrition dataset to answer a simple question: **where is attrition concentrated, and what factors drive it?**
 
The dashboard is built as a 2-page Power BI report:
- **Overview** — headline KPIs and attrition breakdowns by demographic and workplace factors
- **Dive** — department, job role, and salary band deep-dive with a decomposition tree
---
 
## Key Insights
 
| Finding | Detail |
|---|---|
| **Overall attrition rate** | 16.1% (237 of 1,470 employees) — above the 10–15% industry benchmark |
| **Highest-risk department** | Sales (20.6% attrition), driven by Sales Representatives specifically (39.8%) |
| **Pay band effect** | Employees earning under ₹6k attrition at 19.6%, vs. 3.8% for those earning above ₹15k |
| **Overtime effect** | Employees who work overtime leave at 30.5%, nearly 3x the 10.4% rate of those who don't |
| **Age effect** | 18–25 age group attrition at 35.8%, compared to 9.2% for the 36–45 group |
| **Marital status effect** | Single employees leave at 25.5%, over 2x the rate of married employees (12.5%) |
| **Business travel effect** | Frequent travelers attrition at 24.9%, vs. 8.0% for non-travelers |
 
---
 
## Tools & Techniques
 
- **Power BI Desktop** — report design and data modeling
- **DAX** — custom measures for attrition rate, headcount, employees left, and average tenure of leavers
- **Decomposition Tree** — interactive drill-down from Department → Job Role → Salary Band
- **Slicers** — cross-filtering by Department, Salary Band, Age Group, and Gender across both pages
- **Conditional formatting** — color-coded attrition rate tables (red = high risk, green = low risk)

### Sample DAX Measures
```dax
ATTRITION RATE = DIVIDE(
    CALCULATE(COUNTROWS('HR-Employee-Attrition'),
    'HR-Employee-Attrition'[Attrition] = "YES"
    ),
    COUNTROWS('HR-Employee-Attrition')
)
 
EMPLOYEER LEFT = CALCULATE(
    COUNTROWS('HR-Employee-Attrition'),
    'HR-Employee-Attrition'[Attrition] = "YES"
)
 
AVERAGE TENURE OF LEAVERS = CALCULATE(
    AVERAGE('HR-Employee-Attrition'[YearsAtCompany]),
    'HR-Employee-Attrition'[Attrition] = "YES"
)
```
 
---

### Dashboard Perview

Show what the dashboard looks like.![Alt text]
 ![Dashboard Preview](https://github.com/dipanshu-data/HR-Attrition/blob/main/Attrition%20Overview.png)
  ![Dashboard Preview](https://github.com/dipanshu-data/HR-Attrition/blob/main/Attrition%20Deep%20Dive.png)
