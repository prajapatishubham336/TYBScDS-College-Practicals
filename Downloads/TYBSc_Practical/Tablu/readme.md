# Tableau Practicals – Module 1 & Module 2

This repository contains 15 practicals based on Tableau, covering data connection, data preparation, visualization, calculations, dashboards, advanced analytics, Tableau Prep, publishing, customer segmentation, and sales forecasting.

**Software Required:** Tableau Desktop / Tableau Public / Tableau Prep Builder

**Suggested Dataset:** Sample Superstore (or another dataset containing equivalent fields).

---

# MODULE 1

## Practical 1: Getting Started with Tableau and Building Basic Visualizations

### Aim
To connect a CSV dataset, understand the Tableau interface, identify dimensions and measures, and create basic visualizations and an interactive dashboard.

### (a) Connect to a CSV Dataset and Explore the Tableau Interface

**Steps:**
1. Open Tableau Desktop or Tableau Public.
2. Under Connect, select **Text File**.
3. Browse and select the required CSV dataset.
4. Click **Open**.
5. Review the data preview on the Data Source page.
6. Click **Sheet 1** to open a worksheet.
7. Explore the Data Pane, Analytics Pane, Rows Shelf, Columns Shelf, Marks Card, and Filters Shelf.

**Result:** The CSV dataset is successfully connected, and the Tableau interface is explored.

### (b) Identify and Differentiate Measures and Dimensions

**Steps:**
1. Open a worksheet and observe the Data Pane.
2. Identify categorical fields such as Category, Region, and Customer Name under Dimensions.
3. Identify numerical fields such as Sales, Profit, and Quantity under Measures.
4. Drag `Category → Rows`.
5. Drag `Sales → Columns`.
6. Observe how Tableau displays sales for each category.
7. Replace Category with Region and observe the changes.

**Result:** Dimensions and Measures are identified and used to create a basic visualization.

### (c) Convert Fields Between Discrete and Continuous and Observe Changes

**Steps:**
1. Open a new worksheet.
2. Drag `Order Date → Columns`.
3. Click the drop-down arrow on the Order Date pill.
4. Select **Convert to Discrete**.
5. Observe the blue pill and the headers in the view.
6. Open the field menu again.
7. Select **Convert to Continuous**.
8. Observe the green pill and the continuous axis.
9. Compare both visualizations.

**Result:** Fields are successfully converted between Discrete and Continuous, and the changes are observed.

### (d) Create and Customize a Basic Bar Chart

**Steps:**
1. Open a new worksheet.
2. Drag `Category → Rows`.
3. Drag `Sales → Columns`.
4. Select **Bar** from the Marks Card if required.
5. Drag `Category → Color`.
6. Drag `Sales → Label`.
7. Click the Sort button to arrange the bars.
8. Edit the chart title to **Sales by Category**.
9. Use the Format option to customize fonts, labels, and gridlines.

**Result:** A customized bar chart showing Sales by Category is created.

### (e) Build a Line Chart for Time-Series Analysis

**Steps:**
1. Open a new worksheet.
2. Drag `Order Date → Columns`.
3. Select Month or Year from the date pill menu.
4. Drag `Sales → Rows`.
5. Select **Line** from the Marks Card.
6. Drag `Category → Color` for category-wise comparison.
7. Format the date and sales axes.
8. Add the title **Sales Trend Over Time**.

**Result:** A line chart is created to analyze sales trends over time.

### (f) Create a Geographic Map Visualization

**Steps:**
1. Open a new worksheet.
2. Right-click the State or City field in the Data Pane.
3. Select **Geographic Role** and choose the correct geographic type if required.
4. Double-click `State` to generate a map.
5. Drag `Sales → Color`.
6. Drag `Profit → Size` if required.
7. Drag `State → Label` if required.
8. Customize the map colors and title.

**Result:** A geographic map displays sales or profit by location.

### (g) Combine Multiple Charts into a Simple Interactive Dashboard

**Steps:**
1. Create separate worksheets for the Bar Chart, Line Chart, and Map.
2. Click **New Dashboard** at the bottom of Tableau.
3. Select a suitable dashboard size.
4. Drag `Bar Chart Worksheet → Dashboard`.
5. Drag `Line Chart Worksheet → Dashboard`.
6. Drag `Map Worksheet → Dashboard`.
7. Arrange the charts using Tiled or Floating layout.
8. Open the map worksheet menu on the dashboard.
9. Select **Use as Filter** to make the dashboard interactive.
10. Add a dashboard title and save the workbook.

**Result:** An interactive dashboard containing multiple visualizations is created.

---

## Practical 2: Working with Data Sources and Data Preparation in Tableau

### Aim
To connect different data sources, prepare data, combine tables, apply filters, and improve workbook performance.

### (a) Connect to Different Data Sources (Excel, CSV, Database)

**Steps:**
1. Open Tableau.
2. Under Connect, select **Microsoft Excel**.
3. Browse and select the required Excel file.
4. To connect a CSV file, select **Text File** and choose the CSV file.
5. To connect a database, select the required database connector.
6. Enter the server name and authentication details when required.
7. Select the required database and table.
8. Review the data preview.
9. Open a worksheet to use the connected data.

**Result:** Excel, CSV, or database data is successfully connected to Tableau.

### (b) Create and Use Data Extracts vs Live Connections

**Steps:**
1. Connect to the required dataset.
2. Open the Data Source page.
3. Under Connection, select **Live** to use a live connection.
4. Observe that Tableau queries the source when required.
5. Select **Extract** to create a data extract.
6. Open Extract settings if required.
7. Click **Create Extract** and save the extract.
8. Open a worksheet and create a visualization.
9. Compare the Live and Extract connection options.

**Result:** Live and Extract connections are created and their usage is compared.

### (c) Manage Metadata (Rename, Hide, Change Data Types)

**Steps:**
1. Open the Data Source page or Data Pane.
2. Right-click a field and select **Rename**.
3. Enter a new field name and press Enter.
4. Right-click another field and select **Hide**.
5. Click the data type icon beside a field.
6. Select the required type, such as String, Number, Date, or Boolean.
7. Verify that the field is interpreted correctly.

**Result:** Field names, visibility, and data types are successfully managed.

### (d) Perform Joins (Inner, Left, Right) on Multiple Tables

**Steps:**
1. Connect to a dataset containing at least two related tables.
2. Open the Data Source page.
3. Drag `First Table → Canvas`.
4. Drag `Second Table → Beside First Table`.
5. Click the join icon between the tables.
6. Select **Inner Join**.
7. Select the matching fields, for example `Customer ID = Customer ID`.
8. Review the joined data preview.
9. Repeat the process using **Left Join**.
10. Repeat the process using **Right Join**.
11. Compare the resulting records.

**Result:** Inner, Left, and Right joins are performed successfully.

### (e) Apply Data Blending Between Two Sources

**Steps:**
1. Connect to the first data source.
2. Open a worksheet.
3. Select **Data → New Data Source**.
4. Connect to the second data source.
5. Return to the worksheet.
6. Select the primary data source in the Data Pane.
7. Select the secondary data source.
8. Identify a common linking field, such as Region or Customer ID.
9. Activate the linking field using the link icon if required.
10. Drag `Region → Rows`.
11. Drag a measure from the secondary source, such as `Sales → Columns`.
12. Review the blended result.

