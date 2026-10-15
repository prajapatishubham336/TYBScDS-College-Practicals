# 🛒 FreshMart Supermarket – Sales Forecasting & Time Series Analysis

## 🎯 Project Overview

This project focuses on analyzing monthly fruit juice sales for **FreshMart Supermarket, Mumbai**, using R programming and time series analysis.

The dataset covers 24 months, from January 2025 to December 2026. The main objective is to identify sales trends, seasonal patterns, and future sales forecasts to help management make informed business decisions.

**In one sentence:** Understand the data, identify patterns, and forecast future sales.

---

## 📊 Dataset Description

The dataset contains monthly fruit juice sales information.

| Variable | Type      | Description                               |
| -------- | --------- | ----------------------------------------- |
| `Month`  | Character | Month and year, such as Jan-25 and Feb-25 |
| `Sales`  | Numeric   | Monthly sales in Indian Rupees (₹)        |

**Time Period:** January 2025 – December 2026
**Total Observations:** 24 months

### Descriptive Statistics

| Statistic             |           Value |
| --------------------- | --------------: |
| Total Sales           |         ₹42,650 |
| Average Monthly Sales |       ₹1,777.08 |
| Median Sales          |          ₹1,775 |
| Maximum Sales         | ₹2,450 (Dec-26) |
| Minimum Sales         | ₹1,200 (Jan-25) |
| Standard Deviation    |         ₹335.89 |
| Variance              |       112,821.6 |
| Range                 | ₹1,200 – ₹2,450 |

**Interpretation:** Monthly sales range from ₹1,200 to ₹2,450. The average monthly sales are approximately ₹1,777.08. These variations may indicate changes in customer demand and possible seasonal effects.

---

## 🧰 Tools and Technologies

| Tool          | Purpose                                                                |
| ------------- | ---------------------------------------------------------------------- |
| R Programming | Data manipulation, statistical analysis, and forecasting               |
| RStudio       | Integrated development environment for writing and executing R scripts |
| `base`        | Data structures and basic calculations                                 |
| `stats`       | Statistical analysis, regression, and time series functions            |
| `graphics`    | Data visualization                                                     |
| `TTR`         | Moving average calculations                                            |

---

## 🗂️ Project Structure

```text
FreshMart-Forecast/
├── FreshMart_Forecast.R   # Main R script containing project tasks
├── README.md              # Original documentation
├── ARIMA_Forecast.png     # ARIMA forecast visualization
├── final_plot.png         # Combined moving average, trend, and seasonal plots
├── forecast.R             # Alternative R forecasting script
└── sales_data.csv         # Raw monthly sales dataset
```

---

## 📋 Project Tasks and Implementation

### ✅ Task 1: Data Collection and Presentation (8 Marks)

**What was done?**

- Created a data frame named `freshmart` containing Month and Sales columns.
- Displayed the dataset and examined its structure using `str()`.
- Generated summary statistics using `summary()`.
- Displayed the first and last five observations using `head()` and `tail()`.

**R functions used:** `data.frame()`, `str()`, `summary()`, `head()`, `tail()`

**Purpose:** To understand the dataset and prepare it for further analysis.

### ✅ Task 2: Descriptive Statistics (7 Marks)

The following statistical measures were calculated:

| Measure            | R Function |        Result |
| ------------------ | ---------- | ------------: |
| Total Sales        | `sum()`    |       ₹42,650 |
| Average Sales      | `mean()`   |     ₹1,777.08 |
| Median Sales       | `median()` |        ₹1,775 |
| Maximum Sales      | `max()`    |        ₹2,450 |
| Minimum Sales      | `min()`    |        ₹1,200 |
| Standard Deviation | `sd()`     |        335.89 |
| Variance           | `var()`    |     112,821.6 |
| Range              | `range()`  | ₹1,200–₹2,450 |

**Purpose:** To understand the average sales, variability, distribution, and extreme values in the dataset.

### ✅ Task 3: Data Visualization (8 Marks)

Five different graphs were created to explore the sales data.

| Chart      | Purpose                                                                |
| ---------- | ---------------------------------------------------------------------- |
| Bar Chart  | Compares monthly sales and identifies high- and low-sales months       |
| Line Chart | Shows how sales change over time                                       |
| Pie Chart  | Displays the contribution of each month to the 2025 sales distribution |
| Histogram  | Shows the frequency distribution of sales values                       |
| Box Plot   | Illustrates the spread of sales and potential outliers                 |

**R functions used:** `barplot()`, `plot()`, `pie()`, `hist()`, `boxplot()`

**Purpose:** To identify patterns and communicate findings visually.

