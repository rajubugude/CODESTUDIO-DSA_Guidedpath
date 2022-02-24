### [Problem Link Here](https://www.codingninjas.com/codestudio/guided-paths/data-structures-algorithms/content/118821/offering/1381899)

```
def isMatrixSymmetric(matrix):
    # Write your code here.  
    n = len(matrix)
    for i in range(n):
        for j in range(n):
            if i <= j:
                if matrix[i][j] != matrix[j][i]:
                    return False
    return True
```
