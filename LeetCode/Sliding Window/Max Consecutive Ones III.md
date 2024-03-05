### Description
Given a binary array `nums` and an integer `k`, return _the maximum number of consecutive_ `1`_'s in the array if you can flip at most_ `k` `0`'s.

### Test Cases
**Example 1:**

**Input:** nums = [1,1,1,0,0,0,1,1,1,1,0], k = 2
**Output:** 6
**Explanation:** [1,1,1,0,0,**1**,1,1,1,1,**1**]
Bolded numbers were flipped from 0 to 1. The longest subarray is underlined.

**Example 2:**

**Input:** nums = [0,0,1,1,0,0,1,1,1,0,1,1,0,0,0,1,1,1,1], k = 3
**Output:** 10
**Explanation:** [0,0,1,1,**1**,**1**,1,1,1,**1**,1,1,0,0,0,1,1,1,1]
Bolded numbers were flipped from 0 to 1. The longest subarray is underlined.

### Given Solution:
```Python
class Solution:

    def longestOnes(self, nums: List[int], k: int) -> int:

        Ptr1 = 0

        Ptr2 = 0    

        for Ptr2 in range(0, len(nums)):

            if nums[Ptr2] == 0:

                k -= 1

            if k<0:

                if nums[Ptr1] == 0:

                    k += 1

                Ptr1 += 1


        return Ptr2-Ptr1+1
```