**Result:** Data from two different sources is blended using a common linking field.

### (f) Implement Different Types of Filters (Dimension, Measure, Date)

**Steps:**
1. Open a new worksheet.
2. Drag `Category → Rows`.
3. Drag `Sales → Columns`.
4. Drag `Category → Filters` and select the required categories.
5. Drag `Sales → Filters` and select the required range or condition.
6. Drag `Order Date → Filters`.
7. Select a date filter type, such as Range of Dates or Relative Date.
8. Open the filter menu and select **Show Filter**.
9. Test each filter.

**Result:** Dimension, Measure, and Date filters are successfully applied.

### (g) Optimize Performance Using Extracts and Filtering

**Steps:**
1. Open the Data Source page.
2. Change the connection from Live to **Extract**.
3. Open Extract settings.
4. Add extract filters to include only the required records.
5. Remove unused fields from the worksheet.
6. Apply relevant filters to reduce unnecessary data.
7. Avoid unnecessary marks and complex calculations.
8. Use **Help → Settings and Performance → Start Performance Recording**, if available.
9. Interact with the workbook.
10. Stop recording and review the performance report.

**Result:** Workbook performance is improved using extracts and filtering.

---

## Practical 3: Creating Advanced Visualizations in Tableau

### Aim
To create advanced charts for comparison, distribution, relationships, and time-based analysis.

### (a) Create Stacked and Grouped Bar Charts for Comparison

**Stacked Bar Chart – Steps:**
1. Open a new worksheet.
2. Drag `Category → Columns`.
3. Drag `Sales → Rows`.
4. Select **Bar** from the Marks Card.
5. Drag `Region → Color`.
6. Select **Analysis → Stack Marks → On**.
7. Add the title **Sales by Category and Region**.

**Grouped Bar Chart – Steps:**
1. Open another worksheet.
2. Drag `Category → Columns`.
3. Drag `Region → Columns`, next to Category.
4. Drag `Sales → Rows`.
5. Select **Bar** from the Marks Card.
6. Customize colors and labels.
7. Add a suitable title.

**Result:** Stacked and grouped bar charts are created for comparison.

### (b) Build Treemaps and Pie Charts for Part-to-Whole Analysis

**Treemap – Steps:**
1. Open a new worksheet.
2. Drag `Sales → Marks: Size`.
3. Drag `Category → Marks: Color`.
4. Drag `Sub-Category → Marks: Label`.
5. Select **Show Me → Treemap**.
6. Customize the colors and labels.

**Pie Chart – Steps:**
1. Open another worksheet.
2. Select **Pie** from the Marks Card.
3. Drag `Category → Marks: Color`.
4. Drag `Sales → Marks: Angle`.
5. Drag `Sales → Marks: Label`.
6. Adjust the pie chart size.

**Result:** Treemaps and pie charts are created to show part-to-whole relationships.

### (c) Design Scatter Plots to Identify Relationships

**Steps:**
1. Open a new worksheet.
2. Drag `Sales → Columns`.
3. Drag `Profit → Rows`.
4. Select **Circle** from the Marks Card.
5. Drag `Category → Color`.
6. Drag `Customer Name → Detail` to create individual marks if required.
7. Open the Analytics Pane.
8. Drag **Trend Line → View** if required.
9. Observe the relationship between Sales and Profit.

**Result:** A scatter plot is created to identify relationships between numerical measures.

### (d) Create Dual-Axis and Combination Charts

**Steps:**
1. Open a new worksheet.
2. Drag `Order Date → Columns`.
3. Drag `Sales → Rows`.
4. Drag `Profit → Rows`, next to Sales.
5. Open the drop-down menu of the second measure.
6. Select **Dual Axis**.
7. Right-click an axis and select **Synchronize Axis** if appropriate.
8. Select the Sales Marks Card and choose **Bar**.
9. Select the Profit Marks Card and choose **Line**.
10. Format the axes and chart title.

**Result:** A dual-axis combination chart is created to compare Sales and Profit.

### (e) Develop Histograms for Distribution Analysis

**Steps:**
1. Open a new worksheet.
2. Right-click the numerical field `Sales` in the Data Pane.
3. Select **Create → Bins**.
4. Set an appropriate bin size and click OK.
5. Drag `Sales (bin) → Columns`.
6. Drag `Number of Records → Rows`, or use an appropriate record count measure.
7. Select **Bar** from the Marks Card.
8. Customize the bin size and axis labels.

**Result:** A histogram is created to show the distribution of Sales.

### (f) Build Box-and-Whisker Plots

**Steps:**
1. Open a new worksheet.
2. Drag `Category → Columns`.
3. Drag `Sales → Rows`.
4. Select **Show Me → Box-and-Whisker Plot**.
5. Add a detailed field such as `Customer Name → Detail` if required.
6. Open the Analytics Pane.
7. Drag **Box Plot → Pane** if using the Analytics Pane.
8. Review the median, quartiles, whiskers, and possible outliers.

**Result:** A box-and-whisker plot is created to compare distributions and identify outliers.

### (g) Use Gantt Charts and Advanced Date Visualizations

**Gantt Chart – Steps:**
1. Open a new worksheet containing task start and end dates.
2. Drag `Task Name → Rows`.
3. Drag `Start Date → Columns`.
4. Select the appropriate date level.
5. Select **Gantt Bar** from the Marks Card.
6. Create a calculated field named Duration:

   ```text
   DATEDIFF('day', [Start Date], [End Date])
   ```

7. Drag `Duration → Marks: Size`.
8. Add task labels and format the date axis.

**Advanced Date Visualization – Steps:**
1. Open another worksheet.
2. Drag `Order Date → Columns`.
3. Select Year, Quarter, Month, or Exact Date.
4. Drag `Sales → Rows`.
5. Select Line or Bar from the Marks Card.
6. Drag `Category → Color` if required.
7. Add a suitable title.

**Result:** Gantt charts and advanced date visualizations are created.

---

## Practical 4: Performing Data Analysis using Calculations in Tableau

### Aim
To create calculated fields, perform row-level and aggregate calculations, use LOD expressions and parameters, and improve data quality.

### (a) Create Basic Calculated Fields Using Formulas

**Steps:**
1. Select **Analysis → Create Calculated Field**.
2. Enter the field name `Profit Ratio`.
3. Enter the formula:

   ```text
   SUM([Profit]) / SUM([Sales])
   ```

4. Click OK.
5. Drag `Category → Rows`.
6. Drag `Profit Ratio → Columns`.
7. Format the field as a percentage.

**Result:** A calculated field is created to display the Profit Ratio.

### (b) Perform Row-Level Calculations

**Steps:**
1. Select **Analysis → Create Calculated Field**.
2. Name the field `Row Profit`.
3. Enter the formula:

   ```text
   [Sales] - [Cost]
   ```

4. Click OK.
5. Drag `Order ID → Rows`.
6. Drag `Row Profit → Text` on the Marks Card.
7. Review the calculated value for each record.

