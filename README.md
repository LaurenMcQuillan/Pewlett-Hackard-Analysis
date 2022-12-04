# Pewlett Hackard Analysis

## Overview

The purpose of this analysis is to determine who will be retiring soon from Hewlett Packard by title so they can be prepared to fill open positions and determine how many retirement packages they will need to offer. The retiring employees were found based on their date of birth.  Employees born between 1/1/1952 and 12/31/1955 are considered of retirement age. Additionally, they wanted to know which employees are eligible to participate in a mentorship program. Employees born between 1/1/1965 and 12/31/1965 are considered eligible for the mentorship program. Hewlett Packard provided csv files containing employee data, which I was able to use to build a database and writes queries using SQL to complete the analysis.

## Results

* To find the number of employees retiring by title, multiple queries were needed:
   *  Find employee number, first name, last name, title, from date, and to date from the employees and titles table (joined on primary key), and filter on birth date where the employee was born between 1/1/1952 and 12/31/1955 to create the retirement_titles table
   *  Find distinct employee number based on most recent title, first name, last name, and title from the retirement_titles table, and filter on to date to exclude any employees who had already retired to create the unique_titles table
   *  Find the count of titles by title from the unique_titles table

![Deliverable 1 Queries](https://user-images.githubusercontent.com/115508658/205504310-ec7a0fec-83e3-4f22-8b31-b06030a64490.png)


* The title that has the most employees expected to retire is Senior Engineer, followed by Senior Staff. Senior employees are likely to be high valued with the most experience, so it’s very beneficial to plan ahead for their retirement.

![Retirement_Count_by_Title](https://user-images.githubusercontent.com/115508658/205503761-9d10ca29-0ec9-428f-9c77-5dfbfc09860e.png)


## Summary
