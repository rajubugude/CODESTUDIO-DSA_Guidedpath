### [Problem Link Here](https://www.codingninjas.com/codestudio/guided-paths/data-structures-algorithms/content/118509/offering/1376556)

#### Bruteforce
```
def maxArea(h):
    n = len(h)
    maxarea = 0
    for i in range(n):
        temp = 0
        for j in range(i+1,n):
            area = (j-i)*min(h[i],h[j])
            temp = max(area,temp)
        maxarea = max(temp,maxarea)
    return maxarea
```

#### Optimal, T.C = O(N)
```
def maxArea(h):
    n = len(h)
    area = 0
    i = 0
    j = n-1
    while i<j:
        area = max(area,min(h[i],h[j])*(j-i))
        if h[i] < h[j]:
            i += 1
        else:
            j -= 1
    return area
```
