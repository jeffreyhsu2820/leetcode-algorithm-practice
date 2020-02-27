# leetcode-algorithm-practice
## 1. Two Sum
Given an array of integers, return indices of the two numbers such that they add up to a specific target.You may assume that each input would have exactly one solution, and you may not use the same element twice.

**Example:**

    Given nums = [2, 7, 11, 15], target = 9,

    Because nums[0] + nums[1] = 2 + 7 = 9,
    return [0, 1].

**Ans:**

    class Solution:
        def twoSum(self,nums, target):
            length=len(nums)
            for i in range(length):
                num2=target-nums[i]
                try:
                    return [i,nums.index(num2,i+1,length)]
                except ValueError:
                    continue
