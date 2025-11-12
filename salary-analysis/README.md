# Project 2 Analysis

## Introduction

As a current job seeker, I’m struck by the scarcity of information regarding the best jobs and skills in the data science field. I aimed to investigate the skills that leading employers seek and how to achieve a better salary.

### Questions to Analyze

To understand the data science job market, I asked the following:

1. **Do more skills get you better pay?**
2. **What’s the salary for data jobs in different regions?**
3. **What are the top skills of data professionals?**
4. **What’s the pay for the top 10 skills?**

### Excel Skills Used

The following Excel skills were utilized for analysis:

- **📊 Pivot Tables**
- **📈 Pivot Charts**
- **🧮 DAX (Data Analysis Expressions)**
- **🔍 Power Query**
- **💪 Power Pivot**

### Data Jobs Dataset

The data is from Luke Barousse's Excel course, which provides a foundation in analyzing data using this powerful tool. The data contains detailed information on job titles, salaries, locations, and essential skills that are presented here.

It includes detailed information on:

- **👨‍💼 Job titles**
- **💰 Salaries**
- **📍 Locations**
- **🛠️ Skills**

## 1️⃣ Do more skills get you better pay?

### 🔍 Skill: Power Query (ETL)

#### 📥 Extract

- Firstly, I utilized Power Query to extract the original data (`data_salary_all.xlsx`) and create two queries:
    - 🗃️ First one with all the data jobs information.
    - 🔧 The second listing the skills for each job ID.

#### 🔄 Transform

