## Solution

```
public ListNode deleteAtMiddle(ListNode head, int position) {
    if ((head==null) || (head.next==null)) return null;
    
    if(position==1) return head.next;
    
    int i=1;
    ListNode pre =null;
    ListNode curr = head;
    while (curr!=null)
    {
        ListNode next = curr.next;
        if((pre!=null) && (i==position))
        {
           pre.next = next;
           return head;
        }
        pre = curr;
        curr = curr.next;

        i++;
    }
    
    //if(i==position) pre.next = null;
    
    return head;
}
```

## Notes
