# Salary Dashboard
## Introduction
This project focuses on analysing data science salaries using Excel. The goal of this project is to understand how the data is analysed and how an interactive dashboard is created using Excel features.
The dashboard allows users to compare salaries across different job roles, countries, and job schedule types.

https://github.com/user-attachments/assets/def1e6e2-1cd8-40f6-886b-8d0a725e9f3a

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

### 📉 Charts

**📊 Median Salary by Job Role - Bar Chart**

<img align="center" width="600" height="400" alt="image" src="https://github.com/user-attachments/assets/adaa8b47-771f-4ba7-9e72-5915d22e54d2" />

I created a horizontal bar chart to compare median salaries across different data science job roles.
- Job titles were sorted by salary so higher-paying roles are easy to identify.
- Salary values were formatted for better readability.
- The chart clearly shows that senior and engineering roles generally have higher salaries than analyst roles.


**🗺️ Median Salary by Country - Map Chart**

<img align="center" width="500" height="400" alt="image" src="https://github.com/user-attachments/assets/e17c7799-e128-48a7-9fb1-335de3b8c411" />

A map chart was used to visualise median salaries across different countries.
- Each country is colour-coded based on salary level.
- This makes it easy to see salary differences between regions.
- The map helps quickly identify countries with higher and lower salary ranges.

**📊 Median Salary by Job Schedule Type - Bar Chart**

<img align="center" width="500" height="460" alt="image" src="https://github.com/user-attachments/assets/67e2f921-4031-4e1c-bf90-fd7dc812d8b4" />

I created a horizontal bar chart to compare median salaries across different job schedule types.
- Job schedule types were sorted by median salary so higher-paying work arrangements are easy to identify.
- Salary values were formatted for better readability.
- The chart shows that certain schedule types offer higher median salaries compared to others, highlighting how work arrangements can impact pay.

### 🧮 Formulas and Functions
  
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

**⚙️ Background Table**

<img align="center" width="300" height="300" alt="image" src="https://github.com/user-attachments/assets/c411926e-c013-4eb3-b95c-c2389213f79b" /> 

**📉 Dashboard Implementation**

https://github.com/user-attachments/assets/ed716b2e-9eb9-44c1-9d38-8128d2dfa61a

**⏰ Count of Job Schedule Type**

``` sql
=FILTER(J2#,(NOT(ISNUMBER(SEARCH("and",J2#))+ISNUMBER(SEARCH(",",J2#))))*(J2#<>0))
```

I used a FILTER() formula to clean the job schedule type data by removing entries containing "and" or "commas", and "omit zero values". This helped create a clear list of unique job schedule types used in the dashboard.

**⚙️ Background Table**

<img width="200" height="137" alt="image" src="https://github.com/user-attachments/assets/af2db612-7616-4918-a0cf-e147a23c9682" />


**📉 Dashboard Implementation:**

https://github.com/user-attachments/assets/dd1f4485-1c20-43bb-84d5-23d1f48f6236


**🔍 Top Job Posting Platform**

This metric identifies the platform with the highest number of job postings based on the user’s selected job title, country, and job schedule type.

```sql
=COUNTIFS(
    jobs[job_via], A2,
    jobs[job_title_short], title,
    jobs[job_country], country,
    jobs[job_schedule_type], type
)
```

- The calculation counts how many times each job posting platform appears in the job_via column.
- Filters are applied based on the selected job title, country, and schedule type.
- The platform with the highest job count is then identified as the top job posting source.
This helps users understand which platforms most frequently advertise roles that match their selected criteria.

**⚙️ Background Table**

<img width="500" height="233" alt="image" src="https://github.com/user-attachments/assets/c46b3095-8f82-4d1e-bc15-8dda5eb37d77" />


**📉 Dashboard Implementation:**

https://github.com/user-attachments/assets/ae3ec0a9-669d-4253-9cd4-7aceb2afac62


### ❎ Data Validation

Data validation was applied to dropdown menus for job title, country, and schedule type.

- This restricts inputs to valid options only.
- Prevents errors in the dashboard.
- Makes the dashboard easier and more intuitive to use.
