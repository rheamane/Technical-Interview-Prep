### Description:
For two strings `s` and `t`, we say "`t` divides `s`" if and only if `s = t + ... + t` (i.e., `t` is concatenated with itself one or more times).

Given two strings `str1` and `str2`, return _the largest string_ `x` _such that_ `x` _divides both_ `str1` _and_ `str2`.

### Approach:
```java
Suppose str1 = "ABCABC" and str2 = "ABC"
str1 + str2 = ABCABCABC
str2 + str1 = ABCABCABC
str1 + str2 == str2 + str1
return str.substr(0, gcd(size(str1), gcd(size(str2))))
where gcd(3, 6) = 3
So, answer is "ABC"

Also str1 = "LEET", str2 = "CODE"
str1 + str2 = "LEETCODE"
str2 + str1 = "CODELEET"
So, return ""
```

### Code: 
```python
class Solution:
    def gcdOfStrings(self, str1: str, str2: str) -> str:
        # Check if concatenated strings are equal or not, if not return ""
        if str1 + str2 != str2 + str1:
            return ""
        # If strings are equal than return the substring from 0 to gcd of size(str1), size(str2)
        from math import gcd
        return str1[:gcd(len(str1), len(str2))]
```

```java
class Solution {
    public String gcdOfStrings(String str1, String str2) {
        // Check if concatenated strings are equal or not, if not return ""
        if (!(str1 + str2).equals(str2 + str1))
            return "";
        // If strings are equal than return the substring from 0 to gcd of size(str1), size(str2)
        int gcd = gcd(str1.length(), str2.length());
        return str1.substring(0, gcd);
    }

    private int gcd(int a, int b) {
        return b == 0 ? a : gcd(b, a % b);
    }
}
```
