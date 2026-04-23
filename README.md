## SQL-WITH-Subquery
A demonstration of modular SQL programming using the WITH clause (CTEs) and subqueries. This repository showcases how to refactor complex nested logic into clean, readable, and maintainable code which is a vital skill for scalable data analysis.

### Table Used
<img width="640" height="267" alt="1" src="https://github.com/user-attachments/assets/fb967547-5392-4c05-8aa2-8a34ebf125c8" />

### 1. What is the name and salary of employees in HR?

```SQL
SELECT Name, Salary
FROM Sales
WHERE Department = 'HR';
```
<img width="173" height="88" alt="2" src="https://github.com/user-attachments/assets/3178a056-c9e9-491c-a7a6-ee97d007d7a6" />

### 2
From the above result, I want to know the name of the employees in HR whose salary is higher than 4400, so what do i do?

### a. WITH Clause
I would rename the initial query response as 'Findings' by introducing a WITH clause

```SQL
WITH Findings AS (
SELECT Name, Salary
FROM Sales
WHERE Department = 'HR'
)
```

### b. SELECT
I would introduce another SELECT statement to get my answer from the renamed table 'Findings'

```SQL
WITH Findings AS (
SELECT Name, Salary
FROM Sales
WHERE Department = 'HR'
)
SELECT Name
FROM Findings
WHERE Salary > 4400;
```
<img width="127" height="60" alt="3" src="https://github.com/user-attachments/assets/1f76ed5f-a809-415b-9748-74507b03ec2d" />
