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
## 15. 3Sum
Given an array nums of n integers, are there elements a, b, c in nums such that a + b + c = 0? Find all unique triplets in the array which gives the sum of zero.

Note:
The solution set must not contain duplicate triplets.

**Example:**

    Given array nums = [-1, 0, 1, 2, -1, -4],

    A solution set is:
    [
      [-1, 0, 1],
      [-1, -1, 2]
    ]
**Ans:**

    class Solution:
        def threeSum(self, nums: List[int]) -> List[List[int]]:
            res = set()
            nums=sorted(nums)
            length = len(nums)
            for i in range(length-2):
                if nums[i]>0: 
                    break
                l=i+1
                r = length-1
                while l<r:
                    total = nums[i]+nums[l]+nums[r]
                    if total<0:
                        l+=1
                    elif total>0:
                        r-=1
                    else:
                        res.add(tuple([nums[i], nums[l], nums[r]]))
                        l+=1
                        r-=1
            return list(res)
