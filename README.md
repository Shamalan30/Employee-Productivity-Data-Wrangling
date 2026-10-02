# 📊 Employee Productivity Data Wrangling & Exploratory Analysis

A Python-based **data wrangling and exploratory data analysis (EDA)** project that examines employee productivity in relation to **work preference, job satisfaction, tool proficiency, department, weekly working hours, and years of experience**.

The project uses a structured employee productivity dataset and applies **Pandas, Matplotlib, Seaborn, and Plotly** to summarize the data and visualize relationships between employee characteristics and productivity.

---

# 📌 Project Overview

This project explores an employee productivity dataset containing information about:

* Employee departments
* Gender
* Remote work preferences
* Weekly working hours
* Overtime frequency
* Tool proficiency
* Job satisfaction
* Years of experience
* Productivity scores

The analysis focuses on understanding how different workplace-related factors are associated with employee productivity.

The complete analysis is implemented in:

```text
Data_Wrangling.ipynb
```

---

# 🎯 Objectives

The main objectives of this project are to:

1. Load and inspect an employee productivity dataset.
2. Examine the structure and completeness of the dataset.
3. Compare productivity across different work preferences.
4. Compare average working hours across work preferences.
5. Examine job satisfaction levels across departments.
6. Visualize the relationship between work preference, satisfaction, and productivity.
7. Investigate the relationship between job satisfaction and productivity.
8. Investigate the relationship between tool proficiency and productivity.
9. Explore the relationship between years of experience and productivity.
10. Use interactive visualization to explore employee-level patterns.

---

# 🗂️ Dataset

The notebook loads an Excel file named:

```text
employee_productivity_dataset.xlsx
```

The dataset contains:

```text
550 employees
10 columns
```

The data is loaded using Pandas:

```python
df = pd.read_excel('/content/employee_productivity_dataset.xlsx')
```

---

# 📋 Dataset Variables

The dataset contains the following columns:

| Column                 | Description                           |
| ---------------------- | ------------------------------------- |
| `EmployeeID`           | Unique employee identifier            |
| `Department`           | Employee department                   |
| `Gender`               | Employee gender                       |
| `RemotePreference`     | Employee's preferred work arrangement |
| `WeeklyHours`          | Number of hours worked per week       |
| `OvertimeFreq`         | Frequency of overtime                 |
| `ToolProficiency`      | Employee tool proficiency level       |
| `JobSatisfactionLevel` | Employee job satisfaction level       |
| `YearsExperience`      | Years of professional experience      |
| `ProductivityScore`    | Employee productivity score           |

---

# 🔍 Initial Data Inspection

The notebook begins by inspecting the dataset using:

```python
df.info()
```

The dataset contains:

```text
550 rows
10 columns
```

The column data types are:

```text
3 integer columns
7 object columns
```

The integer variables are:

```text
WeeklyHours
YearsExperience
ProductivityScore
```

The remaining variables are categorical/object columns.

---

# 🧹 Missing Data

The initial dataset inspection shows that most columns contain 550 non-null values.

The exception is:

```text
JobSatisfactionLevel
```

which contains:

```text
540 non-null values
```

Therefore, the dataset contains:

```text
10 missing values
```

in `JobSatisfactionLevel`.

The notebook does not perform a missing-value imputation or deletion step. Instead, the available values are used directly in the subsequent analysis.

---

# 📈 Work Preference Analysis

The project groups employees according to:

```text
RemotePreference
```

The three work preferences represented in the dataset are:

* Hybrid
* Office
* Remote

For each category, the notebook calculates:

* Employee count
* Average productivity score
* Average weekly working hours

---

## Results

| Work Preference | Employee Count | Average Productivity Score | Average Weekly Hours |
| --------------- | -------------: | -------------------------: | -------------------: |
| Hybrid          |            171 |                      59.57 |                41.25 |
| Office          |            217 |                      54.79 |                41.11 |
| Remote          |            162 |                      59.21 |                40.88 |

These values describe the averages observed in this dataset.

The analysis does **not** establish that work preference causes changes in productivity.

---

# 🏢 Job Satisfaction by Department

