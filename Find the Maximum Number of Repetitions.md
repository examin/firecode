## Solution

```
public static int getMaxRepetition(int[] a) {
    int k = a.length;
    if(k==0) return 0;
    
    for(int i=0; i<a.length; i++)
    {
        int index = a[i];
        a[index%k] += k;
    }
    
    int max_pos = 0;
    for(int i=1; i<a.length; i++)
    {
        if(a[i]>a[max_pos])
          max_pos = i;
    }
    
    return max_pos;  
}
```

## Notes
Numbers stored in the array are constrained by the length of the array.

1. Iterate through the input array a. For every element a[i], increment a[a[i]%k] by k, where the array contains numbers in range of k-1.

2. Find the max value in the modified array. Index of the maximum element is the biggest repeating elemen