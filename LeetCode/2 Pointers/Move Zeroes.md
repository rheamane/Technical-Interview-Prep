#easy #leetcode #2pointers
### Description:
Given an integer array `nums`, move all `0`'s to the end of it while maintaining the relative order of the non-zero elements.

**Note** that you must do this in-place without making a copy of the array.

### Test cases:
**Example 1:**

**Input:** nums = [0,1,0,3,12]
**Output:** [1,3,12,0,0]

**Example 2:**

**Input:** nums = [0]
**Output:** [0]

### Solution
```Python
class Solution:

    def moveZeroes(self, nums: List[int]) -> None:

        """

        Do not return anything, modify nums in-place instead.

        """

        # for len = 1 nums remains the same

        if(len(nums) > 1):

            ptr1 = 0

            ptr2 = 1

            while(ptr2 < len(nums)):

                if(nums[ptr1] == 0 and nums[ptr2] != 0):
                    # todo: switch
                    temp = nums[ptr1]

                    nums[ptr1] = nums[ptr2]

                    nums[ptr2] = temp

                    # move ptr 1++

                    ptr1 += 1

                elif(nums[ptr1] == 0 and nums[ptr2] == 0):
                # todo: move ptr2 ++

                    ptr2 += 1

                else:
                    #elif((ptr1 != 0 and ptr2 == 0) or (ptr1 != 0 and ptr2 != 0)):

                    # todo: move both over

                    ptr1 += 1

                    ptr2 += 1

        print(nums)
```

