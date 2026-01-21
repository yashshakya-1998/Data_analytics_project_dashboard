# Project 2 - analysis
## 📢 Introduction
I’ve always been surprised by the lack of data exploring the most optimal jobs and skills in the data science market. I set out to understand what skills top employers request and how to land more pay.
### ⚡ Questions to Analyze
To understand the data science job market, I asked the following:
1. Which are tha top 10 skills in data science jobs?
2. What is the approximate skill per job required data science jobs?
3. Whats the data science salary bucket with different regions?
4. Which are the top 10 sites to look for data science jobs?
### 🔑 Excels skills used
- Pivot charts
- Pivot tables
- Power query
- Power pivot
- DAX( Data analysis expression)
### 📊 Data jobs dataset
The dataset used for this project contains real-world data science job information from 2023. The dataset file is available in dataset folder.
It includes detailed information on:
1. Job titles
2. Salary
3. Job posted date
4. Job schedule type (eg: Full-time, Part-time, Internship, etc)
5. Job via (eg: linkedin, indeed, upwork, etc)
## 1️⃣ Which are the top 10 skills in data science jobs?
### 🔍 Skill: Powerquery & Pivotchart & DAX

📥 **Extract**
- Firstly I extracted the skill data with job index from the main data salary datset.
  - first query with all the data info
  - second query with all the skills and job id

🔄 **Transform**
- i cleaned up the job skill column form square brackets and apostrophe
- then i used the split transformation by splitting that job skill column.

   - **data jobs salary**
     
     <img width="200" height="300" alt="6" src="https://github.com/user-attachments/assets/95dfaf80-24b0-4d3c-8406-3f31367a6dd0" />

   - **data jobs skill**
  
       <img width="200" height="300" alt="7" src="https://github.com/user-attachments/assets/e3256b53-7c4d-49d5-8795-741722be7d1b" />


🔗 **Load**
- Finally, I loaded both transformed queries into the workbook, setting the foundation for my subsequent analysis.
  - **data jobs salary all**
  
    <img width="1920" height="1080" alt="Screenshot (1008)" src="https://github.com/user-attachments/assets/b044983a-d553-4bd4-b748-30b086c861b7" />
  - **data jobs skill**
  
    <img width="1920" height="1080" alt="Screenshot (1009)" src="https://github.com/user-attachments/assets/38f4d799-44cd-4dfe-9ac1-95e64bb5ec01" />

🔗 **Measures**
- I created a new measure Median salary - skill to create a new relationship between queries
  - data jobs salary &
  - job skill
- using CROSSFILTER( ) and CALCULATE( )
```
=CALCULATE(
          [Median salary],
          CROSSFILTER(data_jobs_salary[job_id],
                      data_jobs_skill[job_id],
                      Both
                      )
          )

```
- **data model showcase**

<img width="500" height="500" alt="12" src="https://github.com/user-attachments/assets/0956c97e-7e4c-447b-bae8-dfab9ae3cffa" />


### 📊 Analysis
💡 **Insights**
- 🔨 I created a combo pivot chart
  - left axis of median salary
  - right axis of skill likelihood
- 📧 As we can see for all the jobs postings spark and aws were the highest paying skills.
- 🎯 Also by the likelihood of skills sql and python were the most in demand skills.
  
  <img width="250" height="200" alt="9" src="https://github.com/user-attachments/assets/a3741a97-a744-4252-8b6a-96da828cd901" />
  <img width="700" height="389" alt="8" src="https://github.com/user-attachments/assets/f17a1565-7c79-4b3d-964f-d7231720d343" />

🤔 **Result**
- This trend emphasizes the value of acquiring multiple relevant skills, particularly for individuals aiming for higher-paying roles.
## 2️⃣ What is the approximate skill per job required data science jobs?
### 🧮 Skills: Pivottable
📈 **Pivot Table**
- using the same queries i created a pivot table by job title in rows and median salary and skill per job as values in rows.
📈 **DAX**
- to calculate skill per job
  - I used DAX to create a new measures.
  - skill per job = (skill count/job count)

