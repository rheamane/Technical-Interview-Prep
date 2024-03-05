### Description
Two strings are considered **close** if you can attain one from the other using the following operations:

- Operation 1: Swap any two **existing** characters.
    - For example, `abcde -> aecdb`
- Operation 2: Transform **every** occurrence of one **existing** character into another **existing** character, and do the same with the other character.
    - For example, `aacabb -> bbcbaa` (all `a`'s turn into `b`'s, and all `b`'s turn into `a`'s)

You can use the operations on either string as many times as necessary.

Given two strings, `word1` and `word2`, return `true` _if_ `word1` _and_ `word2` _are **close**, and_ `false` _otherwise._

### Test Cases:
**Example 1:**

**Input:** word1 = "abc", word2 = "bca"
**Output:** true
**Explanation:** You can attain word2 from word1 in 2 operations.
Apply Operation 1: "abc" -> "acb"
Apply Operation 1: "acb" -> "bca"

**Example 2:**

**Input:** word1 = "a", word2 = "aa"
**Output:** false
**Explanation:** It is impossible to attain word2 from word1, or vice versa, in any number of operations.

**Example 3:**

**Input:** word1 = "cabbba", word2 = "abbccc"
**Output:** true
**Explanation:** You can attain word2 from word1 in 3 operations.
Apply Operation 1: "cabbba" -> "caabbb"
Apply Operation 2: "caabbb" -> "baaccc"
Apply Operation 2: "baaccc" -> "abbccc"

### My solution (Bad time complexity)
```Python
class Solution:

    def closeStrings(self, word1: str, word2: str) -> bool:

        if(len(word1)== len(word2)):

            if(set(word1) == set(word2)):

                # get a list of frequencies:

                list1 = sorted(Solution.findFrequencies(word1))

                list2 = sorted(Solution.findFrequencies(word2))

                if(list1 == list2):

                    return True

  

        return False

    def findFrequencies(word: str) -> list:

        freqDict = {}

        for i in range (0, len(word)):

            if(word[i] not in freqDict):

                freqDict[word[i]] = 1

            else:

                freqDict[word[i]] += 1

        return list(freqDict.values())
```