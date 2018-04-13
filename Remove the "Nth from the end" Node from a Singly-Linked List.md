## Solution

```
public ListNode removeNthFromEnd(ListNode head, int n) {
    if(head==null) return null;
    
    ListNode curr = head;
    ListNode pre = null;
    ListNode next = null;
    while(curr!=null)
    {
        next = curr.next;
        curr.next = pre;
        pre = curr;
        curr = next;
    }
    
    if(n==1)
    {
      pre = pre.next;
      
    }else{
        int index = 1;
        ListNode curr2 = pre;
        ListNode pre2 = null;
        
        while(curr2!=null)
        {
            if(n==index)
            {
              pre2.next = curr2.next;
              break;
            }
            index++;
            pre2 = curr2;
            curr2 = curr2.next;
        }
    }
    
    ListNode curr3 = pre;
    ListNode pre3 = null;
    ListNode next3 = null;
    while(curr3!=null)
    {
        next3 = curr3.next;
        curr3.next = pre3;
        pre3 = curr3;
        curr3 = next3;
    }
    
    return pre3;
}
```

## Notes
1. Use "reverse linked list" smartly
2. another way is to get the length of the list, and find the position fro the beginning by doing length-n