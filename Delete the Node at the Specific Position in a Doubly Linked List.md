## Solution

```
Given a doubly-linked list, write a method to delete the node at a given position (starting from 1 as the head position) and return the modified list's head. Do nothing if the input position is out of range.

public DoublyLinkedNode deleteAtPos(DoublyLinkedNode head, int pos) {
    if(head==null) return null;
    
    if(pos==1&&head.next!=null) return head.next;
    if(pos==1&&head.next==null) return null;

    DoublyLinkedNode cur = head;
    int i = 1;
    while(cur.next!=null)
    {
       if(pos==i)
       {
           cur.prev.next = cur.next;
           cur.next.prev = cur.prev;
       }
       cur = cur.next;
       i++;
    }
    
    if(pos==i) 
      cur.prev.next=null;
    
    return head;
}
```

## Notes

