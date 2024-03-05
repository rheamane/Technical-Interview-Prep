### Description


### My solution (times out)
```python
class Solution:

    def productExceptSelf(self, nums: List[int]) -> List[int]:

        prodArr = []

        currIndex = 0

        for i in range(0, len(nums)):

            prodArr.append(Math.prod(nums[currIndex:i]).astype(int)*Math.prod(nums[i+1:len(nums)]).astype(int))          

        print(prodArr)

        return prodArr
```

### Given Solution
```python
class Solution:

    def productExceptSelf(self, nums: List[int]) -> List[int]:

        n = len(nums)

        prefix_product = 1

        postfix_product = 1

        result = [0]*n

        for i in range(n):

            result[i] = prefix_product

            prefix_product *= nums[i]

        for i in range(n-1,-1,-1):

            result[i] *= postfix_product

            postfix_product *= nums[i]

        return result
```