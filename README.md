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
