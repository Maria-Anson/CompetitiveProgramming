> Table: `Customer`
> 
> <pre>+-------------+---------+
> | Column Name | Type    |
> +-------------+---------+
> | id          | int     |
> | name        | varchar |
> | referee_id  | int     |
> +-------------+---------+
> id is the primary key column for this table.
> Each row of this table indicates the id of a customer, their name, and the id of the customer who referred them.
> </pre>
> 
> Write an SQL query to report the names of the customer that are **not referred by** the customer with `id = 2`.
> 
> Return the result table in **any order**.
> 
> The query result format is in the following example.
> 
> **Example 1:**
> 
> <pre>**Input:** 
> Customer table:
> +----+------+------------+
> | id | name | referee_id |
> +----+------+------------+
> | 1  | Will | null       |
> | 2  | Jane | null       |
> | 3  | Alex | 2          |
> | 4  | Bill | null       |
> | 5  | Zack | 1          |
> | 6  | Mark | 2          |
> +----+------+------------+
> **Output:** 
> +------+
> | name |
> +------+
> | Will |
> | Jane |
> | Bill |
> | Zack |
> +------+</pre>
```
# Write your MySQL query statement below
SELECT name FROM Customer
WHERE (referee_id IS null OR
        referee_id <>2);
```
>
> -- https://leetcode.com/problems/find-customer-referee/description/?envType=study-plan&id=sql-i#qd-content
