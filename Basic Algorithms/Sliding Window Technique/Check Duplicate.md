### [Problem Link Here](https://www.codingninjas.com/codestudio/guided-paths/data-structures-algorithms/content/118509/offering/1376579?leftPanelTab=0)

```
def checkDuplicate(arr, n, k):
    d = {}
    i = 0
    j = 0
    while j < n:
        if j - i < k:
            if arr[j] not in d:
                d[arr[j]] = 1
            else:
                d[arr[j]] += 1
                return True

            j += 1
        elif j - i == k:
            if arr[j] not in d:
                d[arr[j]] = 1
            else:
                d[arr[j]] += 1
                return True
            del d[arr[i]]
            i += 1
            j += 1

    return False
```
