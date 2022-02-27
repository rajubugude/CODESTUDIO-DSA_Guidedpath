### [Problem Link Here](https://www.codingninjas.com/codestudio/guided-paths/data-structures-algorithms/content/118821/offering/1381907)

```
def rowWaveForm(mat):
    n = len(mat)
    m = len(mat[0])
    l = []
    for i in range(n):
        if i % 2 == 0:
            for j in range(m):
                l.append(mat[i][j])
        else:
            for j in range(m-1,-1,-1):
                l.append(mat[i][j])
    return l
```
