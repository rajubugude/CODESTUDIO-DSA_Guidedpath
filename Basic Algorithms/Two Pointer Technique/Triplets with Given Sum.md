### [Problem Link Here](https://www.codingninjas.com/codestudio/guided-paths/data-structures-algorithms/content/118509/offering/1376558)

#### Same as triplet sum == 0 problem, here sum = k
```
def findTriplets(arr, n, k):
    ans = list()
    arr = sorted(arr)
    f = 0
    i = 0
    while i < n:
        target = k - arr[i]
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
