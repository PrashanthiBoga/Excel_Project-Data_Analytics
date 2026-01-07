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

The dataset used for this project contains real-world data science job information from 2023. It includes detailed information on:

- **👨‍💼 Job titles**
- **💰 Salaries**
- **📍 Locations**
- **🛠️ Skills**

## 1️⃣ Does having more skills lead to higher pay?

### Tool Used: Power Query (ETL)

#### Process:

- Extracted the data using Power Query and created two queries with `all data jobs information` and `skills for each job ID`.
- Transformed the data: changed column types, removed unnecessary columns, and cleaning text to eliminate specific words, and trimming excess whitespace.
- Loaded the cleaned data into Excel for further analysis.

#### Insights:

- Jobs requiring more skills, such as Senior Data Engineer or Data Scientist, tend to offer higher salaries.
- Roles with fewer required skills, like Business Analyst, generally have lower pay.

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
- Calculated `median salaries` using DAX for both US and international jobs.

    ```
    Median Salary := MEDIAN(data_jobs_all[salary_year_avg])
    ```

#### Insights:

- Roles such as Senior Data Engineer and Data Scientist earn higher median salaries both in the US and globally, highlighting the strong worldwide demand for advanced data expertise.
- However, theres a clear pay gap between US and non-US roles, likely driven by the high concentration of major tech companies in the United States.

#### Takeaway:

- Understanding regional salary differences helps professionals negotiate pay and plan their career moves more strategically, while also enabling companies to align compensation with market standards and geographical variations.

## 3️⃣ What are the top skills of data professionals?

### Tool Used: Power Pivot

#### Process:

 - I built a data model by combining the `data_jobs_all` and `data_jobs_skills` tables and linking them through the `job_id` column. 
 - Using the Power Pivot menu, I refined the data model and efficiently created measures for analysis.

#### Insights:

- SQL and Python are the most common skills, reflecting their essential role in data processing and analysis.
- Emerging technologies like AWS and Azure also show significant presence, underlining the industry's shift towards cloud services and big data technologies.

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

#### Takeaway:

- Investing in high-value skills like Python and SQL can lead to better-paying opportunities in tech-focused roles.

## Conclusion

This project gave me a hands-on experience to explore the data science job market. By analyzing real-world job postings with Excel’s advanced features like Power Query, PivotTables, DAX, and Pivot charts, I identified clear links between skills, job roles, regions, and salaries. The findings highlight the importance of acquiring in-demand technical skills like Python, SQL, and cloud technologies to maximize career opportunities and earning potential.
