# Data Science Job Market Analysis

## Introduction

This project explores what skills top employers are looking for, how salaries vary, and what factors can lead to higher pay in data-related roles.

### Key Questions

To guide my analysis, I focused on four main questions:

1. **Does having more skills lead to higher pay?**
2. **How do salaries vary across different regions?**
3. **What are the top skills of data professionals?**
4. **What’s the pay for the top 10 skills?**

### Excel Skills Used

The following Excel skills were utilized for analysis:

- **📊 Pivot Tables**
- **📈 Pivot Charts**
- **🧮 DAX (Data Analysis Expressions)**
- **🔍 Power Query**
- **💪 Power Pivot**

### Dataset

The [dataset](Project_2-Analysis/data_jobs_salary_all.xlsx) used for this project contains real-world data science job information from 2023. It includes detailed information on:

- **👨‍💼 Job titles**
- **💰 Salaries**
- **📍 Locations**
- **🛠️ Skills**

## 1️⃣ Does having more skills lead to higher pay?

### Tool Used: Power Query (ETL)

#### Process:

- Extracted the data using Power Query and created two queries with all data jobs information and skills for each job ID.
- Transformed the data: changed column types, removed unnecessary columns, and cleaning text to eliminate specific words, and trimming excess whitespace.
- 📊 data_jobs_all
  
  <img width="181" height="218" alt="image" src="https://github.com/user-attachments/assets/887f391f-dd73-4bff-ad05-f025e2294a97" />

- 📊 data_jobs_skills
  
  <img width="182" height="233" alt="image" src="https://github.com/user-attachments/assets/bffda4ae-6f3a-4269-8f5b-50b1c66dc11b" />
  
- Loaded the cleaned data into Excel for further analysis.

- 📊 data_jobs_all
  
  <img width="955" height="346" alt="image" src="https://github.com/user-attachments/assets/aff0ff39-1e16-4663-9872-e25818a786c4" />

- 📊 data_jobs_skills

   <img width="956" height="365" alt="image" src="https://github.com/user-attachments/assets/6866c7d1-692e-4e9b-a938-7e53cc6dccea" />

#### Insights:

- Jobs requiring more skills, such as Senior Data Engineer or Data Scientist, tend to offer higher salaries.
- Roles with fewer required skills, like Business Analyst, generally have lower pay.

  <img width="374" height="224" alt="image" src="https://github.com/user-attachments/assets/ebcb120a-7212-4a92-932d-a9b896aa5abc" />



#### Takeaway:

- Developing multiple relevant skills can significantly improve earning potential.

## 2️⃣ How do salaries vary across different regions?

### Tool Used: PivotTables & DAX

#### Process:

- Built a PivotTable using the data model I created with Power Pivot and moved the `job_title_short` to the rows area and `salary_year_avg` into the values area. Then added a new measure to calculate the `median salary` for United States jobs.

    ```
    =CALCULATE(
        MEDIAN(data_jobs_all[salary_year_avg]),
        data_jobs_all[job_country] = "United States")
    ```
- Calculated `median salaries` using DAX.

    ```
    Median Salary := MEDIAN(data_jobs_all[salary_year_avg])
    ```

#### Insights:

- Roles such as Senior Data Engineer and Data Scientist earn higher median salaries both in the US and globally, highlighting the strong worldwide demand for advanced data expertise.
- However, theres a clear pay gap between US and non-US roles, likely driven by the high concentration of major tech companies in the United States.

  <img width="572" height="185" alt="image" src="https://github.com/user-attachments/assets/0f0ab02e-99fa-4d69-ad2f-f49d0def77ae" />


#### Takeaway:

- Understanding regional salary differences helps professionals negotiate pay and plan their career moves more strategically, while also enabling companies to align compensation with market standards and geographical variations.

## 3️⃣ What are the top skills of data professionals?

### Tool Used: Power Pivot

#### Process:

 - I built a data model by combining the `data_jobs_all` and `data_jobs_skills` tables and linking them through the `job_id` column.

   <img width="484" height="308" alt="image" src="https://github.com/user-attachments/assets/2ab7f922-6dfc-499c-bacf-08886cabef38" />

 - Using the Power Pivot menu, I refined the data model and efficiently created measures for analysis.

   <img width="935" height="298" alt="image" src="https://github.com/user-attachments/assets/1c62a6ac-193a-428d-9849-91fe52fe1cb0" />


#### Insights:

- SQL and Python are the most common skills, reflecting their essential role in data processing and analysis.
- Emerging technologies like AWS and Azure also show significant presence, underlining the industry's shift towards cloud services and big data technologies.

  <img width="366" height="242" alt="image" src="https://github.com/user-attachments/assets/43127335-8669-4117-b94e-e0e60899f0f6" />

#### Takeaway:

- Focusing on widely used and emerging skills helps professionals stay competitive in the market.

## 4️⃣ What’s the pay for the top 10 skills? 

### Tool Used: Advanced Charts (Pivot Chart)

#### Process:

- Created a combo PivotChart showing `median salary` (Clustered Column) and `skill likelihood` (%) (Line with Markers).
- Customized the chart for clarity (added a title axis title, removed the lines (skill likelihood), and changed the markers to diamonds).

#### Insights:

- Skills like Python, SQL, and Oracle are linked to higher-paying roles.
- Basic skills like PowerPoint and Word are associated with lower salaries.

  <img width="413" height="213" alt="image" src="https://github.com/user-attachments/assets/39c890e7-f6a3-4b70-96eb-40eacb02d744" />


#### Takeaway:

- Investing in high-value skills like Python and SQL can lead to better-paying opportunities in tech-focused roles.

## Conclusion

This project gave me a hands-on experience to explore the data science job market. By analyzing real-world job postings with Excel’s advanced features like Power Query, PivotTables, DAX, and Pivot charts, I identified clear links between skills, job roles, regions, and salaries. The findings highlight the importance of acquiring in-demand technical skills like Python, SQL, and cloud technologies to maximize career opportunities and earning potential.
