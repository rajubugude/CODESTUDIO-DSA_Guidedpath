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
    r = 0
    rows = n
    c = 0
    cols = m
    # Make array to store path.
    path =[]
    while r < rows and c < cols:
        
        # Push the first row from the remaining rows.
        for i in range (c, cols):
            path.append(matrix[r][i])
        r += 1
        
        # Push the last column from the remaining columns. 
        for i in range (r, rows):
            path.append(matrix[i][cols - 1])
        cols -= 1
        
        # Push the last row from the remaining rows. 
        if r < rows:          
            for i in range (cols - 1, c - 1, -1):
                path.append(matrix[rows - 1][i])
            rows -= 1
        
        # Push the first column from the remaining columns. 
        if c < cols:            
            for i in range (rows - 1, r - 1, -1):
                path.append(matrix[i][c])
            c += 1
            
    return path
```
