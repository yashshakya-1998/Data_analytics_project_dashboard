# Project 2 - analysis
## Introduction
I’ve always been surprised by the lack of data exploring the most optimal jobs and skills in the data science market. I set out to understand what skills top employers request and how to land more pay.
### Questions to Analyze
To understand the data science job market, I asked the following:
1. Which are tha top 10 skills in data science jobs?
2. What is the approximate skill per job required data science jobs?
3. Whats the data science job trend with different regions?
4. Which arethe top 10 sites to look for data science jobs?
### Excels skills used
- Pivot charts
- Pivot tables
- Power query
- Power pivot
- DAX( Data analysis expression)
### Data jobs dataset
The dataset used for this project contains real-world data science job information from 2023. The dataset file is available in dataset folder.
It includes detailed information on:
1. Job titles
2. Salary
3. Job posted date
4. Job schedule type (eg: Full-time, Part-time, Internship, etc)
5. Job via (eg: linkedin, indeed, upwork, etc)
## Which are the top 10 skills in data science jobs?
### 🔍 Skill: Power Query (ETL)

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

### 📊 Analysis
💡 **Insights**
- As we can see for all the jobs postings spark and aws were the highest paying skills.
- Also by the likelihood of skills sql and python were the most in demand skills.
  
  <img width="250" height="200" alt="9" src="https://github.com/user-attachments/assets/a3741a97-a744-4252-8b6a-96da828cd901" />
  <img width="700" height="389" alt="8" src="https://github.com/user-attachments/assets/f17a1565-7c79-4b3d-964f-d7231720d343" />


  				
