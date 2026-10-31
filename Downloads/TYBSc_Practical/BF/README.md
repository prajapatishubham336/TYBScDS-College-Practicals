# TYDS Business Forecasting Practical

# TYDS Business Forecasting Practicals – README

## Module 1 – Practical 1: Qualitative and Quantitative Forecasting

```r
# Qualitative Forecasting
expert_opinions <- c(500, 550, 520, 530, 540)

forecast <- mean(expert_opinions)

print(paste("Forecasted Demand:", forecast))


# Quantitative Forecasting – Moving Average
sales <- c(120, 135, 150, 145, 160, 170)

forecast <- mean(tail(sales, 3))

print(paste("Forecast for Next Month:", forecast, "units\n"))
```

## Module 1 – Practical 2: Data Collection, Classification and Presentation

```r
student_id <- c(101,102,103,104,105,106,107,108,109,110)

student_name <- c("Amit","Priya","Rahul","Sneha",
                  "Vikas","Neha","Ajay","Pooja",
                  "Rohan","Anjali")

marks <- c(85,72,91,65,78,88,55,92,70,81)

student_data <- data.frame(student_id, student_name, marks)

student_data$grade <- ifelse(student_data$marks >= 80, "A",
                      ifelse(student_data$marks >= 60, "B", "C"))

print(student_data)

summary(student_data$marks)

grade_count <- table(student_data$grade)

print(grade_count)

barplot(grade_count,
        main = "Grade Distribution",
        xlab = "Grade",
        ylab = "Number of Students",
        col = c("green", "yellow", "red"))

pie(grade_count,
    main = "Grade Distribution",
    col = c("green", "yellow", "red"))

hist(student_data$marks,
     main = "Marks Distribution",
     xlab = "Marks",
     col = "skyblue",
     border = "black")

boxplot(student_data$marks,
        main = "Marks Boxplot",
        col = "orange")
```

## Module 1 – Practical 3: Introduction to Forecasting Software

```r
# Forecasting using R Linear Regression

sales <- c(100, 120, 130, 150, 170)

time <- c(1, 2, 3, 4, 5)

model <- lm(sales ~ time)

print(model)

summary(model)

forecast <- predict(model, data.frame(time = 6))

print(forecast)
```

## Module 1 – Practical 4: Components of Time Series

```r
# Monthly Sales Data – 24 Months

sales <- c(
  100,120,140,180,200,220,240,230,210,260,280,320,
  110,130,150,190,210,240,260,250,230,280,300,340
)

# Create Time Series Object
sales_ts <- ts(sales,
               start = c(2024, 1),
               frequency = 12)

print(sales_ts)

# Plot Original Series
plot(sales_ts,
     main = "Monthly Sales Time Series",
     xlab = "Month",
     ylab = "Sales",
     col = "blue",
     lwd = 2)

# Decompose Time Series
decomp <- decompose(sales_ts)

# Plot Components
plot(decomp)

# Extract Components
trend <- decomp$trend
seasonal <- decomp$seasonal
random <- decomp$random

cat("Trend Component:\n")
print(trend)

cat("\nSeasonal Component:\n")
print(seasonal)

cat("\nRandom Component:\n")
print(random)

# Moving Average Trend
trend_ma <- filter(sales_ts,
                   rep(1/3, 3),
                   sides = 2)

# Plot Trend
plot(sales_ts,
     main = "Trend Analysis using Moving Average",
     xlab = "Month",
     ylab = "Sales")

lines(trend_ma,
      col = "red",
      lwd = 3)

legend("topleft",
       legend = c("Original Data", "Trend"),
       col = c("black", "red"),
       lty = 1,
       lwd = 2)
```

## Module 1 – Practical 5: Simple and Weighted Moving Average

```r
# Simple Moving Average (SMA)

data <- c(10, 20, 30, 40, 50, 60, 70, 80)

n <- 3

sma <- filter(data, rep(1/n, n), sides = 1)

print("Original Data:")
print(data)

print("Simple Moving Average:")
print(sma)


# Weighted Moving Average (WMA)

data <- c(10, 20, 30, 40, 50, 60, 70, 80)

weights <- c(1, 2, 3)

n <- length(weights)

wma <- rep(NA, length(data))

for(i in n:length(data))
{
  wma[i] <- sum(data[(i-n+1):i] * weights) / sum(weights)
}

print("Original Data:")
print(data)

print("Weighted Moving Average:")
print(wma)
```

