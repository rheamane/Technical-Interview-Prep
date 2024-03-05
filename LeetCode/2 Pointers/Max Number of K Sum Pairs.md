#medium #leetcode #2pointers 
### Description:
You are given an integer array `nums` and an integer `k`.

In one operation, you can pick two numbers from the array whose sum equals `k` and remove them from the array.

Return _the maximum number of operations you can perform on the array_.

### My code:
```Python
class Solution:

    def maxOperations(self, nums: List[int], k: int) -> int:

        count = 0

        nums.sort()

        leftPtr = 0

        rightPtr = len(nums) - 1

        while(leftPtr < rightPtr):

            sumPair = nums[leftPtr] + nums[rightPtr]

            if(sumPair == k):

                count += 1

                nums[leftPtr] = 0

                nums[rightPtr]= 0

                leftPtr += 1

                rightPtr -= 1

  

            elif(sumPair < k):

                leftPtr+=1

  

            elif(sumPair > k):

                rightPtr-=1

        for i in nums:

            if(i == 0):

                nums.remove(i)

  

        print(nums)

        return(count)
```