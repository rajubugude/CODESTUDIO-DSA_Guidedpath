### [Problem Link Here](https://www.codingninjas.com/codestudio/guided-paths/data-structures-algorithms/content/118621/offering/1377953)

#### O(N)
```
def squareRoot(a):
    if a == 0 or a == 1:
        return a
    else:
        ans = 1
        i = 2
        while i < a//2:
            t = i*i
            if t <= a:
                ans = i
                i += 1
            else:
                break
        return ans
```

#### O(logN)

```
def squareRoot(a):
    if a == 0 or a == 1:
        return a
    
    low = 0; high = a
    ans = -1
    while low <= high:
        mid = (low+high)//2
        if mid*mid > a:
            high = mid-1
        elif mid*mid < a:
            low = mid+1
            ans = mid
        else:
            ans = mid
            break
    return ans
```