## Module 1 – Practical 6: Trend Analysis – Linear Trend Method

```r
Month <- c("Jan", "Feb", "Mar", "Apr", "May", "Jun")

Deliveries <- c(8200, 8500, 8900, 9300, 9700, 10100)

X <- 1:6

delivery_data <- data.frame(Month, X, Deliveries)

print("Food Delivery Dataset")
print(delivery_data)

trend_model <- lm(Deliveries ~ X)

print("Linear Trend Model")
print(summary(trend_model))

a <- coef(trend_model)[1]
b <- coef(trend_model)[2]

cat("\nTrend Equation:\n")
cat("Y =", round(a, 2), "+", round(b, 2), "* X\n")

july_prediction <- predict(trend_model,
                           newdata = data.frame(X = 7))

cat("\nPredicted Deliveries for July =",
    round(july_prediction), "\n")

plot(X, Deliveries,
     pch = 19,
     col = "blue",
     xlab = "Month Number",
     ylab = "Daily Deliveries",
     main = "Linear Trend Analysis")

abline(trend_model,
       col = "red",
       lwd = 2)

points(7, july_prediction,
       pch = 19,
       col = "green",
       cex = 1.5)

text(7, july_prediction,
     labels = "July Forecast",
     pos = 3,
     col = "green")

if(july_prediction > max(Deliveries)){
  cat("\nBusiness Recommendation:\n")
  cat("The number of deliveries is expected to increase.\n")
  cat("The company should hire additional delivery partners.\n")
} else {
  cat("\nBusiness Recommendation:\n")
  cat("Current number of delivery partners is sufficient.\n")
}
```

## Module 1 – Practical 7: Seasonal Variation – Simple Method

```r
# Seasonal Variation – Simple Average Method

sales <- c(120, 180, 160, 140,
           130, 195, 170, 150)

print("Quarterly Sales Data")
print(sales)

# Calculate Overall Average
overall_average <- mean(sales)

cat("\nOverall Average =", overall_average, "\n")

# Arrange Data into Matrix
sales_matrix <- matrix(sales,
                       nrow = 2,
                       byrow = TRUE)

colnames(sales_matrix) <- c("Q1", "Q2", "Q3", "Q4")
rownames(sales_matrix) <- c("Year1", "Year2")

print("\nSales Matrix")
print(sales_matrix)

# Calculate Seasonal Average
seasonal_average <- colMeans(sales_matrix)

cat("\nSeasonal Average\n")
print(seasonal_average)

# Calculate Seasonal Index
seasonal_index <- (seasonal_average / overall_average) * 100

cat("\nSeasonal Index\n")
print(round(seasonal_index, 2))

# Interpretation
cat("\nInterpretation:\n")

for(i in 1:4)
{
  if(seasonal_index[i] > 100)
  {
    cat(colnames(sales_matrix)[i],
        "- Sales are ABOVE average.\n")
  }
  else
  {
    cat(colnames(sales_matrix)[i],
        "- Sales are BELOW average.\n")
  }
}
```

## Module 1 – Practical 8: Sales Forecasting and Time Series Analysis

