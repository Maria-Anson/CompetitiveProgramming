> Table: `Customers`
> 
> <pre>+-------------+---------+
> | Column Name | Type    |
> +-------------+---------+
> | id          | int     |
> | name        | varchar |
> +-------------+---------+
> id is the primary key column for this table.
> Each row of this table indicates the ID and name of a customer.
> </pre>
> 
> Table: `Orders`
> 
> <pre>+-------------+------+
> | Column Name | Type |
> +-------------+------+
> | id          | int  |
> | customerId  | int  |
> +-------------+------+
> id is the primary key column for this table.
> customerId is a foreign key of the ID from the Customers table.
> Each row of this table indicates the ID of an order and the ID of the customer who ordered it.
> </pre>
> 
> Write an SQL query to report all customers who never order anything.
> 
> Return the result table in **any order**.
> 
> The query result format is in the following example.
> 
> **Example 1:**
> 
> <pre>**Input:** 
> Customers table:
> +----+-------+
> | id | name  |
> +----+-------+
> | 1  | Joe   |
> | 2  | Henry |
> | 3  | Sam   |
> | 4  | Max   |
> +----+-------+
> Orders table:
> +----+------------+
> | id | customerId |
> +----+------------+
> | 1  | 3          |
> | 2  | 1          |
> +----+------------+
> **Output:** 
> +-----------+
> | Customers |
> +-----------+
> | Henry     |
> | Max       |
> +-----------+</pre>
>
```
# Write your MySQL query statement below
SELECT cus.name as Customers
FROM (Customers cus LEFT JOIN Orders ord
        ON cus.id = ord.customerId)
WHERE ord.id IS NULL; 
```
> -- https://leetcode.com/problems/customers-who-never-order/description/?envType=study-plan&id=sql-i#qd-content
