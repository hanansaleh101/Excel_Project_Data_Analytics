# Excel Salary Dashboard 
<img width="800" height="308" alt="ezgif-414d6188b0260109" src="https://github.com/user-attachments/assets/7eb1956d-e9c4-4631-9b75-e960f92d8577" />

## Introduction
This Salary Dashboard helps data job seekers to learn about the Median salaries of different data roles across all countries and according to job type (full-time or part-time).  

## Dashboard File  
My Final dashboard is in [1_Salary_Dashboard.xlsx](1_Salary_Dashboard.xlsx)  

## Data Job Datasets  
The dataset used for this project contains real-world data science job information from 2023. The dataset is available via Luke Barousse's Excel course, which provides a foundation for analyzing data using Excel. It includes detailed information on:

- Job titles
- Salaries
- Locations
- Skills

## Excel Skills Used  
- Charts
- Formulas and Functions
- Data Validation

## Dashboard Build 
1. **Charts**  
**Data Science Job Salaries - Bar Chart** 
<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/c62516de-1c13-4aef-be5b-6a10b18ca75e" />

- **🔧 Excel Features**: Created a horizontal bar chart with currency-formatted axis ($K) and clean layout for accurate comparison.
- **🎨 Design Choice**: Used horizontal bars to improve readability of long job titles and enhance visual clarity.
- **📊 Data Organization**: Sorted roles in descending order of median salary to establish a clear ranking structure.
- **💡 Insights Gained**: Senior and engineering roles significantly out-earn analyst roles, highlighting a strong salary progression in data careers.

**Country Median Salaries - Map Chart**    

<img width="500" height="300" alt="1_Salary_Dashboard_Country_Map" src="https://github.com/user-attachments/assets/1f522d97-e537-4f1e-a69c-20e10d8bc05d" />    


- **🌍 Excel Features** : Created a filled map chart with color scaling to show salary differences by country.
- **🎨 Design Choice**: Used a gradient color scheme to highlight higher-paying regions clearly.
- **📊 Data Organization**: Aggregated median salaries by country for accurate geographic comparison.
- **🔍 Interactivity**: Added hover tooltips to display exact salary values.
- **💡 Insights Gained**: Salaries are highest in North America and Europe, showing clear global gaps.  

**2. Formulas and Functions**  

**Median Salary by Job Titles**
```excel
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
- **🧮 Formula Logic**: Built an array formula using MEDIAN + IF to calculate median salary under multiple conditions.   
- **🔍 Multi-Condition Filtering**: Applied boolean logic (*) to filter by job title, country, and job type simultaneously.  
- **⚙️ Text Matching**: Used SEARCH + ISNUMBER to handle partial matches for job schedule types. 

**Result**: This table in the background:  
 <img width="265" height="220" alt="image-2" src="https://github.com/user-attachments/assets/209facba-e552-4f10-b5e5-d0dcb4aa6ec3" />  
 
To implement this dashboard below:   

<img width="300" height="300" alt="image-3" src="https://github.com/user-attachments/assets/43309015-b7fa-42c5-bd84-84de2446a7bf" />

**Count of Job Schedule Type**  

```excel
=FILTER(J2#,(NOT(ISNUMBER(SEARCH("and",J2#))+ISNUMBER(SEARCH(",",J2#))))*
(J2#<>0)
)
```   

- **🧮 Formula Use**: Applied FILTER to extract relevant job schedule types.
- **🔍 Data Cleaning**: Removed entries containing “and” to keep categories consistent.
- **⚙️ Logic Handling**: Used SEARCH + ISNUMBER to control inclusion criteria.   

**Result**: This table in the background:   

<img width="400" height="400" alt="image-4" src="https://github.com/user-attachments/assets/e9e995f2-4b65-48c1-94f2-be30dc5f814a" />

 **3. Data Validation**  

<img width="400" height="400" alt="1_Salary_Dashboard_Data_Validation (1)" src="https://github.com/user-attachments/assets/02297f4e-8bd8-4c13-b667-98013ba6e529" />

  
  ## Conclusion 
  This Salary dashboard is helpful to Data job seekers. It gives them easy insights on their career search for different roles in any country.
