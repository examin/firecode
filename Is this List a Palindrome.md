## Solution

```
public Boolean isListPalindrome(ListNode head) {
    if (head==null) return true;
    if (head.next==null) return true;
    if (head.next.next==null)
    {
        if(head.data==head.next.data)
           return true;
        else
           return false;
    }
    
    ListNode slow = head;
    ListNode fast = head;
    
    while(fast!=null&&fast.next!=null&&fast.next.next!=null)
    {
        slow = slow.next;
        fast = fast.next.next;
    }
    
    ListNode curr = slow;
    ListNode pre = null;
    ListNode next = null;
    
    while(curr!=null)
    {
        next = curr.next;
        curr.next = pre;
        pre = curr;
        curr = next;
    }
    
    while(pre!=null&&head!=null)
    {
        if(pre.data!=head.data)
           return false;
        pre = pre.next;
        head = head.next;
    }
    
    return true;

}
```

## Notes
1. Fast-slow mode
2. reverse the second/first half
3. compare corresponing data
