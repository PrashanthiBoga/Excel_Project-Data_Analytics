# Salary Dashboard
## Introduction
This project focuses on analysing data science salaries using Excel. The goal of this project is to understand how the data is analysed and how an interactive dashboard is created using Excel features.

The dashboard allows users to compare salaries across different job roles, countries, and job schedule types.


## Dataset Used
The dataset contains real-world data science job information from 2023. It includes information such as:

- **👨‍💼 Job titles**
- **💰 Salaries**
- **📍 Locations**
- **🛠️ Skills**

## Excel Skills Used

During this project, I practiced and applied the following Excel skills:

- **📉 Charts**
- **🧮 Formulas and Functions**
- **❎ Data Validation**

## Building the Dashboard

### Charts

**📊 Median Salary by Job Role - Bar Chart**



I created a horizontal bar chart to compare median salaries across different data science job roles.
- Job titles were sorted by salary so higher-paying roles are easy to identify
- Salary values were formatted for better readability
- The chart clearly shows that senior and engineering roles generally have higher salaries than analyst roles


**🗺️ Median Salary by Country - Map Chart**



A map chart was used to visualise median salaries across different countries.

- Each country is colour-coded based on salary level.
- This makes it easy to see salary differences between regions.
- The map helps quickly identify countries with higher and lower salary ranges.

**📊 Job Count by Job Schedule Type - Bar chart**

I created a horizontal bar chart to compare the number of job postings across different job schedule types.

- Job schedule types were sorted by job count so the most common work arrangements are easy to identify
- Values were formatted for better readability
- The chart clearly shows that full-time roles are the most common, followed by other schedule types

  ### Formulas and Functions
  
**💰 Median Salary Calculation by Job Titles**

```sql
=MEDIAN(
    IF(
        (jobs[job_title_short]=A2) *
        (jobs[job_country]=country) *
        (ISNUMBER(SEARCH(type, jobs[job_schedule_type]))) *
        (jobs[salary_year_avg]<>0),
        jobs[salary_year_avg]
    )
)
```

To calculate median salary values, I used an array formula that filters the data based on:

- Job title
- Country
- Job schedule type
- Non-zero salary values
  
This ensures that the median salary displayed in the dashboard updates based on user selections.

**🍽️ Background Table**



📉 Dashboard Implementation



**⏰ Count of Job Schedule Type**

```=FILTER(J2#,(NOT(ISNUMBER(SEARCH("and",J2#))+ISNUMBER(SEARCH(",",J2#))))*(J2#<>0))```

I used a FILTER() formula to clean the job schedule type data by removing entries containing "and" or commas, and omit zero values. This helped create a clear list of unique job schedule types used in the dashboard.

🍽️ Background Table



📉 Dashboard Implementation:



### Data Validation

Data validation was applied to dropdown menus for job title, country, and schedule type.

- This restricts inputs to valid options only.
- Prevents errors in the dashboard
- Makes the dashboard easier and more intuitive to use