```r
# Dataset
Month <- c(
  "Jan-25","Feb-25","Mar-25","Apr-25","May-25","Jun-25",
  "Jul-25","Aug-25","Sep-25","Oct-25","Nov-25","Dec-25",
  "Jan-26","Feb-26","Mar-26","Apr-26","May-26","Jun-26",
  "Jul-26","Aug-26","Sep-26","Oct-26","Nov-26","Dec-26"
)

Sales <- c(
  1200,1250,1400,1650,1900,2100,
  1850,1750,1600,1700,1950,2300,
  1300,1350,1500,1750,2000,2250,
  1950,1850,1700,1800,2100,2450
)

sales_data <- data.frame(Month, Sales)

# Task 1 – Data Collection and Presentation
print(sales_data)
str(sales_data)
summary(sales_data)
head(sales_data, 5)
tail(sales_data, 5)

# Task 2 – Descriptive Statistics
cat("Total Sales:", sum(Sales), "\n")
cat("Average Sales:", mean(Sales), "\n")
cat("Median Sales:", median(Sales), "\n")
cat("Maximum Sales:", max(Sales), "\n")
cat("Minimum Sales:", min(Sales), "\n")
cat("Standard Deviation:", sd(Sales), "\n")
cat("Variance:", var(Sales), "\n")
cat("Range:", range(Sales), "\n")

# Task 3 – Data Visualization
barplot(Sales,
        names.arg = Month,
        main = "Monthly Sales Bar Chart",
        xlab = "Month",
        ylab = "Sales",
        col = "skyblue",
        las = 2)

plot(Sales,
     type = "o",
     main = "Monthly Sales Line Chart",
     xlab = "Month",
     ylab = "Sales",
     col = "blue",
     xaxt = "n")

axis(1, at = 1:length(Month), labels = Month, las = 2)

pie(Sales,
    labels = Month,
    main = "Monthly Sales Pie Chart")

hist(Sales,
     main = "Sales Histogram",
     xlab = "Sales",
     col = "lightgreen",
     border = "black")

boxplot(Sales,
        main = "Monthly Sales Box Plot",
        ylab = "Sales",
        col = "orange")

# Task 4 – Components of Time Series
sales_ts <- ts(Sales,
               start = c(2025, 1),
               frequency = 12)

plot(sales_ts,
     main = "Monthly Sales Time Series",
     xlab = "Year",
     ylab = "Sales")

decomp <- decompose(sales_ts)

plot(decomp)

trend <- decomp$trend
seasonal <- decomp$seasonal
random <- decomp$random

print(trend)
print(seasonal)
print(random)

# Task 5 – Simple Moving Average
sma_3 <- stats::filter(Sales, rep(1/3, 3), sides = 1)
sma_4 <- stats::filter(Sales, rep(1/4, 4), sides = 1)

cat("3-Month Moving Average:\n")
print(sma_3)

cat("4-Month Moving Average:\n")
print(sma_4)

# Weighted Moving Average
weights <- c(0.2, 0.3, 0.5)

wma <- rep(NA, length(Sales))

for(i in 3:length(Sales))
{
  wma[i] <- sum(Sales[(i-2):i] * weights)
}

cat("Weighted Moving Average:\n")
print(wma)

next_month_forecast <- sum(tail(Sales, 3) * weights)

cat("Next Month Forecast:", next_month_forecast, "\n")

# Task 6 – Linear Trend Analysis
time <- 1:length(Sales)

trend_model <- lm(Sales ~ time)

print(summary(trend_model))
print(coefficients(trend_model))

a <- coef(trend_model)[1]
b <- coef(trend_model)[2]

cat("Trend Equation: Sales =", a, "+", b, "* time\n")

jan_2027 <- predict(trend_model,
                    newdata = data.frame(time = 25))

cat("Forecast for January 2027:", jan_2027, "\n")

plot(time, Sales,
     main = "Actual Sales and Trend Line",
     xlab = "Month Number",
     ylab = "Sales",
     pch = 19)

abline(trend_model, col = "red", lwd = 2)

# Task 7 – Seasonal Variation
sales_matrix <- matrix(Sales,
                       nrow = 2,
                       byrow = TRUE)

colnames(sales_matrix) <- c("Q1", "Q2", "Q3", "Q4",
                             "Q5", "Q6", "Q7", "Q8",
                             "Q9", "Q10", "Q11", "Q12")

# Quarterly data using three-month groups
quarterly_sales <- matrix(Sales,
                          nrow = 4,
                          byrow = FALSE)

quarterly_sales <- matrix(
  c(
    sum(Sales[1:3]), sum(Sales[4:6]),
    sum(Sales[7:9]), sum(Sales[10:12]),
    sum(Sales[13:15]), sum(Sales[16:18]),
    sum(Sales[19:21]), sum(Sales[22:24])
  ),
  nrow = 2,
  byrow = TRUE
)

colnames(quarterly_sales) <- c("Q1", "Q2", "Q3", "Q4")
rownames(quarterly_sales) <- c("Year1", "Year2")

overall_average <- mean(quarterly_sales)
seasonal_average <- colMeans(quarterly_sales)
seasonal_index <- (seasonal_average / overall_average) * 100

print(quarterly_sales)
print(seasonal_average)
print(round(seasonal_index, 2))

cat("Quarter with Maximum Seasonal Index:",
    names(which.max(seasonal_index)), "\n")

# Task 8 – Business Interpretation
highest_month <- Month[which.max(Sales)]
lowest_month <- Month[which.min(Sales)]

cat("Highest Sales Month:", highest_month, "\n")
cat("Lowest Sales Month:", lowest_month, "\n")

if(b > 0) {
  cat("Sales Trend: Increasing\n")
} else {
  cat("Sales Trend: Decreasing\n")
}

cat("Highest Seasonal Quarter:",
    names(which.max(seasonal_index)), "\n")

cat("Next Month Forecast:", next_month_forecast, "\n")

cat("Business Decisions:\n")
cat("1. Increase inventory before high-demand periods.\n")
cat("2. Plan promotions during low-sales periods.\n")
cat("3. Allocate staff and stock according to forecast demand.\n")
```

