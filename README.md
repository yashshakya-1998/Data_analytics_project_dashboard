# Data Analytics Project on Data Science job Dashboard
https://github.com/user-attachments/assets/c7b8a528-208f-4cb5-8daa-ed2baea0b354

## Introduction

This Data Jobs Salary Dashboard is designed to help job seekers explore salary trends across different roles and assess whether they are being fairly compensated.

The dataset comes from my Excel course, which focuses on building a strong foundation in data analysis. It includes detailed information on job titles, salary ranges, locations, and key skills, all of which are visualized in this dashboard.

### Dashboard File
📊 [Download the Excel file](data/data_jobs_salary_dashboard.xlsx)

## 🛠️ Excel Skills Used
The following Excel features were applied to analyze and visualize the data:

- 📉 Charts for trend and comparison analysis  
- 🧮 Formulas and functions for calculations and insights  
- ❎ Data validation to ensure data accuracy and consistency  

## 📊 Data Jobs Dataset
This project uses a real-world dataset containing data science job information from **2023**. The dataset is sourced from my **Excel course**, which focuses on building a strong foundation in data analysis using Excel.

The dataset includes detailed information on:
- 👨‍💼 Job titles  
- 💰 Salary data  
- 📍 Job locations  
- 🛠️ Required skills  

## 📈 Dashboard Build

### 📉 Charts
- 📊 **Data Science Job Salaries** – Bar chart for comparing salary ranges across roles
<img width="873" height="412" alt="Capture" src="https://github.com/user-attachments/assets/982669a3-622c-48e3-80d1-1a7df96d9024" />

### 📊 Chart Details

- 🛠️ **Excel Features:** Used bar chart functionality with formatted salary values and an optimized layout for improved clarity.
- 🎨 **Design Choice:** Implemented a horizontal bar chart to allow easy visual comparison of median salaries.
- 📉 **Data Organization:** Sorted job titles in descending order of salary to enhance readability.
- 💡 **Insights Gained:** The chart highlights clear salary trends, showing that senior-level roles and engineering positions tend to offer higher compensation compared to analyst roles.

 ###  📦 Formula and Functions used
  💲 Median Salary by Job titles
```

=MEDIAN(
        IF(
           (DScJobs[job_title_short]='median salary '!$L4)*
           (DScJobs[salary_year_avg]<>0)*
           (DScJobs[job_country]=country)*
           (ISNUMBER(SEARCH(type,DScJobs[job_schedule_type]))
          ),
        DScJobs[salary_year_avg]))

```
-  🔨 **Multi criteria fiter:** Checks for job titles,saalary whether its empty or not, job country and job schedule type.
-  🔩  **Array formula:** Uses MEDIAN() with nested IF() statement to analyse the statement.
-  📝 **Tailored Insights:** Summarizes specific salary info according to job titles, job type and job country.
-  🎯 **formula purpose:** This formula populates the table below, returning the median salary based on job title, country, and type specified.

📖 Table overview
 
 <img width="300" height="220" alt="1" src="https://github.com/user-attachments/assets/94507938-fd0e-4df4-b479-4bf07b9c1e05" />

📜 Dashboard overview

<img width="400" height="450" alt="2" src="https://github.com/user-attachments/assets/506d3279-a4b1-4ac9-aadc-fedc5acd955d" />


⌚ **Unique Job Schedule Type** 

```
=UNIQUE(DScJobs[job_schedule_type])

```

📊 Table overview

<img width="180" height="420" alt="3" src="https://github.com/user-attachments/assets/6a9f8300-1df2-4756-bdda-698988970e1f" />

```

=FILTER(P2#,NOT(ISNUMBER(SEARCH("and",P2#)))*(P2#<>0))

```

👀 Explanation

- P2# refers to a dynamic array spilled from cell P2.
- SEARCH("and", P2#) checks each value in the array for the word "and".
- ISNUMBER(...) returns TRUE if the word "and" is found.
- NOT(...) excludes any values that contain the word "and".
- (P2# <> 0) removes zero values from the results.
- FILTER(...) returns only the values that do not contain "and" and are not equal to zero.

```

=SORT(FILTER(Q2:R6,ISNUMBER(R2:R6)),2,-1)

```
👀 Explanation

- Q2:R6 is the data range being analyzed (two columns of related data).
- ISNUMBER(R2:R6) checks which cells in column R contain numeric values.
- FILTER(Q2:R6, ...) keeps only the rows where column R has valid numbers.
- SORT(..., 2, -1) sorts the filtered data:
- 2 → sorts by the second column (column R)
- 1 → sorts values in descending order



📊 Table overview

<img width="330" height="120" alt="4" src="https://github.com/user-attachments/assets/81c18d1a-067a-4e2e-b701-464ae9303267" />

📰  Dashboard overview

<img width="500" height="450" alt="5" src="https://github.com/user-attachments/assets/768795ad-8679-4cb3-8245-f2c61a75cc42" />


### 🔍 Filtered List & Data Validation

- 🔒 **Enhanced Data Validation:** The filtered list is applied as a data validation rule for the **Job Title**, **Country**, and **Type** fields using Excel’s Data Validation feature.
- 🎯 **Controlled Input:** Restricts user selections to predefined, validated options only.
- 🚫 **Error Prevention:** Prevents incorrect or inconsistent data entries.
- 👥 **Improved Usability:** Enhances the overall user experience and reliability of the dashboard.

## 🧾 Conclusion

This dashboard was created to highlight key salary trends across a range of data-related job roles. Using data sourced from my Excel course, the dashboard enables users to explore and compare compensation patterns with confidence.

By interacting with the dashboard, users can better understand how factors such as **job title**, **location**, and **employment type** influence salary levels, supporting more informed career decisions.
