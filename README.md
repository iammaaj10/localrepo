Exp 10
1. DONUT CHART — Average Gross by Genre

Insert → Donut Chart

Fields:

Legend → Genre

Values → Average(Gross)

Sort → Highest to lowest

This replaces the radial chart.

⭐ 2. DONUT CHART — Average Budget by Genre

Duplicate the first donut chart

Change Values → Average(Budget)

Legend → Genre

⭐ 3. Histogram — IMDb Score Distribution

Click Get more visuals → Search “Histogram”

Insert Histogram visual

Field → IMDb Score

Check bin width (auto is okay)

Observation: Highest bar = most common score range.

⭐ 4. Scatter Plot — Budget vs Gross (Correlation)

Insert Scatter Chart

X-axis → Budget

Y-axis → Gross

Details → Movie Title

Analytics → Add Trend Line

If slope ↑ = positive correlation.

⭐ 5. Column Chart — Avg IMDb Score by Country

Insert Clustered Column Chart

Axis → Country

Values → Average(IMDb Score)

Sort → Descending

⭐ 6. Line Chart — Genre Rating Over Years

Insert Line Chart

Axis → Year

Legend → Genre

Values → Average(IMDb Score)**

Shows rating trend.

⭐ 7. Bar Chart — High-Budget Movies by Year (Budget > 100M)

Add visual level filter → Budget > 100,000,000

Insert Bar Chart

Axis → Year

Value → Count of Movie Title

Find the year with maximum big-budget movies.

⭐ 8. Bar Chart — Movies Where Budget > Gross (Loss-Making)

Create a new column:
Modeling → New Column:

LossMovie = IF([Budget] > [Gross], 1, 0)


Insert Bar Chart

Axis → Genre

Values → Sum(LossMovie)

⭐ 9. Table — Countries with High Rated Movies (Score > 7)

Add filter → IMDb Score > 7

Insert Table

Fields: Country, Movie Title, IMDb Score

Add Count of Movie Title → sort descending

⭐ 10. Python KDE Plot (Optional)

Use only if teacher wants it.

Insert → Python Visual

Add fields:

Genre

IMDb Score

Use:

import seaborn as sns
import matplotlib.pyplot as plt

df_action = dataset[dataset['Genre'] == 'Action']['IMDB_Score']
df_drama = dataset[dataset['Genre'] == 'Drama']['IMDB_Score']

sns.kdeplot(df_action, label='Action')
sns.kdeplot(df_drama, label='Drama')
plt.legend()

🟦 STEP 5: Format Dashboard

Make it look clean:

✔ Title: IMDb Movie Analysis Dashboard (2006–2016)
✔ Use themes (View → Themes → choose one)
✔ Align visuals properly
✔ Place slicers on left side
✔ Arrange visuals in 2 rows

🟦 FINAL LAYOUT (TOP SCORING DESIGN)
Left Panel (Slicers):

Genre

Country

Year

Score Range

Row 1:

Donut Chart (Avg Gross by Genre)

Donut Chart (Avg Budget by Genre)

Column Chart (Avg IMDb Score by Country)

Row 2:

Histogram (IMDb Score)

Line Chart (Rating trend over years)

Scatter Plot (Budget vs Gross)

Row 3 (Optional/Analysis Section):

High-Budget Movies by Year

Loss Movies by Genre

High Score Countries (Table)

KDE Plot (optional)

🎉 You're now ready for your exam!

If you want, I’ll also prepare:

✔ Full written explanation for submission
✔ Oral exam script (what you will say point-by-point)
✔ Screenshot-based dashboard layout

Just tell me:
👉 “Give me the oral script” or
👉 “Give me PDF-ready explanation”








Exp11
EXPERIMENT 11 — Human Resources Analytics (Power BI)

📌 Goal: Analyze employees, performance, turnover, hiring trends and create HR dashboard.

🟦 STEP 1 — Download HR Dataset

Use any of these Kaggle datasets:

HR Analytics – Employee Attrition

HR Employee Attrition & Performance

HR Dataset (Kaggle HR Analytics)

Your dataset must include:

Age

Gender

Department

Job Role

Monthly Income

