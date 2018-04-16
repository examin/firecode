## Solution

```
Given a singly-linked list, implement the method that returns Nth node from the end of the list. You are allowed to use extra memory for this implementation. 

public ListNode findNthNodeFromEnd(ListNode head, int n) {
    if(head==null) return null;
    
    ListNode curr = head;
    int i = 0;
    while(curr!=null)
    {
        curr = curr.next;
        i++;
    }
    
    int pos = i - n;
    
    curr = head;
    i = 0;
    while(curr!=null)
    {
        if(pos == i)
          return curr;
        curr = curr.next;
        i++;
    }
    
    return null;
                
}

```

## Notes
