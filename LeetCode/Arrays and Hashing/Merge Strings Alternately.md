### Constraints
You are given two strings `word1` and `word2`. Merge the strings by adding letters in alternating order, starting with `word1`. If a string is longer than the other, append the additional letters onto the end of the merged string.

Return _the merged string._
### Test cases

1. Input: word1 = "abc", word2 = "pqr"
Output: "apbqcr"
Explanation: The merged string will be merged as so:
word1:  a   b   c
word2:    p   q   r
merged: a p b q c r

2. **Input:** word1 = "ab", word2 = "pqrs"
**Output:** "apbqrs"
**Explanation:** Notice that as word2 is longer, "rs" is appended to the end.
word1:  a   b 
word2:    p   q   r   s
merged: a p b q   r   s

3. **Input:** word1 = "abcd", word2 = "pq"
**Output:** "apbqcd"
**Explanation:** Notice that as word1 is longer, "cd" is appended to the end.
word1:  a   b   c   d
word2:    p   q 
merged: a p b q c   d


### Brute Force
```python
class Solution:

    def mergeAlternately(self, word1: str, word2: str) -> str:

        finalWord = ""

        if(len(word1) > len(word2)):

            for i in range(0, len(word2)):

                finalWord = finalWord +(word1[i] + word2[i])

  

            finalWord += word1[len(word2) :]

        elif(len(word1) < len(word2)):

            for i in range(0, len(word1)):

                finalWord = finalWord +(word1[i] + word2[i])

  

            finalWord += word2[len(word1) :]

        else:

            for i in range(0, len(word1)):

                finalWord = finalWord +(word1[i] + word2[i])        

  

        return finalWord
```

### Optimize
```python
class Solution(object):
    def mergeAlternately(self, word1, word2):
        """
        :type word1: str
        :type word2: str
        :rtype: str
        """
        result = []
        i = 0
        while i < len(word1) or i < len(word2):
            if i < len(word1):
                result.append(word1[i])
            if i < len(word2):
                result.append(word2[i])
            i += 1
        return ''.join(result)
```

