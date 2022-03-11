### [Problem Link Here](https://www.codingninjas.com/codestudio/guided-paths/data-structures-algorithms/content/118621/offering/1377951)

![WhatsApp Image 2022-03-11 at 9 42 52 PM](https://user-images.githubusercontent.com/88735632/157906623-c0db48fb-6456-4c6f-8adb-066be93242ae.jpeg)

#### Binary search approach T.C = O(NlogN)

```
def isPossible(arr,pages,m, n):
    count = 0
    sumallocated = 0
    for i in range(n):
        if sumallocated + arr[i] > pages:
            count += 1
            sumallocated = arr[i]
            if sumallocated > pages:
                return False        
        else:
            sumallocated += arr[i]
    if count < m:
        return True
    return False    

def allocateBooks(arr, n, m):
    if m > n :
        return -1   
    l = min(arr) ; h = sum(arr)
    ans = -1
    while l <= h:
        mid =(l+h)//2
        if isPossible(arr,mid,m,n):
            ans = mid
            h = mid-1
        else:
            l = mid+1
    return ans
```
