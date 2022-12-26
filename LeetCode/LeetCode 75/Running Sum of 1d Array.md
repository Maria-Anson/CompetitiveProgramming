> Given an array `nums`. We define a running sum of an array as `runningSum[i] = sum(nums[0]…nums[i])`.
> 
> Return the running sum of `nums`.
> 
> **Example 1:**
> 
> <pre>**Input:** nums = [1,2,3,4]
> **Output:** [1,3,6,10]
> **Explanation:** Running sum is obtained as follows: [1, 1+2, 1+2+3, 1+2+3+4].</pre>
> 
> **Example 2:**
> 
> <pre>**Input:** nums = [1,1,1,1,1]
> **Output:** [1,2,3,4,5]
> **Explanation:** Running sum is obtained as follows: [1, 1+1, 1+1+1, 1+1+1+1, 1+1+1+1+1].</pre>
> 
> **Example 3:**
> 
> <pre>**Input:** nums = [3,1,2,10,1]
> **Output:** [3,4,6,16,17]
> </pre>
> 
> **Constraints:**
> 
> *   `1 <= nums.length <= 1000`
> *   `-10^6 <= nums[i] <= 10^6`
>
> -- https://leetcode.com/problems/running-sum-of-1d-array/?envType=study-plan&id=level-1#qd-content

```
class Solution:
    def runningSum(self, nums: List[int]) -> List[int]:
        # Calculating running sum
        for i in range(1,len(nums)):
            nums[i] = nums[i]+ nums[i-1]
        return nums
```
