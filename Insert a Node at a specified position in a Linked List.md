## Solution

```
Given a singly-linked list, implement a method to insert a node at a specific position and return the head of the list.

If the given position is greater than the list size, simply insert the node at the end.

public ListNode insertAtPosition(ListNode head, int data, int pos) {
    ListNode node = new ListNode(data);
    
    if (head==null) return node;
    
    int index = 1;
    ListNode pre = null;
    ListNode curr = head;
    
    if(pos==1)
    {
        node.next = head;
        return node;
    }
    
    while(curr!=null)
    {
        if(index == pos)
        {
            pre.next = node;
            node.next = curr;
            break;
        }
        pre = curr;
        curr = curr.next;
        index++;
    }
    
    if(pos>=index) 
       pre.next = node;
    
    return head;
}

```

## Notes
