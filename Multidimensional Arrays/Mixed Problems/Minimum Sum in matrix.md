### [Problem Link Here](https://www.codingninjas.com/codestudio/guided-paths/data-structures-algorithms/content/118821/offering/1381909)

#### Recursion

```
def solve(i, j, n, arr):
    if (i == n - 1):
        return arr[i][j]

    current = 1000000007
    for k in range(3):
        if (k != j):
            current = min(current, arr[i][j] + solve(i + 1, k, n, arr))
    return current


def minSum(arr):
    n = len(arr)
    ans = 1000000007
    for col in range(3):
        ans = min(ans, solve(0, col, n, arr))
    return ans
```

#### Memoization

```
import sys
sys.setrecursionlimit(10**6)
def solve(i, j, n, arr,dp):
    if (i == n - 1):
        return arr[i][j]

    if dp[i][j] != -1:
        return dp[i][j]

    current = 1000000007
    for k in range(3):
        if (k != j):
            current = min(current, arr[i][j] + solve(i + 1, k, n, arr,dp))
    dp[i][j] = current
    return dp[i][j]


def minSum(arr):
    n = len(arr)
    ans = 1000000007
    dp = [[-1 for _ in range(3)] for _ in range(n)]
    for col in range(3):
        ans = min(ans, solve(0, col, n, arr,dp))
    return ans
```

#### Optimal, T.C = O(N)

```
def minSum(arr):
    n = len(arr)
    # Create an list temp to store all the combinations
    temp = [0]*6
    # Traverse through all the N-1 rows
    for i in range(n-1):
        # Find all the possible 6 combinations
        temp[0] = arr[i][1] + arr[i + 1][0]
        temp[1] = arr[i][2] + arr[i + 1][0]
        temp[2] = arr[i][0] + arr[i + 1][1]
        temp[3] = arr[i][2] + arr[i + 1][1]
        temp[4] = arr[i][0] + arr[i + 1][2]
        temp[5] = arr[i][1] + arr[i + 1][2]
        # Update the (i+1)th row with the combinations calculated above
        arr[i + 1][0] = min(temp[0], temp[1])
        arr[i + 1][1] = min(temp[2], temp[3])
        arr[i + 1][2] = min(temp[4], temp[5])
    # Find the answer as the minimum all the 3 values
    ans = min(arr[n - 1][0],arr[n - 1][1], arr[n - 1][2])
    return ans
```