**Result:** A row-level calculation is created and displayed for individual records.

### (c) Perform Aggregate-Level Calculations

**Steps:**
1. Select **Analysis → Create Calculated Field**.
2. Name the field `Average Sales`.
3. Enter the formula:

   ```text
   AVG([Sales])
   ```

4. Click OK.
5. Drag `Category → Rows`.
6. Drag `Average Sales → Columns`.
7. Compare average sales across categories.

**Result:** Aggregate-level calculations are performed to summarize data.

### (d) Implement FIXED Level of Detail (LOD) Calculations

**Steps:**
1. Select **Analysis → Create Calculated Field**.
2. Name the field `Customer Total Sales`.
3. Enter the formula:

   ```text
   { FIXED [Customer Name] : SUM([Sales]) }
   ```

4. Click OK.
5. Drag `Customer Name → Rows`.
6. Drag `Customer Total Sales → Columns`.
7. Sort the values to identify customers with higher sales.

**Result:** FIXED LOD calculates total sales at the customer level.

### (e) Use INCLUDE and EXCLUDE LOD Expressions

**INCLUDE – Steps:**
1. Select **Analysis → Create Calculated Field**.
2. Name the field `Customer Sales`.
3. Enter the formula:

   ```text
   { INCLUDE [Customer Name] : SUM([Sales]) }
   ```

4. Click OK.
5. Drag `Region → Rows`.
6. Drag `Customer Sales → Text`.
7. Use an appropriate aggregation, such as AVG, when comparing average customer-level sales.

**EXCLUDE – Steps:**
1. Create another calculated field named `Sales Excluding Sub-Category`.
2. Enter:

   ```text
   { EXCLUDE [Sub-Category] : SUM([Sales]) }
   ```

3. Click OK.
4. Drag `Category → Rows`.
5. Drag `Sub-Category → Columns`.
6. Add the EXCLUDE calculation to the view.
7. Compare the results.

**Result:** INCLUDE and EXCLUDE LOD expressions are used to control the level of detail in calculations.

### (f) Create and Use Parameters for Dynamic Analysis

**Steps:**
1. In the Data Pane, open the menu and select **Create Parameter**.
2. Name it `Select Measure`.
3. Set Data Type to String.
4. Add allowable values: Sales and Profit.
5. Click OK.
6. Select **Analysis → Create Calculated Field**.
7. Name the field `Selected Measure`.
8. Enter:

   ```text
   CASE [Select Measure]
   WHEN "Sales" THEN SUM([Sales])
   WHEN "Profit" THEN SUM([Profit])
   END
   ```

9. Click OK.
10. Drag `Category → Rows`.
11. Drag `Selected Measure → Columns`.
12. Right-click the parameter and select **Show Parameter**.
13. Change the parameter value and observe the chart.

**Result:** A parameter is created to switch the displayed measure dynamically.

### (g) Apply Calculations to Fix Data Issues and Enhance Insights

**Steps:**
1. Select **Analysis → Create Calculated Field**.
2. Name the field `Clean Sales`.
3. Enter:

   ```text
   IFNULL([Sales], 0)
   ```

4. Create another calculated field named `Clean Category`.
5. Enter:

   ```text
   IFNULL([Category], "Unknown")
   ```

6. Click OK after creating each field.
7. Create a Profit Ratio calculation:

   ```text
   SUM([Profit]) / SUM([Sales])
   ```

8. Drag the cleaned fields into a worksheet.
9. Verify that null values are handled as expected.

**Result:** Calculations are used to handle null values and generate additional insights.

---

## Practical 5: Analyzing Data using Table Calculations in Tableau

### Aim
To analyze data using running totals, moving averages, growth rates, rankings, and window functions.

### (a) Apply Quick Table Calculations (Running Total, Percent of Total)

**Running Total – Steps:**
1. Open a worksheet.
2. Drag `Order Date → Columns`.
3. Select Month from the date pill menu.
4. Drag `Sales → Rows`.
5. Open the Sales pill menu.
6. Select **Quick Table Calculation → Running Total**.
7. Review the cumulative sales values.

**Percent of Total – Steps:**
1. Open another worksheet.
2. Drag `Category → Rows`.
3. Drag `Sales → Columns`.
4. Open the Sales pill menu.
5. Select **Quick Table Calculation → Percent of Total**.
6. Format the result as a percentage.

**Result:** Running Total and Percent of Total calculations are applied successfully.

### (b) Create Moving Averages and Cumulative Metrics

**Moving Average – Steps:**
1. Open a new worksheet.
2. Drag `Order Date → Columns`.
3. Select Month.
4. Drag `Sales → Rows`.
5. Open the Sales pill menu.
6. Select **Quick Table Calculation → Moving Average**.
7. Select **Edit Table Calculation** to configure the moving window if required.
8. Observe the smoothed sales trend.

**Cumulative Metric – Steps:**
1. Use the same date-based view.
2. Open the Sales pill menu.
3. Select **Quick Table Calculation → Running Total**.
4. Set Compute Using to the date field.
5. Review cumulative sales over time.

**Result:** Moving averages and cumulative metrics are created to analyze trends.

### (c) Perform Year-over-Year Growth Analysis

**Steps:**
1. Open a new worksheet.
2. Drag `Order Date → Columns`.
3. Select Month or Year, depending on the analysis.
4. Drag `Sales → Rows`.
5. Open the Sales pill menu.
6. Select **Quick Table Calculation → Year over Year Growth** or Percent Difference if available.
7. If using Percent Difference, edit the table calculation and set the comparison to the previous year.
8. Set Compute Using to the date field.
9. Format the result as a percentage.

**Result:** Year-over-year sales growth is calculated and displayed.

### (d) Use Ranking Functions (Top N, Bottom N)

**Steps:**
1. Select **Analysis → Create Calculated Field**.
2. Name the field `Sales Rank`.
3. Enter:

   ```text
   RANK(SUM([Sales]), 'desc')
   ```

4. Click OK.
5. Drag `Customer Name → Rows`.
6. Drag `Sales → Columns`.
7. Drag `Sales Rank → Label`.
8. Sort the view by Sales in descending order.
9. Drag `Sales Rank → Filters`.
10. Select the required rank range, such as 1 to 10.
11. For Bottom N, create a calculation using:

   ```text
   RANK(SUM([Sales]), 'asc')
   ```

**Result:** Customers or products are ranked, and Top N or Bottom N records are identified.

### (e) Implement Window Functions (WINDOW_SUM, WINDOW_AVG)

**WINDOW_SUM – Steps:**
1. Select **Analysis → Create Calculated Field**.
2. Name it `Window Total Sales`.
3. Enter:

   ```text
   WINDOW_SUM(SUM([Sales]))
   ```

4. Click OK.
5. Drag `Order Date → Columns`.
6. Drag `Window Total Sales → Rows`.
7. Edit the table calculation to configure addressing and partitioning.

**WINDOW_AVG – Steps:**
1. Create another calculated field named `Window Average Sales`.
2. Enter:

   ```text
   WINDOW_AVG(SUM([Sales]))
   ```

3. Click OK.
4. Add the field to the view.
5. Configure the calculation direction.

