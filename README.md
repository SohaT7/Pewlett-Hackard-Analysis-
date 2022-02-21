# An Analysis for Pewlett Hackard

## Introduction
### Purpose of the Analysis
Pewlett Hackard is soon to undergo the "silver tsunami", i.e. many of its employees will be reaching the retirement age soon. The company intends to figure out who will be retiring soon, and how many new positions will be opening up in each department and for each title. This will help plan for the retirees' retirement packages, as well as plan for a new mentorship program at Pewlett Hackard.
The purpose of [this analysis](https://github.com/SohaT7/Pewlett-Hackard-Analysis-/blob/main/Queries/Employee_Database_challenge.sql) is to determine how many employees will be retiring against each title, and to determine which employees will be eligible for the mentorship program. The mentorship program is intended to help the retirees transition from full-time to part-time, where they will mentor the nerw hires, before retiring completely. 

## Description
In order to efficiently perform both these assignments, an Entity Relationships Diagram (ERD) was created. It lays out the relationships between different tables. This ERD made writing out [the queries](https://github.com/SohaT7/Pewlett-Hackard-Analysis-/blob/main/Queries/Employee_Database_challenge.sql) alot more easier.
![ERD for the 6 data tables we were provided with](https://github.com/SohaT7/Pewlett-Hackard-Analysis-/blob/main/EmployeeDB.png)

### Deliverable 1: The Number of Retiring Employees by Title
For this deliverable, a [Retirement Titles table](https://github.com/SohaT7/Pewlett-Hackard-Analysis-/blob/main/Data/retirement_titles.csv) was first created. It holds the titles of all the emplyees born between January 1, 1952 and December 31, 1955. 
![Retirement Titles table](https://github.com/SohaT7/Pewlett-Hackard-Analysis-/blob/main/retirement_titles.png)

Since some of the employees have multiple titles (such as due to promotion(s)), we tweaked the table to include only the most recent titles for such employees. Additionally, we excluded the ones who have already left the company. This is reflected in the [Unique Titles table](https://github.com/SohaT7/Pewlett-Hackard-Analysis-/blob/main/Data/unique_titles.csv).
![Unique Titles table](https://github.com/SohaT7/Pewlett-Hackard-Analysis-/blob/main/unique_titles.png) 

Next, we calculated the total count against each title for the soon-to-be retirees, as is shown in the [Retiring Titles table](https://github.com/SohaT7/Pewlett-Hackard-Analysis-/blob/main/Data/retiring_titles.csv) below.
![Retiring Titles](https://github.com/SohaT7/Pewlett-Hackard-Analysis-/blob/main/retiring_titles.png)

### Deliverable 2: The Employees Eligible for the Mentorship Program
The [Mentorship Eligibility table](https://github.com/SohaT7/Pewlett-Hackard-Analysis-/blob/main/Data/mentorship_eligibility.csv) contains the important information on all the employees born between January 1, 1965 and December 31, 1965, who are eligible for the mentorship program. 
![Mentorship Eligibility table](https://github.com/SohaT7/Pewlett-Hackard-Analysis-/blob/main/mentorship_eligibility.png)

## Results
The results we can derive from the tables we created are as follows:

![Image1](https://github.com/SohaT7/Pewlett-Hackard-Analysis-/blob/main/Retiring_Titles_Rank.png)
![Image2](https://github.com/SohaT7/Pewlett-Hackard-Analysis-/blob/main/Mentorship_eligibility_Analyze.png)

- The highest number of retirees will be Senior Engineers (at 25,916) whereas the lowest will be managers (only 2 will be retiring). 
- The second highest number of retirees will be those with the title of Senior Staff. 
- A total of 1,549 employees are eligible for the mentorship program. 
- There is no manager in our list of employees who are eligible for the mentorship program, even though 2 managers will be retiring from Pewlett Hackard.

## Summary
According to the Retiring Titles table, there will be 25,916 Senior Engineers, 24,926 Senior Staff, 9,285 Engineers, 7,636 Staff, 3,603 Technique Leaders, 1,090 Assistant Engineers, and 2 Managers that will be retiring. This makes up to a total of 72,458 employees retiring soon, and 72,458 roles that will need to be filled as the "silver tsunami" sets in. It will be extrememly helpful to create a table by ascending dates of retirement for the employees (sorted by titles as well as by departments). This will tell management, HR, and each department about which roles need to be filled first and/or on an immediate basis and exactly by when. 
As of yet, we do not have any mentorship program-eligible employees that can train new managers. There might be a dearth of such trainers on other levels or departments too. A table can be created to compare how many employees eligible for the mentorship program fall in each department particularly. Moreover, this can be compared with how many employees that department will be losing to retirement (apart from these mentors). For instance, say the Sales department will have 2 Senior Staff and 10 Staff retiring soon. If Sales department only has 4 Staff eligible for mentorship program, that means there is a dearth of mentors/trainers in the Sales department for the new hires/promotees, and the gap needs to be adjusted somehow. 
