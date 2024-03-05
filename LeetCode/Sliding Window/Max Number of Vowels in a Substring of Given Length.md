### Description:
Given a string `s` and an integer `k`, return _the maximum number of vowel letters in any substring of_ `s` _with length_ `k`.

**Vowel letters** in English are `'a'`, `'e'`, `'i'`, `'o'`, and `'u'`.

### Test Cases:
**Example 1:**

**Input:** s = "abciiidef", k = 3
**Output:** 3
**Explanation:** The substring "iii" contains 3 vowel letters.

**Example 2:**

**Input:** s = "aeiou", k = 2
**Output:** 2
**Explanation:** Any substring of length 2 contains 2 vowels.

**Example 3:**

**Input:** s = "leetcode", k = 3
**Output:** 2
**Explanation:** "lee", "eet" and "ode" contain 2 vowels.

### Solution:
```Python
class Solution:

    def maxVowels(self, s: str, k: int) -> int:

        vowels = ['a', 'e', 'i', 'o', 'u']

        count = 0

        maxCount = 0

        # Made window

        subStr = s[0:0+k]

        # Calculating result of window

        for i in subStr:

            if(i in vowels):

                count += 1

        maxCount = count

        # looping the window

        for j in range(k, len(s)):

            # subStr = s[j:j+k]

            if(s[j] in vowels):

                count += 1

            if(s[j-k] in vowels):

                count -= 1

            if(count > maxCount):

                maxCount = count          

        return maxCount
```
