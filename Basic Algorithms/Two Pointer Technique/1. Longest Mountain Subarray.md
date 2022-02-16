### [Problem Link Here](https://www.codingninjas.com/codestudio/guided-paths/data-structures-algorithms/content/118509/offering/1376554?leftPanelTab=0)

#### [Explanation](https://www.youtube.com/watch?v=VXeukMTbxkw)

```
def longestMountain(arr, n):
    if n < 3:
        return 0
    ans = 0
    i = 1
    while i < n-1:
        if arr[i] > arr[i-1] and arr[i] > arr[i+1]: #if it's a peak
            count = 1 #include peak in length
            j = i
            while j > 0 and arr[j] > arr[j-1]: #count left side of peak
                j -= 1
                count += 1
            while i < n-1 and arr[i] > arr[i+1]: # count rightside of peak
                i += 1
                count += 1
            ans = max(ans,count)
        else:
            i += 1
    return ans
```
