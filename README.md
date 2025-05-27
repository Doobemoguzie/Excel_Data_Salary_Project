# Introduction

"This salary dashboard provides key insights into compensation trends for data-related jobs, helping professionals assess fair pay for their roles.

The dataset includes job titles, salaries, locations, and in-demand skills—offering valuable benchmarks for job seekers and hiring managers alike.



# Dashboard
![alt text](image.png)

*A data-powered salary dashboard that helps job seekers and employers understand fair compensation for data roles. Features include salary breakdowns by experience, location, and schedule—type ensuring transparency in the job market*

### Dashboard File
📂 [Salary_dashbord_file](data_jobs_salary_all.xlsx)

## Excel Skills Used

The analysis was performed using these Excel skills:

* 📉 Charts
* 🧮 Dynamic Salary Calculation (Formula)
* ❎ Data Validation

## Dataset Overview
The dataset includes real-world 2023 salary data for data-related jobs, covering:
- 👨‍💼 Job Titles
- 💵 Salary Figures
- 🌍 Geographic Locations
- 🛠️ Key Skills

# Dashboard Build
## 📉 Charts
### 📊 Salary Comparison by Job Title (Bar Chart)

![alt text](image-1.png)

* **Excel Tools and Tecnique:** Transformed raw data into clear bar charts (formatted salaries) with a user-friendly layout.

* **Design Preference:** Horizontal bar visualization revealed key insights in median salary distributions.

* **Data Arrangement:**  Sorted job titles by descending salary for improved readability.

* **Discoveries Made:** This visualization allows for rapid trend analysis, clearly showing Senior positions and Engineers command higher salaries than Analyst roles.

### 🌍 Country Median Salaries - Map Chart

![alt text](image-2.png)

* **Excel Tools and Tecnique:** Mapped worldwide median salary distributions using Excel’s built-in map charts.

* **Design Preference:**  Color gradients highlight regional salary differences.

* **Data Arrangement:**  Median salaries displayed per country.

* **Discoveries Made:** Clear visualization of high-paying vs. low-paying regions worldwide.

## 🧮 Dynamic Salary Calculation (Formula)

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
* **Multi-Condition Filtering:** Evaluates job title, country, schedule type, and valid salaries.

* **Array Processing:** Uses MEDIAN() with nested IF() for precise calculations.

* **Purpose:** Generates median salary data for the dashboard table.

### 📋 Supporting Tables

![alt text](image-3.png)

### 📉 Dashboard Implementation 

![alt text](image-4.png)

## ⏰ Job Schedule Type Filtering (Formula)

```
=FILTER(
  J2#,
  (NOT(ISNUMBER(SEARCH("and",J2#))+ISNUMBER(SEARCH(",",J2#))))*(J2#<>0)
)
```
### 🔍 Behind the Scenes
**Supporting Tables & Data Prep**
1. Job Schedule Types Table:

- Uses FILTER() to isolate unique entries (e.g., "Full-time" vs. "Contract").

- Excludes compound entries (e.g., "Full-time and Part-time").

2. Data Validation Rules:

- Ensures dropdowns only show valid job titles/countries.

- Prevents typos and inconsistent inputs.
 
## ❎ Data Validation

### 🔍 Filtered Data

- **Controlled Selections:** Dropdown menus restrict inputs to valid job titles, countries, and schedule types.

- **Benefits:** Ensures accuracy and improves dashboard usability.

# 🎯 Key Takeaways

1. Role Matters: Senior/engineering titles offer 20–40% higher pay than junior/analyst roles.

2. Location Impact: Salaries in the US are 2–3× higher than in Eastern Europe/SE Asia.

3. Flexibility Pays: Remote roles often have lower median salaries but wider geographic opportunities.

# 📝 Conclusion

This project demonstrates Excel’s power in transforming raw salary data into actionable insights. Whether you’re negotiating a job offer or planning a career move, this dashboard equips you with data-driven clarity.


