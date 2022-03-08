### [Problem Link Here](https://www.codingninjas.com/codestudio/guided-paths/data-structures-algorithms/content/118621/offering/1377945)

```
def findInMatrix(k, matrix):
    n = len(matrix)
    m = len(matrix[0])
    i = 0
    while i<n:
        low  = 0
        high = m-1
        while low <= high:
            mid = (low+high)//2
            if matrix[i][mid] == k:
                return True
            if matrix[i][mid]>k:
                high = mid-1
            else:
                low = mid+1
        i+=1
    return False
```

#### Optimal

```
def findInMatrix(x, arr):
    n = len(arr)
    m = len(arr[0])

    low = 0
    high = (n - 1) * m + m - 1
    while (low <= high):
        mid = (low + high) // 2
        row = mid // m
        col = mid % m     
        #    Element found.
        if (arr[row][col] == x):
            return True        
        #    Reduce the search space
        elif (arr[row][col] > x):
            high = mid - 1
        #    Reduce the search space.
        else:
            low = mid + 1
    return False
```
