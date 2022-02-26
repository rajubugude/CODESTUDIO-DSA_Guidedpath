### [Problem Link Here](https://www.codingninjas.com/codestudio/guided-paths/data-structures-algorithms/content/118821/offering/1381904)

```
def inplaceRotate(a, n):
    ans = []
    for i in range(n-1,-1,-1):
        temp = []
        for j in range(n):
            temp.append(a[j][i])
        ans.append(temp)
    return ans
```
