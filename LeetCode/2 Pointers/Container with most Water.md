#medium #leetcode #2pointers 
### Description
You are given an integer array `height` of length `n`. There are `n` vertical lines drawn such that the two endpoints of the `ith` line are `(i, 0)` and `(i, height[i])`.

Find two lines that together with the x-axis form a container, such that the container contains the most water.

Return _the maximum amount of water a container can store_.
### Code:
```Python
class Solution:

    def maxArea(self, height: List[int]) -> int:        

        maxArea = 0

        leftPtr = 0

        rightPtr = len(height) - 1

        while(leftPtr != rightPtr):

            if(height[leftPtr] <= height[rightPtr]):

                area = height[leftPtr]* (rightPtr - leftPtr)

                leftPtr+=1

            elif(height[leftPtr] > height[rightPtr]):

                area = height[rightPtr]* (rightPtr - leftPtr)

                rightPtr-=1

            if(area >= maxArea):

                maxArea = area

        return maxArea
```