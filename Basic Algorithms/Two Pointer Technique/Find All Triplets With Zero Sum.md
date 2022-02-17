### [Problem Link Here](https://www.codingninjas.com/codestudio/guided-paths/data-structures-algorithms/content/118509/offering/1376555?leftPanelTab=0)

#### Brute force

```
def findTriplets(arr, n):
    visited = set()
    ans = list()
    for i in range(n - 2):
        for j in range(i + 1, n - 1):
            for k in range(j + 1, n):
                if arr[i] + arr[j] + arr[k] == 0:
                    triplet = [arr[i], arr[j], arr[k]]
                    triplet.sort()
                    triplet = tuple(triplet)
                    if triplet not in visited:
                        visited.add(triplet)

    for i in visited:
        ans.append(list(i))

    return ans

```


#### Optimal

```
def findTriplets(arr, n):
    ans = list()
    arr = sorted(arr)

    f = 0
    i = 0
    while i < n:
        target = -arr[i]
        front, back = i + 1, n - 1
        while front < back:
            sum = arr[front] + arr[back]
            if sum < target:
                front += 1

            elif sum > target:
                back -= 1

            else:
                f = 1
                x, y = arr[front], arr[back]
                ans.append([arr[i], x, y])
                while front < back and arr[front] == x:
                    front += 1

                while front < back and arr[back] == y:
                    back -= 1

        while i + 1 < n and arr[i] == arr[i + 1]:
            i += 1

        i += 1
    return ans
```
