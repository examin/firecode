## Solution

```
public static int findMissingNumber(int[] arr) {
    int base = 55;
    int total = 0;
    
    for(int i: arr){
        total += i;
    }
    return base - total;
}
```

## Notes

