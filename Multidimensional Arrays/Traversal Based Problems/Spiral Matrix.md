### [Problem Link Here](https://www.codingninjas.com/codestudio/guided-paths/data-structures-algorithms/content/118821/offering/1381901)

```
def spiralPathMatrix(matrix, n, m):
    startI,startJ = 0, 0
    endI,  endJ = m-1, n-1
    ans = []

    while startI <= endI and startJ <= endJ:
        
        #toprow
        if startI <= endI:
            l, r = startI, endI
            for j in range(l, r+1):
                ans.append(matrix[startJ][j])
            startJ += 1
        else:
            break
        
        #rytside
        if startJ <= endJ:
            t, b = startJ, endJ
            for i in range(t, b+1):
                ans.append(matrix[i][endI])
            endI -= 1
        else:
            break
        
        #bottom
        if startI <= endI:
            l, r = startI, endI
            for j in range(r, l-1, -1):
                ans.append(matrix[endJ][j])
            endJ -= 1
        else:
            break
        
        #leftside
        if startJ <= endJ:
            t, b = startJ, endJ
            for i in range(b, t-1, -1):
                ans.append(matrix[i][startI])
            startI += 1
        else:
            break
    return ans 
```
