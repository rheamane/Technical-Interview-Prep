#easy #leetcode
### Constraints
- Given 2 strings, s and t
- Return true if t is an anagram of s
- False otherwise
- Use all original letters exactly once

### Test cases
1. **Input:** s = "anagram", t = "nagaram"
	**Output:** true

2. **Input:** s = "rat", t = "car"
	**Output:** false

### Brute Force 
```python
class Solution(object):
    def isAnagram(self, s, t):
        """
        :type s: str
        :type t: str
        :rtype: bool
        """

        listS = list(s)
        listT = list(t)

        listS.sort()
        listT.sort()

          if (listS == listT):
            return True
        return False
```

Running Time Complexity: $O(n*log(n))$

### Optimized
```python
class Solution:
    def isAnagram(self, s: str, t: str) -> bool:
        count = defaultdict(int)
        
        # Count the frequency of characters in string s
        for x in s:
            count[x] += 1
        
        # Decrement the frequency of characters in string t
        for x in t:
            count[x] -= 1
        
        # Check if any character has non-zero frequency
        for val in count.values():
            if val != 0:
                return False
        
        return True
```

Running Time Complexity: $O(n)$
