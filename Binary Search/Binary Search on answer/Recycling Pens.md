### [Problem Link Here](https://www.codingninjas.com/codestudio/guided-paths/data-structures-algorithms/content/118621/offering/1377952?leftPanelTab=0)

#### T.C =  O(N)
```
def pens(n,r,k,c):
    ans = 0
    for i in range(1, n+1):
        # Check if i is a possible answer
        recycleCost = (n - i) * k
        netMoney = (r + recycleCost)
        # Can we buy mid number of pens with that money?
        if (netMoney < i * c):
            break
        else:
            ans = i
    return ans
```

#### T.C = O(logN)

```
def pens(n,r,k,c):
    lo, hi = 0, n
    while lo < hi:
        mid = (lo + hi + 1) // 2  #coz start from 1 pen so " +1 "
        recycleCost = (n - mid) * k
        netMoney = (r + recycleCost)
        # Can we buy mid number of pens with that money?
        if (netMoney >= mid * c):
            lo = mid
        else:
            hi = mid - 1
    return lo
```
