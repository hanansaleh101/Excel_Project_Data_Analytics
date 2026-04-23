# Excel Project Analysis  
<img width="900" height="650" alt="project 2 overall" src="https://github.com/user-attachments/assets/7c75cf6b-f55a-4b0c-9844-7a54798c6b52" />

## Introduction  
This project explores salary trends and skill demand across different data roles using Excel and Power Pivot.
It focuses on analyzing how skills, location, and job roles influence median salaries.
Through this analysis, I applied data modeling and DAX to turn raw data into meaningful insights.
## Questions Analyzed 
1. Do more skills equal more money for Data roles?  

2. What is the Median Salary for data roles in different regions?  

3. What are the top skills of Data roles?  

4. What's the pay of the top 10 skills?

## Dashboard File  
My Final Analysis is in [2_Project_Analysis.xlsx](2_Project_Analysis.xlsx)  

## Data Job Datasets  
The dataset used for this project contains real-world data science job information from 2023. The dataset is available via Luke Barousse's Excel course, which provides a foundation for analyzing data using Excel. It includes detailed information on:

- Job titles
- Salaries
- Locations
- Skills   

## Excel Skills Used  
- Power Query 
- Power Pivot
- Pivot tables and Pivot Charts 
- DAX

## 1. Do more skills equal more money for Data roles?   
Skills used: Powr Query and Pivot Tables 
- I created 2 queries: 
   - one with all data job info
    
     <img width="1916" height="649" alt="2_Project_Analysis_Screenshot3" src="https://github.com/user-attachments/assets/1f5ffa34-3095-46ea-855a-41c3f1303f68" />

  -  one with jobID and skills
     <img width="1914" height="702" alt="2_Project_Analysis_Screenshot4" src="https://github.com/user-attachments/assets/7bc876d9-99c0-423c-8d32-618fe6c60b98" />
- Trandofrmed the data to remove unnecessary columns, cleaned and trimmed the text in both tables.  
     <img width="244" height="312" alt="2_Project_Analysis_Screenshot1" src="https://github.com/user-attachments/assets/398a7654-510f-49c4-aae0-9e897bd818fc" />

### Insights:  
<img width="1504" height="761" alt="image-1" src="https://github.com/user-attachments/assets/35cdd008-cc8f-4f3c-b6f9-00c7f578dadc" />

 
1. *More skills usually mean higher salary*  
Jobs that require more skills tend to pay more, but the relationship isn’t very strong.
Example: A Senior Data Engineer requires around 8+ skills and earns about $150K, while a Data Analyst with ~3–4 skills earns around $90K.

2. *Job role matters more than skill count*  
Some roles pay more than others even if they require the same number of skills.
Example: A Data Scientist and a Software Engineer both require about 5 skills, but the Data Scientist earns more (around $130K vs $125K).

## 2. What is the Median Salary for data roles in different regions?  
 Skills used: Pivot Table and DAX  

- I set my dataset into Power Pivot to create a Data Model.
- I created a pivot table.  
- Put `job_title_short` in the rows and `salary_year_Avg` in the values.
- I added a new measure and used DAX to calculate and filter the median salary for United States jobs only. 

```excel
=CALCULATE(
    MEDIAN(data_jobs_all[salary_year_avg]),
    data_jobs_all[job_country] = "United States")
```

- I used DAX to calculate the median salary globally.  
```excel
= MEDIAN(data_jobs_all[salary_year_avg])
```

### Insights:  
<img width="1774" height="779" alt="image" src="https://github.com/user-attachments/assets/e9a53328-35fb-43b0-9c84-4f5128e1c68a" />

*1. Salaries are generally higher in the US compared to Egypt and other regions*  
Most data roles earn more in the US compared to Non-US regions.  
Example: A Data Scientist earns about $130K in the US vs ~$119K outside the US.

*2. The gap varies depending on the role*  
Some roles have a large salary difference, while others are almost the same across regions.
Example: A Machine Learning Engineer earns $150K in the US vs ~$101K Non-US (big gap), while a Senior Data Scientist earns $155K in both regions (no gap).

## 3. What are the top skills of Data Nerds?
 Skills used: Power Pivot.  

- I integrated the `data_jobs_all` and `data_jobs_skills` tables into one Data model.

- I created a relationship between the two tables using `job_id` column. 
<img width="1788" height="1264" alt="2_Project_Analysis_Screenshot5" src="https://github.com/user-attachments/assets/87c3b4a0-f22c-4828-9582-4a4b9eda8945" />


- Calculated the Skill Likelihood by taking the percentage of skill count/job count.  
- Added a Job Title slicer and a Country slicer.  

### Insights:  
<img width="1286" height="705" alt="image" src="https://github.com/user-attachments/assets/f192b5d3-d8cf-46b9-a3fd-518fa29ec6a5" />

*1. SQL and Excel dominate as the most in-demand skills*
These two skills appear far more frequently in job postings compared to others.
Example: SQL (~52%) and Excel (~41%) are significantly higher than tools like Python (~28%) or Tableau (~29%).

*2. Technical tools are prioritized over general tools*
Specialized data tools are much more in demand than general office tools.
Example: Skills like Python (~28%) and Power BI (~16%) are more commonly required than Word (~10%) or PowerPoint (~9%). 

## 4. What's the pay of the top 10 skills?
 Skills used: Advanced Charts (Power Chart) 

- I created a combo PivotChart to plot median salary and skill likelihood (%) from my PivotTable.
- Edited the combo chart to replace the lines with diamond markers to enhance visibility.  

### Insights:  
<img width="1314" height="636" alt="image" src="https://github.com/user-attachments/assets/caf4efc3-019b-4b5e-aae0-1003de17eecc" />  

*1. Higher-paying skills are not always the most in-demand*
Some of the highest-paying skills appear less frequently in job postings.
Example: Oracle (~ $97K) and Python (~ $97K) offer top salaries, but their demand (~ 25–30%) is lower than SQL (~ 55%), which pays less (~ $90K).

*2. Widely used tools tend to have lower salary premiums*
Skills that are more common across roles tend to offer slightly lower salaries.
Example: Excel (~ 40%) and Word (~ 12%) are widely used but have lower median salaries
(~ $84K and ~ $82K) compared to more specialized tools.  

## Conclusion  
Following this guided project in Luke Barousse's course allowed me to reflect on better questions to use and analyze the data. 

 This helps draw even better insights about something as big as the data science job market.  
 Using Excel features like Power Query, PivotTables, DAX, and charts. Key discoveries were made in the correlations between multiple skills and higher salaries, particularly in Python, SQL, and cloud technologies.

