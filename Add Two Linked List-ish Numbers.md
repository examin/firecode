## Solution

```
public static ListNode sumTwoLinkedLists(ListNode input1, ListNode input2) {
    ListNode head = new ListNode(1);
    ListNode pre = head;
    int digit = 0;
    while(input1!=null&&input2!=null)
    {
        int num = (input1.data+input2.data+digit)%10;
        ListNode node = new ListNode(num);
        pre.next = node;
        pre = node;
        if((input1.data+input2.data)>=10) 
          digit = 1;
        else
          digit = 0;
        input1=input1.next;
        input2 = input2.next;
    }
    
    while(input1!=null)
    {
        int num = (input1.data+digit)%10;
        ListNode node = new ListNode(num);
        pre.next = node;
        pre = node;
        if((input1.data+digit)>=10) 
          digit = 1;
        else
          digit = 0;
        input1 = input1.next;

    }
    
    while(input2!=null)
    {
        int num = (input2.data+digit)%10;
        ListNode node = new ListNode(num);
        pre.next = node;
        pre = node;
        if((input2.data+digit)>=10) 
          digit = 1;
        else
          digit = 0;
        input2 = input2.next;

    }
    
    if(digit==1) pre.next = new ListNode(1);
    
    return head.next;
}
```

## Notes