```
  ## Job count

  =COUNT(data_jobs_salary[job_id])

  ## Skill count

  =COUNT(data_jobs_skill[job_id])

  ## Skill per job

  =DIVIDE([Skill Count],[Job count])
```
### 📊 Analysis
💡 **Insights**
- 📈 There is a positive correlation between the number of skills requested in job postings and the median salary, particularly in roles like Senior Data Engineer and Data Scientist.
- 💼 Roles that require fewer skills, like Business Analyst, tend to offer lower salaries, suggesting that more specialized skill sets command higher market value.
  <img width="1520" height="644" alt="10" src="https://github.com/user-attachments/assets/22eff91d-525f-4ae1-acd2-0855ac845396" />

🤔 **Result**
- This trend emphasizes the value of acquiring multiple relevant skills, particularly for individuals aiming for higher-paying roles.
## 3️⃣ Whats the data science salary bucket with different regions?
### 🧮 Skills: DAX & Pivot table
- Job roles are grouped into salary buckets using median salary values.  
- This simplifies comparison across experience levels.

🧮 **Salary Buckets**
- **< $100,000** → Fresher / Starter Salary  
- **< $130,000** → Intermediate / Satisfactory Salary  
- **> $130,000** → Experienced / Advanced Salary  

🌍 **Interactivity**
- A country slicer allows filtering salaries by location.
- Salary buckets update dynamically based on selection.

📚 **advanced DAX formula used**
  - IF( )
  - SWITCH( )

```

### IF()

=IF([Median salary]<100000,"Fresher salary",
 IF([Median salary]<130000,"Intermediate salary",
 "Experienced salary"))

### SWITCH()

=SWITCH(
        TRUE(),
        [Median salary]<100000,"Starter Salary",
        [Median salary]<130000,"Satisfactory Salary",
        [Median salary]>130000,"Advanced Salary"
        )

```
### 📊 Analysis
💡 **Insights**
- 📑 Higher seniority leads to higher pay.
- 💴 Specialized roles earn more than analyst roles.
- ✒️ Salary bucketing improves readability and decision-making.
<img width="500" height="450" alt="11" src="https://github.com/user-attachments/assets/043a16c9-a0d1-4810-afe5-70d3421b803a" />

🤔 **Result**
- These salary insights are important for planning and salary negotiations, helping professionals and companies align their offers with market standards while considering geographical variations.
## 4️⃣ Which are the top 10 sites to look for Data Science jobs?

### 🧮 Skills Used
- Advanced Pivot Tables
- Advanced DAX calculations

---

### 📈 Pivot Table
- Created a pivot table with **Job Site** as rows.
- Used **Median Salary** as values.
- Included **Job Count** for comparison.

---

### 📈 Advanced DAX
- Created two custom measures using `CALCULATE()`:
  - 🏡 Median salary for Work From Home jobs
  - 🏦 Median salary for Office-based jobs

```DAX

### Median salary for WFH jobs

Median salary WFH jobs:=
CALCULATE(
    [Median Salary],
    data_jobs_salary[job_work_from_home] = TRUE
)

### Median salary for Office jobs

Median Salary Office :=
CALCULATE(
    [Median Salary],
    data_jobs_salary[job_work_from_home] = FALSE
)

```
### 📊 Analysis

💡 **Insights**
- 💰 LinkedIn offers the highest median salary among all platforms.
- 📈 Indeed and LinkedIn have the highest number of job listings.
- ‼️ High salary does not always correlate with high job availability.
- 😎 Combining high-paying and high-volume platforms improves job search outcomes.
<img width="1466" height="454" alt="13" src="https://github.com/user-attachments/assets/6f9dabce-94f7-41ba-a10a-3990c9066a79" />

## 🧾 Conclusion

This Excel-based project explores key trends in the data science job market using real-world job posting data.  
The analysis covers job titles, salaries, locations, and required skills.

Using Excel features such as **Power Query**, **PivotTables**, **DAX**, and **charts**, the project reveals strong links between higher salaries and in-demand skills, especially **Python**, **SQL**, and **cloud technologies**.

This dashboard is intended to guide data professionals in understanding market demand and identifying skills associated with higher-paying roles.
