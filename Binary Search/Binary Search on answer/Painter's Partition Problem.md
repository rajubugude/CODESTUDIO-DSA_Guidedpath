### [Problem Link Here](https://www.codingninjas.com/codestudio/guided-paths/data-structures-algorithms/content/118621/offering/1377955)

![WhatsApp Image 2022-03-12 at 11 42 48 PM](https://user-images.githubusercontent.com/88735632/158029795-ad1e5c8c-b184-495f-a276-6b2299993dc2.jpeg)


### Same as BOOK ALLOCATION PROBLEM

```
def isPossible(arr,mid,k, n):
    count = 1
    board = 0
    for i in range(n):
        if board + arr[i] > mid:
            count += 1
            if count > k or arr[i] > mid:
                return False 
            else:
                board = 0
                board += arr[i]
        else:
            board += arr[i]
    return True

def findLargestMinDistance(arr:list, m:int):
    n = len(arr)
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