**Result:** Window functions are used to calculate totals and averages across a selected range of marks.

### (f) Customize Addressing and Partitioning

**Steps:**
1. Open a new worksheet.
2. Drag `Order Date → Columns`.
3. Drag `Category → Color`.
4. Drag `Sales → Rows`.
5. Apply a Running Total table calculation to Sales.
6. Open the measure pill menu.
7. Select **Edit Table Calculation**.
8. Under Compute Using, select the required field or Specific Dimensions.
9. Select Month as the addressing field.
10. Use Category to divide the calculation into partitions.
11. Observe how the calculation restarts for each partition.

**Result:** Addressing and partitioning are configured to control table calculations.

### (g) Create Dynamic Titles and Labels Using Table Calculations

**Steps:**
1. Open a worksheet.
2. Drag `Order Date → Columns`.
3. Drag `Sales → Rows`.
4. Apply a table calculation such as Running Total or Percent of Total.
5. Drag the calculated measure → Marks: Label.
6. Open Label and enable **Show mark labels**.
7. Edit the worksheet title.
8. Use the Insert option to add available field values.
9. Use a parameter or calculated field for a user-selected title if required.
10. Format the title and labels.

**Result:** Dynamic labels and informative titles are added to the visualization.

---

## Practical 6: Designing Effective and Visually Appealing Dashboards

### Aim
To format worksheets and dashboards, improve readability, and communicate insights effectively.

### (a) Apply Worksheet-Level and Workbook-Level Formatting

**Steps:**
1. Open a worksheet.
2. Select **Format** from the top menu.
3. Adjust fonts, alignment, shading, borders, and lines.
4. Apply the required formatting to the worksheet.
5. Use workbook-level formatting options available in the Tableau version.
6. Set consistent fonts and formatting where supported.
7. Review multiple worksheets for consistency.

**Result:** Worksheet and workbook formatting are applied consistently.

### (b) Customize Number, Date, and Null Value Formatting

**Steps:**
1. Right-click `Sales` in the Data Pane.
2. Select **Default Properties → Number Format**.
3. Choose Number, Currency, Percentage, or another suitable format.
4. Right-click `Order Date` if date formatting is required.
5. Select the available Date Format option.
6. Choose the required date display.
7. To handle null values, create a calculated field:

   ```text
   IFNULL([Sales], 0)
   ```

8. Use the cleaned field in the worksheet.
9. Verify the formatting.

**Result:** Number, date, and null values are formatted appropriately.

### (c) Design Effective Color Schemes and Layouts

**Steps:**
1. Open a worksheet.
2. Drag a dimension or measure → Marks: Color.
3. Click **Color → Edit Colors**.
4. Select a suitable color palette.
5. Use sequential colors for ordered values and diverging colors for positive and negative comparisons.
6. Open a dashboard.
7. Arrange worksheets using Tiled or Floating layout.
8. Keep related charts together.
9. Maintain consistent spacing and colors.

**Result:** A clear color scheme and organized dashboard layout are created.

### (d) Create Informative Tooltips

**Steps:**
1. Open the required worksheet.
2. Select the Marks Card → Tooltip.
3. Edit the tooltip text.
4. Use the Insert option to add field values such as Sales, Profit, Category, and Region.
5. Remove unnecessary information.
6. Format the tooltip.
7. Hover over marks to test it.

**Result:** Informative tooltips display relevant details when users hover over marks.

### (e) Implement Viz in Tooltip

**Steps:**
1. Create a main worksheet, such as Sales by Category.
2. Create a second worksheet showing details, such as Sales by Sub-Category.
3. Return to the main worksheet.
4. Select Marks Card → Tooltip.
5. Click **Insert → Sheets**.
6. Select the detail worksheet.
7. Configure the fields used to filter the embedded view.
8. Click OK.
9. Hover over a mark in the main chart to view the embedded visualization.

**Result:** A secondary visualization is displayed inside the tooltip.

### (f) Improve Readability and User Experience

**Steps:**
1. Open the dashboard.
2. Use clear and meaningful chart titles.
3. Remove unnecessary gridlines and borders.
4. Use readable font sizes.
5. Keep colors consistent across worksheets.
6. Place related charts together.
7. Add only useful filters and legends.
8. Test the dashboard at its intended display size.

**Result:** The dashboard becomes easier to read and use.

### (g) Apply Best Practices for Visual Storytelling

**Steps:**
1. Identify the main question the dashboard should answer.
2. Place the most important chart in a prominent position.
3. Arrange charts in a logical order.
4. Use titles that communicate the key message.
5. Highlight important values using labels or colors.
6. Add tooltips to provide supporting details.
7. Avoid unnecessary charts and decorative elements.
8. Review the dashboard as a complete story.

**Result:** A dashboard is designed to communicate data insights clearly and logically.

---

## Practical 7: Creating Interactive Dashboards and Data Stories

### Aim
To build interactive dashboards using filters, actions, parameters, and Tableau Story features.

### (a) Design a Basic Dashboard Layout Using Sheets

**Steps:**
1. Create worksheets for Sales by Category, Sales Trend, and Sales by Region.
2. Click **New Dashboard**.
3. Select a suitable dashboard size.
4. Drag `Sales by Category Worksheet → Dashboard`.
5. Drag `Sales Trend Worksheet → Dashboard`.
6. Drag `Sales by Region Worksheet → Dashboard`.
7. Arrange the worksheets using Tiled or Floating layout.
8. Add a dashboard title and save the workbook.

**Result:** A basic dashboard layout is created using multiple worksheets.

### (b) Add Filters and Interactive Controls

**Steps:**
1. Open the dashboard.
2. Select a worksheet on the dashboard.
3. Open the sheet menu → Filters.
4. Select a field such as Category or Region.
5. Show the filter card.
6. Select a filter style, such as Single Value or Multiple Values.
7. Open the filter card menu.
8. Select **Apply to Worksheets**.
9. Choose the worksheets that should respond to the filter.
10. Test the filter selections.

**Result:** Filters and interactive controls are added to the dashboard.

### (c) Implement Highlight and Filter Actions

**Filter Action – Steps:**
1. Open the dashboard.
2. Select **Dashboard → Actions → Add Action → Filter**.
3. Enter an action name.
4. Select the source worksheet.
5. Select the target worksheet.
6. Choose the action to run, such as Select.
7. Set the clearing selection behavior.
8. Click OK and test the action.

**Highlight Action – Steps:**
1. Select **Dashboard → Actions → Add Action → Highlight**.
2. Select the source and target worksheets.
3. Choose the fields used for highlighting.
4. Click OK.
5. Select a mark and observe the highlighted related marks.

**Result:** Filter and Highlight actions make dashboard charts interactive.

### (d) Use URL and Set Actions for Interactivity

**URL Action – Steps:**
1. Open the dashboard.
2. Select **Dashboard → Actions → Add Action → Go to URL**.
3. Enter an action name.
4. Select the source worksheet.
5. Enter a valid destination URL.
6. Insert a field value into the URL if the destination supports it.
7. Click OK and test the action.

