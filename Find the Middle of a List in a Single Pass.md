## Solution

```
public ListNode findMiddleNode(ListNode head) {
    if (head==null) return null;
    //if ((head.next == null) || (head.next.next ==null)) return head;

    ListNode slow = head;
    ListNode fast = head;
    while ((fast!=null) && (fast.next!=null) && (fast.next.next!=null))
    {
        slow = slow.next;
        fast = fast.next.next;
    }
    
    return slow;
}
```

## Notes
1. Traverse the list by moving over one reference with twice the speed as that of the of the other reference : 
slow = slow.next
fast = (fast.next).next

2. Stop the traversal when the faster ListNode reference reaches the end of the linked list.

In the end, the fast will either be at the last node or the second last. Slow will be at the middle.

3. The slower node will invariably be pointing to the middle ListNode. Return slow