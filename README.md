# Data Jobs Analysis: U.S. Data Analyst Career Insights

## Project Overview

This project analyzes U.S. data job postings using the `lukebarousse/data_jobs` dataset. The main goal is to understand the U.S. Data Analyst job market by exploring job availability, required skills, skill trends, salary levels, and the most valuable skills to learn.

The analysis is divided into five notebooks:

| Notebook | Main Question |
|---|---|
| `1_EDA_Intro.ipynb` | What does the U.S. Data Analyst job market look like? |
| `2_Skills_Count.ipynb` | What are the most demanded skills for the top data roles? |
| `3_Skills_Trend.ipynb` | How are in-demand Data Analyst skills trending over time? |
| `4_Salary_Analysis.ipynb` | How well do jobs and skills pay for Data Analysts? |
| `5_Optimal_Skills.ipynb` | Which skills are the most optimal to learn for Data Analysts? |

---

## Tools and Libraries Used

The project was completed in Python using Jupyter Notebook. The main libraries include:

- `pandas` and `numpy` for data cleaning, transformation, grouping, and aggregation
- `matplotlib` and `seaborn` for data visualization
- `datasets` to load the job posting dataset
- `ast` to convert skill lists stored as strings into Python lists
- `adjustText` to improve scatter plot label readability

---

## Data Preparation

Across the notebooks, the dataset was cleaned and prepared using the following steps:

1. Loaded the `lukebarousse/data_jobs` dataset.
2. Converted `job_posted_date` into a datetime format.
3. Converted `job_skills` from string format into list format.
4. Filtered the dataset mainly for:
   - `job_country == "United States"`
   - `job_title_short == "Data Analyst"` for Data Analyst-specific analysis
5. Used `explode()` on `job_skills` so that each skill could be analyzed individually.
6. Removed missing salary values when salary analysis was required.

---

## What Was Done

### 1. Exploratory Data Analysis

The first notebook focused on understanding the general U.S. Data Analyst job market.

The analysis included:

- Filtering job postings for Data Analyst roles in the United States
- Identifying the top job locations
- Reviewing work-from-home availability
- Reviewing degree mention and health insurance indicators
- Identifying companies with the highest number of Data Analyst postings

This step helped build an initial understanding of where Data Analyst jobs are concentrated and what common job posting characteristics look like.

---

### 2. Skill Demand Analysis

The second notebook analyzed the most requested skills across the top three data roles in the United States:

- Data Analyst
- Data Engineer
- Data Scientist

The analysis counted how often each skill appeared in job postings and also converted those counts into percentages of total job postings for each role.

Key observations:

- SQL is the most demanded skill for Data Analyst roles.
- Excel is also highly requested for Data Analysts, showing that traditional spreadsheet skills are still very important.
- Python is strongly demanded across multiple data roles, especially Data Scientist and Data Engineer roles.
- Data Analyst roles tend to emphasize SQL, Excel, Tableau, Python, and Power BI.
- Data Scientist roles have stronger emphasis on Python, R, and machine learning-related tools.
- Data Engineer roles are more focused on technical tools such as Python, SQL, cloud tools, and engineering-related technologies.

---

### 3. Skill Trend Analysis

The third notebook focused on how Data Analyst skill demand changed by month.

The steps included:

- Filtering U.S. Data Analyst postings
- Extracting the posting month from `job_posted_date`
- Exploding the skills column
- Creating a pivot table with months as rows and skills as columns
- Calculating skill demand as a percentage of monthly Data Analyst postings
- Plotting the top five skills over time

This analysis showed that the most important Data Analyst skills remained relatively consistent across the year. SQL, Excel, Python, Tableau, and other analytics tools stayed among the most frequently requested skills.

The conclusion is that core Data Analyst skills are not only popular overall, but also consistently demanded across time.

---

### 4. Salary Analysis

The fourth notebook analyzed salary distribution by job title and by skill.

The analysis included:

- Filtering U.S. jobs with available yearly average salary
- Comparing salary distribution across the top six data-related roles using box plots
- Focusing specifically on Data Analyst roles
- Calculating median salary by skill
- Comparing:
  - The highest-paying skills
  - The most in-demand skills

Important results from the Data Analyst skill salary analysis:

