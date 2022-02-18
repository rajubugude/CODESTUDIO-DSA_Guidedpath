### [Problem Link Here](https://www.codingninjas.com/codestudio/guided-paths/data-structures-algorithms/content/118509/offering/1376560?leftPanelTab=0)

#### [Explanation](https://www.youtube.com/watch?v=QhPdNS143Qg)

```
def checkValidString(s):
    leftMin, leftMax = 0, 0
    for c in s:
        if c == "(":
            leftMin, leftMax = leftMin + 1, leftMax + 1
        elif c == ")":
            leftMin, leftMax = leftMin - 1, leftMax - 1
        else:
            leftMin, leftMax = leftMin - 1, leftMax + 1
        if leftMax < 0:
            return False
        if leftMin < 0: # required because -> s = ( * ) (
            leftMin = 0
    return leftMin == 0
```
