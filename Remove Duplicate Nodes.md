## Solution

```
Given a singly-linked list, remove duplicates in the list and return head of the list. Target a worst case space complexity of O(n). 

public ListNode removeDuplicates(ListNode head) {
    if(head==null) return null;
    
    Map<Integer, Integer> map = new HashMap<Integer, Integer>();
    List<Integer> list = new ArrayList<Integer>();
    
    ListNode curr = head;
    int i = 0;
    while(curr!=null)
    {
        int data = curr.data;
        if(map.get(data)==null)
           map.put(data, 1);
        else
           list.add(i);
        curr = curr.next;
        i++;
    }
    
    curr = head;
    ListNode pre = null;
    i = 0;
    int j = 0;
    while(curr!=null&& j<list.size())
    {
        if(i==list.get(j))
        {
            pre.next = curr.next;
            j++;
        }
        pre = curr;
        curr = curr.next;
        i++;
    }

    return head;
}

```

## Notes
An easier way is to maintain a hashtable/map to check whether a node appears before, and remove it in the same iteration