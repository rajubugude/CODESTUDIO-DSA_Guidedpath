### [Problem Link Here](https://www.codingninjas.com/codestudio/guided-paths/data-structures-algorithms/content/118786/offering/1381244?leftPanelTab=0)

```
# Function to count the number of nodes in the list.
def countDigits(head):
    c = 0
    while (head):
        head = head.next
        c += 1

    return c


# Function to reverse the list.
def reverseList(head):
    prev, curr = None, head
    nextNode = None

    while(curr != None):
        nextNode = curr.next
        curr.next = prev
        prev = curr
        curr = nextNode

    return prev


def addTwoLists(first, second):
    # Reverse both lists for simplicity.
    first = reverseList(first)
    second = reverseList(second)

    # Assign list with more digits to first list.
    if (countDigits(first) < countDigits(second)):
        first, second = second, first

    carry = 0
    head = first

    # Iterate and add the nodes till second list does not reach end.
    while (second != None):
        first.data += second.data + carry
        carry = first.data // 10
        first.data %= 10

        # If the list ends but a carry remains.
        if (first.next == None and carry):
            newNode = Node(carry)
            first.next = newNode

            first = first.next
            carry = 0
            break

        first = first.next
        second = second.next

    # If there are more digits left to process in first list.
    while (first != None):
        first.data += carry
        carry = first.data // 10
        first.data %= 10

        # If the list ends but a carry remains.
        if (first.next == None and carry):
            newNode = Node(carry)
            first.next = newNode
            break

        first = first.next

    # Reverse the list to get the final number.
    head = reverseList(head)

    # Return the answer list obtained after adding two lists.
    return head
```
