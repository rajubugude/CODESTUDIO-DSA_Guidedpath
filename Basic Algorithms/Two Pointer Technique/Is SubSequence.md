### [Problem Link Here](https://www.codingninjas.com/codestudio/guided-paths/data-structures-algorithms/content/118509/offering/1376572)

```
def isSubSequence(s1, s2):
    n1 = len(s1)
    n2 = len(s2)
    cur = 0
    for i in range(n2):
        if cur != n1 and s1[cur] == s2[i]:
            cur += 1
    if cur == n1:
        return True
    return False
```
