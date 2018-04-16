## Solution

```
Write a method to replace all spaces in a string with a given replacement string. 
replace("This is a test","/") --> "This/is/a/test"
Note: Avoid using the in-built String.replaceAll() method. 

public static String replace(String a, String b) {
    if(a==null) return null;
    StringBuilder sb = new StringBuilder();
    
    for(int i=0; i<a.length(); i++)
    {
        String c = a.charAt(i) + "";
        if(c.equals(" "))
          sb.append(b);
        else
          sb.append(c);
    }
    
    return sb.toString();
}
```

## Notes
