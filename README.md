# HR-Analytics-Attrition-Analysis-Capstone-1---Part-2-
HR Analytics Attrition Analysis (Capstone 1 - Part 2)
Project Overview

This project focuses on analyzing employee attrition using SQL and SQLite3. We explore the dataset through various queries to understand key factors that influence employee turnover. The project includes:

Data Ingestion: Creating an SQLite3 database from a CSV file.

Attrition Rate Calculation: Summarizing attrition percentages.

Detailed Attrition Breakdown:

By Gender

By Department

By Age Group

By Job Level & Income

By Years at Company

Main Reasons for Attrition:

Comparing attrition rates for employees aged 40-50 vs. over 50.

Analyzing why high-paid employees still leave.

Identifying key drivers for employees with tenure of less than 5 years.

Project Structure

HR_Analytics/
│── HR_Analytics.csv             # Input dataset
│── HR_Analytics.db              # SQLite3 database
│── attrition_analysis.ipynb     # Jupyter Notebook with SQL queries
│── main.py                      # Python script for execution
│── README.md                    # Project documentation

Requirements

To run this project, install the following dependencies:

pip install pandas sqlite3

Running the Project

Clone the repository:

git clone <repository-url>
cd HR_Analytics

Run the Python script:

python main.py

Open the Jupyter Notebook (optional for exploration):

jupyter notebook attrition_analysis.ipynb

Sample Queries

Example query to analyze attrition by age group:

SELECT
    CASE
        WHEN Age < 30 THEN 'Under 30'
        WHEN Age BETWEEN 30 AND 39 THEN '30-40'
        WHEN Age BETWEEN 40 AND 49 THEN '40-50'
        ELSE 'Over 50'
    END AS Age_group,
    COUNT(*) AS num_leaving
FROM hr_data
WHERE Attrition = 'Yes'
GROUP BY Age_group;

Results and Insights

Employees over 50 have higher attrition rates due to job satisfaction and work-life balance issues.

High-paying job levels still experience attrition, potentially due to work stress.

Employees with tenure <5 years leave due to workplace satisfaction and commute factors.

Contribution

Feel free to contribute by forking the repo and submitting a pull request.
