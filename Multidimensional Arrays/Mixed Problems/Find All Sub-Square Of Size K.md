### [Problem Link Here](https://www.codingninjas.com/codestudio/guided-paths/data-structures-algorithms/content/118821/offering/1381911?leftPanelTab=0)

#### Bruteforce

```
def sumOfKxKMatrices(mat:list, k:int):
    n = len(mat)
    ans = [[0 for i in range(n-k+1)] for j in range(n-k+1)]
    for i in range(n-k+1):
        for j in range(n-k+1):
            sm = 0
            for x in range(k):
                for y in range(k):
                    sm += mat[x + i][y + j]
            ans[i][j] = sm
    return ans
```


#### Optimal (Using PrefixSum)

```
def sumOfKxKMatrices(arr:list, k:int):

    n = len(arr)

    # This list of lists stores our answer.
    ans = [[0 for i in range(n-k+1)] for j in range(n-k+1)]
    
    # This list of lists stores our prefix sum of elements.
    prefix = [[0 for i in range(n+1)] for j in range(n+1)]

    for i in range(1,n+1):
        for j in range(1,n+1):
            # Calculating the prefix sums.
            prefix[i][j] = prefix[i - 1][j] + prefix[i][j - 1] - prefix[i - 1][j - 1] + arr[i - 1][j - 1]
        
    for i in range(1,n-k+2):
        for j in range(1,n-k+2):
            # Using the formula as described in the explanation.
            ans[i - 1][j - 1] = prefix[i + k - 1][j + k - 1] - prefix[i - 1][j + k - 1] - prefix[i + k - 1][j - 1] + prefix[i - 1][j - 1]

    # Return the final answer.
    return ans
    
```