# Module 2 – Regression and Business Forecasting Applications

## Module 2 – Practical 1: Correlation and Karl Pearson Correlation Coefficient

```r
# Concept of Correlation
# Pearson's Correlation Coefficient using R

cat("\014")

# Enter the Data
study_hours <- c(1, 2, 3, 4, 5)
marks <- c(35, 40, 50, 55, 65)

n <- length(study_hours)

cat("============================================\n")
cat("        CORRELATION ANALYSIS IN R\n")
cat("============================================\n\n")

# Original Data
data <- data.frame(
  Student = c("A", "B", "C", "D", "E"),
  Study_Hours = study_hours,
  Marks = marks
)

print(data)

# Calculation Table
X <- study_hours
Y <- marks

X2 <- X^2
Y2 <- Y^2
XY <- X * Y

calculation_table <- data.frame(
  X = X,
  Y = Y,
  X2 = X2,
  Y2 = Y2,
  XY = XY
)

cat("\nCalculation Table:\n")
print(calculation_table)

# Calculate Totals
sum_X <- sum(X)
sum_Y <- sum(Y)
sum_X2 <- sum(X2)
sum_Y2 <- sum(Y2)
sum_XY <- sum(XY)

cat("\n============================================\n")
cat("            SUMMATION VALUES\n")
cat("============================================\n")

cat("n =", n, "\n")
cat("Sum X =", sum_X, "\n")
cat("Sum Y =", sum_Y, "\n")
cat("Sum X2 =", sum_X2, "\n")
cat("Sum Y2 =", sum_Y2, "\n")
cat("Sum XY =", sum_XY, "\n")

# Pearson Correlation Manually
numerator <- n * sum_XY - (sum_X * sum_Y)

denominator <- sqrt(
  (n * sum_X2 - sum_X^2) *
  (n * sum_Y2 - sum_Y^2)
)

r <- numerator / denominator

cat("\nPearson Correlation Coefficient:\n")
cat("r =", round(r, 3), "\n")

# Verify using R cor() Function
r_builtin <- cor(X, Y, method = "pearson")

cat("\nUsing R built-in cor() function:\n")
cat("r =", round(r_builtin, 3), "\n")

# Interpretation
cat("\n============================================\n")
cat("             INTERPRETATION\n")
cat("============================================\n")

if (r > 0.90) {
  cat("There is a VERY STRONG POSITIVE correlation.\n")
} else if (r > 0.70) {
  cat("There is a STRONG POSITIVE correlation.\n")
} else if (r > 0.40) {
  cat("There is a MODERATE POSITIVE correlation.\n")
} else if (r > 0.10) {
  cat("There is a WEAK POSITIVE correlation.\n")
} else if (r < -0.90) {
  cat("There is a VERY STRONG NEGATIVE correlation.\n")
} else if (r < -0.70) {
  cat("There is a STRONG NEGATIVE correlation.\n")
} else if (r < -0.40) {
  cat("There is a MODERATE NEGATIVE correlation.\n")
} else if (r < -0.10) {
  cat("There is a WEAK NEGATIVE correlation.\n")
} else {
  cat("There is NO significant linear correlation.\n")
}

cat("\nConclusion:\n")
cat("As study hours increase, examination marks also tend\n")
cat("to increase. Therefore, the data shows a very strong\n")
cat("positive linear relationship between study hours and marks.\n")

# Scatter Plot
plot(
  X, Y,
  main = "Correlation between Study Hours and Marks",
  xlab = "Study Hours",
  ylab = "Marks",
  pch = 19
)

abline(lm(Y ~ X), lwd = 2)

legend(
  "topleft",
  legend = paste("Pearson r =", round(r, 3)),
  bty = "n"
)
```

## Module 2 – Practical 2: Linear Regression Method – E-Commerce Case Study

