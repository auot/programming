https://leetcode.com/problems/palindromic-substrings/description/

Given a string, your task is to count how many palindromic substrings in this string.

```python3
class Solution:
    def countSubstrings(self, s):
        """
        :type s: str
        :rtype: int
        """
        def count(x, y):
            n = 0
            while x >= 0 and y < len(s) and s[x] == s[y]:
                n += 1
                x -= 1
                y += 1
            return n
        
        i, j = 0, 0
        p = 0
        while j < len(s):
            p += count(i, j)
            if i == j:
                j += 1
            else:
                i += 1
        return p
```
