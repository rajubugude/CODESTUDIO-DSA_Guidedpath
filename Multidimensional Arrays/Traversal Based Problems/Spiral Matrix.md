### [Problem Link Here](https://www.codingninjas.com/codestudio/guided-paths/data-structures-algorithms/content/118821/offering/1381901)


#### Recursive Code
```
def spiralPathHelper(matrix, r, c, rows, cols, ans):
    
    # If outside the matrix.
    if (r >= rows or c >= cols):
        return
    
    # Push First Row.
    for p in range(c, cols):
        ans.append(matrix[r][p])
        
    # Push Last Column.
    for p in range(r + 1, rows):
        ans.append(matrix[p][cols - 1])
  
    # Push Last Row, if Last and First Row are not same.
    if((rows - 1) != r):
        
        for p in range(cols - 2, c - 1, -1):
            ans.append(matrix[rows - 1][p])
            
    # Print First Column,if Last and First Column are not same.
    if ((cols - 1) != c):
        
        for p in range(rows - 2, r, -1):
            ans.append(matrix[p][c])
            
    # Make recursive call on smaller submatrix.
    spiralPathHelper(matrix, r + 1, c + 1, rows - 1, cols - 1 ,ans)
    
def spiralPathMatrix(matrix, n, m):
    
    r = 0
    c = 0
    
    ans = []
    
    # Take help of helper function to pass recursive calls.
    spiralPathHelper(matrix, r, c, n, m, ans)
    
    return ans
```

#### Iterative
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
