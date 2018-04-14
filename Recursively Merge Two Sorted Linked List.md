## Solution

```
public ListNode mergeTwoSortedList(ListNode l1, ListNode l2) {
    if(l1==null&&l2==null) return null;
    ListNode head = new ListNode(-1);
    ListNode pre = head;
    
    while(l1!=null&&l2!=null)
    {
        if(l1.data<l2.data)
        {
           pre.next = l1;
           pre = l1;
           l1 = l1.next;
        }else{
           pre.next = l2;
           pre = l2;
           l2 = l2.next;
        }
    }
    
    while(l1!=null)
    {
        pre.next = l1;
        pre = l1;
        l1 = l1.next;
    }
    
    while(l2!=null)
    {
        pre.next = l2;
        pre = l2;
        l2 = l2.next;
    }
    
    return head.next;
}
```

## Notes
public ListNode mergeTwoSortedList(ListNode l1, ListNode l2) {    
      ListNode newHead;
      if(l1==null) return l2;
      if(l2==null) return l1;
      if(l1.data <= l2.data) {
          newHead = l1;
          newHead.next = mergeTwoSortedList(l1.next, l2);
      } else {
          newHead = l2;
          newHead.next = mergeTwoSortedList(l2.next, l1);
      }
      return newHead;
  }


