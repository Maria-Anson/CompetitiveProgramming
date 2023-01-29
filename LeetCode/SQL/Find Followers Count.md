> Table: `Followers`
> 
> <pre>+-------------+------+
> | Column Name | Type |
> +-------------+------+
> | user_id     | int  |
> | follower_id | int  |
> +-------------+------+
> (user_id, follower_id) is the primary key for this table.
> This table contains the IDs of a user and a follower in a social media app where the follower follows the user.</pre>
> 
> Write an SQL query that will, for each user, return the number of followers.
> 
> Return the result table ordered by `user_id` in ascending order.
> 
> The query result format is in the following example.
> 
> **Example 1:**
> 
> <pre>**Input:** 
> Followers table:
> +---------+-------------+
> | user_id | follower_id |
> +---------+-------------+
> | 0       | 1           |
> | 1       | 0           |
> | 2       | 0           |
> | 2       | 1           |
> +---------+-------------+
> **Output:** 
> +---------+----------------+
> | user_id | followers_count|
> +---------+----------------+
> | 0       | 1              |
> | 1       | 1              |
> | 2       | 2              |
> +---------+----------------+
> **Explanation:** 
> The followers of 0 are {1}
> The followers of 1 are {0}
> The followers of 2 are {0,1}</pre>
>
```
# Write your MySQL query statement below
SELECT user_id, COUNT(follower_id) AS followers_count
FROM Followers
GROUP BY user_id
ORDER BY user_id;
```
> -- https://leetcode.com/problems/find-followers-count/description/?envType=study-plan&id=sql-i#qd-content