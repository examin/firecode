## Solution

```
public Boolean isListEven(ListNode head) {
    if(head==null) return true;
    //if(head.next==null) return false;
    //if(head.next.next==null) return true;
    
    //ListNode fast = head.next.next;
    ListNode fast = head;
    
    while(fast!=null&&fast.next!=null&&fast.next.next!=null)
    {
        fast = fast.next.next;
    }
    
    if(fast.next!=null) 
       return true;
    else
       return false;
}
```

## Notes
