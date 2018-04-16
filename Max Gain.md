## Solution

```
public static int maxGain(int[] a) {
    int max = 0;
    if(a==null||a.length==1) return max;
    
    int min = a[0];
    int gain = 0;
    for(int i=1; i<a.length; i++)
    {
        gain = a[i] - min;
        //max = gain>max?gain:max;
        max = Math.max(gain, max);
        min = Math.min(a[i], min);
    }
    
    return max;

}
```

## Notes
Keep track of the min and the previous max gain.

Related questions: https://www.geeksforgeeks.org/stock-buy-sell/
