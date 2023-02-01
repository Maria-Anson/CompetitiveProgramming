> You are a professional robber planning to rob houses along a street. Each house has a certain amount of money stashed. All houses at this place are **arranged in a circle.** That means the first house is the neighbor of the last one. Meanwhile, adjacent houses have a security system connected, and **it will automatically contact the police if two adjacent houses were broken into on the same night**.
> 
> Given an integer array `nums` representing the amount of money of each house, return _the maximum amount of money you can rob tonight **without alerting the police**_.
> 
> **Example 1:**
> 
> <pre>**Input:** nums = [2,3,2]
> **Output:** 3
> **Explanation:** You cannot rob house 1 (money = 2) and then rob house 3 (money = 2), because they are adjacent houses.
> </pre>
> 
> **Example 2:**
> 
> <pre>**Input:** nums = [1,2,3,1]
> **Output:** 4
> **Explanation:** Rob house 1 (money = 1) and then rob house 3 (money = 3).
> Total amount you can rob = 1 + 3 = 4.
> </pre>
> 
> **Example 3:**
> 
> <pre>**Input:** nums = [1,2,3]
> **Output:** 3
> </pre>
> 
> **Constraints:**
> 
> *   `1 <= nums.length <= 100`
> *   `0 <= nums[i] <= 1000`
>
```
class Solution:
    def rob_helper(self,nums):
        n = len(nums)
        if n==1:
            return nums[0]
        else:
            dp = [0 for _ in range(n)]
            dp[0] = nums[0]
            dp[1] = max(nums[0], nums[1])
            for i in range(2,n):
                # Bellman equation
                dp[i] = max(dp[i-1], nums[i]+dp[i-2])
        return dp[-1]

    def rob(self, nums: List[int]) -> int:
        n = len(nums)
        if n==1: 
            return nums[0]
        # Rob from 1st house to last before house
        dp1 = self.rob_helper(nums[:-1])
        # Rob from 2nd house to last house
        dp2 = self.rob_helper(nums[1:])
        return(max(dp1,dp2))
```
> -- https://leetcode.com/problems/house-robber-ii/description/?envType=study-plan&id=dynamic-programming-i#qd-content
