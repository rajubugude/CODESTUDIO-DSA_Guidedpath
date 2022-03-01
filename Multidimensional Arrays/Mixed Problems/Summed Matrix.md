### [Problem Link Here](https://www.codingninjas.com/codestudio/guided-paths/data-structures-algorithms/content/118821/offering/1381910)

```
def query(n, q):
    if q <= n+1:
        return q-1
    else:
        return 2*n-q+1
```
