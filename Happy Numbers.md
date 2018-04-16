## Solution

```
Write a method to determine whether a postive number is Happy.
A number is Happy (Yes, it is a thing!) if it follows a sequence that ends in 1 after following the steps given below : 
Beginning with the number itself, replace it by the sum of the squares of its digits until either the number becomes 1 or loops endlessly in a cycle that does not include 1.


public static boolean isHappyNumber(int n) {
    Set<Integer> s = new HashSet<>();
    while(!s.contains(n))
    {
        s.add(n);
        n = helper(n);
        if(n==1) return true;
    }
    
    return false;
}

public static int helper(int n)
{
    int x = 0;
    while(n!=0)
    {
        x = x + (int)Math.pow(n%10,2);
        n = n/10;
    }
    return x;
}
```

## Notes
you'll need a buffer of some sort to keep a history of visited numbers. A HashSet is a good choice!
