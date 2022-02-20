### [Problem Link Here](https://www.codingninjas.com/codestudio/guided-paths/data-structures-algorithms/content/118509/offering/1376580?leftPanelTab=0)

#### T.C = O(N), S.C = O(K)
```
from collections import deque
def maximumInAllSubarraysOfSizeK(nums, n, k):
    q = deque(); res = []
    j = 0; i = 0
    while j < n:
        while q and nums[j] > q[-1]:
            q.pop()
        q.append(nums[j])
        if j-i+1 < k:
            j += 1
        elif j-i+1 == k:
            res.append(q[0])
            if q[0] == nums[i]:
                q.popleft()
            i += 1
            j += 1
    return res
 ```   
