### [Problem Link Here](https://www.codingninjas.com/codestudio/guided-paths/data-structures-algorithms/content/118786/offering/1381242)


```
def lastAppearance(head):
    d = {}
    curr = head
    while curr is not None:
        if curr.data in d:
            d[curr.data] += 1
        else:
            d[curr.data] = 1
        curr = curr.next

    dummy = curr = Node(-1)  #curr = tail, dummy = head
    temp = head
    while temp:
        if d[temp.data] == 1:
            curr.next = Node(temp.data)
            curr = curr.next
        else:
            d[temp.data] -= 1
        temp = temp.next
    return dummy.next
```
