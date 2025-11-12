# Excel Salary Dashboard

![Salary Dashboard for Data Jobs.png](https://github.com/eldarhasanly/excel-projects/blob/master/salary-dashboard/img/1_Salary_Dashboard_Final_Dashboard.gif)

## Introduction

The purpose of this data jobs salary dashboard is to assist job searchers in researching salaries for positions they are interested in and making sure they are receiving fair compensation.

The data is from Luke Barousse's Excel course, which provides a foundation in analyzing data using this powerful tool. The data contains detailed information on job titles, salaries, locations, and essential skills that are presented here.

### Dashboard File
My final dashboard is in [Salary Dashboard for Data Jobs.xlsx](https://github.com/eldarhasanly/excel-projects/blob/master/salary-dashboard/Salary%20Dashboard%20for%20Data%20Jobs.xlsx).

### Excel Skills Used

The following Excel skills were utilized for analysis:

- **📉 Charts**
- **🧮 Formulas and Functions**
- **❎ Data Validation**

### Data Jobs Dataset

- Real-world data science job data from 2023 is included in the dataset utilized for this research. It contains comprehensive details about:

- **👨‍💼 Job titles**
- **💰 Salaries**
- **📍 Locations**
- **🛠️ Skills**

## Dashboard Build

### 📉 Charts

#### 📊 Data Science Job Salaries - Bar Chart

<img src="https://github.com/eldarhasanly/excel-projects/blob/master/salary-dashboard/img/1_Salary_Dashboard_Chart1.png" width="850" height="550" alt="Salary Dashboard Map Chart">

- 🛠️ **Excel Features:** Utilized bar chart feature (with formatted salary values) and optimized layout for clarity.
- 🎨 **Design Choice:** Horizontal bar chart for visual comparison of median salaries.
- 📉 **Data Organization:** Sorted job titles by descending salary for improved readability.
- 💡 **Insights Gained:** This enables quick identification of salary trends, noting that Senior roles and Engineers are higher-paying than Analyst roles.

#### 🗺️ Country Median Salaries - Map Chart

![Salary Dashboard Map Chart.png](https://github.com/eldarhasanly/excel-projects/blob/master/salary-dashboard/img/1_Salary_Dashboard_Country_Map.gif)

- 🛠️ **Excel Features:** Utilized Excel's map chart feature to plot median salaries globally.
- 🎨 **Design Choice:** Color-coded map to visually differentiate salary levels across regions.
- 📊 **Data Representation:** Plotted median salary for each country with available data.
- 👁️ **Visual Enhancement:** Improved readability and immediate understanding of geographic salary trends.
- 💡 **Insights Gained:** Enables quick grasp of global salary disparities and highlights high/low salary regions.

### 🧮 Formulas and Functions

#### 💰 Median Salary by Job Titles

```
=MEDIAN(
IF(
    (jobs[job_title_short]=A2)*
    (jobs[job_country]=country)*
    (ISNUMBER(SEARCH(type,jobs[job_schedule_type])))*
    (jobs[salary_year_avg]<>0),
    jobs[salary_year_avg]
)
)
```

- 🔍 **Multi-Criteria Filtering:** Checks job title, country, schedule type, and excludes blank salaries.
- 📊 **Array Formula:** Utilizes `MEDIAN()` function with nested `IF()` statement to analyze an array.
- 🎯 **Tailored Insights:** Provides specific salary information for job titles, regions, and schedule types.
- **🔢 Formula Purpose:** This formula populates the table below, returning the median salary based on job title, country, and type specified.

🍽️ Background Table

![Salary Dashboard Screenshot1.png](https://github.com/eldarhasanly/excel-projects/blob/master/salary-dashboard/img/1_Salary_Dashboard_Screenshot1.png)

📉 Dashboard Implementation

<img src="https://github.com/eldarhasanly/excel-projects/blob/master/salary-dashboard/img/1_Salary_Dashboard_Job_Title.png" width="400" height="500" alt="Salary Dashboard Title">

#### ⏰ Count of Job Schedule Type

```
=FILTER(J2#,(NOT(ISNUMBER(SEARCH("and",J2#))+ISNUMBER(SEARCH(",",J2#))))*(J2#<>0))
```

- 🔍 **Unique List Generation:** This Excel formula below employs the `FILTER()` function to exclude entries containing "and" or commas, and omit zero values.
- **🔢 Formula Purpose:** This formula populates the table below, which gives us a list of unique job schedule types.

🍽️ Background Table

![1_Salary_Dashboard_Type.png](https://github.com/eldarhasanly/excel-projects/blob/master/salary-dashboard/img/1_Salary_Dashboard_Screenshot2.png)

📉 Dashboard Implementation:

<img src="https://github.com/eldarhasanly/excel-projects/blob/master/salary-dashboard/img/1_Salary_Dashboard_Type.png" width="350" height="500" alt="Salary Dashboard Type">

### ❎ Data Validation

#### 🔍 Filtered List

- 🔒 **Enhanced Data Validation:** Implementing the filtered list as a data validation rule under the `Job Title`, `Country`, and `Type` option in the Data tab ensures:
    - 🎯 User input is restricted to predefined, validated schedule types
    - 🚫 Incorrect or inconsistent entries are prevented
    - 👥 Overall usability of the dashboard is enhanced

<img src="https://github.com/eldarhasanly/excel-projects/blob/master/salary-dashboard/img/1_Salary_Dashboard_Data_Validation.gif" width="425" height="400" alt="Salary Dashboard Data Validation">

## Conclusion

I created this dashboard to provide insights into compensation trends for a variety of data-related job titles. This dashboard enables users to make well-informed decisions about their career pathways by utilizing our data and investigating the features to determine how job type and location affect pay. 
