### [Problem Link Here](https://www.codingninjas.com/codestudio/guided-paths/data-structures-algorithms/content/118821/offering/1381914)
```
def coverageOfMatrix(mat):
    n = len(mat)
    m = len(mat[0])
    count = 0
    for i in range(n):
        for j in range(m):
            if mat[i][j] == 0:
                #top
                if i >= 1 and mat[i-1][j] == 1:
                    count +=1
                #bottom
                if i < n - 1 and mat[i][j-1]==1:
                    count += 1
                #left
                if j >= 1 and mat[i][j-1] == 1:
                    count += 1
                #right
                if j < m-1 and mat[i][j+1] == 1:
                    count += 1
    return count
```
