## Solution

```
In doubly linked list, implement a method to insert a node at specified position and return the list's head. Do nothing if insertion position is outside the bounds of the list.

public DoublyLinkedNode insertAtPos(DoublyLinkedNode head, int data, int pos) {
    int i=1;
    DoublyLinkedNode node = new DoublyLinkedNode(data);
    
    if(head==null&&pos==1) return node;
    
    DoublyLinkedNode curr = head;
    DoublyLinkedNode pre = null;
    while(curr!=null)
    {
        if(pos==i)
        {
            node.next = curr;
            node.prev = curr.prev;
            if(curr.prev!=null) curr.prev.next = node;
            curr.prev = node;
            if(pos==1) head = node;
            break;
        }
        i++;
        pre = curr;
        curr = curr.next;
    }
    
    if(pos==i&&i!=1) 
    {
        pre.next = node;
        node.prev = pre;
    }
    

    return head;
}
3 senarios: beginning, middle, end
```

## Notes
3 senarios: beginning, middle, end
