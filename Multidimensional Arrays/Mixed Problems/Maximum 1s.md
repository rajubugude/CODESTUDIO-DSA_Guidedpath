### [Problem Link Here](https://www.codingninjas.com/codestudio/guided-paths/data-structures-algorithms/content/118821/offering/1381908?leftPanelTab=0)

T.C = O(nlogn)

```
def firstOccurence(nums,n, target):
    f = -1
    first = 0
    last = n - 1
    while first <= last:
        mid = (first + last)//2
        if target < nums[mid]:
            last = mid - 1
        elif target > nums[mid]:
            first = mid + 1
        else:
            if target == nums[mid]:
               if nums[mid] != nums[mid - 1] or mid == 0:
                   return mid
               else:
                    last = mid-1
    return f

def maxOne(mat):
    n = len(mat)
    m = len(mat[0])
    count = 0
    idx = -1
    ans = 0
    for i in range(n):
        idx += 1
        first = firstOccurence(mat[i],m,1)
        if first != -1:
            if count < m - first:
                count = m - first
                ans = idx
    return ans
```
