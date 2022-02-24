### [Problem Link Here](https://www.codingninjas.com/codestudio/guided-paths/data-structures-algorithms/content/118821/offering/1381900)

```
def countFlip(mat):
    n = len(mat)
    # Initialise both visited row and col as 0.
    visitedRow = [False for i in range(n)]
    visitedCol = [False for i in range(n)]
    count = 0
    s = []
    for i in range(n):
        for j in range(n):
            if (mat[i][j] == 0):
                s.append([i, j])

    for element in s:
        # Fixing column.
        if (visitedCol[element[1]] == False):
            for k in range(n):

                if (mat[k][element[1]] == 1):
                    count += 1
                    mat[k][element[1]] = -1

                if (k == n - 1):
                    visitedCol[element[1]] = True

        # Fixing row.
        if (visitedRow[element[0]] == 0):
            for k in range(n):
                if (mat[element[0]][k] == 1):
                    count += 1
                    mat[element[0]][k] = -1

                if (k == n - 1):
                    visitedRow[element[0]] = True

    return count
```
