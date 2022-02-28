### [Problem Link Here](https://www.codingninjas.com/codestudio/guided-paths/data-structures-algorithms/content/118821/offering/1381906)

```
def emptyCells(n, k, tasks):
    rowMap = set()
    colMap = set()
    rows, columns = n, n
    output = []
    for x,y in tasks:
        if x not in rowMap:
            rowMap.add(x)
            rows -= 1
        if y not in colMap:
            colMap.add(y)
            columns -= 1
        output.append(rows*columns)
    return output
    
```