### ✅ Task 4: Time Series Analysis (6 Marks)

The monthly sales data was converted into a time series object using the `ts()` function with `frequency = 12`, representing monthly observations.

A time series plot was then created to examine the main components.

| Component           | Observation                                                              |
| ------------------- | ------------------------------------------------------------------------ |
| Trend               | Overall increasing trend                                                 |
| Seasonality         | December sales peak and a September dip were observed                    |
| Cyclical Component  | No clear cyclical pattern can be established from only two years of data |
| Irregular Component | Short-term fluctuations that are not explained by the other components   |

**Purpose:** To understand the underlying patterns in sales before performing forecasting.

### ✅ Task 5: Moving Average Analysis (8 Marks)

#### A. Simple Moving Average (SMA)

Three-month and four-month moving averages were calculated to smooth short-term fluctuations and identify the underlying sales trend.

| Period              |                 3-Month Moving Average |                 4-Month Moving Average |
| ------------------- | -------------------------------------: | -------------------------------------: |
| Jan-25              |                                     NA |                                     NA |
| Intermediate months | Calculated from available observations | Calculated from available observations |
| Dec-26              |                               2,116.67 |                               2,012.50 |

- **3-month moving average:** Generally responds more quickly to recent sales changes.
- **4-month moving average:** Produces a smoother series but may respond more slowly to changes.

#### B. Weighted Moving Average (WMA)

A weighted moving average was used to give greater importance to recent sales observations.

**Weights:**

- Oldest observation: 0.2
- Middle observation: 0.3
- Latest observation: 0.5

**January 2027 Forecast**

The last three months of sales were:

- October 2026: ₹1,800
- November 2026: ₹2,100
- December 2026: ₹2,450

Calculation:

WMA = (0.2 × 1,800) + (0.3 × 2,100) + (0.5 × 2,450)

WMA = 360 + 630 + 1,225

**Forecast for January 2027 = ₹2,215**

**Purpose:** The weighted moving average emphasizes recent observations, making it useful for short-term forecasting when recent changes are relevant.

### ✅ Task 6: Trend Analysis Using Linear Regression (7 Marks)

A linear regression model was used to estimate the long-term sales trend.

**Regression Equation**

Sales = 1471.377 + 24.45652 × Time

**Interpretation:**

- **Intercept (1471.377):** The model's estimated sales when the time variable equals zero.
- **Slope (24.45652):** The model estimates an increase of approximately ₹24.46 per month.

#### January 2027 Forecast

Since January 2027 represents time period 25:

Sales = 1471.377 + 24.45652 × 25

Sales = 1471.377 + 611.413

**Forecast for January 2027 ≈ ₹2,083**

#### Forecast Comparison

| Method                  | January 2027 Forecast |
| ----------------------- | --------------------: |
| Weighted Moving Average |                ₹2,215 |
| Linear Regression       |                ₹2,083 |

**Purpose:** Linear regression estimates the overall trend, whereas weighted moving averages emphasize the most recent observations. These forecasts use different assumptions and should be evaluated against actual future sales when available.

### ✅ Task 7: Seasonal Variation Analysis (6 Marks)

Seasonal averages and indices were calculated to compare quarterly sales patterns.

| Quarter               | Seasonal Average | Seasonal Index |
| --------------------- | ---------------: | -------------: |
| Q1 (January–March)    |        ₹1,616.67 |         90.97% |
| Q2 (April–June)       |        ₹1,933.33 |         98.01% |
| Q3 (July–September)   |        ₹1,816.67 |        100.82% |
| Q4 (October–December) |        ₹2,141.67 |        110.20% |

**Interpretation:**

- **Q4:** The reported seasonal index of 110.20% indicates sales approximately 10.20% above the reference average.
- **Q1:** The reported seasonal index of 90.97% indicates sales approximately 9.03% below the reference average.
- **Highest-demand quarter:** Q4 (October–December).

**Purpose:** Seasonal analysis can help businesses plan inventory, staffing, and promotional campaigns.

*Note: Seasonal indices should be validated against the actual calculation method and the complete dataset before drawing firm conclusions.*

### ✅ Task 8: Business Interpretation (Bonus – 5 Marks)

| Business Question              | Finding                            |
| ------------------------------ | ---------------------------------- |
| Highest Sales Month            | December 2026 – ₹2,450             |
| Lowest Sales Month             | January 2025 – ₹1,200              |
| Overall Sales Trend            | Increasing                         |
| Highest Seasonal Index Quarter | Q4 – 110.20%                       |
| January 2027 Forecast          | ₹2,215 (WMA) / ₹2,083 (Regression) |

---

## 💼 Business Recommendations

