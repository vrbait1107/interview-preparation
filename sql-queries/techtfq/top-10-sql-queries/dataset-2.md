
```sql

DROP TABLE IF EXISTS employee;

CREATE TABLE employee (
    id INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(100),
    dept VARCHAR(100),
    salary INT
);

INSERT INTO employee (name, dept, salary) VALUES ('Alexander', 'Admin', 6500);
INSERT INTO employee (name, dept, salary) VALUES ('Leo', 'Finance', 7000);
INSERT INTO employee (name, dept, salary) VALUES ('Robin', 'IT', 2000);
INSERT INTO employee (name, dept, salary) VALUES ('Ali', 'IT', 4000);
INSERT INTO employee (name, dept, salary) VALUES ('Maria', 'IT', 6000);
INSERT INTO employee (name, dept, salary) VALUES ('Alice', 'Admin', 5000);
INSERT INTO employee (name, dept, salary) VALUES ('Sebastian', 'HR', 3000);
INSERT INTO employee (name, dept, salary) VALUES ('Emma', 'Finance', 4000);
INSERT INTO employee (name, dept, salary) VALUES ('John', 'HR', 4500);
INSERT INTO employee (name, dept, salary) VALUES ('Kabir', 'IT', 8000);

SELECT * FROM employee;

```

---

1. **Aggregate Functions**: Write a query to find the average salary of employees in each department. Sort the results by department name.

```sql

SELECT dept, ROUND(AVG(salary), 0) as average_salary
FROM employee
GROUP BY dept;

```

---

2. **Salary Distribution**: Create a query that shows the number of employees in each salary range (e.g., 0-3000, 3001-6000, 6001-9000).

```sql

SELECT 
    CASE
        WHEN salary BETWEEN 0 AND 3000 THEN 'LOW'
        WHEN salary BETWEEN 3001 AND 6000 THEN 'MEDIUM'
        WHEN salary BETWEEN 6001 AND 9000 THEN 'HIGH'
        ELSE 'OTHER'
    END AS category,
    COUNT(*)
FROM
    employee
GROUP BY category;

```

---


3. **Top N Salaries**: Write a query to find the top 3 highest salaries and their corresponding employee names.

```sql

WITH ranked_salaries AS (
SELECT name, 
salary,
dense_rank() OVER(order by salary desc) as ranking 
FROM employee
)

select * from ranked_salaries
WHERE ranking <= 3;

```

---

4. **Salary Increase Calculation**: Assume a company-wide policy to increase salaries by 10% for employees earning less than 5000. Write an SQL statement to apply this increase.

```sql

SELECT
    *, 
    CASE
        WHEN salary < 5000 THEN ROUND(salary + (salary * 0.10), 0)
        ELSE salary
    END AS increamented_salary
FROM
    employee;

```


---

5. **Department Analysis**: Write a query that retrieves the department with the highest total salary expenditure.

```sql

SELECT 
    SUM(salary) AS highest_salary, dept
FROM
    employee
GROUP BY dept
ORDER BY highest_salary DESC
LIMIT 1;

```

---


6. **Employee Count by Department**: Create a query that returns the number of employees in each department, along with the average salary of those employees.

```sql

SELECT 
    dept, ROUND(AVG(salary), 0) AS avg_dept_salary, COUNT(*) AS emp_count
FROM
    employee
GROUP BY dept;

```

---

7. Write a query to find employees who earn more than the average salary of their department.

```sql

WITH cte_employee AS (
SELECT *, AVG(salary) OVER(partition by dept) as avg_dept_salary
FROM employee
)

SELECT *  FROM cte_employee 
WHERE salary > avg_dept_salary;

```

---

8. **Window Functions**: Write a query using a window function to assign a rank to employees based on their salaries within their respective departments.

```sql

SELECT *, dense_rank() OVER(PARTITION BY dept ORDER BY salary)
FROM employee;

```

---

9.  **Salary Comparison**: Create a query that compares the salaries of employees in the 'IT' department against the overall average salary of all employees.

```sql

SELECT *, ROUND(AVG(salary) OVER(), 2) as avg
FROM employee
WHERE dept = "IT";

```



