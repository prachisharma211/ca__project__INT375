# ca__project__INT375
# Electricity Generation Analysis – India (2019–2024)
# Project Overview
This project presents a comprehensive data-driven analysis of India's electricity generation patterns across fuel types, states, and time periods. Using real monthly generation data, the project uncovers seasonal trends, fuel mix shifts, and statistical insights — making it a complete end-to-end data science workflow from raw CSV to advanced visualizations.

# Objectives

Analyze India's monthly electricity generation data (2019–2024)
Compare generation across fuel types: Coal, Solar, Wind, Hydro, Nuclear, and Gas
Identify seasonal patterns and year-over-year growth trends
Perform exploratory data analysis (EDA) with rich visualizations
Apply statistical methods including correlation analysis and probability distributions
Detect outliers and understand the distribution of generation data


# Dataset

File: india_monthly_full_release_long_format.csv
Format: Long format — one row per (State, Date, Variable, Unit) combination
Coverage: Pan-India monthly electricity data across multiple states and fuel sources
Key Columns: State, Date, Variable (fuel type / metric), Unit, Value, YoY absolute change, YoY % change


# Data Preprocessing

Parsed Date column to datetime and extracted Year, Month, Month_Name
Dropped rows with missing Value entries
Filled missing YoY absolute change and YoY % change columns with 0
Filtered India-level totals separately from state-level data
Structured fuel-wise subset for comparative analysis


# Exploratory Data Analysis (EDA)
The following visualizations were produced:

Line Plot – Monthly electricity generation trend with a 6-month rolling average
Bar Chart – Fuel-wise annual generation (Coal, Solar, Wind, Hydro, Nuclear, Gas)
Heatmap – Monthly generation (GWh) broken down by year (seasonality view)
Stacked Area Chart – Fuel-wise monthly generation stacked over time
Donut Pie Chart – Fuel mix share for the most recent year
Correlation Heatmap – Relationships between Year, Month, Value, and YoY metrics
Boxplots – Distribution of generation by Year and by Month (seasonality)
Histogram + KDE – Distribution of monthly generation with mean/median markers


# Statistical Analysis

Computed full descriptive statistics: mean, median, std deviation, variance, min/max, percentiles
Year-wise breakdown of generation statistics
Correlation matrix across key numeric features
Outlier detection using the IQR method (1.5× IQR rule)
Demonstrated three probability distributions relevant to power data:

Normal Distribution (μ=0, σ=1)
Binomial Distribution (n=20, p=0.6)
Poisson Distribution (λ=5, modeling events like outages)




# Key Insights

Coal continues to dominate India's electricity mix, but renewables (Solar, Wind) show consistent year-on-year growth
Clear seasonal patterns exist — generation dips in certain months, likely tied to demand and hydro availability
Strong correlation observed between Year and total generation, reflecting India's growing power demand
No significant statistical outliers detected in the national total generation series
The distribution of monthly generation is approximately normal with a slight right skew


# Tools & Technologies
ToolPurposePythonCore programming languagePandasData loading, cleaning, and manipulationNumPyArray operations and statistical computationsMatplotlibCustom plots and chart stylingSeabornHeatmaps, boxplots, and distribution plotsSciPyProbability distribution modelingSQLite (pandasql)SQL-style querying on dataframes

# Project Structure
electricity-india-analysis/
│
├── data/
│   └── india_monthly_full_release_long_format.csv
│
├── notebook/
│   └── Electricity_India_DS_Project.ipynb
│
├── visuals/
│   ├── plot1_line_trend.png
│   ├── plot2_bar_fuel.png
│   ├── plot3_heatmap.png
│   ├── plot4_area_fuels.png
│   ├── plot5_pie_fuelmix.png
│   ├── plot6_corr_heatmap.png
│   ├── plot7_boxplot.png
│   ├── plot8_distribution.png
│   └── plot9_distributions.png
│
└── README.md

# Learnings

Long-format datasets require thoughtful pivoting and filtering before analysis
Rolling averages are highly effective for smoothing noisy time-series data
Fuel-type breakdowns reveal structural shifts in India's energy policy over time
Combining statistical methods with visual EDA leads to much richer insights


# Limitations

Analysis is limited to national totals and does not deeply explore state-level disparities
Missing values in YoY columns were filled with 0, which may underrepresent change in early periods
No machine learning model was built for forecasting in this version


# Future Improvements

Build a forecasting model (ARIMA / Prophet) to predict future generation trends
Add state-level deep dive analysis for top 10 states
Integrate renewable energy growth rate projections
Build an interactive dashboard using Plotly or Streamlit


# Author
Prachi Sharma
B.Tech Computer Science Engineering – Data Analytics
Lovely Professional University