The notebook uses a cross-tabulation to examine the distribution of job satisfaction levels across departments.

The satisfaction categories used are:

```text
Low
Medium
High
```

The analysis creates a stacked bar chart showing the number of employees at each satisfaction level within each department.

This allows the distribution of satisfaction levels to be compared across departments.

---

# 📊 Proportional Job Satisfaction Analysis

A second visualization normalizes the department-level satisfaction counts.

Instead of displaying the absolute number of employees, the chart displays the:

```text
Proportion of employees
```

for each satisfaction category within each department.

The resulting stacked bar chart contains:

```text
Low
Medium
High
```

This provides a proportional view of job satisfaction across departments.

---

# 💼 Work Preference, Satisfaction & Productivity

The project uses a Seaborn boxplot to examine:

```text
RemotePreference
        +
JobSatisfactionLevel
        ↓
ProductivityScore
```

The visualization places:

* Work preference on the x-axis
* Productivity score on the y-axis
* Job satisfaction level as the grouping variable

This allows productivity-score distributions to be examined across combinations of work preference and satisfaction level.

The boxplot can show differences in:

* Median productivity
* Distribution
* Spread
* Potential outliers

across the different groups.

---

# 😊 Job Satisfaction & Productivity

The notebook creates a bar chart comparing:

```text
JobSatisfactionLevel
```

against:

```text
ProductivityScore
```

The visualization calculates the average productivity score for each satisfaction category.

The categories are:

```text
Low
Medium
High
```

This allows the dataset's observed relationship between job satisfaction and average productivity to be examined visually.

---

# 🛠️ Tool Proficiency & Productivity

The project also examines:

```text
ToolProficiency
```

against:

```text
ProductivityScore
```

A bar chart is used to compare the average productivity score associated with the different tool-proficiency levels present in the dataset.

This provides a visual way to explore whether employees with different levels of tool proficiency have different average productivity scores in the dataset.

---

# 📚 Experience vs. Productivity

The final analysis uses an interactive Plotly scatter plot.

The visualization compares:

```text
YearsExperience
```

against:

```text
ProductivityScore
```

Employees are colored according to:

```text
RemotePreference
```

The interactive plot also provides additional information when hovering over data points:

```text
Department
JobSatisfactionLevel
```

This makes it possible to explore individual observations while examining the broader relationship between experience and productivity.

---

# 🖱️ Interactive Visualization

The Plotly visualization is designed to allow interactive exploration of the dataset.

Users can hover over individual observations to view:

* Years of experience
* Productivity score
* Remote preference
* Department
* Job satisfaction level

This provides more detailed exploration than a static chart.

---

# 🧰 Technologies Used

## Python

The project is implemented using Python.

## Pandas

Used for:

* Loading the Excel dataset
* Data inspection
* Grouping
* Aggregation
* Cross-tabulation

## Matplotlib

Used for:

* Bar charts
* Stacked bar charts
* Figure configuration
* Chart labeling

## Seaborn

Used for:

* Boxplots
* Statistical visualization
* Bar plots
* Improved visualization styling

## Plotly Express

Used for:

* Interactive scatter plots
* Hover information
* Interactive exploration

---

# 📦 Libraries

The notebook uses the following Python libraries:

```python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
import plotly.express as px
```

---

# ▶️ How to Run

## 1. Prepare the Dataset

Place the following Excel file in the expected notebook location:

```text
employee_productivity_dataset.xlsx
```

The notebook currently expects the file at:

```text
/content/employee_productivity_dataset.xlsx
```

This path is commonly used when running the notebook in Google Colab.

---

## 2. Open the Notebook

Open:

```text
Data_Wrangling.ipynb
```

using:

* Google Colab
* Jupyter Notebook
* JupyterLab
* VS Code with Jupyter support

---

## 3. Install Required Libraries

If the libraries are not already installed:

```bash
pip install pandas matplotlib seaborn plotly openpyxl
```

`openpyxl` is required for reading the Excel `.xlsx` file through Pandas.

---

## 4. Run the Notebook

Execute the notebook cells sequentially.

The notebook will:

