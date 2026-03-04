# SQL-Practice
Practical task of SQL queries

- Data filtering (WHERE, IN, BETWEEN)
- Sorting (ORDER BY)
- Pattern search (LIKE)
- Aggregate functions (COUNT)
- Data grouping (GROUP BY, HAVING)
- Table joining (JOIN)

The work was performed in DBeaver (SQLite database).

# Tables Used

- employees
- employeeTerritories
- titles
- salaries

1. Sorting Data
   
SELECT employee_no, first_name, last_name, hire_date
FROM employees
ORDER BY hire_date DESC;

2. Filtering by Date
   
SELECT first_name, last_name, birth_date
FROM employees
WHERE birth_date >= '1960-01-01';


3. Pattern Matching (LIKE)
   
SELECT first_name, last_name, birth_date
FROM employees
WHERE first_name LIKE 'Ma%';


4. Using IN Operator
   
SELECT employee_no, city
FROM employeeTerritories
WHERE city IN ('Kyiv', 'Dnipro', 'Lviv');


5. Aggregate Function (COUNT)
   
SELECT COUNT(title) AS total_engineers
FROM titles
WHERE title = 'Engineer';


6. GROUP BY + HAVING
   
SELECT city, COUNT(employee_no)
FROM employeeTerritories
GROUP BY city
HAVING COUNT(employee_no) > 10;


7. JOIN (employees + titles)
   
SELECT employees.first_name, employees.last_name, titles.title
FROM employees
JOIN titles
ON employees.employee_no = titles.employee_no;


8. JOIN + BETWEEN

SELECT employees.first_name, employees.last_name, salaries.salary
FROM employees
JOIN salaries
ON employees.employee_no = salaries.employee_no
WHERE salary BETWEEN 50000 AND 60000;


During this practice, I strengthened my SQL skills, learned how to join multiple tables, analyze data using aggregate functions, and apply different filtering techniques to retrieve meaningful information from a database.
