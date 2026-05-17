# Excel Salary Analysis

## 📌Overview

As an aspiring data analyst entering the job market, I noticed there was limited accessible data showing which skills and roles are most valuable in the data industry. This inspired me to analyze salary trends, in-demand skills, and employer requirements to better understand how data professionals can improve their career opportunities and earning potential.  

### Questions to Analyze

1. Does having a wider range of skills lead to higher salaries?
2. How do salaries for data-related roles vary across different regions?
3. Which skills are most commonly possessed by data professionals?
4. What salary levels are associated with the top 10 in-demand skills?

### Excel Skills Used
- 📅 Pivot Tables
- 📊 Pivot 
- 🔍 Power Query
- 🧮 DAX (Data Analysis Expressions)
- 💪 Power Pivot

### Data Jobs Dataset

The dataset used for this project contains real-world data science job information from 2023. It includes detailed information on:  

- 👨‍💼 Job titles
- 💰 Salaries
- 📍 Locations
- 🛠️ Skills

## 1️⃣ Do more skills get you better pay?

### 🔍 Power Query (ETL)

#### 📥 Extract

Using Power Query, I imported the original dataset and generated two separate queries:  
- 🗃️ One containing complete information on data-related job roles.
- 🔧 Another mapping the required skills to each corresponding job ID.

#### 🔄 Transform

Next, I cleaned and transformed the queries by adjusting data types, removing irrelevant columns, refining text entries by deleting unwanted words, and eliminating extra spaces to improve data consistency and accuracy.

- 📊 data_jobs_all

<img width="249" height="300" alt="data all" src="https://github.com/user-attachments/assets/72a62908-e359-4dff-b300-f5568d3f0b85" />  

- 🛠️ data_job_skills

<img width="246" height="322" alt="data skills" src="https://github.com/user-attachments/assets/c03fa86c-a16f-47e1-a6bc-680a6f8b759e" />  

#### 🔗 Load

Lastly, I imported the cleaned and transformed queries into the workbook, creating a solid foundation for the analysis and dashboard development that followed.  

- 📊 data_jobs_all

<img width="1600" height="701" alt="dat all" src="https://github.com/user-attachments/assets/3f569d47-4054-4c1b-ba2b-722adb95b173" />  

- 🛠️ data_job_skills

<img width="1600" height="700" alt="dat skl" src="https://github.com/user-attachments/assets/61921f86-51f4-4610-8264-cdb4be2ccde9" />  

### 📊 Analysis

#### 💡 Insights

- 📈 The analysis reveals a positive relationship between the number of skills required in job postings and median salary levels, especially for positions such as Senior Data Engineer and Data Scientist.
- 💼 Job roles that demand fewer technical skills, such as Business Analyst positions, generally show lower salary ranges, indicating that highly specialized skill sets are often associated with greater earning potential.

<img width="545" height="346" alt="skl chrt" src="https://github.com/user-attachments/assets/63f961ce-a4f8-4787-84c0-641e2be571b9" />  

#### 🤔 Key Takeaway
This trend highlights the importance of developing a broad and relevant skill set, especially for professionals seeking better-paying opportunities in the data industry.  

## 2️⃣ What’s the salary for data jobs in different regions?

### 🧮 PivotTables & DAX

#### 📅 Pivot Tables

- 🔢 I built a PivotTable from the Data Model developed in Power Pivot to support deeper salary analysis.
- 📊 The job_title_short field was placed in the Rows section, while salary_year_avg was added to the Values section for aggregation.
- 🧮 Afterward, I created a custom measure to compute the median salary specifically for jobs located in the United States.  

```
{
=CALCULATE(
    MEDIAN(data_jobs_all[salary_year_avg]),
    data_jobs_all[job_country] = "United States")
}
```

#### 🧮 DAX

To calculate the median year salary I used DAX.

```
{
Median Salary := MEDIAN(data_jobs_all[salary_year_avg])
}
```

### 📊 Analysis

#### 💡 Insights

