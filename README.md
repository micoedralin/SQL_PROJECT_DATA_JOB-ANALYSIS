# Introduction
Provide insight into the data job market. Focusing on data analyst roles, this project explores top-paying jobs, in-demand skills, and optimal skills needed for top-paying jobs.

SQL queries? Check them out here: [project_sql folder](/project_sql/)
# Background
A desire to navigate the data analyst job market more effectively, this project was created to find the top-paid and in-deamnd skills, streamlining others work to find optimal jobs.

Data comes from a course I took [SQL Course](https://lukebarousse.com/sql). The data is packed with insights on job titles, salaries, location, job schedule, companies, and skills.

### The questions I answered in this course
1. What are the top-paying data analyst jobs?
2. What skills are required for these top-paying jobs?
3. What skills are most in demand for data analysts?
4. Which skills are assocaited with higher salaries?
5. What are the most optimal skills to learn?

# Tools I Used
- **SQL:** The main part of my analysis, SQL allowed me to query the database and find critical insights needed for the project
- **PostgreSQL:** The database management used for handling the job posting data
- **Visual Studio Code:** Used for database management and executing SQL queries
- **Git & Github:** Used for sharing my work insluding my SQL scripts and analysis

# The Analysis
Each query for this project is aimed at investigating specific aspects of the data analyst job market. This query is part of the project and queries the high paying opportunities in data analyst roles.

```sql
SELECT
    name AS company_name,
    job_id,
    job_title,
    job_location,
    job_schedule_type,
    salary_year_avg,
    job_posted_date
FROM
    job_postings_fact
LEFT JOIN
    company_dim ON company_dim.company_id = job_postings_fact.company_id
WHERE
    job_title_short = 'Data Analyst'
    AND job_location = 'Anywhere'
    AND salary_year_avg IS NOT NULL
ORDER BY
    salary_year_avg DESC
LIMIT 10;
```
Here's a breakdown of the findings of this query
- **Wide Salary Range:** Top 10 paying data analyst roles span from $184,000 to $650,000, indicating significant salary potential in the field
- **Diverse Employers:** Companies like SmartAsset, Meta, and AT&T are among those offering high salaries, showing a broad interest across different industries.
- **Job Title Variety:** There's a high diversity in job_titles, from Data Analyst to Director of Analytics, reflecting varied roles and specializations within data analytics.

# What I Learned
From the final analysis that I did, Python, R, and Tableau seemed to be the most useful skills when it came to the highest paying jobs. There were other skills that had a higher average salary than those I listed but what separated them were the number of skills that were in-demand and those three had a wide gap compared to the rest of the other skills.

# Conclusions
Besides learning the most optimal skill that goes along with the highest paying jobs in this data, I was able to get a deeper understanding of SQL learning how to use CTEs, Subqueries (although not used in this project) and get a better understanding of how to get the information I need out of a database. I was also able to learn about how to use Github to showcase what I learned and what I can do when it comes to analyzing data