| Skill | Job Count | Median Salary |
|---|---:|---:|
| Python | 1,431 | $97,500 |
| Tableau | 1,364 | $92,875 |
| R | 893 | $92,500 |
| SQL Server | 286 | $92,500 |
| SQL | 2,508 | $91,000 |
| SAS | 926 | $90,000 |
| Power BI | 838 | $90,000 |
| PowerPoint | 462 | $85,000 |
| Excel | 1,808 | $84,392 |
| Word | 461 | $81,195 |

Some skills had very high median salaries, such as `dplyr`, `bitbucket`, `gitlab`, and `solidity`, but their job counts were very small. Because of this, they may not be as reliable for general career planning.

A stronger conclusion is that skills with both high demand and solid salary levels are more useful for Data Analyst career planning.

---

### 5. Optimal Skills Analysis

The fifth notebook combined demand and salary to identify the most optimal skills for Data Analysts.

The analysis calculated:

- `skill_count`: number of Data Analyst job postings mentioning the skill
- `median_salary`: median yearly salary for jobs mentioning the skill
- `skill_percent`: percentage of Data Analyst jobs requiring the skill

Only skills appearing in more than 5% of Data Analyst postings were treated as high-demand skills.

Key high-demand skills identified:

| Skill | Skill Count | Median Salary | Share of Data Analyst Jobs |
|---|---:|---:|---:|
| SQL | 2,508 | $91,000 | 57.7% |
| Excel | 1,808 | $84,392 | 41.6% |
| Python | 1,431 | $97,500 | 32.9% |
| Tableau | 1,364 | $92,875 | 31.4% |
| SAS | 926 | $90,000 | 21.3% |
| R | 893 | $92,500 | 20.5% |
| Power BI | 838 | $90,000 | 19.3% |
| PowerPoint | 462 | $85,000 | 10.6% |
| Word | 461 | $81,195 | 10.6% |
| SQL Server | 286 | $92,500 | 6.6% |
| Oracle | 274 | $96,924 | 6.3% |
| Go | 224 | $90,000 | 5.1% |

The optimal skills were visualized using a scatter plot with:

- X-axis: percentage of Data Analyst jobs requiring the skill
- Y-axis: median yearly salary

This helped identify skills that are both practical and financially valuable.

---

## Main Conclusions

Based on the analysis, the best skills to prioritize for a U.S. Data Analyst role are:

### 1. SQL is the most important core skill

SQL appeared in the highest percentage of Data Analyst job postings, at around 57.7%. This makes it the most essential skill for Data Analyst roles.

### 2. Excel is still highly relevant

Excel appeared in around 41.6% of Data Analyst postings. Even though it has a lower median salary than Python or SQL, it remains one of the most commonly requested tools.

### 3. Python offers strong salary value

Python appeared in around 32.9% of postings and had one of the highest median salaries among high-demand skills at $97,500. This makes Python one of the most valuable skills to learn after SQL.

### 4. Visualization tools are important

Tableau and Power BI both appeared as major Data Analyst skills. Tableau had a median salary of around $92,875, while Power BI had a median salary of around $90,000. These tools are important for dashboarding, reporting, and business communication.

### 5. High salary alone is not enough

Some niche skills showed very high median salaries, but the number of job postings was very small. These skills may be valuable in specialized roles, but they are less reliable as general learning priorities.

### 6. The most practical learning path is skill balance

The strongest Data Analyst skill set should combine:

1. SQL for data extraction and querying
2. Excel for business analysis and quick reporting
3. Python for automation and advanced analysis
4. Tableau or Power BI for visualization and dashboarding
5. Basic statistics and business understanding to interpret results

---

## Recommended Skill Learning Priority

Based on both demand and salary, the recommended learning order is:

1. **SQL** — highest demand and essential for most Data Analyst roles
2. **Excel** — highly demanded and useful for business reporting
3. **Python** — strong salary value and useful for automation and analysis
4. **Tableau or Power BI** — important for visualization and dashboard creation
5. **R / SAS / SQL Server / Oracle** — useful depending on the target company or industry

---

## Final Summary

This project shows that the U.S. Data Analyst market values a combination of technical, analytical, and business reporting skills. SQL is the strongest foundation, Excel remains highly practical, Python improves salary potential, and visualization tools such as Tableau and Power BI are important for communicating insights.

The main takeaway is that the most optimal Data Analyst skills are not only the highest-paying skills, but the skills that balance strong job demand with strong salary potential.