**Set Action – Steps:**
1. In the Data Pane, right-click `Customer Name`.
2. Select **Create → Set**.
3. Choose the required members and click OK.
4. Open the dashboard.
5. Select **Dashboard → Actions → Add Action → Change Set Values**.
6. Choose the source worksheet and target set.
7. Configure how selected values are added or removed.
8. Click OK and test the action.

**Result:** URL and Set actions are configured to provide dashboard interaction.

### (e) Create Dynamic Dashboards Using Parameters

**Steps:**
1. Create a parameter named `Choose Measure`.
2. Set Data Type to String.
3. Add values such as Sales and Profit.
4. Create a calculated field named `Dynamic Measure`.
5. Enter:

   ```text
   CASE [Choose Measure]
   WHEN "Sales" THEN SUM([Sales])
   WHEN "Profit" THEN SUM([Profit])
   END
   ```

6. Click OK.
7. Drag `Category → Rows`.
8. Drag `Dynamic Measure → Columns`.
9. Right-click the parameter and select **Show Parameter**.
10. Add the worksheet to a dashboard.
11. Change the parameter value and observe the dashboard.

**Result:** A parameter-driven dashboard is created.

### (f) Design Dashboards for Multiple Devices

**Steps:**
1. Open the dashboard.
2. Select **Device Preview**.
3. Choose Desktop, Tablet, or Phone.
4. Review the dashboard on each device.
5. Use Add Layout or device-specific layout options where available.
6. Rearrange or resize charts for smaller screens.
7. Remove unnecessary elements from the mobile layout.
8. Preview each device layout and save the dashboard.

**Result:** Dashboard layouts are adjusted for different screen sizes.

### (g) Build a Complete Data Story Using Story Feature

**Steps:**
1. Create the required worksheets and dashboard.
2. Click **New Story** at the bottom of Tableau.
3. Select a suitable story size.
4. Drag the first worksheet or dashboard → Story.
5. Add a caption explaining the first insight.
6. Click **New Story Point**.
7. Add the next worksheet or dashboard.
8. Enter a caption for each story point.
9. Arrange the story points in a logical sequence.
10. Preview the story and save the workbook.

**Result:** A complete data story is created using multiple story points.

---

# MODULE 2

## Practical 8: Performing Advanced Analytics using Trends, Clustering, and Forecasting

### Aim
To use trend lines, clustering, distribution analysis, and forecasting features for advanced data analysis.

### (a) Add and Interpret Trend Lines (Linear, Exponential)

**Steps:**
1. Open a worksheet.
2. Drag `Sales → Columns`.
3. Drag `Profit → Rows`.
4. Open the Analytics Pane.
5. Drag **Trend Line → View**.
6. Right-click the trend line and select **Edit Trend Lines**.
7. Select a supported model such as Linear or Exponential.
8. Review the direction and fit of the trend line.

**Result:** Trend lines are added to the chart and interpreted.

### (b) Customize and Analyze Trend Models

**Steps:**
1. Open a worksheet containing suitable measures.
2. Add a trend line from the Analytics Pane.
3. Right-click the trend line.
4. Select **Edit Trend Lines**.
5. Select the required model type.
6. Configure the available options.
7. Right-click the trend line and select **Describe Trend Model**.
8. Review the model details and statistical information.

**Result:** Trend models are customized and their statistical details are reviewed.

### (c) Perform Clustering on Datasets

**Steps:**
1. Open a worksheet with at least two numerical measures.
2. Drag `Sales → Columns`.
3. Drag `Profit → Rows`.
4. Drag `Customer Name → Detail`.
5. Open the Analytics Pane.
6. Drag **Cluster → View**.
7. Review the generated clusters.
8. Drag the Cluster field → Color if required.
9. Review the characteristics of each cluster.

**Result:** Records are grouped into clusters based on selected measures.

### (d) Analyze Distributions Using Built-in Tools

**Steps:**
1. Open a new worksheet.
2. Drag `Category → Columns`.
3. Drag `Sales → Rows`.
4. Open the Analytics Pane.
5. Explore tools such as Box Plot, Distribution Band, Average Line, Median, and Percentile.
6. Drag the required tool → View or Pane.
7. Review the distribution and variation in the data.

**Result:** Built-in analytical tools are used to understand data distribution.

### (e) Apply Forecasting Techniques

**Steps:**
1. Open a new worksheet.
2. Drag `Order Date → Columns`.
3. Select Month or another suitable date level.
4. Drag `Sales → Rows`.
5. Open the Analytics Pane.
6. Drag **Forecast → View**.
7. Tableau generates a forecast using historical time-series data.
8. Right-click the forecast area and select **Describe Forecast**.
9. Adjust forecast options if required.

**Result:** A sales forecast is generated using historical data.

### (f) Compare Different Statistical Models

**Steps:**
1. Create a time-series worksheet.
2. Drag `Order Date → Columns`.
3. Drag `Sales → Rows`.
4. Add a forecast from the Analytics Pane.
5. Open **Analysis → Forecast → Forecast Options**.
6. Review the available forecast model options.
7. Select Automatic or a supported specific model.
8. Compare the forecast results and model details.
9. Use Describe Forecast to review the selected model information.

**Result:** Available forecasting model options are compared and interpreted.

### (g) Export and Interpret Statistical Results

**Steps:**
1. Open the worksheet containing trend, cluster, or forecast analysis.
2. Review the chart and analytical details.
3. For a trend line, right-click it and select **Describe Trend Model**.
4. For a forecast, right-click the forecast and select **Describe Forecast**.
5. Select the appropriate Export option from the Worksheet menu.
6. Choose a supported format such as Image, PDF, or Crosstab.
7. Save the exported file.
8. Interpret the important values and patterns.

**Result:** Statistical results are exported in a supported format and interpreted.

---

## Practical 9: Cleaning and Structuring Data for Analysis

### Aim
To clean missing or inconsistent data, reshape tables, combine files, and prepare data for analysis.

### (a) Identify and Handle Missing or Inconsistent Data

**Steps:**
1. Connect the dataset to Tableau.
2. Open the Data Source page.
3. Review the data preview for null or unexpected values.
4. Open a worksheet.
5. Drag the relevant field into the view.
6. Use the field filter to identify Null values.
7. Exclude unwanted null records or create a calculated field.
8. Use the formula:

   ```text
   IFNULL([Sales], 0)
   ```

9. Use aliases or Tableau Prep to standardize inconsistent text values.
10. Verify the cleaned result.

**Result:** Missing and inconsistent data is identified and handled.

### (b) Convert Wide Data into Tall Format

**Steps:**
1. Connect to the dataset.
2. Open the Data Source page.
3. Select the columns that should be converted into rows.
4. Right-click the selected columns.
5. Select **Pivot**.
6. Tableau creates Pivot Field Names and Pivot Field Values.
7. Rename these fields to meaningful names, such as Period and Sales.
8. Review the reshaped data.

**Result:** Wide-format data is converted into a tall or long format using Pivot.

### (c) Perform Union of Multiple Files

**Steps:**
1. Connect to the first file.
2. Open the Data Source page.
3. Drag `First Table → Canvas`.
4. Drag `Second Table → Below First Table`.
5. Select **Union** when the option appears.
6. Add more files using the Union interface if required.
7. Review the combined rows in the data preview.
8. Check that the columns align correctly.

