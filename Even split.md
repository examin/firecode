## Solution

```
public static boolean splitArray(int[] arr) {
    if(arr==null||arr.length==0) return false;
    int sum = 0;
    for(int a:arr)
    {
        sum +=a;
    }
    
    if(sum%2!=0) return false;
    
    int target = sum/2;
    
    return helper(arr, target, arr.length-1);
}

public static boolean helper(int[] arr, int target, int i)
{
    if(target==0) return true;
    if(i<0) return false;
    
    if(helper(arr, target-arr[i], i-1)||helper(arr, target, i-1))
      return true;
    
    return false;
}
```

## Notes
