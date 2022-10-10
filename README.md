# An Analysis for Pewlett Hackard
## Table of Contents
- [Overview of the Analysis](#overview-of-the-analysis)
    - [Purpose](#purpose)
    - [About the Dataset](#about-the-dataset)
    - [Tools Used](#tools-used)
    - [Description](#description)
- [Results](#results)
    - [The Number of Retiring Employees by Title](#The-Number-of-Retiring-Employees-by-Title)
        - [Retirement Employees by Title](#Retirement-Employees-by-Title)
        - [Unique Titles](#Unique-Titles)
        - [Generating the Number of Retiring Employees by Title](#Generating-the-Number-of-Retiring-Employees-by-Title)
    - [The Employees Eligible for the Mentorship Program](#The-Employees-Eligible-for-the-Mentorship-Program)
    - [Coalescing the Results](#Coalescing-the-Results)
- [Summary](#summary)
- [Contact Information](#contact-information)

## Overview of the Analysis
### Purpose:
The purpose of [this analysis](https://github.com/SohaT7/Pewlett-Hackard-Analysis-/blob/main/Queries/Employee_Database_challenge.sql) is to determine how many employees at the company will soon be retiring against each title, and to determine which employees will be eligible for the mentorship program. The mentorship program is intended to help the retirees transition from full-time to part-time, where they will mentor the new hires before retiring completely. 

### About the Dataset:
The dataset comprises of the following CSV files:
 - [Departments](https://github.com/SohaT7/Pewlett-Hackard-Analysis-/blob/main/Data/departments.csv)
 - [Department Employees](https://github.com/SohaT7/Pewlett-Hackard-Analysis-/blob/main/Data/dept_emp.csv) 
 - [Department Manager](https://github.com/SohaT7/Pewlett-Hackard-Analysis-/blob/main/Data/dept_manager.csv)
 - [Employees](https://github.com/SohaT7/Pewlett-Hackard-Analysis-/blob/main/Data/employees.csv) 
 - [Salaries (Employee Code, Salary, Dates)](https://github.com/SohaT7/Pewlett-Hackard-Analysis-/blob/main/Data/salaries.csv)
 - [Titles (Employee Code, Title, Dates)](https://github.com/SohaT7/Pewlett-Hackard-Analysis-/blob/main/Data/titles.csv)

### Tools Used:
 - SQL
 - PostgreSQL
 - pgAdmin

### Description:
In order to efficiently perform the analysis, an Entity Relationships Diagram (ERD) was created (click [here](https://github.com/SohaT7/Pewlett-Hackard-Analysis-/blob/main/Queries/schema.sql) to view the queries generated). It lays out the relationships between the 6 tables created from the data files:
 - departments
 - employees
 - dept_manager
 - salaries
 - titles
 - dept_emp

![ERD for the 6 data tables we were provided with](https://github.com/SohaT7/Pewlett-Hackard-Analysis-/blob/main/Images/EmployeeDB.png)

In order analyse who the soon-to-be-retirees are, and whether they are eligible to mentor the new hires, the following four new tables were created (click [here](https://github.com/SohaT7/Pewlett-Hackard-Analysis-/blob/main/Queries/Employee_Database_challenge.sql) to view the queries generated):
 - retirement_titles
 - unique_titles
 - retiring_titles
 - mentorship_eligibility

## Results
### The Number of Retiring Employees by Title:
#### Retirement Employees by Title 
To determine the number of retiring employees by title, a [Retirement Titles table](https://github.com/SohaT7/Pewlett-Hackard-Analysis-/blob/main/Data/retirement_titles.csv) was first created. It holds the titles of all the employees born between January 1, 1952 and December 31, 1955. 
![Retirement Titles table](https://github.com/SohaT7/Pewlett-Hackard-Analysis-/blob/main/Images/retirement_titles.png)

#### Unique Titles
Since some of the employees have multiple titles (such as due to promotion(s)), the table was tweaked to include only the most recent titles for such employees. Additionally, the ones who have already left the company were excluded from the table. This is reflected in the [Unique Titles table](https://github.com/SohaT7/Pewlett-Hackard-Analysis-/blob/main/Data/unique_titles.csv).
![Unique Titles table](https://github.com/SohaT7/Pewlett-Hackard-Analysis-/blob/main/Images/unique_titles.png) 

#### Generating the Number of Retiring Employees by Title
Next, a total count against each title was calculated for the soon-to-be retirees, as is shown in the [Retiring Titles table](https://github.com/SohaT7/Pewlett-Hackard-Analysis-/blob/main/Data/retiring_titles.csv) below.
![Retiring Titles](https://github.com/SohaT7/Pewlett-Hackard-Analysis-/blob/main/Images/retiring_titles.png)

### The Employees Eligible for the Mentorship Program:
The [Mentorship Eligibility table](https://github.com/SohaT7/Pewlett-Hackard-Analysis-/blob/main/Data/mentorship_eligibility.csv) contains the important information on all the employees born between January 1, 1965 and December 31, 1965, who are eligible for the mentorship program. 
![Mentorship Eligibility table](https://github.com/SohaT7/Pewlett-Hackard-Analysis-/blob/main/Images/mentorship_eligibility.png)

### Coalescing the Results:
The results that can be derived from the tables that have been created are as follows:

![Image1](https://github.com/SohaT7/Pewlett-Hackard-Analysis-/blob/main/Images/Retiring_Titles_Rank.png)
![Image2](https://github.com/SohaT7/Pewlett-Hackard-Analysis-/blob/main/Images/Mentorship_eligibility_Analyze.png)

- The highest number of retirees will be Senior Engineers (at 25,916) whereas the lowest will be managers (only 2 will be retiring). 
- The second highest number of retirees will be those with the title of Senior Staff. 
- A total of 1,549 employees are eligible for the mentorship program. 
- There is no manager in our list of employees who are eligible for the mentorship program, even though 2 managers will be retiring from Pewlett Hackard.

## Summary
According to the Retiring Titles table, there will be 25,916 Senior Engineers, 24,926 Senior Staff, 9,285 Engineers, 7,636 Staff, 3,603 Technique Leaders, 1,090 Assistant Engineers, and 2 Managers that will be retiring. This makes up to a total of 72,458 employees retiring soon, and 72,458 roles that will need to be filled in. It will be extrememly helpful to create a table by ascending dates of retirement for the employees (sorted by titles as well as by departments). This will tell management, HR, and each department about which roles need to be filled first and/or on an immediate basis, and exactly by when. 

As of yet, we do not have any mentorship program-eligible employees that can train new managers. There might be a dearth of such trainers on other levels or in other departments too. A table can be created to compare how many of the employees who are eligible for the mentorship program, fall in each department particularly. Moreover, this can be compared with how many employees that department will be losing to retirement (apart from these mentors). For instance, say the Sales department will have 2 Senior Staff and 10 Staff retiring soon. If Sales department only has 4 Staff eligible for mentorship program, that means there is a dearth of mentors/trainers in the Sales department for the new hires/promotees, and the gap needs to be adjusted somehow. 

## Contact Information
Email: st.sohatariq@gmail.com
