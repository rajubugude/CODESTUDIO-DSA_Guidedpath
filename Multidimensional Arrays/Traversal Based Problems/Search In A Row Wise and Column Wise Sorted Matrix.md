### [Problem Link Here](https://www.codingninjas.com/codestudio/guided-paths/data-structures-algorithms/content/118821/offering/1381898)

#### T.C = O(NlogN)
```
def search(matrix, k):
   n = len(matrix)
   i = 0
   while i<n:
       low  = 0
       high = n-1
       while low <= high:
           mid = (low+high)//2
           if matrix[i][mid] == k:
               return [i,mid]
           if matrix[i][mid]>k:
               high = mid-1
           else:
               low = mid+1
       i+=1  
   p1= -1
   p2 = -1
   return [p1,p2]
```

#### T.C = O(N)

```
def search(matrix, x):
    
    n = len(matrix)
    
    if n == 0:
        return -1, -1
    
    i = 0
    j = n - 1
    
    while(i < n and j >= 0):
        
        if matrix[i][j] == x:
            return i, j
        # Move to the previous column.
        if matrix[i][j] > x:
            j -= 1
        # Move to the next row.
        else:
            i += 1
            
    return -1, -1
```