**Result:** Multiple files with compatible structures are combined using Union.

### (d) Execute Cross-Database Joins

**Steps:**
1. Connect to the first database.
2. Select **Data → New Data Source**.
3. Connect to the second database.
4. Open the data model.
5. Drag `First Table → Canvas`.
6. Drag `Second Table → Beside First Table`.
7. Select the matching key fields.
8. Configure the required join type, such as Inner or Left.
9. Review the joined data preview.
10. Check that the linking fields have compatible data types.

**Result:** Tables from different supported databases are joined for analysis.

### (e) Restructure Data for Better Visualization

**Steps:**
1. Connect to the dataset.
2. Open the Data Source page.
3. Review the current table structure.
4. Use **Pivot** to convert selected columns into rows if required.
5. Use **Union** to append files with similar structures if required.
6. Rename fields to meaningful names.
7. Set the correct data types.
8. Open a worksheet and use the restructured fields in a chart.
9. Verify that the new structure supports the intended analysis.

**Result:** Data is restructured into a format that is easier to visualize.

### (f) Handle Different Levels of Detail in Datasets

**Steps:**
1. Connect to the dataset.
2. Identify the level of detail of each table, such as Order-level, Product-level, or Customer-level.
3. Identify common linking fields between tables.
4. Use Relationships or Joins as appropriate on the Data Source page.
5. Avoid joining tables in a way that duplicates measures unintentionally.
6. Create an LOD calculation if a calculation is required at a fixed level.
7. Use the formula:

   ```text
   { FIXED [Customer Name] : SUM([Sales]) }
   ```

8. Compare the result with the expected level of detail.

**Result:** Different levels of detail are managed to support accurate analysis.

### (g) Apply Advanced Data Cleaning Techniques

**Steps:**
1. Open the Data Source page or Tableau Prep.
2. Review field names, data types, nulls, and inconsistent values.
3. Rename unclear fields.
4. Hide unused fields.
5. Correct data types.
6. Use filters to remove unwanted records.
7. Use aliases or grouping to standardize category values.
8. Create a calculated field using:

   ```text
   TRIM([Customer Name])
   ```

9. Review the cleaned dataset before creating visualizations.

**Result:** Advanced data cleaning techniques are applied to prepare the dataset for analysis.

---

## Practical 10: Data Preparation and Transformation using Tableau Prep

### Aim
To prepare and transform data using Tableau Prep Builder and create a reusable data preparation flow.

### (a) Connect and Load Data into Tableau Prep

**Steps:**
1. Open Tableau Prep Builder.
2. Click **Connect to Data**.
3. Select a source such as Microsoft Excel or Text File.
4. Browse and select the dataset.
5. Select the required sheet or table.
6. Click the Plus (+) icon and add a Clean Step if required.
7. Review the data in the Profile Pane.

**Result:** Data is connected and loaded into Tableau Prep.

### (b) Clean and Profile Data

**Steps:**
1. Open the flow in Tableau Prep.
2. Add a **Clean Step**.
3. Review the Profile Cards for each field.
4. Identify null values, unexpected values, and data type issues.
5. Rename fields where required.
6. Change incorrect data types.
7. Remove unwanted fields or records.
8. Review the cleaned data.

**Result:** Data is profiled and cleaned using Tableau Prep.

### (c) Group and Standardize Values

**Steps:**
1. Add a Clean Step to the flow.
2. Select the field containing inconsistent values.
3. Open the field menu.
4. Select **Group Values**.
5. Choose a grouping method, such as manual grouping or fuzzy grouping if available.
6. Combine values that represent the same category.
7. Rename the standardized group.
8. Review the updated values.

**Result:** Similar and inconsistent values are grouped and standardized.

### (d) Merge Mismatched Fields

**Steps:**
1. Open the relevant Clean Step.
2. Identify fields that contain the same type of information but have different names or values.
3. Select the fields to merge or use the appropriate merge option available in Prep.
4. Configure the resulting field name.
5. Review the merged values.
6. Correct any remaining mismatches.

**Result:** Mismatched fields are merged or standardized into a consistent field.

### (e) Perform Aggregations in Prep

**Steps:**
1. Open the flow.
2. Click the Plus (+) icon.
3. Select **Aggregate**.
4. Drag `Region → Grouped Fields`.
5. Drag `Sales → Aggregated Fields`.
6. Select the required aggregation, such as SUM, AVG, MIN, or MAX.
7. Review the aggregated output.

**Result:** Data is aggregated by the selected fields and measures.

### (f) Apply Filters and Transformations

**Steps:**
1. Add a Clean Step to the flow.
2. Select the field to filter.
3. Open the field menu and select Filter.
4. Choose the required values or conditions.
5. Apply transformations such as Rename, Split, Group, or Change Data Type.
6. Review the output after each transformation.
7. Verify that unwanted records have been removed.

**Result:** Filters and transformations are applied to prepare the data.

### (g) Create and Automate Data Preparation Flows

**Steps:**
1. Complete the required Input, Clean, Join, Union, and Aggregate steps.
2. Add an **Output Step** to the flow.
3. Select the output type, such as a Tableau data extract or supported file.
4. Enter an output file name and location.
5. Click **Run Flow**.
6. Review the output and confirm that it was generated successfully.
7. Save the flow.
8. For scheduled automation, publish the flow to a supported Tableau Server or Tableau Cloud environment.
9. Configure a schedule if the environment, permissions, and license support it.

**Result:** A reusable data preparation flow is created and run. Scheduling is configured where supported.

---

## Practical 11: Implementing Advanced Visualization Techniques and Customizations

### Aim
To create specialized charts and apply advanced dashboard customization techniques.

### (a) Create Slope Charts and Lollipop Charts

**Slope Chart – Steps:**
1. Prepare data containing a category, two time periods, and a measure.
2. Open a worksheet.
3. Drag `Period → Columns`.
4. Drag `Measure → Rows`.
5. Drag `Category → Color`.
6. Drag `Category → Detail`.
7. Filter the Period field to the two periods being compared.
8. Select Line from the Marks Card.
9. Add labels and format the chart.

**Lollipop Chart – Steps:**
1. Open a new worksheet.
2. Drag `Category → Rows`.
3. Drag `Sales → Columns`.
4. Add a second copy of Sales to Columns.
5. Open the second measure menu and select **Dual Axis**.
6. On the first Marks Card, select Bar and reduce its size.
7. On the second Marks Card, select Circle.
8. Synchronize axes and hide the unnecessary duplicate header.
9. Format the chart.

**Result:** Slope and lollipop charts are created for comparing values.

### (b) Design Waterfall Charts

**Steps:**
1. Open a worksheet containing Category and Profit fields.
2. Drag `Category → Columns`.
3. Drag `Profit → Rows`.
4. Create a calculated field named `Running Profit`.
5. Enter:

   ```text
   RUNNING_SUM(SUM([Profit]))
   ```

6. Create another calculated field named `Negative Profit`.
7. Enter:

   ```text
   -SUM([Profit])
   ```

