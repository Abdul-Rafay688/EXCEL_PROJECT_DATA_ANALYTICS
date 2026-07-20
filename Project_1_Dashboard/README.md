# Excel Salary Dashboard

![Salary Dashboard Demo](images/Project_1_Dashbaord.gif)

## Introduction

This data jobs salary dashboard was created to help job seekers investigate salaries for their desired jobs and ensure they are being adequately compensated.

The data is from Luke Barousse's Excel for Data Analytics course, which provides a foundation in analyzing data using Excel. The data contains detailed information on job titles, salaries, locations, and essential skills that are presented here.

### Dashboard File

My final dashboard is in [`1_Salary_dashbaord_Excel_Project.xlsx`](./1_Salary_dashbaord_Excel_Project.xlsx).

### Excel Skills Used

The following Excel skills were utilized for analysis:

- **📉 Charts**
- **🧮 Formulas and Functions**
- **❎ Data Validation**
- **🔢 Named Ranges**

### Data Jobs Dataset

The dataset used for this project contains real-world data job information. It includes detailed information on:

- **👨‍💼 Job titles**
- **💰 Salaries**
- **📍 Locations (countries)**
- **⏰ Job schedule types**
- **🌐 Job posting platforms**

## Dashboard Build


### 🧮 Formulas and Functions

#### 💰 Median Salary by Job Title, Country & Type

```
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

- 🔍 **Multi-Criteria Filtering:** Checks job title, country, schedule type, and excludes blank salaries.
- 📊 **Array Formula:** Uses `MEDIAN()` with a nested `IF()` to evaluate the whole `jobs` table at once.
- 🎯 **Tailored Insights:** Returns the exact median salary for whatever Job Title + Country + Type is selected.

#### 🌍 Unique, Sorted Country List

```
=UNIQUE(jobs[job_country])
=SORT(ANCHORARRAY(G2))
```

- 🔍 **Dynamic List Generation:** `UNIQUE()` pulls every distinct country from the dataset, and `SORT()` alphabetizes it for the dropdown.

#### ⏰ Filtered Job Schedule Types

```
=FILTER(
  ANCHORARRAY(M2),
  NOT(ISNUMBER(SEARCH("and",ANCHORARRAY(M2))))*(ANCHORARRAY(M2)<>0)
)
```

- 🔍 **Clean List Generation:** `FILTER()` removes combined types (like "Full-time and Part-time") and blanks, leaving only clean, single schedule types for the dropdown.

#### 🔎 Instant Lookup

```
=XLOOKUP(title, ANCHORARRAY(A2), B2:B11, "No Result")
```

- 🎯 **Direct Match:** Pulls the count/value that matches whichever job title is currently selected.

#### 🌐 Platform Job Counts

```
=COUNTIFS(
  jobs[job_via], A2,
  jobs[job_title_short], title,
  jobs[job_country], country,
  jobs[job_schedule_type], type
)
```

- 🔍 **Multi-Criteria Counting:** Counts how many postings for the selected filters came from each job platform (LinkedIn, Indeed, ZipRecruiter, etc.).

### ❎ Data Validation

#### 🔍 Dropdown Filters

- 🔒 Implemented dropdowns for **Job Title**, **Country**, and **Type** on the Salary Calculator sheet using data validation, sourced from the dynamic array lists above.
- 🎯 User input is restricted to predefined, validated values.
- 🚫 Incorrect or inconsistent entries are prevented.
- 👥 Overall usability of the dashboard is enhanced — change a dropdown, and every chart and figure updates instantly.

### 🔢 Named Ranges

- Used named ranges (`title`, `country`, `type`) so formulas read like plain English (e.g. `IF(...=country,...)`) instead of raw cell references like `$I$3`.

## Conclusion

I built this dashboard to showcase salary trends across various data-related job titles. It lets a user pick their job title, country, and job type, and instantly see the median salary and how it compares across platforms — turning a 32,000-row spreadsheet into something anyone can explore in seconds.
