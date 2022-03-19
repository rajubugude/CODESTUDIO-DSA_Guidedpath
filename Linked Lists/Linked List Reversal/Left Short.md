### [Problem Link Here](https://www.codingninjas.com/codestudio/guided-paths/data-structures-algorithms/content/118786/offering/1381252)

```
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None

def getListAfterDeleteOperation(head):
    if head is None or head.next is None:
        return None
    curr = head.next #curr for moving and is ahead of left 
    prev = head #prev for connecting
    left = prev #left for moving
    while curr is not None:
        if left.data > curr.data:
            prev.next = curr.next
        else:
            prev = prev.next
        left = curr
        curr = curr.next
    return head
```
