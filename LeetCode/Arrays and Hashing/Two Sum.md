#easy #leetcode 
### Constraints
- Array of integers: nums[]
- int target
- return indices of 2 numbers so that they add up to the target
- - **Only one valid answer exists.**
### Test Cases
1. **Input:** nums = [2,7,11,15], target = 9
	**Output:** [0,1]
2. **Input:** nums = [3,2,4], target = 6
	**Output:** [1,2]
3.  **Input:** nums = [3,3], target = 6
	**Output:** [0,1]

### Brute Force
```python
class Solution(object):
    def twoSum(self, nums, target):
        """
        :type nums: List[int]
        :type target: int
        :rtype: List[int]
        """
        for k in range(0, len(nums)):
            for i in range(k+1, len(nums)):
                sumnos = nums[k] + nums[i]
                if(sumnos == target):
                    return [k,i]
        return
```

Running Time Complexity: $O(n^2)$
### Optimized
```python
class Solution(object):
    def twoSum(self, nums, target):
        """
        :type nums: List[int]
        :type target: int
        :rtype: List[int]
        """
        prevMap = {}  # val -> index
        
        for i, n in enumerate(nums):
            diff = target - n
            if diff in prevMap:
                return [prevMap[diff], i]
            prevMap[n] = i
```
Running Time Complexity: $O(n)$
