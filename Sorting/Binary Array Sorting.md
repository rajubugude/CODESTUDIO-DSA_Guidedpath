### [Problem Link Here](https://www.codingninjas.com/codestudio/guided-paths/data-structures-algorithms/content/118822/offering/1382143?leftPanelTab=0)

```
def sortBinaryArray(arr, n):
    # Write your code here
    j = 0
    for i in range(n):
        if arr[i] == 0:
            arr[i], arr[j] = arr[j], arr[i]
            j += 1
    return arr
```
