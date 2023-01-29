> Table: `Employee`
> 
> <pre>+-------------+------+
> | Column Name | Type |
> +-------------+------+
> | id          | int  |
> | salary      | int  |
> +-------------+------+
> id is the primary key column for this table.
> Each row of this table contains information about the salary of an employee.
> </pre>
> 
> Write an SQL query to report the second highest salary from the `Employee` table. If there is no second highest salary, the query should report `null`.
> 
> The query result format is in the following example.
> 
> **Example 1:**
> 
> <pre>**Input:** 
> Employee table:
> +----+--------+
> | id | salary |
> +----+--------+
> | 1  | 100    |
> | 2  | 200    |
> | 3  | 300    |
> +----+--------+
> **Output:** 
> +---------------------+
> | SecondHighestSalary |
> +---------------------+
> | 200                 |
> +---------------------+
> </pre>
> 
> **Example 2:**
> 
> <pre>**Input:** 
> Employee table:
> +----+--------+
> | id | salary |
> +----+--------+
> | 1  | 100    |
> +----+--------+
> **Output:** 
> +---------------------+
> | SecondHighestSalary |
> +---------------------+
> | null                |
> +---------------------+</pre>
>
```
# Write your MySQL query statement below
SELECT MAX(salary) AS SecondHighestSalary
        FROM Employee
        WHERE salary < (
            SELECT MAX(salary) from Employee
        );
```
> -- https://leetcode.com/problems/second-highest-salary/description/?envType=study-plan&id=sql-i#qd-content
