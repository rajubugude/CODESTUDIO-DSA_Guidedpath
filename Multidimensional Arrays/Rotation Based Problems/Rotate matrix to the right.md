### [Problem Link Here](https://www.codingninjas.com/codestudio/guided-paths/data-structures-algorithms/content/118821/offering/1381903?leftPanelTab=0)

```
def reverse(arr, start, end):
    while start < end:
        arr[start], arr[end] = arr[end], arr[start]
        start += 1
        end -= 1

def rotate(arr, k):
    reverse(arr, 0, len(arr) - 1)
    reverse(arr, 0, k - 1)
    reverse(arr, k, len(arr) - 1)

    
def rotateMatRight(mat, n, m, k):
    k = k%m
    if k == m:
        return mat
    for i in mat:
        rotate(i,k)
    return mat
```
