> Table: `Users`
> 
> <pre>+----------------+---------+
> | Column Name    | Type    |
> +----------------+---------+
> | user_id        | int     |
> | name           | varchar |
> +----------------+---------+
> user_id is the primary key for this table.
> This table contains the ID and the name of the user. The name consists of only lowercase and uppercase characters.
> </pre>
> 
> Write an SQL query to fix the names so that only the first character is uppercase and the rest are lowercase.
> 
> Return the result table ordered by `user_id`.
> 
> The query result format is in the following example.
> 
> **Example 1:**
> 
> <pre>**Input:** 
> Users table:
> +---------+-------+
> | user_id | name  |
> +---------+-------+
> | 1       | aLice |
> | 2       | bOB   |
> +---------+-------+
> **Output:** 
> +---------+-------+
> | user_id | name  |
> +---------+-------+
> | 1       | Alice |
> | 2       | Bob   |
> +---------+-------+</pre>
```
# Write your MySQL query statement below
SELECT user_id,  
CONCAT(UPPER(LEFT(name, 1)),
        REVERSE(LOWER(LEFT(REVERSE(name), LENGTH(name)-1)))) AS name
FROM Users
ORDER BY user_id;
```
>
> -- https://leetcode.com/problems/fix-names-in-a-table/description/?envType=study-plan&id=sql-i#qd-content
