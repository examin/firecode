## Solution

```
Given the head pointer of a singly linked list, implement a method to reverse the list and return the new head. 

public ListNode reverseList(ListNode head) {
    if(head==null) return null;
    if(head.next==null) return head;
    
    ListNode cur = head;
    ListNode pre = null;
    ListNode next = head.next;
    while(cur!=null)
    {
        next = cur.next;
        cur.next = pre;
        pre = cur;
        cur = next;
    }
    
    return pre;
}
```

## Notes

