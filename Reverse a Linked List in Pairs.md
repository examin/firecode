## Solution

```
public ListNode reverseInPairs(ListNode head) {
    if(head==null) return null;
    if(head.next == null) return head;
    
    ListNode cur = head;
    ListNode new_head = null;

    while(cur!=null&&cur.next!=null)
    {
        ListNode fast = cur.next.next;
        ListNode next = cur.next;
        if(cur==head) new_head = next;
        next.next = cur;
        if(fast!=null&&fast.next!=null) 
           cur.next = fast.next;
        else if(fast!=null)
           cur.next = fast;
        else
           cur.next = null;
        cur = fast;
    }
    
    return new_head;
    
    // while(cur!=null&&cur.next!=null)
    // {
    //   ListNode next = cur.next;
    //   int temp = cur.data;
    //   cur.data = next.data;
    //   next.data = temp;
    //   cur = cur.next.next;
    // }
    
    // return head;
}
```

## Notes
Another solution is to swap values.
// while(cur!=null&&cur.next!=null)
    // {
    //   ListNode next = cur.next;
    //   int temp = cur.data;
    //   cur.data = next.data;
    //   next.data = temp;
    //   cur = cur.next.next;
    // }
    
    // return head;
