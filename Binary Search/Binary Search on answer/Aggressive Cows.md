### [Problem Link Here](https://www.codingninjas.com/codestudio/guided-paths/data-structures-algorithms/content/118621/offering/1377954)

```
def isPossible(a,k,n,m):
    count = 1
    co_od = a[0]
    for i in range(1,n):
        if a[i] - co_od >= m:
            count += 1
            co_od = a[i]
            if count == k:
                return True
    return False           
      

def aggressiveCows(a, k):
    n = len(a)
    a.sort()
    ans = 0
    l = 1; h = a[n-1]-a[0]
    while l <= h:
        m = (l+h)//2
        if isPossible(a,k,n,m):
            l = m + 1
            ans = m
        else:
            h = m-1
    return ans
```
