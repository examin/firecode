## Solution

```
Implement a method that reverses an integer - without using additional heap space 

public static int reverseInt(int x) {
    int rev = 0;
    
    while (x!=0)
    {
      rev = rev*10 + x%10; 
      x = x/10;
    }
    
    return rev;
}
```

## Notes
Huge trick:

    while (x!=0)
    {
      rev = rev*10 + x%10; 
      x = x/10;
    }
