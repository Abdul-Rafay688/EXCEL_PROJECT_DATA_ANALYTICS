# Excel Skill & Salary Analysis

## Introduction

This analysis workbook digs deeper into the same data jobs dataset to answer a question every job seeker cares about: **which skills should I actually learn?** It looks at how often each skill is requested, and how much each skill is associated with in median salary.

The data and approach are from Luke Barousse's Excel for Data Analytics course, using Power Query and PivotTables to go from raw job postings to clear, comparable numbers.

### Analysis File

My final analysis is in [`2_Analysis_Excel_Project.xlsx`](./2_Analysis_Excel_Project.xlsx).

### Excel Skills Used

The following Excel skills were utilized for analysis:

- **🔗 Power Query**
- **📊 PivotTables**
- **🧮 Calculated Fields**
- **🗂️ Data Model**

### Data Jobs Dataset

Same real-world data job postings dataset used in the dashboard project, imported and cleaned via Power Query into two queries: `Data_Jobs_Salary` and `Data_Jobs_Skills`.

## Analysis Build

### 🔗 Power Query

- 🛠️ **Data Import:** Brought in the raw job postings and job skills data from source, cleaning and shaping them into two separate queries before any analysis.
- 🗂️ **Data Model:** Loaded both queries into the Data Model so they could be related and analyzed together instead of duplicating data across sheets.

### 📊 PivotTables

#### 🛠️ Skill Likelihood — `Skill_Job_Analysis`

![Top Skills for Data Nerds](</images/Screenshot 2026-07-21 011626.png>)

- 📊 **Calculated Field:** Built a `Skill_Likelihood` measure showing how often each skill appears per job posting.
- 💡 **Insight:** SQL and Excel are the two skills most likely to show up in a job posting — each appearing in a significant share of all postings.

#### 💰 Salary by Job Title — `Salary_Analysis`

- 📊 **Comparison:** Median salary broken out by job title, and separately for US vs. non-US postings.
- 💡 **Insight:** Senior and specialized roles (Senior Data Scientist, Senior Data Engineer, Machine Learning Engineer) post the highest median salaries, both in the US and abroad.

#### 🛠️ Skills vs. Salary — `Skills_VS_Salary`

![Do more skills get you better pay](</images/Screenshot 2026-07-21 013542.png>)

- 📊 **Comparison:** Median salary plotted against the average number of skills required, by job title.
- 💡 **Insight:** Roles asking for more skills per posting (like Senior Data Engineer) tend to also pay more.

#### 💰🛠️ Skill Salary Analysis — `Skill_Salary_Analysis`

![What's the pay of the top 10 skills](</images/Screenshot 2026-07-21 011848.png>)

- 📊 **Comparison:** Median salary associated with each individual skill, alongside how in-demand that skill is.
- 💡 **Insight:** Python has the highest median salary among common skills, while SQL and Excel remain the most in-demand overall — showing that "most requested" and "highest paying" aren't always the same skill.

## Conclusion

This analysis turns a large, messy dataset into a clear answer: to be competitive as a data analyst, SQL and Excel are non-negotiable, but skills like Python can push earning potential higher. Power Query and PivotTables made it possible to explore this from several angles without writing a single line of code.
