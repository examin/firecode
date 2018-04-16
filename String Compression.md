## Solution

```
public static String compressString(String text) {
    if (text==null || text.length()==0) return null;
    
    StringBuilder sb = new StringBuilder();
    Character pre = text.charAt(0);
    int count = 0;
    for(int i=0; i<text.length(); i++)
    {
        Character curr = text.charAt(i);
        if(curr.equals(pre))
           count++;
        else
        {
           sb.append(pre);
           if(count>1) sb.append(String.valueOf(count));
           pre = curr;
           count = 1;
        }
    }
    
    sb.append(pre);
    if(count>1) sb.append(String.valueOf(count));

    return sb.toString();
}
```

## Notes