8. Drag `Running Profit → Rows`.
9. Select **Gantt Bar** from the Marks Card.
10. Drag `Negative Profit → Marks: Size`.
11. Configure the table calculation to compute using Category.
12. Use Color to distinguish positive and negative values.

**Result:** A waterfall chart is created to show how values contribute to a cumulative total.

### (c) Build Sparklines for Trend Analysis

**Steps:**
1. Open a new worksheet.
2. Drag `Category → Rows`.
3. Drag `Order Date → Columns`.
4. Select Month or another suitable date level.
5. Drag `Sales → Rows`.
6. Select **Line** from the Marks Card.
7. Reduce row height and simplify the axes.
8. Remove unnecessary headers and gridlines.
9. Compare the compact trend lines across categories.

**Result:** Compact sparkline-style charts are created to show trends.

### (d) Implement Sheet Swapping for Dynamic Dashboards

**Steps:**
1. Create two worksheets named Sales Chart and Profit Chart.
2. Create a parameter named `Select View`.
3. Set the values to Sales and Profit.
4. Create a calculated field named `Show Sales`:

   ```text
   [Select View] = "Sales"
   ```

5. Drag `Show Sales → Filters` on the Sales worksheet and select True.
6. Create another calculated field named `Show Profit`:

   ```text
   [Select View] = "Profit"
   ```

7. Drag `Show Profit → Filters` on the Profit worksheet and select True.
8. Add both worksheets to the same dashboard area.
9. Right-click the parameter and select **Show Parameter**.
10. Change the parameter and verify that the displayed sheet changes.

**Result:** Sheet swapping is implemented to display different views dynamically.

### (e) Create Custom Geographic Territories

**Steps:**
1. Open a worksheet containing a geographic field such as State.
2. Right-click the geographic field.
3. Select **Create → Group**.
4. Select the states or locations that should form a territory.
5. Click Group.
6. Rename the group to a meaningful territory name.
7. Repeat for other territories.
8. Drag `State (Group) → Color`.
9. Drag `Sales → Size` or Color.
10. Review the map.

**Result:** Custom geographic territories are created and displayed on a map.

### (f) Use Background Images in Dashboards

**Steps:**
1. Open the dashboard.
2. Select the Image object from the Objects pane.
3. Browse and select the required image.
4. Drag `Image Object → Dashboard`.
5. Adjust its size and placement.
6. If using a worksheet background image, select **Map → Background Images** where appropriate.
7. Configure the image and required coordinates if applicable.
8. Check that the image does not hide important chart information.

**Result:** A background or dashboard image is added and positioned appropriately.

### (g) Apply Animation and Transparency Techniques

**Steps:**
1. Open the worksheet or dashboard.
2. To use animations, open **Format → Animations** if supported.
3. Enable animations and choose the required settings.
4. Change a filter or parameter to observe the transition.
5. Select a mark on the Marks Card to adjust transparency.
6. Click **Color**.
7. Adjust the Opacity slider.
8. Review the chart to ensure that marks remain visible.

**Result:** Supported animation and transparency settings are applied.

---

## Practical 12: Sharing, Publishing, and Presenting Data Visualizations

### Aim
To export, publish, and share Tableau visualizations with suitable access and interaction settings.

### (a) Export Dashboards as PDF/Image

**Export as PDF – Steps:**
1. Open the dashboard.
2. Select **File → Export as PDF**.
3. Choose the required paper size and orientation.
4. Select the required dashboard or sheets.
5. Click Export.
6. Choose the save location.

**Export as Image – Steps:**
1. Open the dashboard or worksheet.
2. Select the appropriate **Export → Image** option.
3. Select the required image settings.
4. Save the image file.

**Result:** The dashboard is exported as a PDF or image.

### (b) Use Presentation Mode in Tableau

**Steps:**
1. Open the completed dashboard.
2. Save the workbook.
3. Select **Presentation Mode** from the toolbar or Window menu, depending on the version.
4. Review the dashboard in full-screen mode.
5. Use filters and dashboard actions during the presentation.
6. Exit Presentation Mode when finished.

**Result:** The dashboard is displayed in Presentation Mode.

### (c) Publish Dashboards to Tableau Public

**Steps:**
1. Save the workbook.
2. Sign in to Tableau Public.
3. Select **Server → Tableau Public → Save to Tableau Public**.
4. Enter the required workbook name.
5. Wait for the publishing process to complete.
6. Open the published visualization in a browser.
7. Copy the public link if sharing is required.

**Result:** The dashboard is published to Tableau Public. Do not publish confidential data.

### (d) Share Dashboards via Tableau Server/Online

**Steps:**
1. Open the completed workbook.
2. Sign in to the organization's Tableau Server or Tableau Cloud site.
3. Select **Server → Publish Workbook**.
4. Choose the required project.
5. Enter the workbook name.
6. Configure data source and authentication options.
7. Click Publish.
8. Open the published workbook on the server or cloud site.

**Result:** The dashboard is published to Tableau Server or Tableau Cloud.

### (e) Enable User Interaction on Shared Dashboards

**Steps:**
1. Open the published dashboard.
2. Confirm that filters and dashboard actions are configured in the workbook.
3. Open the published view in a browser.
4. Test filters, tooltips, highlight actions, and filter actions.
5. Confirm that users can interact with the dashboard.
6. Republish the workbook if changes are required.

**Result:** Users can interact with the shared dashboard using the enabled controls.

### (f) Manage Permissions and Access Control

**Steps:**
1. Sign in to Tableau Server or Tableau Cloud.
2. Open the required project or workbook.
3. Select **Permissions**.
4. Review the available users and groups.
5. Assign suitable capabilities, such as View, Download, or Edit.
6. Save the permission changes.
7. Test access using an account with the appropriate role, if available.

**Result:** Access permissions are configured for the shared workbook.

### (g) Evaluate and Optimize Sharing Strategies

**Steps:**
1. Identify the intended audience of the dashboard.
2. Choose Tableau Public for public, non-confidential sharing.
3. Choose Tableau Server or Tableau Cloud for controlled organizational sharing.
4. Review workbook size and performance.
5. Use extracts or filters where suitable.
6. Check user permissions and data security.
7. Test the shared dashboard on the intended devices.
8. Confirm that the sharing method meets the audience's needs.

**Result:** A suitable sharing strategy is selected and optimized.

---

## Practical 13: Retail Sales & Profitability Dashboard

### Objective
Analyze sales, profit, and discount impact across regions.

### Aim
To build a retail dashboard that shows sales and profitability by region and category.

### (a) Build Bar, Line, and Map Visualizations

**Bar Chart – Steps:**
1. Open a new worksheet.
2. Drag `Category → Rows`.
3. Drag `Sales → Columns`.
4. Select Bar from the Marks Card.
5. Drag `Profit → Tooltip`.
6. Add the title **Sales by Category**.

**Line Chart – Steps:**
1. Open a new worksheet.
2. Drag `Order Date → Columns`.
3. Select Month or Year.
4. Drag `Sales → Rows`.
5. Select Line from the Marks Card.
6. Add the title **Sales Trend**.

**Map – Steps:**
1. Open a new worksheet.
2. Double-click `State`.
3. Drag `Sales → Color`.
4. Drag `Profit → Tooltip`.
5. Add the title **Regional Sales Map**.

