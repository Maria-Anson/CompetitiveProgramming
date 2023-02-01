> You are given an integer array `cost` where `cost[i]` is the cost of `ith` step on a staircase. Once you pay the cost, you can either climb one or two steps.
> 
> You can either start from the step with index `0`, or the step with index `1`.
> 
> Return _the minimum cost to reach the top of the floor_.
> 
> **Example 1:**
> 
> <pre>**Input:** cost = [10,15,20]
> **Output:** 15
> **Explanation:** You will start at index 1.
> - Pay 15 and climb two steps to reach the top.
> The total cost is 15.
> </pre>
> 
> **Example 2:**
> 
> <pre>**Input:** cost = [1,100,1,1,1,100,1,1,100,1]
> **Output:** 6
> **Explanation:** You will start at index 0.
> - Pay 1 and climb two steps to reach index 2.
> - Pay 1 and climb two steps to reach index 4.
> - Pay 1 and climb two steps to reach index 6.
> - Pay 1 and climb one step to reach index 7.
> - Pay 1 and climb two steps to reach index 9.
> - Pay 1 and climb one step to reach the top.
> The total cost is 6.
> </pre>
> 
> **Constraints:**
> 
> *   `2 <= cost.length <= 1000`
> *   `0 <= cost[i] <= 999`
>
```
class Solution:
    def minCostClimbingStairs(self, cost: List[int]) -> int:
        # So that we can check for the last two steps
        cost.append(0)

        if len(cost)==1:
            return cost[0]
        else:
            n = len(cost)
            dp = [0 for _ in range(n)]
            dp[0:2] = cost[0:2]
            for i in range(2,n):
                # Bellman equation
                dp[i] = min(cost[i]+ dp[i-1], cost[i]+dp[i-2])
            print(dp)
        return dp[-1]
```
> -- https://leetcode.com/problems/min-cost-climbing-stairs/description/?envType=study-plan&id=dynamic-programming-i#qd-content