```r
# LINEAR REGRESSION - E-COMMERCE CASE STUDY

# Create Dataset
advertising <- c(10, 12, 15, 18, 20, 22, 25, 28, 30, 32)

sales <- c(50, 55, 60, 65, 70, 75, 80, 85, 90, 95)

ecommerce <- data.frame(advertising, sales)

print(ecommerce)

# Create Linear Regression Model
model <- lm(sales ~ advertising, data = ecommerce)

# Display Regression Model
print(model)

# Display Summary
summary(model)

# Get Regression Coefficients
coefficients(model)

# Predict Sales for Advertising Expenditure = 35
new_data <- data.frame(advertising = 35)

predicted_sales <- predict(model, newdata = new_data)

print(predicted_sales)

cat("Advertising Expenditure: ₹35,000\n")
cat("Predicted Sales Revenue: ₹",
    round(predicted_sales, 2), " thousand\n")

# Plot Original Data
plot(
  ecommerce$advertising,
  ecommerce$sales,
  main = "Advertising Expenditure vs Sales",
  xlab = "Advertising Expenditure (₹000)",
  ylab = "Sales Revenue (₹000)",
  pch = 19
)

# Add Regression Line
abline(model, lwd = 2)

# Predict Multiple Advertising Budgets
future_advertising <- data.frame(
  advertising = c(15, 20, 25, 30, 35, 40)
)

future_predictions <- predict(
  model,
  newdata = future_advertising
)

prediction_table <- data.frame(
  Advertising = future_advertising$advertising,
  Predicted_Sales = round(future_predictions, 2)
)

print(prediction_table)
```

## Module 2 – Practical 3: Forecasting Using Regression Equation

```r
# Historical Sales Data
month <- c(1, 2, 3, 4, 5, 6)

sales <- c(120, 135, 150, 165, 180, 195)

# Create Data Frame
data <- data.frame(month, sales)

print(data)

# Create Linear Regression Model
model <- lm(sales ~ month, data = data)

# Display Regression Results
summary(model)

# Display Coefficients
coefficients(model)

# Forecast July
july <- data.frame(month = 7)

forecast <- predict(model, newdata = july)

# Display Forecast
cat("Forecasted Sales for July =", forecast, "thousand\n")
```

## Module 2 – Practical 4: Demand and Sales Forecasting Using Seasonal Variation

```r
# SALES FORECASTING USING SEASONAL VARIATIONS
# Ratio-to-Average Method

# Historical Quarterly Sales Data
Q1 <- c(80, 100)
Q2 <- c(120, 150)
Q3 <- c(160, 200)
Q4 <- c(100, 125)

# Create Data Frame
sales_data <- data.frame(
  Year = c("Year 1", "Year 2"),
  Q1 = Q1,
  Q2 = Q2,
  Q3 = Q3,
  Q4 = Q4
)

print(sales_data)

# STEP 1: Calculate Annual Sales
sales_data$Annual_Sales <- rowSums(
  sales_data[, c("Q1", "Q2", "Q3", "Q4")]
)

print(sales_data)

# STEP 2: Calculate Annual Average
sales_data$Annual_Average <- sales_data$Annual_Sales / 4

print(sales_data)

# STEP 3: Calculate Seasonal Relatives
seasonal_relative <- data.frame(
  Q1 = sales_data$Q1 / sales_data$Annual_Average * 100,
  Q2 = sales_data$Q2 / sales_data$Annual_Average * 100,
  Q3 = sales_data$Q3 / sales_data$Annual_Average * 100,
  Q4 = sales_data$Q4 / sales_data$Annual_Average * 100
)

cat("\nSeasonal Relatives:\n")
print(seasonal_relative)

# STEP 4: Calculate Seasonal Indices
seasonal_index <- colMeans(seasonal_relative)

cat("\nSeasonal Indices:\n")
print(seasonal_index)

# STEP 5: Calculate Year 3 Trend
year1_sales <- sales_data$Annual_Sales[1]
year2_sales <- sales_data$Annual_Sales[2]

annual_increase <- year2_sales - year1_sales

year3_sales <- year2_sales + annual_increase

cat("\nYear 1 Sales =", year1_sales, "lakh\n")
cat("Year 2 Sales =", year2_sales, "lakh\n")
cat("Annual Increase =", annual_increase, "lakh\n")
cat("Forecasted Year 3 Sales =", year3_sales, "lakh\n")

# STEP 6: Calculate Average Quarterly Sales for Year 3
year3_quarterly_average <- year3_sales / 4

cat("Year 3 Average Quarterly Sales =",
    year3_quarterly_average, "lakh\n")

# STEP 7: Forecast Year 3 Quarterly Sales
forecast_Q1 <- year3_quarterly_average * seasonal_index["Q1"] / 100
forecast_Q2 <- year3_quarterly_average * seasonal_index["Q2"] / 100
forecast_Q3 <- year3_quarterly_average * seasonal_index["Q3"] / 100
forecast_Q4 <- year3_quarterly_average * seasonal_index["Q4"] / 100

# STEP 8: Display Forecast
forecast <- data.frame(
  Quarter = c("Q1", "Q2", "Q3", "Q4"),
  Seasonal_Index = as.numeric(seasonal_index),
  Forecast_Sales = c(
    forecast_Q1,
    forecast_Q2,
    forecast_Q3,
    forecast_Q4
  )
)

cat("\nYear 3 Sales Forecast:\n")
print(forecast)

# STEP 9: Calculate Total Forecast
total_forecast <- sum(forecast$Forecast_Sales)

cat("\nTotal Forecasted Sales for Year 3 =",
    total_forecast, "lakh\n")
```

