#easy #leetcode 
### Description
Given a string `s`, reverse only all the vowels in the string and return it.

The vowels are `'a'`, `'e'`, `'i'`, `'o'`, and `'u'`, and they can appear in both lower and upper cases, more than once.

### Test cases
**Example 1:**

**Input:** s = "hello"
**Output:** "holle"

**Example 2:**

**Input:** s = "leetcode"
**Output:** "leotcede"

### My Solution 
```Python
class Solution:

    def reverseVowels(self, s: str) -> str:

        vowelArr = []

        indexArr = []

        baseVowelArr = ["a", "A", "e", "E", "i", "I", "o", "O", "u", "U"]

        for i in range (0, len(s)):

            if(s[i] in baseVowelArr):

                vowelArr.append(s[i])

                indexArr.append(i)

        s = list(s)

        for i in range(0, len(vowelArr)):

            j = (len(vowelArr) - 1) - i

            s[indexArr[i]] = vowelArr[j]

            j = 0

  

        s = "".join(s)

        return s
```

### Stats
![[Pasted image 20240129132238.png]]
### Given Solution
```Python
class Solution:
    def reverseVowels(self, s: str) -> str:
        vowels = set(['a', 'e', 'i', 'o', 'u', 'A', 'E', 'I', 'O', 'U'])
        s = list(s)
        left, right = 0, len(s) - 1
        
        while left < right:
            while left < right and s[left].lower() not in vowels:
                left += 1
            while left < right and s[right].lower() not in vowels:
                right -= 1

            s[left], s[right] = s[right], s[left]
            left += 1
            right -= 1

        return "".join(s)
```