- 💼 Positions such as Senior Data Engineer and Data Scientist consistently show high median salaries in both US and international markets, reflecting the strong worldwide demand for advanced data professionals.
- 💰 A significant salary gap exists between US-based and non-US roles, especially in technology-focused positions, likely due to the large presence of major tech industries within the United States.

<img width="767" height="272" alt="med ctry" src="https://github.com/user-attachments/assets/b1d6b0c1-cc4f-490b-8c2d-affe7a6cc27f" />  

#### 🤔 Why This Matters
These salary findings can support career planning and compensation discussions by helping both professionals and employers benchmark salaries against industry standards while accounting for regional differences in pay.  

## 3️⃣ What are the top skills of data professionals?

### 🔧 Power Pivot

#### 💪 Power Pivot

- 🔗 I developed a unified data model by combining the data_jobs_all and data_jobs_skills tables into a single structured model.
- 🧹 Because the datasets had already been cleaned and prepared in Power Query, Power Pivot was able to automatically establish relationships between the two tables.

#### 🔗 Data Model

I created a relationship between my two tables using the job_id column.  

<img width="615" height="541" alt="pwr dv" src="https://github.com/user-attachments/assets/5a5ad3bf-20b9-4719-9b44-87c6850292ee" />  

#### 📃 Power Pivot Menu

The Power Pivot menu was used to refine my data model and makes it easy to create measures.  

<img width="1598" height="539" alt="pwr dat" src="https://github.com/user-attachments/assets/35d08a26-b70a-499f-a75e-642a33ea2ed4" />  

### 📊 Analysis

#### 💡 Insights

- 💻 SQL and Python remain among the most in-demand skills for data-related careers, highlighting their essential role in data management, analysis, and processing.
- ☁️ Cloud platforms such as AWS and Azure are also highly sought after, reflecting the growing industry focus on cloud computing and large-scale data technologies.

<img width="472" height="321" alt="skl like" src="https://github.com/user-attachments/assets/f4d18045-8095-4fcb-893f-2a78f54f82b5" />  

#### 🤔 Why This Matters
Identifying the most commonly requested industry skills helps professionals remain relevant in the job market while also helping educators and training programs prioritize technologies that deliver the greatest career value.

## 4️⃣ What’s the pay of the top 10 skills?

### 📊 Advanced Charts (Pivot Chart)

#### 📈 PivotChart

I developed a combo PivotChart from my PivotTable to visualize both median salary and skill likelihood percentages in a single chart.  

- 🪙 Primary Axis: Displayed median salary using a clustered column chart
- 👍 Secondary Axis: Represented skill likelihood (%) with a line chart and markers  

To improve the chart’s appearance and readability, I added chart and axis titles, removed the connecting lines from the skill likelihood series, and customized the markers into diamond shapes.

### 📊 Analysis

#### 💡 Insights

- 💰 Skills such as Python, Oracle, and SQL are linked to higher median salaries, highlighting their strong importance in well-paying technology and data-related roles.
- 📉 In contrast, tools like PowerPoint and Word show lower median salary values and lower demand frequency, suggesting they are less specialized and less influential in higher-paying career paths.

<img width="539" height="287" alt="skl med" src="https://github.com/user-attachments/assets/99ba0f17-10f8-42fc-8634-93f87359a8ae" />  

#### 🤔 Key Insight
This visualization demonstrates the value of developing in-demand technical skills such as Python and SQL, as they are strongly associated with higher-paying opportunities in the technology and data fields.  

## Conclusion

As an aspiring data analyst passionate about data and career growth, I developed this Excel-based project to gain deeper insights into the data job market. Using a real-world dataset of job postings, I explored salary trends, job roles, locations, and the most in-demand technical skills across the industry.  

By applying Excel tools such as Power Query, PivotTables, DAX, and data visualizations, I was able to identify important relationships between specialized skills and higher salary opportunities, particularly in areas like Python, SQL, and cloud technologies.  

This project reflects both my learning journey in data analytics and my interest in understanding what skills are most valuable for building a successful career in the data field. I hope it provides useful insights for aspiring data professionals looking to make informed career and skill-development decisions.