## Module 2 – Practical 5: Index Numbers – Basics and Applications

```r
# INDEX NUMBERS – BASICS AND APPLICATIONS
# CASE STUDY: COST OF LIVING INDEX

# Clear Environment
rm(list = ls())

# Close Existing Graphics Devices
while (!is.null(dev.list())) {
  dev.off()
}

# CREATE DATA
commodity <- c(
  "Rice",
  "Wheat",
  "Milk",
  "Sugar",
  "Cooking Oil"
)

# Base-Year Quantity
q0 <- c(20, 15, 30, 10, 8)

# Current-Year Quantity
q1 <- c(22, 16, 32, 11, 8)

# Base-Year Price
p0 <- c(50, 40, 50, 45, 120)

# Current-Year Price
p1 <- c(60, 48, 60, 54, 150)

# CREATE DATA FRAME
index_data <- data.frame(
  Commodity = commodity,
  Base_Quantity = q0,
  Current_Quantity = q1,
  Base_Price = p0,
  Current_Price = p1
)

cat("\n================ ORIGINAL DATA ================\n")
print(index_data)

# CALCULATE EXPENDITURES
index_data$P0Q0 <- index_data$Base_Price * index_data$Base_Quantity

index_data$P1Q0 <- index_data$Current_Price * index_data$Base_Quantity

index_data$P0Q1 <- index_data$Base_Price * index_data$Current_Quantity

index_data$P1Q1 <- index_data$Current_Price * index_data$Current_Quantity

cat("\n================ EXPENDITURE TABLE ================\n")
print(index_data)

# PRICE RELATIVES
index_data$Price_Relative <-
  (index_data$Current_Price / index_data$Base_Price) * 100

cat("\n================ PRICE RELATIVES ================\n")

print(index_data[c("Commodity", "Price_Relative")])

# SIMPLE AGGREGATE PRICE INDEX
simple_index <- (sum(p1) / sum(p0)) * 100

# SIMPLE AVERAGE OF PRICE RELATIVES
average_index <- mean(index_data$Price_Relative)

# LASPEYRES PRICE INDEX
laspeyres_index <- (sum(index_data$P1Q0) /
                    sum(index_data$P0Q0)) * 100

# PAASCHE PRICE INDEX
paasche_index <- (sum(index_data$P1Q1) /
                  sum(index_data$P0Q1)) * 100

# FISHER'S IDEAL PRICE INDEX
fisher_index <- sqrt(laspeyres_index * paasche_index)

# TOTAL COST OF CONSUMPTION BASKET
base_cost <- sum(index_data$P0Q0)

current_cost <- sum(index_data$P1Q1)

# PERCENTAGE CHANGE IN COST
percentage_change <- ((current_cost - base_cost) / base_cost) * 100

# DISPLAY RESULTS
cat("\n\n================================ INDEX NUMBER RESULTS ================================\n")

cat("\nSimple Aggregate Price Index : ", round(simple_index, 2))

cat("\nAverage Price Relative      : ", round(average_index, 2))

cat("\nLaspeyres Price Index       : ", round(laspeyres_index, 2))

cat("\nPaasche Price Index         : ", round(paasche_index, 2))

cat("\nFisher's Ideal Price Index  : ", round(fisher_index, 2))

cat("\n\nBase Year Basket Cost       : ₹", base_cost)

cat("\nCurrent Year Basket Cost    : ₹", current_cost)

cat("\nPercentage Increase in Cost : ",
    round(percentage_change, 2), "%")

# RESULT TABLE
results <- data.frame(
  Method = c(
    "Simple Aggregate",
    "Average Price Relative",
    "Laspeyres",
    "Paasche",
    "Fisher's Ideal"
  ),
  Index = round(
    c(
      simple_index,
      average_index,
      laspeyres_index,
      paasche_index,
      fisher_index
    ),
    2
  )
)

cat("\n\n================ RESULT TABLE ================\n")
print(results)

# INTERPRETATION
cat("\n\n================ INTERPRETATION ================\n")

if (fisher_index > 100) {
  cat("\nThe overall price level has increased compared with the base year.")
} else if (fisher_index < 100) {
  cat("\nThe overall price level has decreased compared with the base year.")
} else {
  cat("\nThere is no overall change in the price level.")
}

cat(
  "\n\nFisher's Index indicates that the price level is ",
  round(fisher_index, 2),
  " compared with the base year index of 100."
)

# GRAPH 1 – BASE YEAR VS CURRENT YEAR PRICES
par(mfrow = c(1, 1))

par(mar = c(8, 5, 4, 2) + 0.1)

barplot(
  rbind(p0, p1),
  beside = TRUE,
  names.arg = commodity,
  main = "Base Year vs Current Year Prices",
  xlab = "Commodity",
  ylab = "Price (Rs.)",
  las = 2,
  cex.names = 0.8,
  legend.text = c(
    "Base Year (2024)",
    "Current Year (2026)"
  )
)

# GRAPH 2 – COMPARISON OF INDEX NUMBERS
par(mar = c(6, 5, 4, 2) + 0.1)

index_values <- c(
  simple_index,
  average_index,
  laspeyres_index,
  paasche_index,
  fisher_index
)

index_names <- c(
  "Simple",
  "Average",
  "Laspeyres",
  "Paasche",
  "Fisher"
)

barplot(
  index_values,
  names.arg = index_names,
  main = "Comparison of Index Numbers",
  xlab = "Index Method",
  ylab = "Index Value",
  ylim = c(0, max(index_values) + 10),
  cex.names = 0.8
)

abline(h = 100, lty = 2)

# FINAL MESSAGE
cat("\n\n================================ CASE STUDY COMPLETE ================================\n")

cat("\nBase Year: 2024")
cat("\nCurrent Year: 2026")

cat("\n\nThe R program successfully calculated:")
cat("\n1. Simple Aggregate Price Index")
cat("\n2. Average Price Relative")
cat("\n3. Laspeyres Price Index")
cat("\n4. Paasche Price Index")
cat("\n5. Fisher's Ideal Price Index")
cat("\n6. Cost of Consumption Basket")
cat("\n7. Percentage Change\n")
```

