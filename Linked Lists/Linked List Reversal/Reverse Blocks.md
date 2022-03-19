### [Problem Link Here](https://www.codingninjas.com/codestudio/guided-paths/data-structures-algorithms/content/118786/offering/1381239)

#### Approach 1 : Using Recursion
```
class Node:
    def __init__(self, data):
       	self.data = data
        self.next = None

def reverseKElements(head, n, b, idx):
    if (head == None or idx >= n):
        return head
    K = b[idx]
    # Just move to the next block if size of the current block is zero.
    if (K == 0):
        return reverseKElements(head, n, b, idx + 1)
    cur = head
    prev = None
    cnt = 0
    # Reverse nodes until end of list is reached or current block has been reversed.
    while (cur != None and cnt < K):
        temp = cur.next
        cnt += 1
        cur.next = prev
        prev = cur
        cur = temp
    head.next = reverseKElements(temp, n, b, idx + 1)
    return prev


def getListAfterReverseOperation(head, n, b):
    if (head == None):
        return head
    # Calling reverseKElements function to modify the given linked list.
    head = reverseKElements(head, n, b, 0)
    return head
```
