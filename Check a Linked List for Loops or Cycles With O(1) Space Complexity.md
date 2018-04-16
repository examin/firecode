## Solution

```
Check if a given linked list has cycles. Try to achieve O(n) runtime with a space complexity of O(1). If there is a cycle, return true otherwise return false. Consider empty lists as non cyclic. 

public Boolean isCyclic(ListNode head) {
    if(head==null) return false;
    
    Map<ListNode, Integer> map = new HashMap<ListNode, Integer>();
    map.put(head, 1);
    
    while(head!=null)
    {
       head = head.next;
       if(map.get(head)!=null) 
          return true;
       else
          map.put(head, 1);
    }
    
    return false;
    
}
```

## Notes