- Afterwards, I transformed each query by changing column types, removing unnecessary columns, cleaning text to eliminate specific words, and trimming excess whitespace.
    - 📊 data_jobs_all

        ![Project Analysis Screenshot1.png](https://github.com/eldarhasanly/excel-projects/blob/master/salary-analysis/img/2_Project_Analysis_Screenshot1.png)

    - 🛠️ data_job_skills

        ![Project Analysis Screenshot2.png](https://github.com/eldarhasanly/excel-projects/blob/master/salary-analysis/img/2_Project_Analysis_Screenshot2.png)

#### 🔗 Load

- Finally, I loaded both transformed queries into the workbook, setting the foundation for my subsequent analysis.
    - 📊 data_jobs_all

        ![Project Analysis Screenshot3.png](https://github.com/eldarhasanly/excel-projects/blob/master/salary-analysis/img/2_Project_Analysis_Screenshot3.png)

    - 🛠️ data_job_skills

        ![Project Analysis Screenshot4.png](https://github.com/eldarhasanly/excel-projects/blob/master/salary-analysis/img/2_Project_Analysis_Screenshot4.png)

### 📊 Analysis

#### 💡 Insights

- 📈 There is a positive correlation between the number of skills requested in job postings and the median salary, particularly in roles like Senior Data Engineer and Data Scientist.
- 💼 Roles that require fewer skills, like Business Analyst, tend to offer lower salaries, suggesting that more specialized skill sets command higher market value.

    ![Project Analysis Chart1.png](https://github.com/eldarhasanly/excel-projects/blob/master/salary-analysis/img/2_Project_Analysis_Chart1.png)

#### 🤔 So What

- This trend emphasizes the value of acquiring multiple relevant skills, particularly for individuals aiming for higher-paying roles.

## 2️⃣ What’s the salary for data jobs in different regions?

### 🧮 Skills: PivotTables & DAX

#### 📈Pivot Table

- 🔢 I created a PivotTable using the Data Model I created with Power Pivot.
- 📊 I moved the `job_title_short` to the rows area and `salary_year_avg` into the values area.
- 🧮 Then, I added new measure to calculate the median salary for US jobs.
    ```
    =CALCULATE(
        MEDIAN(data_jobs_all[salary_year_avg]),
        data_jobs_all[job_country] = "United States")
    ```

#### 🧮 DAX

- To calculate the median year salary I used DAX.

    ```
    Median Salary := MEDIAN(data_jobs_all[salary_year_avg])
    ```

### 📊 Analysis

#### 💡 Insights

- 💼 Job roles like Senior Data Engineer and Data Scientist command higher median salaries both in the US and internationally, showcasing the global demand for high-level data expertise.
- 💰 The salary disparity between US and Non-US roles is particularly notable in high-tech jobs, which might be influenced by the concentration of tech industries in the US.

    ![Project Analysis Chart2.png](https://github.com/eldarhasanly/excel-projects/blob/master/salary-analysis/img/2_Project_Analysis_Chart2.png)

#### **🤔 So What**

Understanding salary trends is essential for effective planning and negotiations. It helps both professionals and organizations align their compensation offers with industry benchmarks, taking into account differences based on location.

## 3️⃣ What are the top skills of data professionals?

### 🔧 Skill: Power Pivot

#### 💪 Power Pivot

- 🔗 I created a data model by integrating the `data_jobs_all` and `data_jobs_skills` tables into one model.
- 🧹 Since I had already cleaned the data using Power Query; Power Pivot created a relationship between these two tables.

#### 🔗 Data Model

- I created a relationship between my two tables using the `job_id` column.

    ![Project Analysis Screenshot5.png](https://github.com/eldarhasanly/excel-projects/blob/master/salary-analysis/img/2_Project_Analysis_Screenshot5.png)

#### 📃 Power Pivot Menu

- The Power Pivot menu was used to refine my data model and makes it easy to create measures.

    ![Project Analysis Screenshot6.png](https://github.com/eldarhasanly/excel-projects/blob/master/salary-analysis/img/2_Project_Analysis_Screenshot6.png)

### 📊Analysis

#### 💡Insights

- 💻 SQL and Python dominate as top skills in data-related jobs, reflecting their foundational role in data processing and analysis.
- ☁️ Emerging technologies like AWS and Azure also show significant presence, underlining the industry's shift towards cloud services and big data technologies.

    ![Project Analysis Chart3.png](https://github.com/eldarhasanly/excel-projects/blob/master/salary-analysis/img/2_Project_Analysis_Chart3.png)

#### 🤔So What

Recognizing key skills in the industry helps professionals remain competitive and informs training and educational programs to emphasize impactful technologies.

## 4️⃣ What’s the pay of the top 10 skills?

### 📊 Skill: Advanced Charts (Pivot Chart)

#### 📈 PivotChart

- I created a combo PivotChart to plot median salary and skill likelihood (%) from my PivotTable.
    - 🪙 **Primary Axis:** Median Salary (as a Clustered Column)
    - 👍 **Secondary Axis:** Skill Likelihood (as a Line with Markers)
- To customize the chart, I added a title axis title, removed the lines (skill likelihood), and changed the markers to diamonds.

### 📊 Analysis

#### 💡Insights

- 💰 Higher median salaries are associated with skills like Python, Oracle, and SQL, suggesting their critical role in high-paying tech jobs.
- 📉 Skills like PowerPoint and Word have the lowest median salaries and likelihood, indicating less specialization and demand in high-salary sectors.

    ![Project Analysis Chart4.png](https://github.com/eldarhasanly/excel-projects/blob/master/salary-analysis/img/2_Project_Analysis_Chart4.png)

### 🤔So What

- This chart emphasizes the significance of dedicating time to learn high-value skills like Python and SQL, which are clearly linked to higher-paying positions, particularly for individuals aiming to enhance their earnings in the tech sector.

## Conclusion

As a data enthusiast and job seeker, I embarked on an Excel-based project to gain valuable insights into the data science job market. I used a curated dataset from real-world job postings to analyze job titles, salaries, locations, and essential skills. By leveraging Excel features such as Power Query, PivotTables, DAX, and charts, I uncovered important correlations between various skills and higher salaries, particularly in Python, SQL, and cloud technologies.

I aim for this project to be a practical guide for data professionals, outlining the necessary skills for obtaining higher-paying roles.
