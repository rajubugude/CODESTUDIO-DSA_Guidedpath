### [Problem Link Here](https://www.codingninjas.com/codestudio/guided-paths/data-structures-algorithms/content/118821/offering/1381912)

```
def goodMatrix(n,m,mat):
    grid = []
    for i in range(n):
        for j in range(m):
            if mat[i][j] == 0:
                grid.append([i,j])
    #row
    for x,y in grid:
        for i in range(m):
            mat[x][i] = 0
    #col
    for x,y in grid:
        for i in range(n):
            mat[i][y] = 0
    return mat


t = int(input())
while t:
    t -= 1
    n,m = map(int,input().split())
    mat = []
    for i in range(n):
        l = list(map(int,input().split()))
        mat.append(l)
    print(goodMatrix(n,m,mat))
    
```
