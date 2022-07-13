# Pewlett-Hackard-Analysis
# Overview and Purpose 

## Overview
In this challenge our client, Pewlett-Hackard, was interested in identifying how many employees are expected to retire, grouped by job title. Then, we were asked to identify which of the non-retiring employees were eligible to participate in a mentorship program.

## Purpose
The purpose of this challenge was to better understand how to use PostgreSQL to analyze and manipulate a large dataset. At the beginning of this module we were presented with 6 CSV files holding a very substantial amount of data. Initially we were instructed to use quickdatabasediagrams.com to create a physical Entity Relationship Diagram. This allows the viewer to identify the primary and foreign keys in a table, datatypes, and gives a visualization of where the information overlaps between all 6 tables. Using the ERD as a guide for the rest of the module, we used PostgreSQL to further analyze the data and answer the questions of the client.

# Results:
## Analysis of Deliverable 1
When creating the table titled ‘retirement_titles’ we selected information from the two tables ‘employees’ and ‘titles’ where the employees birthday fell between the years 1952 and 1955. This resulted in a table holding 133,776 rows of data. On this table we used the ‘DISTINCT ON ()’ function to remove duplicate employee number entries. Then, we added another condition in which the ’to_date’ was set equal to 9999-01-01. This ensures that the table does not contain any employees that have already left the company. After we applied these filters the result was a table containing 72,458 rows of data. 
Lastly, we created another table showing each job title and how many employees having that job title are expected to retire. This table was titled retiring_titles, and was exported from the program as a CSV file.
### Results of Deliverable 1
In this table we can see that:
- 72,458 employees are expected to retire soon. 
- The majority of the employees that are retiring have the job title ‘Senior Engineer.’ This job title accounts for 25,916 retiring employees. 
- The job title ’Senior Staff’ is a close second, accounting for 24,926 of the retiring employees.
- Out of the 72,458 retiring employees, only 2 of them have the job title ‘Manager.’ 

## Analysis of Deliverable 2
In the second deliverable we called on information from three tables, ‘employees’, ‘titles’, and ‘dept_emp’, to identify employees that are eligible for a mentorship program. When creating this table we applied two conditions. First, we applied a filter to only include employees having a birthday in the year 1965. Next, we filtered the ‘to_date’ equal to 9999-01-01, to ensure that the table won’t contain any employees that have already left the company. Similarly to deliverable 1, we used the function ’DISTINCT ON ()’ to remove any duplicate employee number entries.
 This resulted in a table containing 1,549 rows of data. This table was titled ‘mentorship_eligibilty’
## Results of Deliverable 2
In this table we found that:
- Only 1,549 employees are eligible to participate in the mentorship program. 


# Summary:
## “How many roles will need to be filled as the "silver tsunami" begins to make an impact?”
To ensure that business is able to continue running smoothly, Pewlett-Hackard must prepare to replace 72,458 retiring employees. The company would especially need to focus on filling Senior Engineer positions and Senior Staff positions.

## “Are there enough qualified, retirement-ready employees in the departments to mentor the next generation of Pewlett Hackard employees?”
It is likely that Pewlett Hackard does not have enough eligible mentors to prepare enough employees to replace those that are expected to retire. In deliverable 2 we found that only 1,549 employees are eligible for the mentorship program. If they were all to participate in the program each mentor would need to take on about 47 people to mentor. 
