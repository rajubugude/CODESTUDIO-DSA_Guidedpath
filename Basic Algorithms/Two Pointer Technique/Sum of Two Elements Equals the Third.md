### [Problem Link Here](https://www.codingninjas.com/codestudio/guided-paths/data-structures-algorithms/content/118509/offering/1376557?leftPanelTab=0)
```
def findTriplet(arr,n):
    ans = list()
    arr.sort()
    for i in range(n - 1, -1, -1):
        j, k = 0, i - 1
        while j < k:
            if arr[i] == arr[j] + arr[k]:
                ans.extend([arr[i], arr[j], arr[k]])
                return ans
            elif arr[i] > arr[j] + arr[k]:
                j += 1
            else:
                k -= 1
    return ans
```    