1. **Increase inventory and staffing during Q4.** Prepare for potentially higher demand between October and December to reduce stockouts and long queues.

2. **Consider promotional offers in September.** If the September decline is confirmed across the data, targeted discounts may help stimulate demand.

3. **Evaluate opportunities for new products.** An increasing sales trend may justify testing new products, subject to customer demand and profitability.

4. **Monitor external factors.** Track festivals, weather, competitor activity, and promotional campaigns that may influence sales.

5. **Collect more historical data.** Two years of monthly observations provide limited evidence for identifying recurring seasonal patterns. Additional data can improve analysis and validation.

6. **Evaluate forecasting models.** Compare moving averages and regression with suitable time series models, such as ARIMA, using out-of-sample forecasting errors.

---

## 🧠 Important Viva Questions and Answers

### Q1. Why was this project developed?

**Answer:** The project was developed to analyze FreshMart Supermarket's monthly sales, identify trends and seasonal patterns, and forecast future sales to support business decisions.

### Q2. What is time series data?

**Answer:** Time series data consists of observations recorded over time, such as monthly sales, daily temperatures, or annual revenue.

### Q3. What is a trend?

**Answer:** A trend represents the long-term direction of data. It can be increasing, decreasing, or stable. The fitted regression model in this project indicates an increasing trend.

### Q4. What is seasonality?

**Answer:** Seasonality refers to patterns that repeat at regular intervals, such as monthly or quarterly changes in demand. A recurring seasonal pattern should ideally be verified using several years of data.

### Q5. Why are moving averages used?

**Answer:** Moving averages smooth short-term fluctuations and help reveal the underlying direction of a time series.

### Q6. What is the advantage of a weighted moving average?

**Answer:** A weighted moving average assigns different weights to observations. In this project, the latest observation receives the greatest weight.

### Q7. What does the regression equation mean?

**Answer:** The equation `Sales = 1471.377 + 24.45652 × Time` estimates sales using a linear trend. Its slope represents an estimated increase of approximately ₹24.46 per time period.

### Q8. What is a seasonal index?

**Answer:** A seasonal index compares a seasonal period's estimated level with a reference average. An index above 100% indicates an above-average level, while an index below 100% indicates a below-average level.

### Q9. Which forecasting method is better?

**Answer:** The weighted moving average gives more importance to recent sales, while linear regression captures a linear trend. Neither method is automatically better. Their performance should be compared using actual forecast errors.

### Q10. What business recommendations can be made?

**Answer:** The business can prepare inventory and staffing for high-demand periods, evaluate targeted promotions during slower periods, monitor external factors, and collect more data to improve forecasts.

---

## 🗓️ Practical Details

| Item              | Details                 |
| ----------------- | ----------------------- |
| Subject           | Business Forecasting    |
| Course            | TYBSc Data Science      |
| Maximum Marks     | 50                      |
| Software          | R and RStudio           |
| Presentation Date | 6 August 2026           |
| Faculty           | Asst. Prof. Raju Kukade |

---

## ⭐ Acknowledgments

I would like to express my sincere gratitude to:

- **Asst. Prof. Raju Kukade** for his guidance and support throughout the Business Forecasting practical sessions.
- **Department of Data Science, Reena Mehta College**, for providing the academic learning environment.
- **The R Foundation**, for developing and maintaining the R programming language.
- **FreshMart Supermarket**, the business scenario used for this sales forecasting project.

---

## 👨‍💻 Author

**Shubham Prajapati**
TYBSc Data Science

- **GitHub:** [Shubham Prajapati](https://github.com/prajapatishubham336)

---

> “Data is the new oil, and forecasting is the engine that drives business success.”

---

## ✅ Project Summary

This project applies R programming and time series analysis to monthly supermarket sales data. It covers data collection, descriptive statistics, visualization, moving averages, linear regression, seasonal variation, and business interpretation.

### Key Findings

- **Trend:** The fitted linear regression model indicates an increasing trend.
- **Highest Recorded Sales:** ₹2,450 in December 2026.
- **Lowest Recorded Sales:** ₹1,200 in January 2025.
- **Highest Seasonal Index:** Q4, reported as 110.20%.
- **January 2027 Forecasts:** ₹2,215 using WMA and approximately ₹2,083 using linear regression.

### Future Improvements

- Build an interactive dashboard using R Shiny.
- Collect additional historical sales data.
- Evaluate ARIMA or other appropriate forecasting models.
- Compare models using out-of-sample forecast accuracy.
- Extend the analysis to multiple products and categories.

**The project demonstrates how data analysis and forecasting can support practical business planning and decision-making.**
