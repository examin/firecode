## Solution

```
public static Boolean isIntPalindrome(int x) {
    int num = x;
    int reverse = 0;
    
    while(num>0)
    {
        reverse = reverse*10+ num%10;
        num = num/10;
    }
    
    if (reverse == x) 
       return true;
    else
       return false;   
}
```

## Notes
Trick: reverse an integer
    while(num>0)
    {
        reverse = reverse*10+ num%10;
        num = num/10;
    }