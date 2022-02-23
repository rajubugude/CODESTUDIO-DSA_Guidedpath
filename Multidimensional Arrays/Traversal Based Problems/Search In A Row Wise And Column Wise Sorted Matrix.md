### [Problem Link Here](https://www.codingninjas.com/codestudio/guided-paths/data-structures-algorithms/content/118821/offering/1381898?leftPanelTab=0)

####  Using Binary Search , T.C = O(NLOGN)
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

#### Optimal O(N)
```
1. Start your search from the top-right corner of the matrix.
2. There can be three cases:
  a)The current element is equal to target: return this position
  b) The current element is greater than the target: This means that any element on the current column is also greater, thus we move to the previous column
  c) The current element is smaller than the target: This means that any element on the current row is also smaller, thus we move to the next row
3.If we go out of the matrix, it means element is not found. So, return {-1, -1}.


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
