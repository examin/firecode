## Solution

```
public ListNode mergeKLists(ArrayList<ListNode> lists) {
    if(lists==null||lists.size()==0) return null;
    
    PriorityQueue<ListNode> q = new PriorityQueue<>(lists.size(), 
    new Comparator<ListNode>(){
        public int compare(ListNode l1, ListNode l2)
        {
            return l1.data - l2.data;
        }
    });
    
    for(ListNode node: lists)
    {
        q.add(node);
    }
    
    // ListNode head = null;
    // ListNode pre = null;
    // while(!q.isEmpty())
    // {
    //     ListNode n = q.poll();
    //     if(head==null) 
    //     {
    //         head = n;
    //     }
    //     if(pre!=null)
    //     {
    //         pre.next = n;
    //     }
    //     pre = n;
    //     if(n.next!=null) q.add(n.next);
    // }
    
    // return head;
    ListNode head = new ListNode(0);
    ListNode node = head;
    while(!q.isEmpty())
    {
        ListNode n = q.poll();
        node.next = n;
        node = n;
        if(n.next!=null) q.add(n.next);
    }
    
    return head.next;    
}
```

## Notes
1. http://www.lifeincode.net/programming/leetcode-merge-k-sorted-lists-java/
2. https://leetcode.com/problems/merge-k-sorted-lists/solution/
3. https://www.geeksforgeeks.org/merge-k-sorted-linked-lists/
Heap: insert (logN), getMin(1)
https://www.cs.cmu.edu/~adamchik/15-121/lectures/Binary%20Heaps/heaps.html

