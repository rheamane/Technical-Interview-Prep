#leetcode #medium

### Description
Given an input string `s`, reverse the order of the **words**.

A **word** is defined as a sequence of non-space characters. The **words** in `s` will be separated by at least one space.

Return _a string of the words in reverse order concatenated by a single space._

**Note** that `s` may contain leading or trailing spaces or multiple spaces between two words. The returned string should only have a single space separating the words. Do not include any extra spaces.

### Test Cases

**Example 1:**

**Input:** s = "the sky is blue"
**Output:** "blue is sky the"

**Example 2:**

**Input:** s = "  hello world  "
**Output:** "world hello"
**Explanation:** Your reversed string should not contain leading or trailing spaces.

**Example 3:**

**Input:** s = "a good   example"
**Output:** "example good a"
**Explanation:** You need to reduce multiple spaces between two words to a single space in the reversed string.

### My Solution
```python
class Solution:

    def reverseWords(self, s: str) -> str:

        wordArr = []

        startIndex = 0

        revStr = ""

        wordArr = s.split()

        print(wordArr)

        for j in range(len(wordArr)-1, -1, -1):

            revStr += wordArr[j] + " "

        revStr = revStr.strip()

        return revStr
```

### Given Solution
```python
class Solution:
    def reverseWords(self, s: str) -> str:
        # Trim the input string to remove leading and trailing spaces
        i, j = 0, len(s) - 1
        while i <= j and s[i] == ' ':
            i += 1  # Find the first non-space character
        while j >= i and s[j] == ' ':
            j -= 1  # Find the last non-space character
        s = s[i : j + 1]  # Extract the trimmed substring

        # Split the trimmed string into words based on spaces
        words = s.split()  # Tokenize the string into words

        # Initialize the output string
        out = []

        # Iterate through the words in reverse order
        for k in range(len(words) - 1, 0, -1):
            # Append the current word and a space to the output
            out.append(words[k])
        # Append the first word to the output (without trailing space)
        out.append(words[0])

        return ' '.join(out)  # Concatenate the reversed words
```
