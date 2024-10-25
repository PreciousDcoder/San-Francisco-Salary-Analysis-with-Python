# San-Francisco-Salary-Analysis-with-Python

# Project Overview

This project analyzes employee salary data from the San Francisco Agency, focusing on key aspects like BasePay, TotalPay, and employee work status. The primary objectives include cleaning and transforming the dataset, handling missing values, and conducting exploratory data analysis (EDA) to uncover trends and relationships within the data.

### Data Analyst Project (2): Salaries Analysis of San Francisco Agency

**Language**: Python  
**Environment**: Jupyter Notebook

---

### Overview

This project focuses on analyzing the salaries of San Francisco Agency employees using Python. The analysis involves handling missing data, performing transformations for scaling, and exploring relationships between different variables within the dataset.

---

### Key Libraries Used

- **SciPy** (`scipy.stats`) – For statistical operations.
- **Statsmodels** (`statsmodels.tsa.seasonal` and `statsmodels.api`) – For time series decomposition and regression analysis.

---

### Key Data Processing Techniques

1. **Handling Missing Values**:  
   - Missing values in the `Status` column were handled based on the following rule:  
     If `BasePay` > `BasePayMean`, then `Status = FT (Full-Time)`.  
     If `BasePay` < `BasePayMean`, then `Status = PT (Part-Time)`.

2. **Data Transformation**:
   - **Box-Cox Transformation** and **Log Transformation** were applied for scaling data.
   - **Data Validation**: `.unique()` was used to validate unique values.
   - **Cleaning Invalid Characters**: `.abs()` was used to eliminate non-numeric characters (e.g., negative signs).
   - **Type Conversion**: `.astype()` was used to ensure proper data types.
   - **Handling Missing Values**: `.fillna()` was employed to fill missing values.
   - **Data Merging**: `.join()` was used to combine DataFrames.
   - **Column Extraction**: `.select_dtypes()` helped in selecting specific data types.
   - **DataFrame Manipulation**: `.pop()` was used to manipulate columns within the DataFrame.

---

### Visualizations Employed

- **Box Plot**  
- **Line Chart**  
- **Histogram**  
- **Heatmap**  
- **Histogram with Rug Plot**  
- **Scatter Plot**  
- **Pie Chart**  
- **Decomposition Plot** (for time series analysis)

---

### Data Cleaning Process

- Irrelevant columns (`Id`, `Notes`) were dropped.
- Data types were handled correctly to ensure consistency.
- Negative and non-numerical characters were removed from numeric columns.
- Missing values were filled, and outliers were handled using the Interquartile Range (IQR) method with a threshold of 1.2.

---

### Data Transformation

- Data validation steps were implemented to ensure consistency and reliability of the analysis.

---

### Exploratory Data Analysis (EDA)

#### Univariate Analysis

- Initial analysis focused on summarizing individual variables to understand their distributions.

#### Key Findings:

- **Bivariate Analysis**:
  - A significant relationship (correlation = 0.99) was found between **BasePay** and **TotalPay**. This indicates that an increase in BasePay results in a corresponding increase in TotalPay.

- **Employee Status Distribution**:
  - 60.3% of employees were classified as **Part-Time (PT)**, and 39.7% as **Full-Time (FT)**. The missing values in the `Status` column were filled based on the rule that employees with BasePay above the mean were classified as FT, and those below were classified as PT.

#### Implications:
- The higher proportion of part-time employees suggests a workforce that emphasizes flexibility, managing fluctuating workloads or seasonal operations. This could also indicate differences in employee benefits, work hours, and overall compensation structures compared to full-time staff. Additionally, this distribution may reflect broader labor market trends, such as increased demand for part-time workers or changes in company policies regarding full-time employment.

#### Multivariate Analysis

- **Top 5 Employees with Highest BasePay**:
  The following employees had the highest BasePay:

  | Employee Name   | BasePay    | Year       |
  |-----------------|------------|------------|
  | Dana Nelson     | 155,936.00 | 2013-01-01 |
  | Diane Lim       | 155,934.26 | 2013-01-01 |
  | Andrew Yick     | 155,858.06 | 2011-01-01 |
  | Michael Berg    | 155,858.06 | 2011-01-01 |
  | Ramon Garcia    | 155,818.52 | 2012-01-01 |

- **Salary Trend**:
  - Average BasePay showed an upward trend from 2011 to 2013, indicating salary growth. However, the drop in 2014 raises concerns about salary stability during this period and may point to economic shifts or changes within the agency’s pay structure.