```text
Load Excel Dataset
        ↓
Inspect Dataset
        ↓
Analyze Work Preferences
        ↓
Analyze Department Satisfaction
        ↓
Visualize Satisfaction Proportions
        ↓
Analyze Productivity Distributions
        ↓
Analyze Satisfaction vs Productivity
        ↓
Analyze Tool Proficiency vs Productivity
        ↓
Explore Experience vs Productivity
```

---

# 📁 Project Structure

A simple GitHub repository can be organized as:

```text
Employee-Productivity-Data-Wrangling/
│
├── Data_Wrangling.ipynb
├── employee_productivity_dataset.xlsx
└── README.md
```

If the dataset is not intended to be uploaded to GitHub, the repository can instead contain:

```text
Employee-Productivity-Data-Wrangling/
│
├── Data_Wrangling.ipynb
└── README.md
```

with instructions for obtaining the dataset separately.

---

# 📊 Analysis Workflow

The overall data analysis workflow is:

```text
                    Excel Dataset
                         │
                         ▼
                  Data Loading
                         │
                         ▼
                Data Inspection
                         │
                         ▼
            Data Structure Analysis
                         │
             ┌───────────┼───────────┐
             ▼           ▼           ▼
       Work Preference  Department  Employee
          Analysis     Satisfaction  Factors
             │           │           │
             ▼           ▼           ▼
       Productivity   Satisfaction  Experience
         & Hours      Distribution       │
             │           │           │
             └───────────┼───────────┘
                         ▼
                  Data Visualization
                         │
                         ▼
              Exploratory Insights
```

---

# 📌 Key Analysis Areas

The notebook focuses on five major relationships:

### 1. Work Preference → Productivity

Compares productivity across:

```text
Hybrid
Office
Remote
```

### 2. Department → Job Satisfaction

Examines:

```text
Low
Medium
High
```

satisfaction levels across departments.

### 3. Work Preference + Satisfaction → Productivity

Uses boxplots to examine productivity distributions across different combinations of work preference and job satisfaction.

### 4. Job Satisfaction → Productivity

Compares average productivity scores between satisfaction levels.

### 5. Experience → Productivity

Uses an interactive scatter plot to explore the relationship between years of experience and productivity.

---

# ⚠️ Data & Analysis Limitations

Several limitations should be considered when interpreting the analysis.

### Missing Values

There are 10 missing values in:

```text
JobSatisfactionLevel
```

The notebook does not explicitly impute or remove these values.

### Observational Analysis

The project explores relationships in the dataset. It does not establish causal relationships.

For example, an observed difference in productivity between remote and office employees does not by itself demonstrate that work preference caused the difference.

### Dataset Scope

The conclusions are based only on the employees represented in the provided dataset.

They should not automatically be generalized to all employees, organizations, industries, or geographic regions.

### No Predictive Model

This notebook is focused on:

```text
Data Wrangling
+
Exploratory Data Analysis
+
Visualization
```

It does not train a machine learning model or generate future productivity predictions.

---

# 🔬 Summary

This project demonstrates how Python-based data analysis can be used to explore employee productivity and workplace factors.

The analysis covers:

```text
Employee Data
      ↓
Work Preferences
      ↓
Working Hours
      ↓
Job Satisfaction
      ↓
Tool Proficiency
      ↓
Years of Experience
      ↓
Productivity
```

Through aggregation, cross-tabulation, statistical visualization, and interactive plotting, the notebook provides multiple perspectives on the relationships contained within the employee productivity dataset.

---

# 📈 Main Dataset Statistics

| Statistic                             | Value |
| ------------------------------------- | ----: |
| Total Employees                       |   550 |
| Total Variables                       |    10 |
| Numeric Variables                     |     3 |
| Categorical/Object Variables          |     7 |
| Missing `JobSatisfactionLevel` Values |    10 |
| Work Preference Categories            |     3 |
| Job Satisfaction Categories           |     3 |

---

# 👨‍💻 Author

**SHAMALAN A/L VELLU THAVAR**

**Matric Number:** A24AI0087

---

# 📜 License

No open-source license is currently specified for this project.

Unless a license is added to the repository, the project's source code remains under the author's default copyright rights.
