### [Problem Link Here](https://www.codingninjas.com/codestudio/guided-paths/data-structures-algorithms/content/118821/offering/1381902?leftPanelTab=0)

```
def findKthElement(matrix, k):
    n = len(matrix[0]) #cols
    m = len(matrix) #rows
    r = 0
    c = 0
    count = 0
    while (r < m and c < n):
        for i in range(c,n):
            count += 1
            if count == k:
                return matrix[r][i]
        r += 1

        """ check the last column
        from the remaining columns """
        for i in range(r,m):
            count += 1
            if count == k:
                return matrix[i][n - 1]
        n -= 1

        """ check the last row from
        the remaining rows """
        if r < m:
            for i in range(n - 1,c-1,-1):
                count += 1
                if count == k:
                    return matrix[m - 1][i]
            m -= 1

        """ check the first column from
        the remaining columns """
        if c < n:
            for i in range(m - 1,r-1,-1):
                count += 1
                if count == k:
                    return matrix[i][c]
            c += 1
```
