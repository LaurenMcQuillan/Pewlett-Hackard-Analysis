# Pewlett Hackard Analysis

## Overview

The purpose of this analysis is to determine who will be retiring soon from Pewlett Hackard by title so the company can be prepared to fill open positions and determine how many retirement packages they will need to offer. The retiring employees were found based on their date of birth.  Employees born between 1/1/1952 and 12/31/1955 are considered of retirement age. Additionally, they wanted to know which employees are eligible to participate in a mentorship program. Employees born between 1/1/1965 and 12/31/1965 are considered eligible for the mentorship program. Pewlett Hackard provided csv files containing employee data, which I was able to use to build a database and writes queries using SQL to complete the analysis.

## Results

* To find the number of employees retiring by title, multiple queries were needed:
  * I pulled in employee number, first name, last name, title, from date, and to date from the employees and titles tables (joined on primary key), and filtered on birth date where the employee was born between 1/1/1952 and 12/31/1955 to create the retirement_titles table
  * I pulled in distinct employee number based on most recent title, first name, last name, and title from the retirement_titles table, and filtered on to date to exclude any employees who had already retired to create the unique_titles table
  * I found the count of titles by title from the unique_titles table

![Deliverable 1 Queries](https://user-images.githubusercontent.com/115508658/205504443-2d88bb75-4ae7-4ac5-b6b0-06d7ec11ea83.png)

* The title that has the most employees expected to retire is Senior Engineer, followed by Senior Staff. Senior employees are likely to be high valued with the most experience, so it’s very beneficial to plan ahead for their retirement.

![Retirement_Count_by_Title](https://user-images.githubusercontent.com/115508658/205503761-9d10ca29-0ec9-428f-9c77-5dfbfc09860e.png)

* To find the employees eligible for the mentorship program, I pulled in distinct employee number, first name, last name, birth date, from date, to date, and title from the employees and dept_emp tables (joined on primary key), and filtered on to date where the employee had not yet retired and birth date where the employee was born between 1/1/1965 and 12/31/1965

![Deliverable 2 Queries](https://user-images.githubusercontent.com/115508658/205508472-38d271c0-d298-4187-8a59-245409e0c6fb.png)

* There are only 1,549 employees eligible for the mentorship program

![Mentorship](https://user-images.githubusercontent.com/115508658/205505439-98161a70-f261-46bf-8d4b-bc5f8b651a6e.png)

## Summary

### There are 72,458 total roles that will need to be filled as the “silver tsunami” begins to make an impact

![total retiring query](https://user-images.githubusercontent.com/115508658/205508934-a23c57a7-b9d7-477d-8280-ca845eca9fc1.png)

![total retiring image](https://user-images.githubusercontent.com/115508658/205508937-649a645f-47e3-412f-923e-901baad775b1.png)

### There are not enough qualified, retirement ready employees in the departments to mentor the next generation of Pewlett Hackard employees

* I found the count of the employees by department who have not yet retired, are not of retiring age, and are not eligible for the mentorship program to create the active_employee_dept_count table
* I found the count of the employees by department who are eligible for the mentorship program to create the mentorship_dept_count table
* I joined the 2 new department tables on department name and calculated how many employees there are for each mentor by department

![Deliverable 3 Queries](https://user-images.githubusercontent.com/115508658/205511591-64232df6-b0fd-4fe2-916b-810427ad86e3.png)

At best, in the Marketing department, there are 88 employees for each mentor.  At worst, in the Finance department, there are 134 employees for each mentor.

![Deliverable 3 Results](https://user-images.githubusercontent.com/115508658/205511692-f4337560-8e93-4935-95ef-80709cc8b1a2.png)

If the mentorship program age requirement were to be expanded to employees born between 1/1/1964 and 12/31/1965, the number of mentors would increase from 1,549 to 19,905.

![Deliverable 3 Queries 2](https://user-images.githubusercontent.com/115508658/205511974-3270b5ca-0e63-4731-9a85-f9d330e2d310.png)

![Deliverable 3 Results 2](https://user-images.githubusercontent.com/115508658/205511985-2371dc93-217c-4799-8baf-ccb472911ff0.png)




