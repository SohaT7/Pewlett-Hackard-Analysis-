# An Analysis for Pewlett Hackard

## Introduction
### Purpose of the Analysis
Pewlett Hackard is soon to undergo the "silver tsunami", i.e. many of its employees will be reaching the retirement age soon. The company intends to figure out who will be retiring soon, and how many new positions will be opening up in each department and for each title. This will help plan for the retirees' retirement packages, as well as plan for a new mentorship program at Pewlett Hackard.
The purpose of this analysis is to determine how many employees will be retiring against each title, and to determine which employees will be eligible for the mentorship program. The mentorship program is intended to help the retirees transition from full-time to part-time, where they will mentor the nerw hires, before retiring completely. 

## Description
In order to efficiently perform both these assignments, an Entity Relationships Diagram (ERD) was created. It lays out the relationships between different tables.
![ERD for the 6 data tables we were provided with](https://github.com/SohaT7/Pewlett-Hackard-Analysis-/blob/main/EmployeeDB.png)

### Deliverable 1: The Number of Retiring Employees by Title
For this deliverable, a Retirement Titles was first created. It holds the titles of all the emplyees born between January 1, 1952 and December 31, 1955. 
![Retirement Titles table](https://github.com/SohaT7/Pewlett-Hackard-Analysis-/blob/main/retirement_titles.png)

Since some of the employees have multiple titles (such as due to promotion(s)), we tweaked the table to include only the most recent titles for such employees. Additionally, we excluded the ones who have already left the company. This is reflected in the Unique Titles table.
![Unique Titles table](https://github.com/SohaT7/Pewlett-Hackard-Analysis-/blob/main/unique_titles.png) 

Next, we calculated the total count against each title for the soon-to-be retirees, as is shown in the Retiring Titles table below.
![Retiring Titles](https://github.com/SohaT7/Pewlett-Hackard-Analysis-/blob/main/retiring_titles.png)

### Deliverable 2: The Employees Eligible for the Mentorship Program

## Results

## Summary