Performance Rating

Attrition (Yes/No)

Training Hours

Job Satisfaction

Hire Date / Tenure

🟦 STEP 2 — Import Dataset in Power BI

Open Power BI Desktop

Go to Home → Get Data → CSV/Excel

Select your HR dataset

Click Load

🟦 STEP 3 — Data Cleaning (Power Query)

Open → Transform Data

Clean the following:

Remove empty rows

Convert columns types:

Age → Whole Number

MonthlyIncome → Whole Number

PerformanceRating → Whole Number

Attrition → Text

HireDate → Date

Create a Tenure Column:
Go to:
Add Column → Date → Subtract → Year (Today – HireDate)
Name it → Tenure (Years)

Click Close & Apply

🟦 STEP 4 — Required Visuals (Based EXACTLY on your Experiment)

The PDF says to use:

Combo Charts

Cards

Bar Charts

Line Charts

Column Charts

Bubble Charts

Maps (Point Maps)

I’ll tell you EXACTLY which visual to create for what insight.

⭐ 1. Card Visual — Total Employees

Visual: Card
Field: Employee Count (Employee ID → Count)

⭐ 2. Bar Chart — Employees by Department

Visual: Clustered Bar Chart
Axis → Department
Value → Count of EmployeeID

This shows workforce distribution.

⭐ 3. Column Chart — Attrition (Turnover) by Department

Visual: Clustered Column Chart
Axis → Department
Value → Count of Attrition
Filter: Attrition = “Yes”

This shows which department has maximum resignations.

⭐ 4. Line Chart — Performance by Tenure

Visual: Line Chart
Axis → Tenure (Years)
Values → Average of PerformanceRating

Shows experience vs performance curve.

⭐ 5. Combo Chart — Monthly Income vs Job Level

Visual: Line and Column Chart
Column → Average Monthly Income
Line → Count of Employees
Axis → JobLevel

Shows which level earns the most and how many employees are at each level.

⭐ 6. Bubble Chart — Salary vs Performance vs Experience

Visual: Scatter Chart
X-axis → Monthly Income
Y-axis → PerformanceRating
Size → Tenure
Legend → Department

Shows employee distribution and outliers.

⭐ 7. Map Visualization (Point Map) — Geography Wise Employees

Use Filled Map or Map
Location → City / Region
Value → Count of Employees

Works only if your dataset has location.

⭐ 8. Attrition Analysis Donut Chart

Visual: Donut Chart
Legend → Attrition (Yes/No)
Values → Count of EmployeeID

Shows % of employees who left the company.

⭐ 9. Bar Chart — Training Hours vs Performance

Axis → Training Hours
Value → Average PerformanceRating

Shows if training is effective.

🟦 STEP 5 — Insights for Viva (From the PDF)

Your experiment expects these insights:

1. Turnover Analysis

Highest attrition in ______ department

Possible reason: workload / low job satisfaction / salary gap

2. Performance Evaluation

Highest performance in ______ team

Lower performance in new joiners (< 1 year)

3. Hiring Effectiveness

Most hires in ______ month/year

Average hiring time can be visualized using HireDate

4. Employee Demographics

Age group distribution

Male/Female ratio

Department-wise employee count

5. Training & Development

Employees with more training hours → higher performance

All these points are directly in the PDF 

faee2e80-4399-40d9-a620-9d21f39…

.

🟦 STEP 6 — Final HR Dashboard Layout (Exact Layout to Score Full Marks)
TOP ROW

🔹 Total Employees (Card)

🔹 Total Attrition (Card)

🔹 Avg Tenure (Card)

🔹 Avg Performance Rating (Card)

ROW 2

🔸 Bar Chart — Employees by Department

🔸 Donut Chart — Attrition Yes vs No

🔸 Column Chart — Attrition by Department

ROW 3

🔸 Line Chart — Performance vs Tenure

🔸 Combo Chart — Income vs JobLevel

🔸 Bubble Chart — Income vs Performance vs Tenure

BOTTOM

🔸 Map — Employees by Location

🔸 Training Hours vs Performance

🔸 Gender Breakdown (Pie Chart)

Perfect and complete.
