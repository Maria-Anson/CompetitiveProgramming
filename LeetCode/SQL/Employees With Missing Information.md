> Table: `Employees`
> 
> <pre>+-------------+---------+
> | Column Name | Type    |
> +-------------+---------+
> | employee_id | int     |
> | name        | varchar |
> +-------------+---------+
> employee_id is the primary key for this table.
> Each row of this table indicates the name of the employee whose ID is employee_id.
> </pre>
> 
> Table: `Salaries`
> 
> <pre>+-------------+---------+
> | Column Name | Type    |
> +-------------+---------+
> | employee_id | int     |
> | salary      | int     |
> +-------------+---------+
> employee_id is the primary key for this table.
> Each row of this table indicates the salary of the employee whose ID is employee_id.
> </pre>
> 
> Write an SQL query to report the IDs of all the employees with **missing information**. The information of an employee is missing if:
> 
> *   The employee's **name** is missing, or
> *   The employee's **salary** is missing.
> 
> Return the result table ordered by `employee_id` **in ascending order**.
> 
> The query result format is in the following example.
> 
> **Example 1:**
> 
> <pre>**Input:** 
> Employees table:
> +-------------+----------+
> | employee_id | name     |
> +-------------+----------+
> | 2           | Crew     |
> | 4           | Haven    |
> | 5           | Kristian |
> +-------------+----------+
> Salaries table:
> +-------------+--------+
> | employee_id | salary |
> +-------------+--------+
> | 5           | 76071  |
> | 1           | 22517  |
> | 4           | 63539  |
> +-------------+--------+
> **Output:** 
> +-------------+
> | employee_id |
> +-------------+
> | 1           |
> | 2           |
> +-------------+
> **Explanation:** 
> Employees 1, 2, 4, and 5 are working at this company.
> The name of employee 1 is missing.
> The salary of employee 2 is missing.</pre>
```
# Write your MySQL query statement below
SELECT em.employee_id
    FROM Employees em 
    LEFT JOIN Salaries sa
    ON em.employee_id = sa.employee_id
    WHERE sa.salary IS NULL
UNION
SELECT sa.employee_id
    FROM Employees em 
    RIGHT JOIN Salaries sa
    ON em.employee_id = sa.employee_id
    WHERE em.name IS NULL
ORDER BY employee_id;
```
>
> -- https://leetcode.com/problems/employees-with-missing-information/description/?envType=study-plan&id=sql-i#qd-content
