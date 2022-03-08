### [Problem Link Here](https://www.codingninjas.com/codestudio/guided-paths/data-structures-algorithms/content/118621/offering/1377950)

```
def countOccurences(arr, n, x) :
    first = firstOccurence(arr,n,x)
    last = lastOccurence(arr,n,x)
    if first == -1 or last == -1:
        return 0
    return abs(first - last) + 1


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


def lastOccurence(nums,n, target):
    l = -1
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
                if  mid == len(nums)-1 or nums[mid] != nums[mid + 1]:
                    return mid
                else:
                    first = mid +1
    return l
```
