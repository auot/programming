https://leetcode.com/problems/positions-of-large-groups/description/

In a string S of lowercase letters, these letters form consecutive groups of the same character.

For example, a string like S = "abbxxxxzyy" has the groups "a", "bb", "xxxx", "z" and "yy".

Call a group large if it has 3 or more characters.  We would like the starting and ending positions of every large group.

```python3
class Solution:
    def largeGroupPositions(self, S):
        """
        :type S: str
        :rtype: List[List[int]]
        """
        counter = 1
        start = 0
        groups = []
        last = ''
        
        for i, c in enumerate(S):
            if c == last:
                counter += 1
            elif c != last:
                if counter > 2:
                    groups.append([start, i - 1])
                counter = 1
                start = i
            last = c
            
        if counter > 2:
            groups.append([start, i])
            
        return groups
```
