## Solution

```
public Boolean isCyclic(ListNode head) {
    if(head==null) return false;
    Map<ListNode, Integer> map = new HashMap<>();
    
    ListNode cur = head;
    while(cur!=null)
    {
        if(map.get(cur.next)!=null) return true;
        map.put(cur, 1);
        cur = cur.next;
    }
    
    return false;
}
```

## Notes
1. Use hashmap/or hashset here change the time complexity to O(n)
2. When a class does not override the equals() or hashCode() methods, the default implementations found on the Object class are used instead. In particular, equals() simply does a check for reference equality.
https://stackoverflow.com/questions/9440380/using-an-instance-of-an-object-as-a-key-in-hashmap-and-then-access-it-with-exac