# Excel Salary Dashboard
<img width="1438" height="586" alt="Excel Salary Dashboard" src="https://github.com/user-attachments/assets/2de5adb0-e4c3-4a0b-a0eb-f66e479b3b3c" />

## 📌Overview

This salary dashboard project is an Excel-based data visualization project created to analyze and present salary-related data in an interactive and easy-to-understand format. 

The goal of this project is to transform raw salary data into meaningful insights that can help users understand salary trends across different job roles, skill levels, and locations.  

This project was completed as part of my practical learning journey in data analytics using Microsoft Excel.  

### Dashboard File
You can explore my final dashboard here: [Salary_Dashboard](Salary_Dashboard)

### Excel Skills Used

- **🧮 Formulas and Functions**
- **✅ Data Validation**
- **📊 Charts**

### Data Jobs Dataset

The dataset used for this project contains real-world data science job information from 2023. It contains salary-related information such as:  

- **👷‍♂️ Job titles**
- **💰 Salary amounts**
- **🤹‍♂️ Skill requirements**
- **📅 Schedule types**
- **📍 Locations**

## Dashboard Build

### 🔬Data Analysis

#### 💰 Median Salary by Job Titles  

```
{
=MEDIAN(
IF(
    (jobs[job_title_short]=A2)*
    (jobs[job_country]=country)*
    (ISNUMBER(SEARCH(type,jobs[job_schedule_type])))*
    (jobs[salary_year_avg]<>0),
    jobs[salary_year_avg]
)
)
}
```
- **🔍 Advanced Data Filtering:** Evaluates job title, country, and work schedule type while ignoring records with missing salary values.
- **📊 Dynamic Array Calculation:** Applies the MEDIAN() function combined with nested IF() statements to process and analyze data arrays efficiently.
- **🎯 Customized Salary Insights:** Generates targeted salary results based on selected job roles, locations, and schedule types.
- **🔢 Formula Functionality:** Automatically fills the table below by calculating the median salary according to the specified job title, country, and schedule category.

**🍽️ Background Table**  
<img width="254" height="222" alt="Median Salary Job" src="https://github.com/user-attachments/assets/e39af476-988d-403d-828e-3deba18a51d7" />  

**📊Dashboard Implementation**  
<img width="418" height="479" alt="median salary dash" src="https://github.com/user-attachments/assets/84121f03-7b23-4193-b2d6-b7d0ba38f508" />  

#### ⏰ Count of Job Schedule Type  

```
{
=FILTER(J2#,(NOT(ISNUMBER(SEARCH("and",J2#))+ISNUMBER(SEARCH(",",J2#))))*(J2#<>0))
}
```  
- **🔍 Refined Data Extraction:** The formula uses the FILTER() function to remove entries containing “and”, commas, or zero values from the dataset.
- **📋 Distinct Schedule Identification:** Generates a clean and unique list of job schedule categories for easier analysis.
- **🔢 Formula Functionality:** Automatically fills the table below with unique job schedule types extracted from the dataset.

**🍽️ Background Table**  
<img width="196" height="122" alt="schedule type" src="https://github.com/user-attachments/assets/39f2a091-4028-4b8f-8dcc-83e03355bf85" />  

**📊Dashboard Implementation**  
<img width="444" height="486" alt="sch typ" src="https://github.com/user-attachments/assets/af97aa57-14dc-41a1-948e-9bae14c204cf" />  

### ✅ Data Validation

#### 🔍 Filtered List

- **🔒 Improved Data Validation:** Applying the filtered list as a validation rule for the Job Title, Country, and Type fields within the Data tab helps maintain accurate and reliable inputs.
   - 🎯 Ensures users can only select from approved and standardized schedule categories
   - 🚫 Minimizes invalid, duplicate, or inconsistent data entries
   - 👥 Creates a smoother and more user-friendly dashboard experience  

  <img width="298" height="204" alt="data val" src="https://github.com/user-attachments/assets/43abc505-83d9-4ad3-be9a-d8e867142ca7" />
  
### 📊Data Visualisation

#### 📊 Data Job Salaries - Bar Chart
<img width="382" height="355" alt="bar chart" src="https://github.com/user-attachments/assets/e9366ad1-bec5-49f5-8dfc-aa792c2e5a3e" />  

- **🛠️ Excel Visualization Techniques:** Applied horizontal bar charts with properly formatted salary labels and a well-structured layout to improve readability and presentation.
- **🎨 Chart Selection:** Chose a horizontal bar chart format to make median salary comparisons across job roles more visually effective.
- **📈 Structured Data Arrangement:** Organized job titles in descending order based on salary values for clearer interpretation and easier analysis.
- **💡 Key Observations:** The visualization highlights salary patterns, showing that Senior positions and Engineering roles generally offer higher salaries compared to Analyst roles.

#### 🗺️ Country Median Salaries - Map Chart
<img width="470" height="311" alt="country" src="https://github.com/user-attachments/assets/5b05230d-b087-4c0a-a241-d718a827e11b" />  

- **🛠️ Excel Mapping Tools:** Used Excel’s map chart functionality to display median salary data across different countries worldwide.
- **🎨 Visual Design Approach:** Applied color gradients to distinguish varying salary levels between regions for clearer comparison.
- **📊 Global Data Visualization:** Represented median salary values for all countries included in the dataset.
- **👁️ Enhanced Clarity:** Improved visual interpretation, making geographic salary patterns easier to identify at a glance.
- **💡 Insights Derived:** Helps reveal worldwide salary differences while identifying regions with comparatively high and low compensation levels.

## Conclusion

I developed this dashboard to present valuable insights into salary patterns across different data-related careers. Using techniques learned during my Excel training, this dashboard helps users explore salary trends and make better-informed career decisions. It also provides an interactive way to examine how factors such as job role and geographic location impact salary levels.
