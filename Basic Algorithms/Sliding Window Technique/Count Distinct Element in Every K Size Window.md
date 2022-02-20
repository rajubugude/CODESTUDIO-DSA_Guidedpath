### [Problem Link Here](https://www.codingninjas.com/codestudio/guided-paths/data-structures-algorithms/content/118509/offering/1376578?leftPanelTab=1)


#### By acquire and release method in hashmaps using sliding window algorithm 

def countDistinctElements(arr, k):
    n = len(arr)
    d = {}
    l = []
    i = 0
    j = 0
    count = 0
    while j < n:
        if j - i + 1 < k:
            if arr[j] not in d:
                d[arr[j]] = 1
            else:
                d[arr[j]] += 1
            j += 1
            
        if j - i + 1 == k:
            if arr[j] not in d:
                d[arr[j]] = 1
            else:
                d[arr[j]] += 1

            count = len(d)
            l.append(count)
            
            if d[arr[i]] == 1:
                del d[arr[i]]
            else:
                d[arr[i]] -= 1
            i += 1
            j += 1

    return l 
