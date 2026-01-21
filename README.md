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






 