**Result:** Bar, line, and map visualizations are created for retail analysis.

### (b) Use Calculated Fields (Profit Ratio)

**Steps:**
1. Select **Analysis → Create Calculated Field**.
2. Name the field `Profit Ratio`.
3. Enter:

   ```text
   SUM([Profit]) / SUM([Sales])
   ```

4. Click OK.
5. Drag `Profit Ratio → Marks: Label` or Tooltip.
6. Format the field as a percentage.

**Result:** Profit Ratio is calculated to measure profitability.

### (c) Apply Filters (Region, Category)

**Steps:**
1. Open the required worksheet or dashboard.
2. Drag `Region → Filters`.
3. Select the required regions and click OK.
4. Drag `Category → Filters`.
5. Select the required categories and click OK.
6. Open each filter menu and select **Show Filter**.
7. Apply the filters to relevant worksheets using **Apply to Worksheets**.
8. Test the filters.

**Result:** Region and Category filters are added to the analysis.

### (d) Create Interactive Dashboard

**Steps:**
1. Create the Bar Chart, Line Chart, and Map worksheets.
2. Click **New Dashboard**.
3. Drag `Bar Chart Worksheet → Dashboard`.
4. Drag `Line Chart Worksheet → Dashboard`.
5. Drag `Map Worksheet → Dashboard`.
6. Add Region and Category filter cards.
7. Select the map sheet menu and choose **Use as Filter**.
8. Arrange the charts and add a dashboard title.
9. Test the filters and map selections.
10. Save the dashboard.

**Result:** An interactive Retail Sales and Profitability Dashboard is created.

---

## Practical 14: Customer Segmentation & Behavior Analysis

### Objective
Identify customer segments based on purchasing patterns.

### Aim
To analyze customer purchasing behavior and identify high-value customer groups.

### (a) Use Clustering

**Steps:**
1. Open a new worksheet.
2. Drag `Sales → Columns`.
3. Drag `Profit → Rows`.
4. Drag `Customer Name → Detail`.
5. Open the Analytics Pane.
6. Drag **Cluster → View**.
7. Review the generated customer clusters.
8. Drag the Cluster field → Color if required.
9. Observe how customers are grouped.

**Result:** Customers are grouped into clusters based on purchasing measures.

### (b) Analyze Frequency, Recency, and Monetary Value (RFM)

**Steps:**
1. Identify the Customer ID, Order Date, Order ID, and Sales fields.
2. Select **Analysis → Create Calculated Field**.
3. Name the field `Frequency`.
4. Enter:

   ```text
   COUNTD([Order ID])
   ```

5. Create another calculated field named `Monetary Value`.
6. Enter:

   ```text
   SUM([Sales])
   ```

7. Create a calculated field named `Recency`.
8. Enter:

   ```text
   DATEDIFF('day', { FIXED : MAX([Order Date]) }, { FIXED [Customer Name] : MAX([Order Date]) })
   ```

9. Click OK after creating each calculation.
10. Drag `Customer Name → Rows`.
11. Add Frequency, Recency, and Monetary Value to the view.
12. Compare customers based on these three measures.

**Result:** Customer purchasing behavior is analyzed using Frequency, Recency, and Monetary Value. A lower Recency value indicates a more recent purchase relative to the dataset's latest order date.

### (c) Create Scatter Plots and Segmentation Dashboards

**Scatter Plot – Steps:**
1. Open a new worksheet.
2. Drag `Frequency → Columns`.
3. Drag `Monetary Value → Rows`.
4. Drag `Customer Name → Detail`.
5. Drag `Recency → Color` or Tooltip.
6. Select Circle from the Marks Card.
7. Review the customer distribution.

**Segmentation Dashboard – Steps:**
1. Create the scatter plot and customer summary worksheets.
2. Click **New Dashboard**.
3. Drag `Scatter Plot Worksheet → Dashboard`.
4. Drag `Customer Summary Worksheet → Dashboard`.
5. Add useful filters such as Region or Segment.
6. Add a title and arrange the views.

**Result:** A customer segmentation dashboard is created using scatter plots and summary views.

### (d) Highlight High-Value Customers

**Steps:**
1. Select **Analysis → Create Calculated Field**.
2. Name the field `Customer Value Group`.
3. Enter:

   ```text
   IF SUM([Sales]) >= 10000 THEN "High Value"
   ELSE "Regular"
   END
   ```

4. Click OK.
5. Adjust the threshold according to the dataset.
6. Drag `Customer Name → Rows`.
7. Drag `Sales → Columns`.
8. Drag `Customer Value Group → Color`.
9. Sort customers by Sales in descending order.
10. Add the view to the segmentation dashboard.

**Result:** High-value customers are highlighted using a calculated customer group.

---

## Practical 15: Sales Forecasting and Trend Analysis

### Objective
Predict future sales using historical data.

### Aim
To analyze historical sales, apply forecasting, and compare seasonal trends and moving averages.

### (a) Build Time-Series Charts

**Steps:**
1. Open a new worksheet.
2. Drag `Order Date → Columns`.
3. Select Month or another suitable date level.
4. Drag `Sales → Rows`.
5. Select Line from the Marks Card.
6. Drag `Category → Color` if category-wise comparison is required.
7. Add the title **Historical Sales Trend**.
8. Review the historical sales pattern.

**Result:** A time-series chart is created to display historical sales trends.

### (b) Apply Forecasting

**Steps:**
1. Open the time-series worksheet.
2. Confirm that `Order Date → Columns` and `Sales → Rows` are used.
3. Open the Analytics Pane.
4. Drag **Forecast → View**.
5. Review the forecasted period and prediction range.
6. Right-click the forecast area and select **Describe Forecast**.
7. Adjust forecast options if required.

**Result:** Future sales are forecast using historical data.

### (c) Compare Seasonal Trends

**Steps:**
1. Open a new worksheet.
2. Drag `Order Date → Columns`.
3. Select Month or Month of Year, depending on the analysis.
4. Drag `Sales → Rows`.
5. Drag `YEAR(Order Date) → Color` if comparing different years.
6. Select Line from the Marks Card.
7. Review repeated peaks and drops across months.
8. Add the title **Monthly Seasonal Sales Comparison**.

**Result:** Seasonal sales patterns are compared across time periods.

### (d) Use Moving Averages

**Steps:**
1. Open a worksheet.
2. Drag `Order Date → Columns`.
3. Select Month.
4. Drag `Sales → Rows`.
5. Open the Sales pill menu.
6. Select **Quick Table Calculation → Moving Average**.
7. Open **Edit Table Calculation** to configure the moving window if required.
8. Set the calculation to compute using the date field.
9. Review the smoothed sales trend.

**Result:** A moving average is applied to smooth short-term fluctuations and identify the overall sales trend.

---

# Conclusion

All 15 Tableau practicals cover data connection, data preparation, basic and advanced visualizations, calculations, table calculations, dashboard design, interactive dashboards, advanced analytics, Tableau Prep, publishing, customer segmentation, and sales forecasting.

These practicals provide hands-on experience in analyzing, visualizing, and presenting data using Tableau.
