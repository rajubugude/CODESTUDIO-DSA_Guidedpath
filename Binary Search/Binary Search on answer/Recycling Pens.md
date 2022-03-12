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
def recyclePens(n, r, k, c):
    lo, hi = 0, n
    ans = 0
    while lo <= hi:
        mid = (lo + hi) // 2
        recycleCost = (n-mid) * k
        netMoney = (r + recycleCost)

        if (netMoney >= mid * c):
            lo = mid + 1
            ans = mid
        elif netMoney < mid * c:
            hi = mid - 1
#         else:
#             ans = mid
#             break
    return ans
```
