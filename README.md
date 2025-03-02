# Aviation KPI Data Science Project

## 1. Machine Learning Phase (ML_Phase)
### Purpose:
To develop a predictive model for analyzing key aviation performance metrics and optimizing operational efficiency.

### Key Steps:
#### Feature Engineering:
- Processed raw aviation KPI data to extract meaningful features (e.g., flight delays, turnaround time, fleet utilization).
- Standardized and normalized numerical variables for improved model performance.

#### Model Selection:
- **Ridge Regression** was chosen due to its ability to handle multicollinearity and prevent overfitting by imposing an L2 regularization penalty.
- **Why not Linear Regression?**
  - The dataset exhibited multicollinearity among features such as fuel efficiency, turnaround time, and aircraft utilization.
  - Ridge Regression mitigates this issue by shrinking coefficients, leading to a more stable model.
- **Why not Logistic Regression?**
  - Logistic Regression is suitable for classification tasks, whereas this project required predicting continuous variables (e.g., revenue, cost, profit).

#### Hyperparameter Tuning:
- GridSearchCV was employed to find the optimal alpha parameter for Ridge Regression, balancing bias and variance.

#### Evaluation Metrics:
- Used **Mean Squared Error (MSE)** and **R-squared** to measure model accuracy and explanatory power.
- Ridge Regression provided better generalization compared to a standard linear regression model.

### Output:
- A robust predictive model capable of estimating key aviation performance indicators such as revenue, operating costs, and net profit margins.

---

## 2. Data Cleaning Phase (Cleaning_Phase)
### Purpose:
To ensure high-quality data by handling inconsistencies, outliers, and missing values.

### Key Steps:
#### Outlier Detection:
- Applied statistical methods (e.g., IQR, Z-score) to identify and remove anomalies in fuel efficiency, fleet utilization, and delay times.

#### Missing Data Handling:
- Imputed missing values using:
  - **Mean/Median** for numerical variables (e.g., turnaround time, aircraft utilization).
  - **Mode** for categorical variables (e.g., airline, aircraft type).

### Tools Used:
- **pandas, numpy**

### Output:
- A clean dataset prepared for machine learning and SQL integration.

---

## 3. SQL Phase
### Purpose:
To integrate MySQL for structured querying and analysis of aviation KPIs.

### Key Steps:
#### Data Extraction:
- Imported the cleaned dataset into MySQL for structured storage.

#### Data Aggregation:
- Utilized **GROUP BY, SUM, AVG** to calculate:
  - Average turnaround time per airline
  - Total revenue and cost per flight
  - Monthly profitability trends

#### Filters:
- Applied **WHERE and HAVING** clauses to filter for high-revenue flights, significant delays, and fleet performance.

#### Database Creation:
- Created a relational database to store flight details, revenue, costs, and delay statistics.

### Output:
- Well-structured MySQL tables ready for analysis and visualization.

---

## 4. Power BI Visualization Phase
### Purpose:
To create interactive dashboards for data-driven decision-making.

### Key Insights Extracted:
- **Total Profit:** 1.03bn USD
- **Total Flights Analyzed:** 200,000
- **Total Revenue:** 5.11bn USD
- **Average Delay:** 59.36 minutes
- **Fleet Utilization Rate:** 12.00%

### Key Visualizations:
- **Flight Delays Analysis:** Breakdown of major, minor, and on-time flights.
- **Daily Trends:** Delay variations by time of day.
- **Revenue and Cost Insights:** Comparison of operating costs and revenue across different efficiency levels.
- **Financial Performance Breakdown:** Profitability trends and revenue contribution by flight.
- **Monthly Profitability Trends:** Visualization of revenue vs. cost per month.

### Interactivity:
- Added **slicers and filters** to explore data dynamically.

### Output:
- A **Power BI dashboard** that provides a comprehensive analysis of aviation KPIs.

---

## General Notes:
- The project workflow is modular, enabling iterative improvements.
- **Tools Used:** Python (pandas, seaborn, sklearn), MySQL, Power BI
- **Key Focus:** Delivering actionable insights aligned with business goals.