## Practical 8 – Forecasting Using Real Business Data

```r
# SALES FORECASTING AND TIME SERIES ANALYSIS
# FreshMart Supermarket – Mumbai

# Dataset
Month <- c(
  "Jan-25","Feb-25","Mar-25","Apr-25","May-25","Jun-25",
  "Jul-25","Aug-25","Sep-25","Oct-25","Nov-25","Dec-25",
  "Jan-26","Feb-26","Mar-26","Apr-26","May-26","Jun-26",
  "Jul-26","Aug-26","Sep-26","Oct-26","Nov-26","Dec-26"
)

Sales <- c(
  1200,1250,1400,1650,1900,2100,
  1850,1750,1600,1700,1950,2300,
  1300,1350,1500,1750,2000,2250,
  1950,1850,1700,1800,2100,2450
)

# Task 1 – Data Collection and Presentation
sales_data <- data.frame(Month, Sales)

print(sales_data)
str(sales_data)
summary(sales_data)
head(sales_data, 5)
tail(sales_data, 5)

# Task 2 – Descriptive Statistics
cat("Total Sales:", sum(Sales), "\n")
cat("Average Sales:", mean(Sales), "\n")
cat("Median Sales:", median(Sales), "\n")
cat("Maximum Sales:", max(Sales), "\n")
cat("Minimum Sales:", min(Sales), "\n")
cat("Standard Deviation:", sd(Sales), "\n")
cat("Variance:", var(Sales), "\n")
cat("Range:", range(Sales), "\n")

# Task 3 – Data Visualization
barplot(
  Sales,
  names.arg = Month,
  main = "Monthly Sales Bar Chart",
  xlab = "Month",
  ylab = "Sales",
  col = "skyblue",
  las = 2
)

plot(
  Sales,
  type = "o",
  main = "Monthly Sales Line Chart",
  xlab = "Month",
  ylab = "Sales",
  col = "blue",
  xaxt = "n"
)

axis(1, at = 1:length(Month), labels = Month, las = 2)

pie(
  Sales,
  labels = Month,
  main = "Monthly Sales Pie Chart"
)

hist(
  Sales,
  main = "Sales Histogram",
  xlab = "Sales",
  col = "lightgreen",
  border = "black"
)

boxplot(
  Sales,
  main = "Monthly Sales Box Plot",
  ylab = "Sales",
  col = "orange"
)

# Task 4 – Components of Time Series
sales_ts <- ts(
  Sales,
  start = c(2025, 1),
  frequency = 12
)

plot(
  sales_ts,
  main = "Monthly Sales Time Series",
  xlab = "Year",
  ylab = "Sales"
)

decomp <- decompose(sales_ts)
plot(decomp)

trend <- decomp$trend
seasonal <- decomp$seasonal
random <- decomp$random

print(trend)
print(seasonal)
print(random)

# Task 5 – Moving Average
sma_3 <- stats::filter(Sales, rep(1/3, 3), sides = 1)
sma_4 <- stats::filter(Sales, rep(1/4, 4), sides = 1)

print(sma_3)
print(sma_4)

# Weighted Moving Average
weights <- c(0.2, 0.3, 0.5)
wma <- rep(NA, length(Sales))

for(i in 3:length(Sales)) {
  wma[i] <- sum(Sales[(i-2):i] * weights)
}

print(wma)

next_month_forecast <- sum(tail(Sales, 3) * weights)

cat("Next Month Forecast:", next_month_forecast, "\n")

# Task 6 – Linear Trend Analysis
time <- 1:length(Sales)

trend_model <- lm(Sales ~ time)

print(summary(trend_model))
print(coefficients(trend_model))

a <- coef(trend_model)[1]
b <- coef(trend_model)[2]

cat("Trend Equation: Sales =", a, "+", b, "* time\n")

jan_2027 <- predict(
  trend_model,
  newdata = data.frame(time = 25)
)

cat("Forecast for January 2027:", jan_2027, "\n")

plot(
  time,
  Sales,
  main = "Actual Sales and Trend Line",
  xlab = "Month Number",
  ylab = "Sales",
  pch = 19
)

abline(trend_model, col = "red", lwd = 2)

# Task 7 – Seasonal Variation
quarterly_sales <- matrix(
  c(
    sum(Sales[1:3]), sum(Sales[4:6]),
    sum(Sales[7:9]), sum(Sales[10:12]),
    sum(Sales[13:15]), sum(Sales[16:18]),
    sum(Sales[19:21]), sum(Sales[22:24])
  ),
  nrow = 2,
  byrow = TRUE
)

colnames(quarterly_sales) <- c("Q1", "Q2", "Q3", "Q4")
rownames(quarterly_sales) <- c("Year1", "Year2")

overall_average <- mean(quarterly_sales)
seasonal_average <- colMeans(quarterly_sales)

seasonal_index <- (seasonal_average / overall_average) * 100

print(quarterly_sales)
print(seasonal_average)
print(round(seasonal_index, 2))

cat(
  "Quarter with Maximum Seasonal Index:",
  names(which.max(seasonal_index)),
  "\n"
)

# Task 8 – Business Interpretation
highest_month <- Month[which.max(Sales)]
lowest_month <- Month[which.min(Sales)]

cat("Highest Sales Month:", highest_month, "\n")
cat("Lowest Sales Month:", lowest_month, "\n")

if(b > 0) {
  cat("Sales Trend: Increasing\n")
} else {
  cat("Sales Trend: Decreasing\n")
}

cat(
  "Highest Seasonal Quarter:",
  names(which.max(seasonal_index)),
  "\n"
)

cat("Next Month Forecast:", next_month_forecast, "\n")
```

