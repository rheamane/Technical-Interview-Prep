#leetcode #easy #2pointers 
### Description
Given two strings `s` and `t`, return `true` _if_ `s` _is a **subsequence** of_ `t`_, or_ `false` _otherwise_.

A **subsequence** of a string is a new string that is formed from the original string by deleting some (can be none) of the characters without disturbing the relative positions of the remaining characters. (i.e., `"ace"` is a subsequence of `"abcde"` while `"aec"` is not).

### Test cases
**Example 1:**

**Input:** s = "abc", t = "ahbgdc"
**Output:** true

**Example 2:**

**Input:** s = "axc", t = "ahbgdc"
**Output:** false

### My code:
```Python
class Solution:

    def isSubsequence(self, s: str, t: str) -> bool:

        sPtr = 0

        tPtr = 0

        foundCount = 0

        while(tPtr < len(t) and (sPtr < len(s))):

            if(s[sPtr] == t[tPtr]):

                # move both

                foundCount += 1

                sPtr += 1

                tPtr += 1

            elif(s[sPtr] != t[tPtr]):

                #move tPtr

                tPtr += 1

        if(foundCount == len(s)):

            return True

        else:

            return False
```

### Stats:
![[Pasted image 20240206103546.png]]
