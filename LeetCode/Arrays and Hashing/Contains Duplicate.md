#easy #leetcode
### Constraints
- True if any value appears at least twice 
- False if every element is distinct

### Test Cases
[1, 2, 3, 1]
[1, 2, 3, 4]
[1,1,1,3,3,4,3,2,4,2]

### Brute Force Method

```python
class Solution(object):

    def containsDuplicate(self, nums):

        """
        :type nums: List[int]

        :rtype: bool
        """

        result = False

        for k in range(0, len(nums)):

            for i in range(k+1, len(nums)):

                if(nums[k] == nums[i]):

                    result = True

        return result
```

Running Time Complexity: $O(n^2)$

### Optimized
```python
class Solution(object):

    def containsDuplicate(self, nums):

        """ 
        :type nums: List[int]

        :rtype: bool

        """

        hashset = set()

        for n in nums:

            if n in hashset:

                return True

            hashset.add(n)

        return False
```

Running Time Complexity: $O(n)$
