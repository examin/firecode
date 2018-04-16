## Solution

```
public static int betterFibonacci(int n) {
    if(n<2) return n;
    
    int i = 2;
    int fn = 0;
    int fn_1 = 0;
    int fn_2 = 0;
    while(i<=n)
    {
        if(i==2)
        {
           fn = 1; 
           fn_1 = fn;
           fn_2 = 1;
        }
        else
        {
           fn = fn_1 + fn_2;
           fn_2 = fn_1;
           fn_1 = fn;
        }
          
        i++;
    }
    
    return fn;
    
}

```

## Notes
