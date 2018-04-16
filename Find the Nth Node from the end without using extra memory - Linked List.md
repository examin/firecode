## Solution

```
public ListNode findNthNodeFromEnd(ListNode head, int n) {
    if(head==null) return null;
    
    ListNode curr = head;
    int i=0;
    
    while(curr!=null)
    {
        curr = curr.next;
        i++;
    }
    
    int j = i - n;
    if(j<0) return null;
    curr = head;
    i = 0;
    while(curr!=null)
    {
        if(i==j)
          return curr;
        curr = curr.next;
        i++;
    }
    
    return null;
    
}

```

## Notes
